<template>
  <main>
    <h1>Contact</h1>
    <p style="font-size : 3rem; color : green">Random joke : {{ joke }}</p>
  </main>
</template>

<script>
export default {
  async asyncData({ params, $http }) {
    const res = await fetch(`https://icanhazdadjoke.com/`, {
      method: "GET",
      headers: { accept: "application/JSON" }
    });
    const { joke } = await res.json();
    return { joke };
  }
};
</script>
