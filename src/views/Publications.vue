<template>
  <section>
    <h1>Publications</h1>
    <ul>
      <li v-for="(pub, i) in publications" :key="i">{{ pub }}</li>
    </ul>
  </section>
</template>
  
<script>
export default {
  data() {
    return {
      publications: [
        "論文 A (2023)",
        "論文 B (2022)",
        "論文 C (2021)",
      ],
    };
  },
};
</script>
