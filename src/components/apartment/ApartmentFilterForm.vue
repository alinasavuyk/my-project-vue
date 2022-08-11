<template>
  <form class="form" @submit.prevent="handleSubmit">
<CustomSelectVue 
:items="cities"
v-model="city"
></CustomSelectVue>
 <CustomInputVue placeholder="ціна"
 v-model='price'/>
 <ButtonEl
 class="form__submit"
 type="submit"
 >Підбір житла</ButtonEl>
 </form>
</template>

<script>

import CustomSelectVue from './shared/CustomSelect.vue'
import CustomInputVue from './shared/CustomInput.vue'
import ButtonEl from '../ButtonEl.vue'

export default {
    components: {
      CustomSelectVue,
      CustomInputVue,
      ButtonEl
},
 data() {
    return {
      price: '',
      city: '',
    };
  },
  computed: {
   /* rules() {
      return [isRequired, charLimit(10)];
    },*/
    cities() {
      return [
        { value: '', label: 'Місто', selected: true },
        'Kyiv',
        'Odesa',
        'Poltava',
        'Kharkiv',
        'Dnipro',
        'Lviv',
        'Kherson',
        'Mariupol',
      ];
    },
  },
 methods: {
    handleSubmit() {
      this.$emit('submit', 
        {city: this.city,
        price: this.price});
    },
 
},
}
</script>

<style lang="scss" scoped>
.form {
  display: flex;
  &__select {
    margin-right: 30px;
  }
  &__submit {
    margin-left: auto;
  }
}
</style>
