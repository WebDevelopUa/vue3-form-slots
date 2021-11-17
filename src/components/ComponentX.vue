<template>
  <h1>Component X</h1>
</template>

<script>
export default {
  name: "ComponentX",
  unmounted() {
    console.log('... Component X is unmounted ...')
  },
  activated() {
    console.log('... Component X is activated ...')
  },
  deactivated() {
    console.log('... Component X is deactivated ...')
  },

}
</script>

