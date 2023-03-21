<script setup>
useHead({
  title: "Camaras de surf en vivo - Buscaolas",
  meta: [
    {
      hid: "description",
      name: "description",
      content: "Camaras de surf en las principales playas de Chile",
    },
    {
      hid: "og:title",
      name: "og:title",
      content: "Buscaolas - camaras en vivo en las principales playas",
    },
    {
      hid: "og:description",
      name: "og:description",
      content: "Camaras de surf en las principales playas de Chile",
    },
    {
      hid: "og:url",
      name: "og:url",
      content: "https://buscaolas.cl",
    },
  ],
});
const ArticuloData = await useFetch("/api/main/home");
// const art = ArticuloData.articulos1.slice(0, 3);
const alert = false;
</script>


<template>
  <div class="overflow-x-hidden">
    <client-only>
      <Header />
      <Detect />
    </client-only>
    <Footer />
  </div>
</template>



<style lang="scss" scoped>
.video-container {
  position: relative;
  padding-bottom: 56.25%;
  padding-top: 30px;
  height: 0;
  overflow: hidden;
}

.video-container iframe,
.video-container object,
.video-container embed {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>