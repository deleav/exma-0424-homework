<template>
  <li>
    {{ todo }}
    <span @click="deleteItem">
      X
    </span>
  </li>
</template>

<script>
export default {
  props: [
    'todo',
    'index'
  ],
  methods: {
    deleteItem() {
      this.$emit( 'deleteItem' );
    }
  }
}
</script>

<style scoped>
li {
  border: 1px solid;
  border-radius: 5px;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 5px;
  padding: 5px;
  width: 200px;
}

span {
  float: right;
}

span:hover {
  cursor: pointer;
}
</style>