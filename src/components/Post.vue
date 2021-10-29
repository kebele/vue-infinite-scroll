<template>
  <div>
    <article>
      <h2>{{ anime.title }}</h2>
      <p>
        {{ anime.decription }}
      </p>
    </article>
  </div>
</template>

<script>
export default {
  props: ["anime"],
};
</script>

<style scoped>
article {
  background-image: linear-gradient(
    109.6deg,
    rgba(118, 12, 99, 1) 11.2%,
    rgba(71, 11, 75, 1) 98.6%
  );
  border-radius: 1rem;
  padding: 1rem 2rem;
  margin-bottom: 2rem;
  color: whitesmoke;
  font-weight: 600;
}
.article h2 {
  margin-bottom: 2rem;
}
</style>
