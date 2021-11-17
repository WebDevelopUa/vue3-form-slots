<template>
  <div>
    <button type="button"
            @click="flag = !flag">
      Toggle
    </button>

    <!-- Add animation #1 -->
    <transition name="fade" mode="out-in" appear>
      <h3 v-if="flag" key="main">
        Primary element
      </h3>
      <h3 v-else key="secondary">
        Secondary element
      </h3>
    </transition>

    <!-- Add animation #2 -->
    <!--    <transition name="fade" mode="in-out" duration="8000">-->
    <!--      <h4 v-show="flag">-->
    <!--        v-show="flag"-->
    <!--      </h4>-->
    <!--    </transition>-->

    <!-- Add animation #3 -->
    <transition name="zoom" type="transition" mode="out-in" appear>
      <h1 v-show="flag">
        ZOOM
      </h1>
    </transition>

  </div>
</template>

<script>
export default {
  name: "TransitionAnimation",
  data() {
    return {
      flag: true
    }
  }
}
</script>

<style scoped>
h1 {
  width: 400px;
  padding: 20px;
  margin: 20px;
}

.fade-enter-from {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 4s linear;
}

.fade-leave-from,
.fade-enter-to {
  opacity: 1;
  background-color: black;
  color: white;
}

.fade-leave-to {
  opacity: 0;
  background-color: orange;
}

.zoom-enter-active {
  animation: zoom-in 2s linear forwards;
  transition: opacity 3s ease-in-out;
}

.zoom-leave-active {
  animation: zoom-out 2s linear forwards;
  transition: opacity 3s ease-in-out;
}

.zoom-enter-from {
  opacity: 0;
  background-color: red;
}

.zoom-leave-to {
  opacity: 0;
  background-color: orange;
}

.zoom-leave-from,
.zoom-enter-to {
  opacity: 1;
  background-color: hotpink;
}

@keyframes zoom-in {
  from {
    transform: scale(0, 0);
  }
  to {
    transform: scale(1, 1);
  }
}

@keyframes zoom-out {
  from {
    transform: scale(1, 1);
  }
  to {
    transform: scale(0, 0);
  }
}

</style>
