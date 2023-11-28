<template>
  <div class="container container-fluid content-row mt-4">
    <div class="row justify-content-center">
      <b-card
        class="mb-3 mr-3 col-sm-9 col-8 col-lg-3 pr-0 pl-0"
        v-for="(project, idx) in projects"
        :key="idx"
        :title="project.name"
        alt=""
      >
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
            style="text-shadow: 1px 1px 2px #333"
            @sliding-start="onSlideStart"
            @sliding-end="onSlideEnd"
          >
            <!-- Text slides with image -->
            <b-carousel-slide :img-src="project.img"></b-carousel-slide>
            <b-carousel-slide
              v-for="(imgG, idx) in project.carsPic"
              :key="idx"
              :caption="imgG.caption"
              :text="imgG.text"
              :img-src="imgG.img"
              :img-height="imgG.height"
            >
            </b-carousel-slide>
          </b-carousel>
        </div>

        <b-card-text>{{ project.description }}</b-card-text>
        <b-card-text
          ><small>{{ project.date }}</small></b-card-text
        >
        <template v-slot:footer>
          <div class="row float-right">
            <span class="mr-1" v-for="icon in project.icons" :key="icon">
              <font-awesome-icon :icon="icon" size="2x" />
            </span>
          </div>
        </template>

        <div>
          <b-button id="show-btn" @click="$bvModal.show('pModal' + idx)"
            >More</b-button
          >
          <b-modal
            :id="'pModal' + idx"
            :title="project.name"
            hide-footer
            centered
            scrollable
            size="lg"
          >
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
                    style="text-shadow: 1px 1px 2px #333"
                    @sliding-start="onSlideStart"
                    @sliding-end="onSlideEnd"
                  >
                    <!-- Text slides with image -->
                    <b-carousel-slide :img-src="project.img"></b-carousel-slide>
                    <b-carousel-slide
                      v-for="(imgG, idx) in project.carsPic"
                      :key="idx"
                      :caption="imgG.caption"
                      :text="imgG.text"
                      :img-src="imgG.img"
                    >
                    </b-carousel-slide>
                  </b-carousel>
                </div>

                <p><strong>Description</strong></p>
                <ul>
                  <li v-for="point in project.details" :key="point">
                    {{ point }}
                  </li>
                </ul>
                <p v-if="project.algorithms">
                  <strong>Algorithms:</strong> {{ project.algorithms }}
                </p>
                <p><strong>Languages:</strong> {{ project.languages }}</p>
                <p v-if="project.tip">
                  <font-awesome-icon icon="star" /> {{ project.tip }}
                </p>
                <div>
                  <a v-if="project.code" :href="project.code" target="_blank"
                    ><b>Source Code Link</b></a
                  >
                  <p v-else>*** {{ project.codeMes }} ***</p>
                </div>
              </b-tab>

              <!-- Second Tab: Video -->
              <b-tab v-if="project.video" title="Video">
                <div>
                  <b-embed
                    type="iframe"
                    aspect="16by9"
                    :src="project.video"
                    allowfullscreen
                  />
                </div>
              </b-tab>
            </b-tabs>

            <b-button class="mt-3" block @click="$bvModal.hide('pModal' + idx)"
              >Close</b-button
            >
          </b-modal>
        </div>
      </b-card>
    </div>
  </div>
</template>

<script>
import {
  faHtml5,
  faVuejs,
  faJs,
  faCss3Alt,
  faReact,
} from "@fortawesome/free-brands-svg-icons";
export default {
  name: "AllProjects",
  props: {
    msg: String,
  },
  data: function () {
    return {
      projects: [
        {
          name: "Addidas Coming Soon Page",
          img: "img/projects/Desktop_2.png",
          description:
            "Langing Page for Addidas. Coded Using HTML and Responsive CSS",
          icons: [faHtml5, faCss3Alt],
          date: "January 2022",
          details: [
            "A Potential Concept Design Page for Addidas",
            "It is 100% Responsive and shows different structures for different screen size",
            "Utilized Important CSS Methods such as Media Queries and Flex-box.",
          ],
          carsPic: [
            { img: "img/projects/Desktop_2.png", caption: "Version 1" },
            { img: "img/projects/Desktop_1.png", caption: "Version 2" },
          ],
          languages: "HTML5 CSS",
          code: "https://github.com/kayoMichael/Coming-Soon-Page",
        },

        {
          name: "Uber Eats Design Page",
          img: "img/projects/Desktop.png",
          description: "Responsive UberEats Web Page",
          icons: [faHtml5, faCss3Alt],
          date: "July 2023",
          details: [
            "Uber Eats Response Page with Custom Pages on Mobile, Desktop",
            "Media Queries on 981 px width screen",
            "Uses Advance Selectors and Flex Box",
          ],
          languages: "HTML, CSS",
          code: "https://github.com/kayoMichael/Uber-eats-confirmation-page",
          carsPic: [{ img: "img/projects/mobile-version.png" }],
        },

        {
          name: "Personal Profolio Webpage",
          img: "img/projects/slideshow/personal-profolio0.png",
          date: "August 2023",
          icons: [faHtml5, faJs, faVuejs],
          description:
            "Personal profolio Webpage talking about Achievements and project history",
          details: [
            "Included with buttons to navigate through profolio",
            "All information about past projects and myself as a programmer",
            "Good display of images",
          ],
          languages: "HTML, Javascript, Vue.js",
          code: "https://github.com/kayoMichael/kayoMichael.github.io",
          carsPic: [
            {
              img: "img/projects/slideshow/personal-profolio0.png",
              caption: "Top",
            },
            {
              img: "img/projects/slideshow/personal-profolio.png",
              caption: "About me",
            },
            {
              img: "img/projects/slideshow/personal-profolio2.png",
              caption: "Skills",
            },
            {
              img: "img/projects/slideshow/personal-profolio3.png",
              caption: "Experiences",
            },
            {
              img: "img/projects/slideshow/personal-profolio4.png",
              caption: "Projects",
            },
            {
              img: "img/projects/slideshow/personal-profolio5.png",
              caption: "Contact",
            },
          ],
        },
        {
          name: "Workout Landing Page",
          img: "img/projects/slideshow/workout-1.png",
          date: "Oct 2023",
          icons: [faHtml5, faCss3Alt],
          description: "WorkOut LandPage With Responsivness",
          details: [
            "Max Strong Work Out Page",
            "Has A Mobile and PC Version for each of the Screen Size",
            "Programmed 100% in Vanilla CSS",
          ],
          languages: "HTML, Javascript, Vue.js",
          code: "https://github.com/kayoMichael/Workout-Land-page",
          carsPic: [
            {
              img: "img/projects/slideshow/workout-2.png",
            },
            {
              img: "img/projects/slideshow/workout-3.png",
            },
            {
              img: "img/projects/slideshow/workout-4.png",
            },
            {
              img: "img/projects/slideshow/workout-5.png",
            },
          ],
        },
        {
          name: "Game Page",
          img: "img/projects/slideshow/Main-Page.png",
          date: "Oct 2023",
          icons: [faHtml5, faCss3Alt, faReact, faJs],
          description: "Epic Games Page",
          details: [
            "A Game Landing Pages Styled With Chakra UI",
            "Fetched Game Information from Rawg API and Displayed Using React",
            "Utilized Hooks and Services for a clean Source Code",
          ],
          languages: "HTML, TypeScript, React, Chakra UI",
          code: "https://github.com/kayoMichael/Game-Page",
          carsPic: [
            {
              img: "img/projects/slideshow/Page-2.png",
            },
            {
              img: "img/projects/slideshow/Page-3.png",
            },
          ],
        },

        // { name: 'Project6', img: '/img1',
        // description: 'Some quick example text to build on the card title and make up the bulk of the cards content.',
        // details: [],
        // languages: '', code: ''}
      ],
    };
  },
};
</script>
