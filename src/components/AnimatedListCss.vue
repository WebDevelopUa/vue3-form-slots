<template>
  <div>
    <h2>Animate.css</h2>

    <button type="button"
            @click="addItem"
    >
      Add +
    </button>
    <ul>
      <!-- Apply Animate.css classes   -->
      <!--      enter-from-class=""  -->
      <!--      enter-active-class=""  -->
      <!--      enter-to-class=""  -->
      <!--      leave-from-class=""  -->
      <!--      leave-active-class=""  -->
      <!--      leave-to-class=""  -->

      <transition-group name="fade"
                        enter-active-class="animate__animated animate__flipInX"
                        leave-active-class="animate__animated animate__backOutRight"
      >
        <li v-for="(number, index) in numbers"
            :key="number"
            @click="removeItem(index)"
        >
          {{ number }}
        </li>
      </transition-group>

    </ul>
  </div>
</template>

<script>
export default {
  name: "AnimatedListCss",
  data() {
    return {
      numbers: [100, 200, 300, 400, 500]
    }
  },
  methods: {
    addItem() {
      const num = Math.floor(Math.random() * 100 + 1)
      const index = Math.floor(Math.random() * this.numbers.length)
      this.numbers.splice(index, 0, num)
    },
    removeItem(index) {
      this.numbers.splice(index, 1)
    }
  }
}
</script>

<style scoped>
.animate__backOutRight,
.animate__flipOutX {
  position: absolute;
}

.animate__animated.animate__flipOutX {
  animation-duration: 1.5s;
}

.animate__animated.animate__backOutRight {
  animation-duration: 5s;
}

.fade-leave-to,
.fade-enter-from {
  font-weight: bold;
  color: crimson;
}

.fade-leave-active {
  position: absolute;
}

.fade-leave-from,
.fade-enter-to {
  color: lawngreen;
  font-weight: bold;
}

.fade-move {
  transition: all 1s linear;
}
</style>
