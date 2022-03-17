<template>
  <div class="container container-fluid content-row mt-4">
    <div class="row justify-content-center">
    
      <b-card class="mb-3 mr-3 col-sm-9 col-8 col-lg-3 pr-0 pl-0" v-for="(project, idx) in projects" :key="idx" 
      :title="project.name" alt="">

          <!-- Carousel -->
          <div>
            <b-carousel
              :id="'carousel' + project.name"
              v-model="slide"
              :interval="3500"
              controls
              indicators
              img-width="1024"
              img-height="480"
              style="text-shadow: 1px 1px 2px #333;"
              @sliding-start="onSlideStart"
              @sliding-end="onSlideEnd">
              <!-- Text slides with image -->
              <b-carousel-slide :img-src="project.img"></b-carousel-slide>
              <b-carousel-slide v-for="(imgG, idx) in project.carsPic" :key="idx"
                :caption="imgG.caption"
                :text="imgG.text"
                :img-src="imgG.img">
              </b-carousel-slide>
            </b-carousel>
          </div>  

          <b-card-text>{{project.description}}</b-card-text>
          <b-card-text><small>{{project.date}}</small></b-card-text>
          <template v-slot:footer>
            <div class="row float-right">
              <span class="mr-1" v-for="icon in project.icons" :key="icon">
                <font-awesome-icon :icon="icon" size="2x" />
              </span>
            </div>
          </template>

          <div>
            <b-button id="show-btn" @click="$bvModal.show('pModal' + idx)">More</b-button>
            <b-modal :id="'pModal' + idx" :title="project.name" hide-footer centered scrollable size="lg">
              <b-tabs content-class="mt-3">

                <!-- First Tab: Description -->
                <b-tab title="About" active>

                  <!-- Carousel -->
                  <div>
                    <b-carousel
                      :id="'carousel' + project.name"
                      v-model="slide"
                      :interval="2500"
                      controls
                      indicators
                      img-width="1024"
                      img-height="480"
                      style="text-shadow: 1px 1px 2px #333;"
                      @sliding-start="onSlideStart"
                      @sliding-end="onSlideEnd">
                      <!-- Text slides with image -->
                      <b-carousel-slide :img-src="project.img"></b-carousel-slide>
                      <b-carousel-slide v-for="(imgG, idx) in project.carsPic" :key="idx"
                        :caption="imgG.caption"
                        :text="imgG.text"
                        :img-src="imgG.img">
                      </b-carousel-slide>
                    </b-carousel>
                  </div>  

                  <p><strong>Description</strong></p>
                  <ul>
                    <li v-for="point in project.details" :key="point">{{point}}</li>
                  </ul>
                  <p v-if="project.algorithms"> <strong>Algorithms:</strong> {{project.algorithms}} </p>
                  <p> <strong>Languages:</strong> {{project.languages}} </p>
                  <p v-if="project.tip"> <font-awesome-icon icon="star" /> {{project.tip}} </p>
                  <div>
                    <a v-if="project.code" :href="project.code" target="_blank"><b>Source Code Link</b></a>
                    <p v-else>*** {{ project.codeMes }} ***</p>
                  </div>
                </b-tab>

                <!-- Second Tab: Video -->
                <b-tab v-if="project.video" title="Video">
                  <div>
                    <b-embed type="iframe" aspect="16by9"
                    :src="project.video" allowfullscreen />
                  </div>
                </b-tab>

              </b-tabs>

              <b-button class="mt-3" block @click="$bvModal.hide('pModal' + idx)">Close</b-button>
            </b-modal>
          </div>
          
      </b-card>
      
    </div>
  </div>
</template>

<script>
import { faPython, faHtml5, faVuejs, faJs,faJava} from '@fortawesome/free-brands-svg-icons'
export default {
  name: 'AllProjects',
  props: {
    msg: String
  },
  data: function() {
    return {
      projects: [
        { name: 'Jeopardy', img: 'img/projects/jeopardy.jpg',
        description: "User Interactive Jeopardy Game",
        icons: [faPython],
        date: 'March 2018',
        details: ['Players click on each individual squares and answer questions', 'And tries to win as much money as possible'],
        carsPic: [{img: 'img/projects/jeopardytkinter.png', caption: 'Jeopardy Game', text: 'Jeopardy game image'}],
        languages: 'Python: tkinter'},

        
        { name: 'Web Book-Keeping System', img: 'img/projects/Book.jpeg',
        description: 'A Book keeping database web system that allows users to choose and purchase books.',
        icons: [faJava, faHtml5,faJs],
        date: 'April 2020',
        details: ['Users can purchase a Book', 'See if a Book is in inventory', 'Assess Purchase history',
        'Login to their own account', 'Navigate through different genres of books on the webpage'],
        languages: 'Java, Javascript, HTML, PostgreSQL', code: 'https://github.com/hazelbestt/book-reservation-code',
        carsPic: [{img: 'img/projects/Database.png'}]},
        
        { name: 'Personal Profolio Webpage', img: 'img/projects/slideshow/personal-profolio0.png',
        date: 'December 2022',
        icons: [faHtml5, faJs, faVuejs],
        description: 'Personal profolio Webpage talking about Achievements and project history',
        details: ['Included with buttons to navigate through profolio', 'All information about past projects and myself as a programmer',
        'Good display of images'],
        languages: 'HTML, Javascript, Vue.js',
        code: 'https://github.com/kayoMichael/kayoMichael.github.io',
        carsPic: [{img: 'img/projects/slideshow/personal-profolio0.png', caption: 'Top'},
                  {img: 'img/projects/slideshow/personal-profolio.png', caption: 'About me'},
                  {img: 'img/projects/slideshow/personal-profolio2.png', caption: 'Skills'},
                  {img: 'img/projects/slideshow/personal-profolio3.png', caption: 'Experiences'},
                  {img: 'img/projects/slideshow/personal-profolio4.png', caption: 'Projects'},
                  {img: 'img/projects/slideshow/personal-profolio5.png', caption: 'Contact'},

        ]},
        
        // { name: 'Project6', img: '/img1', 
        // description: 'Some quick example text to build on the card title and make up the bulk of the cards content.',
        // details: [], 
        // languages: '', code: ''}
      ]
    }
  }
}
</script>