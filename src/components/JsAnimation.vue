<template>
  <div>

    <button type="button"
            @click="show = !show">
      Toggle
    </button>


    <!--  Additional hooks:-->
    <!--  @enter-cancelled="enterCancelled"-->
    <!--  @leave-cancelled="leaveCanceled"-->

    <transition
        @before-enter="beforeEnter"
        @enter="enter"
        @after-enter="afterEnter"
        @before-leave="beforeLeave"
        @leave="leave"
        @after-leave="afterLeave"
        :css="false"
    >
      <h2 v-if="show">JS Animation</h2>

    </transition>

  </div>
</template>

<script>
export default {
  name: "JsAnimation",
  data() {
    return {
      show: false
    }
  },
  methods: {
    beforeEnter(el) {
      console.log('... beforeEnter() ... : ', el)
    },
    enter(el, done) {
      console.log('... enter() ... : ', el)

      const animation = el.animate([{transform: "scale3d(0,0,0)"}, {}],
          {duration: 1000})

      animation.onfinish = () => {
        done()
      }

    },
    afterEnter(el) {
      console.log('... afterEnter() ... : ', el)
    },
    beforeLeave(el) {
      console.log('... beforeLeave() ... : ', el)
    },
    leave(el, done) {
      console.log('... leave() ... : ', el)

      const animation = el.animate([{}, {transform: "scale3d(0,0,0)"}],
          {duration: 1000})

      animation.onfinish = () => {
        done()
      }

    },
    afterLeave(el) {
      console.log('... afterLeave() ... : ', el)
    }
  }

}
</script>

<style scoped>

</style>
