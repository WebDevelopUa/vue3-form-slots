<template>
  <div>
    <h1>Slot Properties component with data(){user,favorites}</h1>
    <p>Bind :user="user" property to slot component; pass the value to the parent component</p>
    <!-- default slot  -->
    <h5>---- default slot location start ----</h5>
    <slot :user="user"
          :favorites="favorites"
    />
    <h5>---- default slot location end ----</h5>
  </div>
</template>

<script>
export default {
  name: "SlotPropComponent",
  data() {
    return {
      // properties: 'user', 'favorites'
      user: {
        name: 'Tom',
        age: 19,
      },
      favorites: ['Music', 'Nike', 'Cars']
    }
  }
}
</script>
