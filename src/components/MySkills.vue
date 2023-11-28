<template>
  <div class="mt-4">
    <!-- Programming Skills -->
    <div class="mb-4">
      <h4>Programming</h4>
      <div class="container-fluid">
        <div class="row justify-content-center">
          <b-card
            v-for="(skill, idx) in skills.program"
            :key="idx"
            class="col-lg-2 col-sm-3 col-4 mr-3 mb-3 pr-0 pl-0"
            border-variant="warning"
            :header="skill.name"
            header-bg-variant="transparent"
            align="center"
          >
            <b-card-img :src="skill.img" class="prog-logo" />
            <template v-slot:footer>
              <span v-for="exp in skill.exps" :key="exp">
                <small class="text-muted">{{ exp }}</small
                ><br />
              </span>
            </template>
          </b-card>
        </div>
      </div>
    </div>

    <!-- System Skills -->
    <div class="mt-2 mb-4">
      <h4>System</h4>
      <div class="container">
        <div class="row justify-content-center">
          <b-card
            v-for="(skill, idx) in skills.system"
            :key="idx"
            class="col-lg-2 col-sm-4 col-4 mr-3 mb-3 pr-0 pl-0"
            border-variant="info"
            :header="skill.name"
            header-bg-variant="transparent"
            align="center"
          >
            <b-card-img :src="skill.img" class="prog-logo" />
            <template v-slot:footer>
              <span v-for="exp in skill.exps" :key="exp">
                <small class="text-muted">{{ exp }}</small
                ><br />
              </span>
            </template>
          </b-card>
        </div>
      </div>
    </div>

    <!-- Framework Skills -->
    <div class="mt-2 mb-4">
      <h4>Framework</h4>
      <div class="container">
        <div class="row justify-content-center">
          <b-card
            v-for="(skill, idx) in skills.framework"
            :key="idx"
            class="col-lg-2 col-sm-4 col-4 mr-3 mb-3 pr-0 pl-0"
            border-variant="info"
            :header="skill.name"
            header-bg-variant="transparent"
            align="center"
          >
            <b-card-img :src="skill.img" class="prog-logo" />
            <template v-slot:footer>
              <span v-for="exp in skill.exps" :key="exp">
                <small class="text-muted">{{ exp }}</small
                ><br />
              </span>
            </template>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MySkills",
  data: function () {
    return {
      skills: {
        program: [
          { name: "Python", exps: ["3 years"], img: "img/logos/python.png" },
          { name: "C", exps: ["1 year"], img: "img/logos/c.png" },
          { name: "HTML", exps: ["1 year"], img: "img/logos/html.png" },
          { name: "CSS", exps: ["1 year"], img: "img/logos/css_logo.png" },
          {
            name: "JavaScript",
            exps: ["2 year"],
            img: "img/logos/Javascript2.jpeg",
          },
        ],
        system: [
          {
            name: "PostgreSQL",
            exps: ["4 months"],
            img: "img/logos/postgreSQL.png",
          },
          { name: "MySQL", exps: ["4 months"], img: "img/logos/mysql.png" },
          { name: "AWS", exps: ["1 year"], img: "img/logos/aws.jpg" },
        ],
        framework: [
          { name: "Vue", exps: ["1 year"], img: "img/logos/vue.png" },
          { name: "Angular", exps: ["1 year"], img: "img/logos/Angular.png" },
          { name: "React", exps: ["8 months"], img: "img/logos/React.png" },
          {
            name: "Bootstrap",
            exps: ["8 months"],
            img: "img/logos/bootstrap.png",
          },
          {
            name: "Chakra",
            exps: ["4 months"],
            img: "img/logos/chakra.svg",
          },
          {
            name: "Serverless",
            exps: ["1 year"],
            img: "img/logos/serverless.svg",
          },
          { name: "Next", exps: ["4 months"], img: "img/logos/next-js.svg" },
          { name: "Node", exps: ["4 months"], img: "img/logos/Node.svg" },
        ],
      },
    };
  },
};
</script>

<style scoped>
.prog-logo {
  width: 100px;
  height: 100px;
}

.hd-logo {
  width: 250px;
  height: 100px;
}
</style>
