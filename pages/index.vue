<template>
  <div id="header">
    <b-container>
      <b-row class="text-center">
        <b-col lg="7" class="mx-auto">
          <div>
            <img data-aos="zoom-in" src="~assets/axel-memoji-1.png"  alt="Axel Memoji">
            <h1 data-aos="fade-up" data-aos-delay="300">Hi, i am axel <img src="~assets/waving-hand.png" height="30" alt="" srcset=""></h1>
            <h2 data-aos="fade-up" data-aos-delay="400">A web developer <br> and UI designer living in Congo DR.</h2>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import AOS from 'aos'
import 'aos/dist/aos.css'

export default {
  mounted () {
    AOS.init({
      // easing: 'ease-out'
    })
  }
}
</script>

<style lang="scss" scoped>
* {
  font-family: 'Outfit', sans-serif;
}
#header {
  height: 100vh;
  display: flex;
  align-items: center;
  img {
    margin-bottom: 20px;
  }
  h1 {
    font-size: 24px;
    font-weight: normal;
  }
  h2 {
    font-size: 60px;
  }
}
</style>
