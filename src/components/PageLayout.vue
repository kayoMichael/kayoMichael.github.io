<template>
  <div>
    <section class="mt-4 mb-4">
      <b-card overlay class="mt-5" img-src="img/header.jpg"
       title="Hello! I'm Nancy Li">
       <em>A Backend & Full Stack Engineer interested in software engineering and system design </em>
      </b-card>
    </section>

    <section id ="about" class="mt-3 mb-4">
      <h1 class="pt-5">About Me</h1>
      <AboutMe />
    </section>

    <section id="skills" class="mt-5 mb-4">
      <h1 class="pt-5">Skills</h1>
      <MySkills />
    </section>

    <section id="experience" class="mt-5 mb-5">
      <h1 class="pt-5">Experience</h1>
      <WorkExperience />
    </section>

    <section id ="projects" class="mt-4 mb-5">
      <h1 class="pt-5">Projects</h1>
      <AllProjects />
    </section>

    <section id ="contact" class="mt-4 mb-4">
      <h1 class="pt-5">Contact</h1>
      <ContactMe />
    </section>
  </div>
</template>

<script>
import AboutMe from './AboutMe.vue'
import MySkills from './MySkills.vue'
import WorkExperience from './WorkExperience.vue'
import AllProjects from './AllProjects.vue'
import ContactMe from './ContactMe.vue'

export default {
  name: 'PageLayout',
  props: {
    msg: String
  },
  components: { AboutMe, MySkills, WorkExperience, AllProjects, ContactMe }
}
</script>
