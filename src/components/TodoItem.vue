<template>
  <li>
    <input type="checkbox"
           v-model="checked">
    <slot name="item"
          v-bind="{checked}"></slot>
  </li>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['item'],
  data () {
    return {
      checked: false
    }
  }
}
</script>

<style>
</style>
