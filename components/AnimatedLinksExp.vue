<template>
  <div class="typewriter">
    <span class="chevrons">&lsaquo;</span>
    <a class="link" href="#nousdecouvrir">
      nous découvrir
    </a>
    <a class="link" href="#nosprestations">
      nos prestations
    </a>
    <a class="link" href="#nouscontacter">
      nous contacter
    </a>
    <span class="chevrons">/&rsaquo;</span>
  </div>
</template>
<script>
export default {

}
</script>
<style lang="scss">
.chevrons {
  display: none;
}
.typewriter{
    overflow: hidden; /* Ensures the content is not revealed until the animation */
    border-right: .15em solid rgb(255, 255, 255); /* The typwriter cursor */
    max-width: 55vw;
    margin: 0 auto; /* Gives that scrolling effect as the typing happens */
    letter-spacing: .15em; /* Adjust as needed */
    animation:
      typing 3.5s steps(40, end),
      blink-caret .75s step-end infinite;
  }
  /* The typing effect */
  @keyframes typing {
    from { width: 0% }
    to { width: 100% }
  }
  /* The typewriter cursor effect */
  @keyframes blink-caret {
    from, to { border-color: transparent }
    50% { border-color: #005F82; }
  }
  .link {
    text-decoration: none;
    color: white;
    display: block;
    background-image: linear-gradient(
      to bottom,
      rgba(255, 255, 255, 0) 50%,
      rgb(255, 255, 255) 50%,
      rgb(255, 255, 255) 60%,
      rgba(255, 255, 255, 0) 60%,
    );
    background-size: 0 100%;
    background-repeat: no-repeat;
    transition: 250ms linear;
  }
  .link:hover {
    background-size: 100% 100%;
  }
@media screen and (min-width: 400px) {
  .typewriter {
    max-width: 42vw;
  }
}

@media screen and (min-width: 1000px){
  .chevrons {
    display: inline;
  }
  .typewriter{
    white-space: nowrap;
    max-width: 100vw;
  }
  .link {
    padding-right: 1rem;
    padding-left: 1rem;
    display: inline;
  }
}
</style>
