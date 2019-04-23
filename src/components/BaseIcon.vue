<template>
  <div class="icon-wrapper">
    <svg class="icon" :width="80" :height="30">
      <use v-bind="{'xlink:href':'/feather-sprite.svg#circle'}"></use>
    </svg>
    <slot></slot>
  </div>
</template>

<script>
export default {}
</script>