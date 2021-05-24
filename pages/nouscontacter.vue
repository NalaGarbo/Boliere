<template>
  <div class="container">
    <div>
      <div>
        <h3 class="subtitle">
          Nous contacter
        </h3>
      </div>
      <div class="contains-text">
        <p>
          Les réponses les plus rapides aux questions les plus simples vous seront données par notre assistant virtuel Willy. <br>
          Si jamais il ne peut vous répondre, il vous renverra automatiquement vers nous. <br><br>
          Vous pouvez bien entendu nous contacter par mail pour toute information complémentaire ou prise de rendez-vous.
        </p>
        <div class="contact-form">
          <contact-form />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ContactForm from '~/components/ContactForm.vue'
export default {
  components: { ContactForm }

}
</script>
<style>
.contact-form {
  padding-top: 50px;
}
</style>
