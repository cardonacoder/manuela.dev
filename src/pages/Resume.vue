<template>
  <div>
    <navbar theme="dark" />
    <section class="resume" aria-label="resume">
      <div class="container">
        <div class="row">
          <h1
            class="section-title wow fadeIn"
            data-wow-duration="1s"
            :data-heading="title"
          >
            {{ title }}
          </h1>
        </div>

        <div class="row">
          <div class="resume__timeline col-xs-offset-2 col-xs-8">
            <div
              class="resume__timeline-section"
              v-for="(listYear, index) in resume"
              :key="index"
            >
              <h3 class="resume__timeline-year">{{ listYear.year }}</h3>
              <ul class="row resume__timeline-list">
                <li
                  class="resume__timeline-item wow zoomIn"
                  v-for="(item, index) in listYear.content"
                  :key="index"
                >
                  <a :href="item.link" class="resume-timeline-item-title">
                    <i
                      class="em"
                      :class="item.icon"
                    ></i>
                    {{ item.title }}
                  </a>
                  <p class="resume__timeline-item-description">{{ item.description }}</p>
                  <p class="resume__timeline-item-date">{{ item.date }}</p>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import WOW from 'wow.js/dist/wow.min'
import Navbar from '../components/Navbar'

export default {
  data () {
    return {
      title: '<Resume />',
      resume: [{
        year: '2019',
        content: [{
          date: 'March - currently',
          description: 'Chapter Leader',
          icon: 'em-woman-raising-hand',
          link: 'https://www.vuevixens.org/team',
          title: 'Vue Vixens'
        }, {
          date: 'February - currently',
          description: 'GitHub Campus Expert',
          icon: 'em-woman-raising-hand',
          link: 'https://githubcampus.expert/manucastrillonm/',
          title: 'GitHub Education'
        }]
      }, {
        year: '2018',
        content: [{
          date: 'September',
          description: 'Co-organizer',
          icon: 'em-woman-raising-hand',
          link: 'https://www.ngcolombia.com/ng-girls',
          title: 'NgGirls'
        }, {
          date: 'September',
          description: 'Academic Comittee',
          icon: 'em-woman-raising-hand',
          link: 'http://www.ngcolombia.com',
          title: 'NgColombia'
        }, {
          date: 'January - currently',
          description: 'Huge',
          icon: 'em-female-technologist',
          link: 'https://www.hugeinc.com/',
          title: 'Web Engineer'
        }, {
          date: 'January - currently',
          description: 'Co-organizer',
          icon: 'em-sparkling_heart',
          link: 'http:///www.pionerasdev.co',
          title: 'Pioneras Developers'
        }]
      }, {
        year: '2017',
        content: [{
          date: 'November',
          description: 'Mentor',
          icon: 'em-woman-raising-hand',
          link: 'https://www.ngcolombia.com/',
          title: 'NgColombia'
        }, {
          date: 'November',
          description: 'Mentor',
          icon: 'em-woman-raising-hand',
          link: 'http://ng-girls.org/NgColombia/',
          title: 'NgGirls'
        }, {
          date: 'August',
          description: 'Volunteer',
          icon: 'em-woman-raising-hand',
          link: 'http://medellinup.co/women-edition/',
          title: 'Startup Weekend Women Edition'
        }, {
          date: 'March - Currently',
          description: 'Co-organizer',
          icon: 'em-woman-raising-hand',
          link: 'https://github.com/CodexUdeA/Encuentros',
          title: 'Codex UdeA'
        }]
      }, {
        year: '2016',
        content: [{
          date: 'September',
          description: 'Competitor',
          icon: 'em-female-technologist',
          link: 'http://communities.techstars.com/colombia/medellin/startup-weekend/9735',
          title: 'Startup Weekend'
        }, {
          date: 'January',
          description: 'Competitor',
          icon: 'em-female-technologist',
          link: 'https://globalgamejam.org/2016/games/elements-souls',
          title: 'Global Game Jam'
        }]
      }, {
        year: '2015',
        content: [{
          date: 'August',
          description: 'Juventic (Google-Colnodo-CUN)',
          icon: 'em-female-student',
          link: '#',
          title: 'Media Content Design and Production'
        }, {
          date: 'February - November',
          description: 'Competitor',
          icon: 'em-female-technologist',
          link: '#',
          title: 'Colombian Collegiate Programming League'
        }, {
          date: 'February - December 2017',
          description: 'Universidad de Antioquia',
          icon: 'em-blue_book',
          link: '#',
          title: 'Administrative Manager'
        }]
      }, {
        year: '2014',
        content: [{
          date: 'September - December',
          description: 'Cymetria Group S.A.S.',
          icon: 'em-female-student',
          link: '#',
          title: 'Visual Communication using Adobe Photoshop® CS6'
        }, {
          date: 'July - July 2015',
          description: 'Universidad de Antioquia',
          icon: 'em-blue_book',
          link: '#',
          title: 'Teaching Assistant - Subject: Discrete Mathematics'
        }]
      }, {
        year: '2013',
        content: [{
          date: 'March - Currently',
          description: 'Universidad de Antioquia',
          icon: 'em-female-student',
          link: '#',
          title: 'Software Engineering'
        }]
      }]
    }
  },
  mounted () {
    new WOW().init()
  },
  components: {
    Navbar
  }
}
</script>

<style lang="scss">
@import '~styles/variables';
@import '~styles/mixins';
@import '~styles/functions';

.resume {

  &__timeline {
    margin-top: 50px;
    position: relative;

    &:before {
      content: '';
      background: color('nevada');
      height: 100%;
      margin-left: 0;
      position: absolute;
      width: 5px;
      z-index: -1;
      border-radius: 50%;

      @include from('md') {
        margin-left: 50%;
      }
    }

    &-list {
      flex-direction: column;
    }

    &-year {
      background-color: color('nevada');
      border-radius: 8px;
      color: color('white');
      font-size: $font-lg;
      margin: 10px auto;
      padding: 5px 15px;
      text-align: center;
      width: fit-content;
      width: -moz-fit-content;
    }

    &-item {
      background-color: color('white');
      border: 2px solid color('nevada');
      border-radius: 8px;
      margin: 15px;
      padding: 10px;
      position: relative;
      width: 80%;

      &::before {
        content: '';
        position: absolute;
        border-style: solid;
        top: 50%;
        width: 10px;
        height: 10px;
        transform: rotate(45deg);
        border-color: color('nevada');
        background-color: color('white');
        left: -7px;
        border-width: 0 0 2px 2px;
      }

      @include from('md') {
        width: 40%;

        &:not(:first-child) {
          margin-top: -30px;
        }

        &:first-child {
          margin-top: 0;
        }

        &:nth-child(even) {
          align-self: flex-end;

          &::before {
            left: -7px;
            border-width: 0 0 2px 2px;
          }
        }

        &:nth-child(odd) {
          align-self: flex-start;

          &::before {
            left: auto;
            right: -7px;
            border-width: 2px 2px 0 0;
          }
        }
      }

      &-title {
        font-size: $font-md;
        font-weight: bold;
        margin: 5px 0;

        .em {
          max-width: 15px;
        }
      }

      &-description {
        margin: 5px 0;
      }

      &-date {
        margin: 0;
        font-size: $font-sm;
        font-style: italic;
      }
    }
  }
}
</style>
