<template>
  <div class="arrow">
    <div class="arrow-top" />
    <div class="arrow-bottom" />
  </div>
</template>
<script>
export default {
}
</script>
<style lang="scss">

.arrow {
  cursor: pointer;
  height: 50px;
  transform: translateY(150%);
  transition: transform .1s;
  width: 50px;

  $transition-time: .15s;

  &-top,
  &-bottom {
    background-color: #666;
    height: 4px;
    left: -5px;
    position: absolute;
    top: 50%;
    width: 100%;

    &:after {
      background-color: #fff;
      content: '';
      height: 100%;
      position: absolute;
      top: 0;
      transition: all $transition-time;
    }
  }

  &-top {
    transform: rotate(45deg);
    transform-origin: bottom right;

    &:after {
      left: 100%;
      right: 0;
      transition-delay: 0s;
    }
  }

  &-bottom {
    transform: rotate(-45deg);
    transform-origin: top right;

    &:after {
      left: 0;
      right: 100%;
      transition-delay: $transition-time;
    }
  }

  &:hover & {

    &-top:after {
      left: 0;
      transition-delay: $transition-time;
    }

    &-bottom:after {
      right: 0;
      transition-delay: 0s;
    }
  }
}
</style>
