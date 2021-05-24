<template>
  <div class="bandeau-container">
    <div>
      <h3 class="subtitle">
        Nos services
      </h3>
      <div class="cards-bandeau-services">
        <div v-for="card in cards" :key="card.title" class="card-services-container">
          <card-service :title="card.title" :copy="card.description" :icon="card.icon" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import CardService from '~/components/CardService.vue'
export default {
  components: { CardService },
  data () {
    return {
      cards: {
        site_sur_mesure: {
          title: 'Site sur mesure',
          description: 'Votre site à vous, adapté à vos besoins, votre activé.',
          icon: 'sitesurmesure'
        },
        site_vitrine: {
          title: 'Site vitrine',
          description: 'Pour une présentation efficace de votre activité.',
          icon: 'sitevitrine'
        },
        site_e_comerce: {
          title: 'Site e-commerce',
          description: 'Pour une boutique en ligne, dynamique et intéractive.',
          icon: 'siteecommerce'
        },
        seo: {
          title: 'SEO',
          description: 'Un site optimisé pour le référencement naturel Google.',
          icon: 'SEO'
        }
      }
    }
  }
}
</script>
<style>
.bandeau-container {
    display: flex;
    margin: 0 auto;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: rgb(255, 255, 255);
    background-color: #005f82b6;
    padding-top: 2rem;
    padding-bottom: 2rem;
  }

.bandeau-container .subtitle {
  text-decoration-color: white;
}
.cards-bandeau-services {
   max-width: 1024px;
   width: 100%;
   padding: 0 4%;
   padding-top: 30px;
   margin: 0 auto;
   display: block;
   justify-content: center;
   align-items: center;
}
.card-services-container {
  display: inline-block;
}

@media screen and (min-width: 1000px) {
  .cards-bandeau-services {
    display: flex;
  }
  .card-services-container {
    display: flex;
    width: 25%;
  }
}
</style>
