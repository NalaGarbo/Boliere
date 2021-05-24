<template>
  <div class="background_image container-accueil">
    <div>
      <a href="#accueil"><img src="~/assets/img/logo.png" class="logo"></a>
      <h1 class="title">
        boliere
      </h1>

      <h3 class="subtitle agence-title">
        Agence Web @Marseille
      </h3>

      <animated-links-exp />
    </div>
  </div>
</template>
<script>
import AnimatedLinksExp from '~/components/AnimatedLinksExp.vue'
export default {
  components: { AnimatedLinksExp }

}
</script>
<style>
.container-accueil {
  display: flex;
  margin: 0 auto;
  min-height: 100vh;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: white;
}
.background_image{
    background-image: url('~assets/img/bg_raw.jpg');
    background-attachment: fixed;
    background-size: cover;
    background-repeat: no-repeat;
    height: 100vh;
    width: 100vw;
}

.logo {
  position: fixed;
  top: 3%;
  left: 3%;
  --size: calc(1rem + 3vmin);
  width: var(--size);
  height: var(--size);
  z-index: 1;
}

.agence-title {
  text-decoration: none;
}
</style>
