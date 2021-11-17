<template>
  <form name="form">

    <div class="help">
      <slot name="help"></slot>
    </div>

    <div class="fields">
      <slot name="fields"></slot>
    </div>

    <div class="buttons">
      <slot name="buttons"></slot>
    </div>

    <!-- default slot location -->
    <slot></slot>
  </form>

</template>

<script>
export default {
  name: "AppForm"
}
</script>
