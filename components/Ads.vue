<script setup>
</script>

<template>
  <div class="mt-6">
    <div class="lg:w-9/12 mx-auto lg:flex go-premium-banner p-10" v-if="premium">
      <div class="heading mb-8 lg:mb-0 font-bold uppercase text-center lg:text-left">
        Con premium puedes ver hasta 7 dias de pronostico.
      </div>
      <div class="mx-auto">
        <NuxtLink to="/premium">
          <button class="go-premium text-white uppercase rounded-sm font-bold block mx-auto lg:mt-8 mb-5">
            hazte premium
          </button>
        </NuxtLink>
        <div class="text text-center">
          Prueba 14 dias gratis y disfruta de los multiples beneficios de premium
        </div>
      </div>
    </div>
    <div class="lg:w-9/12 mx-auto lg:flex go-premium-banner" v-if="!premium">
      <a :href="ads_info.url_basic" v-on:click="track(ads_info.id, ads_info.clicks)">
        <img :src="ads_info.ads_url" alt="" class="">
      </a>
    </div>
  </div>
</template>

<style>
</style>