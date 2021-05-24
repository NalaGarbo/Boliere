<template>
  <div class="card-services">
    <div class="icon">
      <img :src="require(`~/assets/icons/${icon}.png`)" class="icon">
    </div>
    <p class="title-card-services">
      {{ title }}
    </p>
    <p class="card-services-text">
      {{ copy }}
    </p>
  </div>
</template>
<script>
export default {
  name: 'CardPrestation',
  props: {
    title: { type: String, default: 'Card Title' },
    copy: { type: String, default: 'This is the card default description.' },
    icon: { type: String, default: 'CardPNG' }
  }
}
</script>
<style>
.card-services {
   width: 200px;
   height: 180px;
   background-color: #ffffffa1;
   margin: 10px;
   border-radius: 10px;
   box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.24);
   border: 2px solid rgba(7, 7, 7, 0.12);
   font-size: 16px;
   transition: all 0.3s ease;
   position: relative;
   display: block;
   justify-content: center;
   align-items: center;
   cursor: pointer;
   transition: all 0.3s ease;
}

.icon {
   margin: 0 auto;
   width: 100%;
   height: 70px;
   max-width:80px;
   display: flex;
   justify-content: center;
   align-items: center;
   transition: all 0.8s ease;
   background-position: 0px;
}

.title-card-services {
  font-weight: bold;
  color: black;
}

.title-card-services {
  margin-top: 25px;
}

.card-services .card-services-text {
   width: 80%;
   margin: 0 auto;
   font-size: 13px;
   text-align: center;
   margin-top: 20px;
   color: rgb(0, 0, 0);
   font-weight: 200;
   letter-spacing: 2px;
   opacity: 0;
   max-height:0;
   transition: all 0.3s ease;
}

.card-services:hover .card-services-text {
   transition: all 0.3s ease;
   opacity: 1;
   max-height:40px;
}
.card-services:hover .icon, .card-services-text {
  transition: all 0.3s ease;
  margin-top: 0px;
}
.card-services:hover:hover {
   height: 230px;
}
</style>
