<template>
  <div>
    <div class="mt-4 mb-5">
      <h3>Internships</h3>
      <b-card
        v-for="job in jobs"
        :key="job.title"
        :title="job.title"
        class="col-sm-9 col-lg-8 col-11 mx-auto text-left mb-2"
      >
        <ul class="list-inline">
          <li class="list-inline-item">
            <a :href="job.compUrl" target="_blank" class="text-secondary">
              {{ job.company }}
            </a>
            |
          </li>
          <li class="list-inline-item">{{ job.date }} |</li>
          <li class="list-inline-item">{{ job.location }}</li>
        </ul>
        <ul>
          <li v-for="detail in job.details" :key="detail">{{ detail }}</li>
        </ul>
      </b-card>
    </div>

    <div>
      <h3>Extracurricular Activities</h3>
      <b-card
        v-for="entrep in entreps"
        :key="entrep.name"
        class="col-sm-9 col-lg-8 col-11 mx-auto text-left mb-2"
      >
        <b-card-title>
          <a :href="entrep.url" target="_blank" class="text-dark mr-3">{{
            entrep.name
          }}</a>
          <small class="text-muted">{{ entrep.position }}</small>
        </b-card-title>
        <b-img :src="entrep.img" fluid right />
        <ul class="list-inline">
          <li class="list-inline-item">
            <a :href="entrep.projUrl" target="_blank" class="text-secondary">{{
              entrep.project
            }}</a>
            |
          </li>
          <li class="list-inline-item">{{ entrep.date }} |</li>
          <li class="list-inline-item">{{ entrep.location }}</li>
        </ul>
        <ul>
          <li v-for="detail in entrep.details" :key="detail">{{ detail }}</li>
        </ul>
        <p v-if="entrep.urlMes">
          <span class="text-muted">{{ entrep.urlMes }}</span>
        </p>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  name: "WorkExperience",
  data: function () {
    return {
      jobs: [
        {
          title: "Student Database",
          company: "Inspiration Learning Center",
          location: "Missisauga, ON, Canada",
          date: "Jun 2020 - Sep 2020",
          details: [
            "Developed a student database system using Python Flask and MYSQL database with another employee.",
            "Created HTML page to allow the administrator to create, update, and view student information such as name, age, and current courses",
            "Implemented back-end API to store and update student information in MYSQL database",
          ],
          compUrl: "/",
        },
        {
          title: "Internet Exchange Portal Site Development",
          company: "Weseek Inc.",
          location: "Tokyo, Japan",
          date: "May 2022 - Aug 2022",
          details: [
            "Constructed Migration Files using PostgreSQL and Ruby on Rails to effectively retrieve and create new objects from ActiveRecord.",
            "Applied MVC principles to effectively develop robust backend systems and designed complex SQL scripts to optimize database operations on PostgreSQL",
            "Designed a stateful front end from scratch with AngularJS and HTML/Bootstrap with no refresh-rendering and REST API calls",
          ],
          compUrl: "/",
        },
        {
          title: "Payment Portal Site Development",
          company: "Kaima Data",
          location: "Tokyo, Japan",
          date: "May 2022 - Aug 2022",
          details: [
            "Contributed to the development of the company's payment portal, leveraging NEXT.js and Bootstrap to create a user-friendly and efficient payment experience for customers",
            "Proficiently leveraged asynchronous API calls to fetch and process data, dynamically presenting information on the frontend, enhancing user experiences with real-time updates and responsive web applications",
            "Implemented E2E testing with Cypress to simulate user interactions and validate user flows, while using Jest for unit testing to ensure the functionality and correctness of individual components and JavaScript code",
          ],
          compUrl: "/",
        },
        {
          title: "Serverless Application Development",
          company: "Everforth ltd.",
          location: "Remote",
          date: "Nov 2022 - Present",
          details: [
            "Utilized AWS Lambda and AWS API Gateway Service to develop the back-end functionalities within a server-less mobile application.",
            "Developed multiple Python scripts centered around efficiency to optimize business processes, enhance data processing, and achieve fast execution on AWS Lambda",
            "Set up AWS S3 for efficient data storage and retrieval, while connecting to Aurora DB to enable real-time data processing and retrieval within serverless applications",
          ],
          compUrl: "/",
        },
      ],
      entreps: [
        {
          name: "Computer Science Summer Credit Course",
          Insitution: "Cornell University",
          date: "Jun 2020 - Aug 2020",
          location: "Online",
          img: "img/logos/CornellUniversity.jpeg",
          details: [
            "A Selection-Based program",
            "Worked on Weekly lessons and labs mainly focused on Object-oriented Programming and Graphical User Interfaces (GUI)",
            "Programmed a functional and interactive board game utilizing inheritance as a project",
            "Programmed a trivia game with visuals using Tkinter as a project",
          ],
          url: "https://sce.cornell.edu/courses/roster/cs-1110",
        },
      ],
    };
  },
};
</script>
