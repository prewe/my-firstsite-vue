<template>
  <div id="app">
    <transition appear name="preloader-fade">
      <div class="preloader" v-if="!isLoad">
        <div class="bar-wrapper">
          <div class="bar"></div>
          <div class="bar reverse"></div>
          <div class="bar"></div>
        </div>
      </div>
    </transition>
    <header class="menu">
      <ul>
        <li class="menu__item menu__item-1"><a href="#Home" @click="choseHome()" v-bind:class="{ menu__itemborder: isHome }">Home</a></li>
        <li class="menu__item menu__item-2"><a href="#About" @click="choseAbout()" v-bind:class="{ menu__itemborder: isAbout }">About</a></li>
        <li class="menu__item menu__item-3"><a href="#Gallery" @click="choseGallery()" v-bind:class="{ menu__itemborder: isGallery }">Gallery</a></li>
        <li class="menu__item menu__item-4"><a href="#Contacts" @click="choseContacts()" v-bind:class="{ menu__itemborder: isContacts }">Contacts</a></li>
      </ul>
    </header>
    
    <main class="main" v-if="isLoad">
      <transition appear name="slide-fade">
        <div class="home" key="home" v-if="isHome">
          <transition appear name="header">
            <div class="home__header">HOME</div>  
          </transition>
          <transition appear name="content">
            <p class="home__content">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Adipisci cumque quam reprehenderit sunt nesciunt atque! Doloremque ducimus distinctio quae consectetur.</p>  
          </transition>
        </div> 
        <div class="about" key="about" v-if="isAbout">
          <transition appear name="header">
            <div class="home__header">ABOUT</div>
          </transition>
          <transition appear name="content">
            <p class="home__content">Lorem ipsum dolor sit amet consectetur adipisicing elit. Saepe beatae voluptates sequi assumenda amet quo ea accusantium placeat magni nesciunt nam iure dolorum vel, rerum fuga cum deserunt consectetur. Ipsam facere totam vel, dolorem, vitae veritatis laborum consequuntur, labore nam incidunt esse voluptas ratione sapiente amet aliquid ut inventore modi minima dolor sed. Reiciendis voluptatem nam quisquam inventore vel delectus cum id perferendis, soluta doloremque libero! Animi facilis enim sunt sequi praesentium delectus beatae in sapiente totam, deleniti omnis? Explicabo tempore tempora minima molestiae numquam sequi maiores cum aliquid deserunt, quis illo hic quidem illum voluptas voluptatum enim accusantium dolorem.</p>
          </transition>
        </div>
        <div class="gallery" key="gallery" v-if="isGallery">
          <transition appear name="header">
            <div class="home__header" v-if="!isAboutWork">GALLERY</div>
          </transition>
          <transition appear name="content">
            <div class="works-wrapper" v-if="!isAboutWork">
              <div class="work work-1" @click="choseWork1()"></div>
              <div class="work work-2" @click="choseWork2()"></div>
              <div class="work work-3" @click="choseWork3()"></div>
              <div class="work work-4" @click="choseWork4()"></div>
              <div class="work work-5" @click="choseWork5()"></div>
              <div class="work work-6" @click="choseWork6()"></div>
              <div class="work work-7" @click="choseWork7()"></div>
              <div class="work work-8" @click="choseWork8()"></div>
              <div class="work work-9" @click="choseWork9()"></div>
            </div>
          </transition>
          <transition name="about-work">
            <div class="about-work about-work-1" v-if="isAboutWork1">
              <div class="work work-1"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
            <div class="about-work about-work-2"  v-if="isAboutWork2">
              <div class="work work-2"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
            <div class="about-work about-work-3"  v-if="isAboutWork3">
              <div class="work work-3"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
            <div class="about-work about-work-4"  v-if="isAboutWork4">
              <div class="work work-4"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
            <div class="about-work about-work-5"  v-if="isAboutWork5">
              <div class="work work-5"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
            <div class="about-work about-work-6"  v-if="isAboutWork6">
              <div class="work work-6"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
            <div class="about-work about-work-7"  v-if="isAboutWork7">
              <div class="work work-7"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
            <div class="about-work about-work-8"  v-if="isAboutWork8">
              <div class="work work-8"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
            <div class="about-work about-work-9"  v-if="isAboutWork9">
              <div class="work work-9"></div>
              <p class="about-work-content">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam, expedita maxime perspiciatis at laboriosam, omnis saepe dolorem similique corporis atque repudiandae sit perferendis? Molestiae, veritatis aperiam harum enim, illo voluptates quam deleniti est accusantium quaerat, et perspiciatis! Fugiat voluptas earum, aut quisquam, ea tempore numquam, vitae laboriosam ab eius deserunt.</p>
            </div>
          </transition>
        </div>
        
        <div class="contacts" key="contacts" v-if="isContacts">
          <transition appear name="header">
            <div class="home__header">CONTACTS</div>
          </transition>
          <transition appear name="content">
            <p class="home__content">Tomsk <br> Lenina, 1 <br> 8-800-10-20-333</p>
          </transition>
        </div>
      </transition>
    </main>
  </div>
</template>

<script>


export default {
  name: 'app',
  data () {
    return {
      isHome: true,
      isAbout: false,
      isGallery: false,
      isContacts: false,
      isLoad: false,
      isAboutWork: false,
      isAboutWork1: false,
      isAboutWork2: false,
      isAboutWork3: false,
      isAboutWork4: false,
      isAboutWork5: false,
      isAboutWork6: false,
      isAboutWork7: false,
      isAboutWork8: false,
      isAboutWork9: false
    }
  },
  mounted() {
    setTimeout(() => {
      this.isLoad = true;
      console.log(this.isLoad);
    }, 2000);
  },
  methods: {
    choseHome() {
      this.isAbout = false;
      this.isGallery = false;
      this.isContacts = false;
      setTimeout(() => {
        this.isHome = true;
      }, 500);
    },
    choseAbout() {
      this.isHome = false;
      this.isGallery = false;
      this.isContacts = false;
      setTimeout(() => {
        this.isAbout = true;
      }, 500);
    },
    choseGallery() {
      this.isHome = false;
      this.isAbout = false;
      this.isContacts = false;
      setTimeout(() => {
        this.isGallery = true;
      }, 500);
      setTimeout(() => {
        this.isAboutWork = false;
        
      }, 1000);
      this.isAboutWork1 = false;
      this.isAboutWork2 = false;
      this.isAboutWork3 = false;
      this.isAboutWork4 = false;
      this.isAboutWork5 = false;
      this.isAboutWork6 = false;
      this.isAboutWork7 = false;
      this.isAboutWork8 = false;
      this.isAboutWork9 = false;
    },
    choseContacts() {
      this.isHome = false;
      this.isAbout = false;
      this.isGallery = false;
      setTimeout(() => {
        this.isContacts = true;
      }, 500);
    },
    choseWork1() {
      this.isAboutWork = true;
      this.isAboutWork1 = true;
    },
    choseWork2() {
      this.isAboutWork = true;
      this.isAboutWork2 = true;
    },
    choseWork3() {
      this.isAboutWork = true;
      this.isAboutWork3 = true;
    },  
    choseWork4() {
      this.isAboutWork = true;
      this.isAboutWork4 = true;
    },  
    choseWork5() {
      this.isAboutWork = true;
      this.isAboutWork5 = true;
    },  
    choseWork6() {
      this.isAboutWork = true;
      this.isAboutWork6 = true;
    },  
    choseWork7() {
      this.isAboutWork = true;
      this.isAboutWork7 = true;
    },  
    choseWork8() {
      this.isAboutWork = true;
      this.isAboutWork8 = true;
    },  
    choseWork9() {
      this.isAboutWork = true;
      this.isAboutWork9 = true;
    },    
  }
}

</script>

<style lang="scss">

@import url('https://fonts.googleapis.com/css?family=Caveat');

* {
  margin: 0;
  box-sizing: border-box;
}

#app {
  width: 100%;
  height: 100vh;
  background:#130f40;
  overflow: hidden;
  font-family: 'Caveat', cursive;
}

.preloader {
  width: 100%;
  height: 100vh;
  background: #30336b;
  display: flex;
  justify-content: center;
  align-items: center;
}

.bar-wrapper {
  width: 75px;
  height: 150px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.bar {
  width: 15px;
  height: 80px;
  background: #fff;
  animation: preload .5s infinite;
}

.reverse {
  animation: preload .5s infinite reverse;
}


.menu {
  width: 100%;
  height: 100px;
}

.menu ul {
  height: 100%;
  display: flex;
  justify-content: space-around;
  list-style: none;
  align-items: center;
}

.menu__item a {
  text-decoration: none;
  color: white;
  font-size: 50px;
}

.menu__itemborder {
  border-bottom: 2px solid #fff;
}

.main {
  width: 100%;
  height: calc(100vh - 102px);
  display: flex;
  justify-content: center;
  align-items: center; 
}

.home,
.about,
.gallery,
.contacts {
  width: calc(100% - 30px);
  height: calc(100% - 30px);
  font-size: 100px;
  color: white;
  background: #30336b;
  position: relative;
  overflow: auto;
}


.home::-webkit-scrollbar,
.about::-webkit-scrollbar,
.gallery::-webkit-scrollbar,
.contacts::-webkit-scrollbar { 
  width: 0; 
}


.home,
.about,
.gallery,
.contacts { 
  -ms-overflow-style: none; 
}


.home,
.about,
.gallery,
.contacts { 
  overflow: -moz-scrollbars-none; 
}

.home__header {
  position: relative;
  text-align: center;
  top: 3%;
  left: 50%;
  transform: translateX(-50%);
}

.home__content {
  font-size: 50px;
  margin-top: 70px;
  text-align: center;
}

.works-wrapper {
  width: 95%;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin: 30px auto;
}

.work {
  width: 32%;
  height: 300px;
  background-size: cover;
  margin: 10px;
  position: relative;
  cursor: pointer;
}

.work::after {
  content: '';
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background: rgba(17, 13, 59, 0.2);
}



.work-1 {
  background: url('assets/cat1.jpg') no-repeat center;
}
.work-2 {
  background: url('assets/cat2.jpg') no-repeat center;
}
.work-3 {
  background: url('assets/cat3.jpg') no-repeat center;
}
.work-4 {
  background: url('assets/cat4.jpg') no-repeat center;
}
.work-5 {
  background: url('assets/dog1.jpg') no-repeat center;
}
.work-6 {
  background: url('assets/dog2.jpg') no-repeat center;
}
.work-7 {
  background: url('assets/dog3.jpg') no-repeat center;
}
.work-8 {
  background: url('assets/dog4.jpg') no-repeat center;
}
.work-9 {
  background: url('assets/gopher1.jpg') no-repeat center;
}

.header-enter-active {
  transition: all 1s;
  transition-delay: .5s;
}
.header-leave-active {
  transition: all .5s;
  
}

.header-enter {
  top: 50%;
}

.header-leave-to {
  opacity: 0;
}

.content-enter-active {
  transition: all 1s;
  transition-delay: 1.5s;
}

.content-enter {
  opacity: 0;
}

.slide-fade-enter-active {
  transition: all .5s;
}

.slide-fade-leave-active {
  transition: all .5s;
}

.slide-fade-enter, .slide-fade-leave-to {
  transform: scaleY(0);
  opacity: 0;
}

.preloader-fade-leave-active {
  transition: all 1s;
}

.preloader-fade-leave-to {
  opacity: 0;
}

.about-work-enter-active {
  transition: all 1s;
  transition-delay: 1s;
}

.about-work-leave-active {
  transition: all 1s; 
}

.about-work-enter, .about-work-leave-to {
  opacity: 0;
}

.about-work .work {
  width: 40%;
  height: 400px;
  float: left;
}

.about-work-content {
  font-size: 40px;
  width: 95%;
  text-align: justify;
}

@keyframes preload {
  0% {
    transform: scaleY(.5);
  }
  50% {
    transform: scaleY(1);
  }
  100% {
    transform: scaleY(.5);
  }
}

@media screen and (max-width: 1600px) {
  .work { width: 45%; }
}

@media screen and (max-width: 1000px) {
  .work { width: 95%; height: 500px; }
  .about-work { display: flex; flex-direction: column; align-items: center; }
  .about-work .work { width: 95%; height: 500px; }
}




</style>
