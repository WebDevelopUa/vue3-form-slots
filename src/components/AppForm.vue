<template>
  <form name="form">

    <div class="help">
      <h5>---- help slot location start ----</h5>
      <slot name="help"></slot>
      <h5>---- help slot location end ----</h5>
    </div>

    <div class="fields">
      <h5>---- fields slot location start ----</h5>
      <slot name="fields"></slot>
      <h5>---- fields slot location end ----</h5>
    </div>

    <div class="buttons">
      <h5>---- buttons slot location start ----</h5>
      <slot name="buttons"></slot>
      <h5>---- buttons slot location end ----</h5>
    </div>

    <!-- default slot location -->
    <h5>---- default slot location start ----</h5>
    <slot></slot>
    <h5>---- default slot location end ----</h5>
  </form>

</template>

<script>
export default {
  name: "AppForm"
}
</script>
