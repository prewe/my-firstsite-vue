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
            <div class="home__header">GALLERY</div>
          </transition>
          <transition appear name="content">
            <p class="home__content">...</p>
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
      isLoad: false
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
    },
    choseContacts() {
      this.isHome = false;
      this.isAbout = false;
      this.isGallery = false;
      setTimeout(() => {
        this.isContacts = true;
      }, 500);
    }  
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

.header-enter-active {
  transition: all 1s;
  transition-delay: .5s;
}
.header-leave-active {
  transition: all 1s;
  transition-delay: .5s;
}

.header-enter {
  top: 50%;
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




</style>
