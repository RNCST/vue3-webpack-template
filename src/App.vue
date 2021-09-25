<template>
  <h1 @click="increase">
    {{ count }}
  </h1> 
  <div v-if="count > 4">
    <!-- v- ==> 디렉티브 -->
    4보다 큼
  </div>
  <ul>
    <Fruit
      v-for="fruit in fruits"
      :key="fruit"
      :name="fruit">
      {{ fruit }}
    </Fruit>
  </ul>
</template>
  
<script>
import Fruit from '~/components/Fruit'

export default {
  components: {
    Fruit
    // == Fruit: Fruit
  },
  //import compornent선언
  data() {
    return {
      count: 0,
      fruits: ['Apple','Banana','Cheery']
    }
  },
  methods: {
    increase() {
      this.count += 1;
    }
  }
};
</script>

<style lang="scss">
h1 {
  font-size: 50px;
  color: royalblue;
}
ul {
  li {
    font-size: 40px;
  }
}
</style>