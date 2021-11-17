<template>
  <h1>Component Y</h1>
</template>

<script>
export default {
  name: "ComponentY",
  unmounted() {
    console.log('... Component Y is unmounted ...')
  },
  activated() {
    console.log('... Component Y is activated ...')
  },
  deactivated() {
    console.log('... Component Y is deactivated ...')
  },

}
</script>
