<template>
  <header>
    <h1>infinite scroll</h1>
  </header>
  <main>
    <Post v-for="(anime, i) in anime_list" :key="i" :anime="anime" />
  </main>
</template>

<script>
import Post from "./components/Post.vue";
export default {
  name: "App",
  components: {
    Post,
  },
  data() {
    return {
      anime_list: [],
    };
  },
  methods: {
    getAnime() {
      const anime_titles = [
        "ronaldo",
        "bale",
        "isco",
        "varane",
        "roberto",
        "hernandes",
        "podolski",
        "overmars",
        "rooney",
        "hagi",
        "popescu",
      ];
      const anime = [];

      for (let i = 0; i < 10; i++) {
        anime.push({
          title: anime_titles[Math.floor(Math.random() * anime_titles.length)],
          decription:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Perferendis magni, labore sunt reprehenderit ad sint natus. Fugit tempore inventore tenetur!",
        });
      }
      return anime;
    },
    handleScroll() {
      if (
        window.scrollY + window.innerHeight >=
        document.body.scrollHeight - 50
      ) {
        this.anime_list = [...this.anime_list, ...this.getAnime()];
      }
    },
  },
  mounted() {
    this.anime_list = this.getAnime();
    window.addEventListener("scroll", this.handleScroll);
  },
};
</script>

<style>
* {
  margin: 0;
  /* padding: 0; */
  box-sizing: border-box;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  min-height: 100vh;
  padding-top: 3rem;
  /* border: 1px solid black; */
  background-image: radial-gradient(
    circle farthest-corner at 10% 20%,
    rgba(14, 174, 87, 1) 0%,
    rgba(12, 116, 117, 1) 90%
  );
}
header h1 {
  text-align: center;
}
header {
  margin-bottom: 2rem;
}
main {
  padding: 0 2rem;
  max-width: 640px;
  margin: 0 auto;
}
</style>
