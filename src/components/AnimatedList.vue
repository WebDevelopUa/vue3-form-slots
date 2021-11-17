<template>
  <div>
    <h2>Animated list</h2>

    <button type="button"
            @click="addItem"
    >
      Add +
    </button>
    <ul>
      <!-- used for list items -->
      <transition-group name="fade">
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
  name: "AnimatedList",
  data() {
    return {
      numbers: [10, 20, 30, 40, 50]
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
.fade-leave-to,
.fade-enter-from {
  transition: all 1s linear;
  font-weight: bold;
  color: white;
  background-color: red;
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease-in-out;
}

.fade-leave-active {
  position: absolute;
}

.fade-leave-from,
.fade-enter-to {
  opacity: 1;
  color: green;
  background-color: greenyellow;
  font-weight: bold;
  transition: all 1s ease-in-out;
}

.fade-move {
  transition: all .25s linear;
}
</style>
