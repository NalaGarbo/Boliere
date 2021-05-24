<template>
  <div class="bandeau-container">
    <div>
      <h3 class="subtitle">
        Notre plan d'action
      </h3>
      <div class="cards-bandeau">
        <div v-for="(card, index) in cards" :key="card.title" class="card-action-container">
          <card-action :id="`card${index}`" :icon="card.icon" :title="card.title" />
          <arrow-hover-comp :id="`arrow${index}`" class="arrows" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ArrowHoverComp from '~/components/ArrowHoverComp.vue'
import CardAction from '~/components/CardAction.vue'
export default {
  components: { CardAction, ArrowHoverComp },
  data () {
    return {
      cards: [
        {
          title: 'Conception',
          icon: 'conception.svg'
        },
        {
          title: 'Planification',
          icon: 'planification.svg'
        },
        {
          title: 'Réalisation',
          icon: 'realisation.svg'
        },
        {
          title: 'Livraison',
          icon: 'livraison.svg'
        },
        {
          title: 'Accompagnement',
          icon: 'accompagnement.svg'
        }
      ]
    }
  },
  mounted () {
    this.hideLastArrow()
  },
  methods: {
    hideLastArrow () {
      document.querySelector('#arrow4').classList.add('hidden_arrow')
      document.querySelector('#card4').classList.add('resize-card')
    }
  }
}

</script>
<style>
.cards-bandeau{
  max-width: 1024px;
  width: 100%;
  padding: 0 4%;
  padding-top: 30px;
  margin: 0 auto;
  display: block;
  justify-content: center;
  align-items: center;
}
.card-action-container {
  display: inline-block;
}
.arrows {
  display: none;
}

@media screen and (min-width: 1150px){
  .arrows {
    display: flex;
  }
  .cards-bandeau{
  display: flex;
}

  .card-action-container {
    display: flex;
    width: 25%;
  }
  .hidden_arrow {
    display: none;
  }
}
</style>
