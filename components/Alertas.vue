<template>
  <div>
    <div class="lg:w-9/12 mx-auto lg:my-4 error-bg panel w-full text-white rounded-sm uppercase my-0 h-10" v-if="alert">
      <span class="flex items-center justify-center mx-auto text-sm-1 ">
        <span class="font-bold lg:font-normal" v-html="alertas[0].alerta"> </span>
      </span>
    </div>
  </div>
</template>

<script >
  export default {
    data () {
      return {
        alertas: null,
        alert: false
      }
    },
    async fetch(){
      const DataAlerta = await this.$axios.$get("/api/main/alertas");
      this.alertas = DataAlerta
      if (this.alertas.length > 0) {
        this.alert = true
      } 
    }
  }
</script>

<style scoped>
  .error-bg {
    background-color: #C8142E;
  }
  .warning-bg {
    background-color: #FFA800;
  }
</style>