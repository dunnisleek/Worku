<template>
  <section>
    <div>
      <router-link to="/">
        <img src="@/assets/worku..svg" />
      </router-link>
    </div>
    <div>
      <router-link to="/" class="hideMobile">Home</router-link>
      <router-link to="/features" class="hideMobile">Features</router-link>
      <router-link to="" class="hideMobile">Contact</router-link>
      <router-link to="" class="hideMobile">Help</router-link>
      <router-link to="">
        <button class="hideMobile">Login</button>
      </router-link>
      <router-link to="" @click="showSidebar"
        ><img
          src="../assets/featuresImages/menu_FILL0_wght400_GRAD0_opsz24.svg"
          width="30"
          class="hideicon"
      /></router-link>
    </div>
  </section>

  <nav v-show="display">
    <router-link to="" @click="closeIcon"
      ><img
        src="../assets/featuresImages/close_FILL0_wght400_GRAD0_opsz24.svg"
        class="hideicon closeicon"
    /></router-link>
    <div>
      <router-link to="/">Home</router-link>
      <router-link to="/features">Features</router-link>
      <router-link to="">Contact</router-link>
      <router-link to="">Help</router-link>
      <router-link to="">
        <button>Login</button>
      </router-link>
    </div>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      display: false,
    };
  },
  methods: {
    showSidebar() {
      this.display = true;
    },
    closeIcon() {
      this.display = false;
    },
  },
};
</script>

<style scoped>
a {
  color: #fff;
  margin-right: 30px;
  text-decoration: none;
  font-size: 17px;
}
a:hover {
  color: #e0ff00;
}
section {
  top: 11px;
  display: flex;
  width: 90%;
  /* height:10vh; */
  gap: 31rem;
  font-family: "Inter", sans-serif;
  align-items: center;
  max-width: 90%;
  justify-content: center;
  background: transparent;
  position: absolute;
  z-index: 4;
}
button {
  font-size: 17px;
  padding: 8px 25px;
  border-radius: 5px;
  border: none;
  text-transform: capitalize;
}
button:hover {
  background: #e0ff00;
}
/* START OF MOBILE MENU */
nav {
  position: fixed;
  top: 0;
  right: 0;
  backdrop-filter: blur(30px);
  height: auto;
  width: 250px;
  height: 100vh;
  z-index: 999;
  display: none;
}

nav a {
  width: 100%;
  color: #ffffff;
  display: flex;
  flex-direction: column;
  padding: 10px 20px;
}
nav a:hover {
  background: #fff;
  color: #232323;
}
nav img {
  background: #232323;
  width: 100%;
  width: 150px;
}
.hideicon {
  display: none;
}

@media screen and (max-width: 800px) {
  section {
    gap: 12rem;
  }
  nav {
    display: block;
  }
  .hideMobile {
    display: none;
  }
  .hideicon {
    display: block;
    background: #fff;
  }
  .closeicon {
    width: 30px;
    color: white;
    background: #fff;
    display: flex;
    justify-content: flex-end;
    position: relative;
    left: 80%;
  }
  button {
    width: 45%;
  }
  section {
    gap: 9rem;
    left: 0;
  }
}
@media screen and (max-width: 768px) {
  section {
    gap: 29rem;
  }
  nav {
    width: 350px;
  }
}
@media screen and (max-width: 1024px) {
  section {
    top: 11px;
    left: 5%;
    display: flex;
    width: 95%;
    gap: 0rem;
    justify-content: space-between;
    /* gap:12rem; 
    */
  }
}
/* @media screen and(max-width:1024px){
       section{
              width:100%;
              gap:0rem !important;
       }
} */

@media screen and (max-width: 540px) {
  section {
    gap: 45%;
    width: 100%;
  }
}
@media screen and (max-width: 360px) {
  section {
    gap: 10rem;
  }
}
</style>
