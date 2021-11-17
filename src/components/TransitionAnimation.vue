<template>
  <div>
    <button type="button"
            @click="flag = !flag">
      Toggle
    </button>

    <!-- Add animation  -->
    <transition name="fade">
      <h3 v-if="flag">
        Button Clicked!
      </h3>
    </transition>

  </div>
</template>

<script>
export default {
  name: "TransitionAnimation",
  data() {
    return {
      flag: false
    }
  }
}
</script>

<style scoped>
.fade-enter-from {
  opacity: 0;
  color: aqua;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 4s linear;
}

.fade-enter-to {
  opacity: 1;
  color: yellow;
}

.fade-leave-to {
  opacity: 0;
  color: coral;
}


</style>
