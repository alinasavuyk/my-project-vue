<template>
   <input v-model="text"
   class="custom-input">
</template>

<script>
    export default {
        name:"CustomInput"
    }
</script>

<style lang="scss" scoped>
@import '../../../assets/scss/variables';

.custom-input {
  height: 40px;
  width: 200px;
  border: 2px solid $main-color;
  font-size: 18px;
  outline: none;
  line-height: inherit;
  padding: 8px 15px;
  
}
</style>