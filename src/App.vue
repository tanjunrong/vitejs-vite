<script>
import HelloWorld from './components/HelloWorld.vue';
import HtmlTest from './components/HtmlTest.vue';
import VueTest1 from './components/VueTest1.vue';
import NotFound from './components/NotFound.vue';

const routes = {
  '/': HelloWorld,
  '/hello-world': HtmlTest,
  '/vue-test1': VueTest1,
};
export default {
  data() {
    return {
      currentPath: window.location.hash,
    };
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound;
    },
  },
  mounted() {
    window.addEventListener('hashchange', () => {
      this.currentPath = window.location.hash;
    });
  },
};
</script>

<template>
  <a href="#/">App</a> | <a href="#/hello-world">HelloWorld</a> |
  <a href="#/vue-test1">VueTest1</a> |
  <a href="#/non-existent-path">Broken Link</a>
  <component :is="currentView" />

  <p>123</p>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" />
  <div>
    <!-- <HtmlTest /> -->
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
