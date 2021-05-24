<template>
  <div class="container">
    <div>
      <div>
        <h3 class="subtitle">
          Nous découvrir
        </h3>
      </div>
      <div class="contains-text">
        <p>
          Deux alternants, de la passion, une technologie de pointe en vogue et un désir ardent de concret. <br>
          Une formation hybride, des techniques de gestion de projet simples et qualitatives pour un résultat : Bolière. <br>
          Agence Web basée à Marseille et La Ciotat, fruit d’une collaboration forte et complémentaire, Bolière saura accompagner la création de votre projet Web avec sérieux et professionnalisme.
        </p>
      </div>
      <div class="card-container">
        <div class="facecard">
          <card-personne-component id="alan" :name="nala.name" :description="nala.description" :button-name="nala.button" :link="nala.link" />
        </div>
        <div class="vertical_line" />
        <div class="facecard">
          <card-personne-component id="sammy" :name="sammy.name" :description="sammy.description" :button-name="sammy.button" :link="sammy.link" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import CardPersonneComponent from '~/components/CardPersonneComponent.vue'
export default {
  components: { CardPersonneComponent },
  data () {
    return {
      nala: {
        name: 'Alan',
        description: `Ce choix de l'auto-entreprise est motivé par mon désir de proposer du concret après les années de théorie.
        N’hésitez pas à visiter mon site!`,
        button: 'Le CV d\'Alan',
        link: 'https://alangarbo.com'
      },
      sammy: {
        name: 'Samuel',
        description: `L'expérience freelance est pour moi l'occasion parfaite pour développer une expertise.
        Mon C.V vous en diras plus sur moi!`,
        button: 'Le CV de Samuel',
        link: 'https://samuelgaliere.com'
      }
    }
  }
}
</script>
<style>
.card-container {
  padding-top: 80px;
}
.facecard {
  width: 100%;
}
.vertical_line {
  display: none;
}
#alan .card-component {
  background-image: url('~assets/img/alan2021.jpg');
}
#sammy .card-component {
  background-image: url('~assets/img/samuel_pic_final.jpg');
}

@media screen and (min-width: 768px) {
.card-container {
  display: flex;
}
.facecard {
  width: 100%;
}
.vertical_line {
  display: block;
  border-right: 3px solid #005F82;
  height: 67vh;
}
#alan .card-content {
  margin-right: 2rem;
}
#sammy .card-content {
  margin-left: 2rem;
}
}

@media screen and (min-width: 850px) {
  #alan .card-content {
    margin-right: 1rem;
  }
  #sammy .card-content {
    margin-left: 1rem;
  }
}

@media screen and (min-width: 1000px) {
  #alan .card-content {
    margin-right: 2rem;
  }
  #sammy .card-content {
    margin-left: 2rem;
  }
}

@media screen and (min-width: 1150px) {
  #alan .page-content {
    margin-right: 3rem;
  }
  #sammy .page-content {
    margin-left: 3rem;
  }
}

@media screen and (min-width: 1380px) {
  #alan .page-content {
    margin-right: 4rem;
  }
  #sammy .page-content {
    margin-left: 4rem;
  }
}
</style>
