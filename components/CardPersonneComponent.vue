<template>
  <div>
    <div class="card-content">
      <div class="card-component">
        <div class="content">
          <h2 class="titleCard">
            {{ name }}
          </h2>
          <p class="copy">
            {{ description }}
          </p>
          <a class="btn-card-person" :href="link" target="_blank">
            {{ buttonName }}
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    name: {
      type: String, default: 'Ekip'
    },
    description: {
      type: String, default: 'Here goes nothing!'
    },
    buttonName: {
      type: String, default: 'Default copy'
    },
    link: {
      type: String, default: 'https://www.google.fr'
    }
  }
}
</script>
<style lang="scss">

:root {
  --d: 700ms;
  --e: cubic-bezier(0.19, 1, 0.22, 1);
  --font-sans: 'Noto Serif TC';
  --font-serif: 'Noto Serif';
}

.card-content {
  position: relative;
  display: grid;
  grid-gap: 1rem;
  justify-content: center;
  padding: 1rem;
  max-width: 1024px;
  font-family: var(--font-sans);
}

.card-component {
  position: relative;
  height: 60vh;
  width: 50vw;
  display: flex;
  align-items: flex-end;
  overflow: hidden;
  padding: 1rem;
  text-align: center;
  color: rgb(255, 255, 255);
  background-color: whitesmoke;
  box-shadow: 0 1px 1px rgba(0,0,0,0.1),
    0 2px 2px rgba(0,0,0,0.1),
    0 4px 4px rgba(0,0,0,0.1),
    0 8px 8px rgba(0,0,0,0.1),
    0 16px 16px rgba(0,0,0,0.1);

  &:before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 110%;
    background-size: cover;
    background-position: 0 0;
    transition: transform calc(var(--d) * 1.5) var(--e);
    pointer-events: none;
  }

  &:after {
    content: '';
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 200%;
    pointer-events: none;
    background-image: linear-gradient(
      to bottom,
      hsla(0, 0%, 0%, 0) 0%,
      hsla(0, 0%, 0%, 0.009) 11.7%,
      hsla(0, 0%, 0%, 0.034) 22.1%,
      hsla(0, 0%, 0%, 0.072) 31.2%,
      hsla(0, 0%, 0%, 0.123) 39.4%,
      hsla(0, 0%, 0%, 0.182) 46.6%,
      hsla(0, 0%, 0%, 0.249) 53.1%,
      hsla(0, 0%, 0%, 0.320) 58.9%,
      hsla(0, 0%, 0%, 0.394) 64.3%,
      hsla(0, 0%, 0%, 0.468) 69.3%,
      hsla(0, 0%, 0%, 0.540) 74.1%,
      hsla(0, 0%, 0%, 0.607) 78.8%,
      hsla(0, 0%, 0%, 0.668) 83.6%,
      hsla(0, 0%, 0%, 0.721) 88.7%,
      hsla(0, 0%, 0%, 0.762) 94.1%,
      hsla(0, 0%, 0%, 0.790) 100%
    );
    transform: translateY(-50%);
    transition: transform calc(var(--d) * 2) var(--e);
  }
    background: center;
    background-size: cover;
    background-repeat: no-repeat;
    }
  @media screen and (min-width: 768px) {
    .card-component {
      width: 40vw;
      border-radius: 5%;
  }
  }
  @media screen and (min-width: 850px) {
    .card-component {
      height: 60vh;
      width: 40vw;
    }
  }

  @media screen and (min-width: 1000px) {
    .card-component {
      width: 35vw;
    }
  }

  @media screen and (min-width: 1150px) {
    .card-component {
      width: 30vw;
    }
  }

  @media screen and (min-width: 1450px) {
    .card-component {
      width: 25vw;
    }
  }

.content {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  padding: 1rem;
  transition: transform var(--d) var(--e);
  z-index: 1;

  > * + * {
    margin-top: 1rem;
  }
}

.titleCard {
  font-size: 1.3rem;
  font-weight: bold;
  line-height: 1.2;
}

.copy {
  font-family: var(--font-serif);
  font-size: 0.6rem;
  font-style: italic;
  line-height: 1.35;
  word-break: break-word;
}

.btn-card-person {
  cursor: pointer;
  margin-top: 1.5rem;
  padding: 0.75rem 1.5rem;
  font-size: 0.65rem;
  font-weight: bold;
  letter-spacing: 0.025rem;
  text-transform: uppercase;
  color: white;
  background-color: #005f82b6;
  border: none;
  text-decoration: none;

  &:hover {
    background-color: lighten(#005f82b6, 5%);
  }

  &:focus {
    outline-offset: 3px;
  }
}

@media (hover: hover) {
  .card-component:after {
    transform: translateY(0);
  }

  .content {
    transform: translateY(calc(100% - 4.5rem));

    > *:not(.titleCard) {
      opacity: 0;
      transform: translateY(1rem);
      transition:
        transform var(--d) var(--e),
        opacity var(--d) var(--e);
    }
  }

  .card-component:hover,
  .card-component:focus-within {
    align-items: center;

    &:before { transform: translateY(-4%); }
    &:after { transform: translateY(-50%); }

    .content {
      transform: translateY(0);

      > *:not(.titleCard) {
        opacity: 1;
        transform: translateY(0);
        transition-delay: calc(var(--d) / 8);
      }
    }
  }

  .card-component:focus-within {
    &:before,
    &:after,
    .content,
    .content > *:not(.titleCard) {
      transition-duration: 0s;
    }
  }
}

</style>
