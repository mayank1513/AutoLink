<template>
  <a
    href="http://krishna-apps.vercel.app"
    target="_blank"
    rel="noopener noreferrer"
    ><img class="logo" alt="Krishna Apps logo" src="./assets/logo.png"
  /></a>
  <br />
  <h2>Presents</h2>
  <h1>Auto Link</h1>
  <hr />
  <ul id="nav">
    <li v-for="(link, title) in links" :key="link">
      <auto-link :to="link">{{ title }}</auto-link>
    </li>
  </ul>
  <router-view />
</template>

<script>
// import AutoLink from '@mayank1513/auto-link'
import AutoLink from "./components/AutoLink.vue";

export default {
  name: "App",
  data() {
    return {
      links: {
        Home: "/",
        About: "/about",
        Blogs: "https://mayank-1513.medium.com",
        "Vue Crash Course + Guide":
          "https://www.udemy.com/course/vuejs-complete-course-plus-guide/?referralCode=93BDA4A1FE3F73C37CD2",
        "Vue 3 Essentials":
          "https://www.udemy.com/course/vue-3-essentials/?referralCode=E6D2FDE2B8B06C1991F1",
      },
    };
  },
  components: {
    AutoLink,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  max-width: 1400px;
  margin: auto;
}
#nav {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  list-style: none;
}

#nav li {
  margin: 20px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
