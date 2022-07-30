<template>
  <div>
    <div id="cursor" />
    <div id="intro">
      <b-container>
        <b-row>
          <b-col>
            <h1 data-aos="fade-up">
              Hello. <br> I'm a web developer and UI designer based in Kinshasa.
            </h1>
            <p data-aos="fade-up" data-aos-delay="200">
              My name is Axel Ilali and I enjoy creating things that live on the internet.
            </p>
            <span data-aos="fade-up" data-aos-delay="300">Find me on
              <strong><a tabindex="blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/axel-ilali/">LinkedIn</a></strong>,
              <strong><a href="" rel="noopener noreferrer">Github</a></strong> and
              <strong><a target="blank" rel="noopener noreferrer" href="https://twitter.com/im__axel">Twitter</a></strong>
            </span>
            <a data-aos="fade-up" data-aos-delay="400" class="button" href="mailto:ilali.axel@gmail.com">Let's work together</a>
          </b-col>
        </b-row>
      </b-container>
    </div>

    <main>
      <section id="memoji">
        <b-container>
          <b-row>
            <b-col>
              <!-- <img src="~assets/me-1.png" alt="" srcset=""> -->
            </b-col>
          </b-row>
        </b-container>
      </section>

      <section id="about">
        <b-container>
          <b-row>
            <b-col>
              <h2>About Me</h2>
              <h3>Mbote <img height="20" src="~assets/waving-hand.png" alt="Waving hand"> ! My name is Axel and I enjoy creating things that live on the internet. My interest in web development started back in 2012 when I decided to try HTML & CSS. </h3>
              <p>Fast-forward to today, I have had the privilege of working at super cool web development a start-up, and as a freelancer building awsome web apps.</p>
              <p>Here are a few stuff I’ve been working with :</p>
              <span v-for="(techno,key) in technos" :key="key">{{ techno }}</span>
            </b-col>
          </b-row>
        </b-container>
      </section>

      <section id="work">
        <div v-for="(client, key) in clients" :key="key" class="client-box">
          <div class="name">
            <img v-if="client.logo" width="150" :src="require('../assets/clients/'+client.logo)" alt="" srcset="">
            <p v-else>
              {{ client.name }}
            </p>
          </div>
          <div class="desc">
            <p><strong>Work with : <u>{{ client.name }}</u></strong> <br> {{ client.desc }}</p>
          </div>
        </div>
      </section>

      <section id="contact">
        <b-container>
          <b-row>
            <b-col>
              <img data-aos="zoom-in" width="300" src="~assets/me-3.png" alt="" srcset="">
              <h2>What's next ?</h2>
              <p>Feel free to shoot me an email to talk about your next big project. I'll be glad to work with you !</p>
              <a href="mailto:ilali.axel@gmail.com">Hire me</a>
            </b-col>
          </b-row>
        </b-container>
      </section>
    </main>
  </div>
</template>

<script>
import AOS from 'aos'
import 'aos/dist/aos.css'
export default {

  data () {
    return {
      technos: ['HTML', 'CSS', 'JavaScript', 'VueJS', 'Nuxt', 'WordPress', 'PHP', 'Twig', 'JQuery', 'Laravel', 'Wix', 'Adobe XD', 'Figma'],
      clients: [
        {
          name: 'Kinshasa Digital',
          desc: 'Built several custom WordPress themes and web apps for big clients',
          logo: 'kinshasa-digital.png'
        },
        {
          name: 'Pavillion Noir',
          desc: 'Built a live streaming SPA using Nuxt and Vimeo API',
          logo: 'pavillion-noir.png'
        },
        {
          name: 'AW Innovate',
          desc: 'Created a real estate custom WordPress theme using Timber framework, Twig & PHP',
          logo: 'aw-innovate.png'
        },
        {
          name: 'Eliette',
          desc: 'Created a custom WordPress theme and job application plugin using Timber framework, Twig & PHP',
          logo: 'eliette.png'
        },
        {
          name: 'Kalda Group',
          desc: 'Built a WordPress website using WPBakery',
          logo: 'kalda.png'
        },
        {
          name: 'Fondation Bulayima',
          desc: 'Built a WordPress website using WPBakery',
          logo: 'fondation-bulayima.png'
        },
        {
          name: 'Blanchard Nzaka & Associés',
          desc: 'Built a Lawyer website using Wix'
        },
        {
          name: 'Mbote Lingala',
          desc: 'Designed UI interfaces for Learning app '
        }
      ]
    }
  },
  mounted () {
    AOS.init({})
    const cursor = document.getElementById('cursor')
    const links = document.querySelectorAll('a')

    links.forEach((link) => {
      link.addEventListener('mouseover', (e) => {
        cursor.classList.add('grow')
      })

      link.addEventListener('mouseout', (e) => {
        cursor.classList.remove('grow')
      })
    })

    window.addEventListener('mousemove', function (e) {
      cursor.style.top = `${e.clientY}px`
      cursor.style.left = `${e.clientX}px`
    })
  }
}
</script>
<style lang="scss">
$primary: #fd8e8e;
$secondary:#2e304b;
$alternate: #6b6c7b;
$alternate-2: #f1f1f1;

h3,p {
  font-weight: lighter;
}
#cursor {
  display: none;
  position: fixed;
  width: 50px;
  height: 50px;
  border:2px solid #ddd;
  z-index: 20;
  border-radius: 50%;
  transform: translate(-50%,-50%);
  transition: all ease-out .1s;
  pointer-events: none;
  &.grow {
    width: 80px;
    height: 80px;
  }
}
.button {
  color: $primary;
  border:2px solid $primary;
  background: transparent;
  display: inline-block;
  padding: 15px 30px;
  border-radius: 40px;
  transition: all ease .2s;
  &:hover {
    background: $primary;
    color: $secondary;
    text-decoration: none;
    #cursor {
    width: 100px;
    height: 100px;
  }
  }
}
#intro {
  position: fixed;
  width: 50%;
  height: 100vh;
  padding: 0 50px;
  background: $secondary;
  color: $primary;
  display: flex;
  align-items: center;
  span {
    color: #b5b6bd;
    font-size: .8125rem;
    margin-bottom: 50px;
    display: block;
    font-weight: lighter;
    a {
      color: #fff;
    }
  }

  h1,p {
    margin-bottom: 50px;
  }
}
main {
  width: 50%;
  margin-left: 50%;
  section {
    height: 100vh;
    position: sticky;
    top: 0;
    display: flex;
    align-items: center;
    padding: 50px;
  }
  #memoji {
    z-index: 1;
    text-align: center;
    background: url('~assets/bg-2.jpg') no-repeat;
    background-size: cover;
    img {
      max-width: 100%;
    }
  }
  #about {
    z-index: 2;
    background: #fff ;
    color: $secondary;
    h2,h3 {
      margin-bottom: 20px;
    }
    p {
      color:$alternate;
    }
    span {
      display: inline-block;
      padding: 2px 10px;
      background: $secondary;
      color: #fff;
      margin-right: 10px;
      margin-bottom: 10px;
      font-size: .875rem;
      border-radius: 20px;
    }
  }
  #work {
    z-index: 3;
    display: grid;
    grid-template-columns: repeat(2,1fr);
    grid-gap: 2px;
    padding: 0px;
    background: #fff;
    img {
      margin: 0 auto;
    }
    .client-box {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100%;
      p {margin: 0;}
      .name,.desc {
        position: absolute;
        left: 0;
        top: 0;
        bottom: 0;
        right: 0;
        display: flex;
        align-items: center;
        padding: 30px;
      }
      .name {
        background: $alternate-2;
        z-index: 3;
        transition: all ease .1s;
        font-weight: bold;
        justify-content: center;
        p {
          font-size: 1.25rem;
        }
      }
      .desc {
        background: #fff;
        z-index: 2;
        p {
          transition: all ease .3s;
          transform: translateY(10px);
        }
      }
      &:hover {
        .name {
          opacity: 0;
        }
        .desc p {transform: translateY(0px);}
      }
    }
  }
  #contact {
    z-index: 4;
    background: $primary;
    color: #fff;
    text-align: center;

    a {
      display: block;
      margin-top: 50px;
      color: #fff;
      text-decoration: underline;
    }
  }
}
@media screen and (max-width:768px) {
  #intro {
    position: relative;
    width: 100%;
    padding: 20px;
    text-align: center;
  }
  main {
    width: 100%;
    margin-left: 0;
    #memoji {
      background-position: center;
    }
    #about {
      padding: 0 20px;
    }
  }
}
@media screen and (max-width:576px) {
  #cursor {
    display: none;
  }
  main {
    #work {
      img {max-width: 100%;}
      .client-box .desc p {
        font-size: .875rem;
      }
    }
    #contact {
      img { max-width: 100%;}
    }
  }
}

@media screen and (max-width:320px) {
  h1 {
    font-size: 30px;
  }
  main {
    #about {
      position: relative;
      height: max-content;
      .container {
        padding: 50px 10px;
      }
      h3 {
        font-size: 1.5rem;
      }
    }
    #work {
      .client-box .desc {
        padding: 20px;
        p {
        font-size: .625rem;
      }
      }
    }
  }
}
</style>
