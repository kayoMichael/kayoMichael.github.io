<template>
    <div>
        <div class="mt-4 mb-5">
            <h3>Unpaid Internships</h3>
            <b-card v-for="job in jobs" :key="job.title" :title="job.title" 
              class="col-sm-9 col-lg-8 col-11 mx-auto text-left mb-2">
                <ul class="list-inline">
                    <li class="list-inline-item"> <a :href="job.compUrl" target="_blank" class="text-secondary"> {{job.company}} </a> |</li> 
                    <li class="list-inline-item"> {{job.date}} |</li>
                    <li class="list-inline-item"> {{job.location}} </li>
                </ul>
                <ul>
                    <li v-for="detail in job.details" :key="detail">{{detail}}</li>
                </ul>
                
            </b-card>
        </div>

        <div>
            <h3>Extracurricular Activities</h3>
            <b-card v-for="entrep in entreps" :key="entrep.name" 
              class="col-sm-9 col-lg-8 col-11 mx-auto text-left mb-2">
                <b-card-title>
                    <a :href="entrep.url" target="_blank" class="text-dark mr-3">{{entrep.name}}</a>
                    <small class="text-muted">{{entrep.position}}</small>
                </b-card-title>
                <b-img :src="entrep.img" fluid right />
                <ul class="list-inline">
                    <li class="list-inline-item"> <a :href="entrep.projUrl" target="_blank" class="text-secondary">{{entrep.project}}</a> |</li>
                    <li class="list-inline-item"> {{entrep.date}} |</li>
                    <li class="list-inline-item"> {{entrep.location}}</li>
                </ul>
                <ul>
                    <li v-for="detail in entrep.details" :key="detail">{{detail}}</li>
                </ul>
                <p v-if="entrep.urlMes">
                    <span class="text-muted">{{entrep.urlMes}}</span>
                </p>
            </b-card>
        </div>
    </div>
</template>

<script>
export default {
    name: 'WorkExperience',
    data: function() {
        return {
            jobs: [
                {title: 'Book Reservation System', company: 'MPB Japan', location: 'Tokyo Japan',
                 date: 'Jun 2021 - Sep 2021',
                 details: ['Developed a Book Reservation System with mentoring from a senior engineer', 'Implemented business logic of REST API to retrieve, update and check out books\n' +
                 'using Java Spring framework and PostgreSQL database', 'More Details in the Projects Section'],
                 compUrl: '/',
                },

                {title: 'Student Database', company: 'Inspiration Learning Center', location: 'Missisauga, ON, Canada',
                 date: 'Jun 2020 - Sep 2020',
                 details: ['Developed a student database system using Java Spring framework and MYSQL database with another employee.',
                 'Created HTML page to allow the administrator to create, update, and view student information such as name, age, and current courses',
                 'Implemented back-end API to store and update student information in MYSQL database'],
                 compUrl: '/',
                },
                ],
            entreps: [
                {name: 'Computer Science Summer Credit Course', Insitution: 'Cornell University', date: 'Jun 2020 - Aug 2020',
                 location: 'Online', img: 'img/logos/CornellUniversity.jpeg',
                 details: ['A Selection-Based program',
                 'Worked on Weekly lessons and labs mainly focused on Object-oriented Programming and Graphical User Interfaces (GUI)',
                 'Programmed a functional and interactive board game utilizing inheritance as a project',
                 'Programmed a trivia game with visuals using Tkinter as a project'],
                 url: 'https://sce.cornell.edu/courses/roster/cs-1110'},
                ],
        }
    }
}
</script>