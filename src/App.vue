<template>
 <div :id="$style.app">
 <h2>{{text}}</h2>
 <Container>
<ApartmentFilterForm class="apartament-filter"
@submit='logger'/>
</Container>
 <ApartmentsList :items="apartments">
 <template #apartment="{apartment}">
 <ApartmentsItem
  :key="apartment.id"
  :descr="apartment.descr"
  :rating="apartment.rating"
  :imgSrc="apartment.imgUrl"
  :price="apartment.price"
  @click="handleItemClick"
  class="apartments-list-item"
/>
 </template>

 </ApartmentsList>
 </div>
</template>

<script>
import apartments from './components/apartment/apartments'
import ApartmentsList from './components/apartment/ApartmentsList.vue'
import ApartmentsItem from './components/apartment/ApartmentsItem.vue'
import ApartmentFilterForm from './components/apartment/ApartmentFilterForm.vue'

export default {
  name: 'App',
  components: { ApartmentsList, ApartmentsItem, ApartmentFilterForm },
 data() {
return {
  apartments,
  text:''
}
  },
  methods:{
    logger(value){
      console.log(value,'click logger')
    },
   
  }
}
</script>

<style module>
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.apartament-filter{
  margin-bottom: 40px;
}
</style>
