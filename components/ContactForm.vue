<template>
  <div class="form-box">
    <h4>Formulaire de contact</h4>
    <form>
      <div class="user-box">
        <input id="object" type="text" name="object" required>
        <label>Objet du message</label>
      </div>
      <div class="user-box">
        <textarea id="message" name="message" cols="60" rows="4" required />
        <label>Votre message</label>
      </div>
      <a @click="sendMail">
        <span />
        <span />
        <span />
        <span />
        Envoyer
      </a>
    </form>
  </div>
</template>
<script>
export default {
  methods: {
    sendMail () {
      const mailObject = document.querySelector('#object').value
      const mailMessage = document.querySelector('#message').value
      window.open(`mailto:boliere.corp@gmail.com?subject=${mailObject}&body=${mailMessage}`)
    }
  }
}
</script>
<style>
textarea {
    font-family: 'Noto Serif TC', serif;
}
.form-box {
  display: inline-block;
  width: 80vw;
  padding: 40px;
  background: rgba(32, 32, 32, 0.6);;
  box-shadow: 0 15px 25px rgba(20, 20, 20, 0.6);
  border-radius: 10px;
}

@media screen and (min-width: 800px) {
    .form-box {
        width: 70vw;
    }
}
@media screen and (min-width: 1000px) {
    .form-box {
        width: 60vw;
    }
}
@media screen and (min-width: 1200px) {
    .form-box {
        width: 50vw;
    }
}
.form-box h4 {
  margin: 0 0 30px;
  padding: 0;
  color: #fff;
  text-align: center;
}

.form-box .user-box {
  position: relative;
}

.form-box .user-box input,
.form-box .user-box textarea {
  width: 100%;
  padding: 10px 0;
  color: #fff;
  margin-bottom: 30px;
  border: none;
  border-bottom: 1px solid #fff;
  outline: none;
  background: transparent;
}

.form-box .user-box label {
  position: absolute;
  top:-20px;
  left: 0;
  padding: 10px 0;
  font-size: clamp(0.75rem, 1.3vw, 1.5rem);
  color: #fff;
  pointer-events: none;
  transition: .5s;
}

.form-box .user-box input:focus ~ label,
.form-box .user-box input:valid ~ label {
  top: -40px;
  left: 0;
  color: #005f82e8;
}

.form-box .user-box textarea:focus ~ label,
.form-box .user-box textarea:valid ~ label {
  top: -20px;
  left: 0;
  color: #005f82e8;
}

@media screen and (min-width: 700px) {
  .form-box .user-box textarea:focus ~ label,
  .form-box .user-box textarea:valid ~ label {
  top: -25px;
  left: 0;
  color: #005f82e8;
}
}
@media screen and (min-width: 900px) {
  .form-box .user-box textarea:focus ~ label,
  .form-box .user-box textarea:valid ~ label {
  top: -30px;
  left: 0;
  color: #005f82e8;
}
}
@media screen and (min-width: 1100px) {
  .form-box .user-box textarea:focus ~ label,
  .form-box .user-box textarea:valid ~ label {
  top: -35px;
  left: 0;
  color: #005f82e8;
}
}
@media screen and (min-width: 1280px) {
  .form-box .user-box textarea:focus ~ label,
  .form-box .user-box textarea:valid ~ label {
  top: -40px;
  left: 0;
  color: #005f82e8;
}
}

.form-box form a {
  position: relative;
  display: inline-block;
  padding: 10px 20px;
  color: #005f82e8;
  font-size: clamp(0.75rem, 1.1vw, 1.3rem);
  text-decoration: none;
  text-transform: uppercase;
  overflow: hidden;
  transition: .5s;
  margin-top: 40px;
  letter-spacing: 4px
}

.form-box a:hover {
  background: #005f82e8;
  color: #fff;
}

.form-box a span {
  position: absolute;
  display: block;
}

.form-box a span:nth-child(1) {
  top: 0;
  left: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, #005f82e8);
  animation: btn-anim1 1s linear infinite;
}

@keyframes btn-anim1 {
  0% {
    left: -100%;
  }
  50%,100% {
    left: 100%;
  }
}

.form-box a span:nth-child(2) {
  top: -100%;
  right: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(180deg, transparent, #005f82e8);
  animation: btn-anim2 1s linear infinite;
  animation-delay: .25s
}

@keyframes btn-anim2 {
  0% {
    top: -100%;
  }
  50%,100% {
    top: 100%;
  }
}

.form-box a span:nth-child(3) {
  bottom: 0;
  right: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(270deg, transparent, #005f82e8);
  animation: btn-anim3 1s linear infinite;
  animation-delay: .5s
}

@keyframes btn-anim3 {
  0% {
    right: -100%;
  }
  50%,100% {
    right: 100%;
  }
}

.form-box a span:nth-child(4) {
  bottom: -100%;
  left: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(360deg, transparent, #005f82e8);
  animation: btn-anim4 1s linear infinite;
  animation-delay: .75s
}

@keyframes btn-anim4 {
  0% {
    bottom: -100%;
  }
  50%,100% {
    bottom: 100%;
  }
}

</style>
