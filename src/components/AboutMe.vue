<template>
    <div class="about-me container-sm mt-4">
      <div>
          <!-- header & image -->
        <b-img src="img/profile.jpg" width="300" height="300" rounded="circle" fluid alt="Picture of Nancy"/>
        
        <div class="about-me-body">
          <div class="container-sm">
            <br>

            <p class="lead-text"> Hello! My name is Michael Li.</p>
            I am a <strong> 3rd year Stduent</strong>studying Mathematics and Computer Science at the University of Waterloo.
            My passion lies in <u> software development and applied mathematics</u>. I am especially interested in <u> front-end and
            back-end web-development </u>. I enjoy exploring new algorithms and technologies, and am constantly looking for
            methods to improve the <strong> efficiency </strong> of the program. I also value <strong> organization </strong> and <strong> readability </strong> when coding. I put strong emphasis on
            neat project structure, logical classes and database models, and detailed documentation. <br>
            <br>

            In school, I am taking additional classes on <u> mathematics and computer science</u>. I am looking
            to applying these knowledge in software development inorder for myself to become a first hand programmer. I want to use my skills and knowledge
            to build software that can fill <em>the gap</em> in people's lives. 
          </div>
          <br><br>
          <div>
           <!-- download resume -->
            <a class="btn btn-outline-secondary" href="file/Michael_He_yang_Li____3.pdf" target="_blank">Resume</a><br>
          </div>
        </div>

      </div>
    </div>
</template>

<script>
export default {
  name: 'AboutMe',
  props: {
    msg: String
  },
}
</script>

<style scoped>
  .lead-text {
    font-size: 1.3rem;
    font-weight: 500;
  }
  .about-me-body {
    font-size: 1.1rem;
  }
</style>