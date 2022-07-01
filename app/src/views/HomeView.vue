<template>
  <div class="home">
    <foodList/>
  </div>
</template>

<script>
// @ is an alias to /src
import foodList from '@/components/foodList.vue'

export default {
  name: 'HomeView',
  components: {
    foodList
  }
}
</script>
