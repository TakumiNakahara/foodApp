<template>
  <div>
    <h1>{{category}}</h1>
    <ul class="food-list">
      <template v-if="category === 'firstQs'">
        <li v-for="(firstQ , index) in firstQs" :key="index.category" v-on:click="()=> changeState(index)">
        {{ firstQ.item}}
        </li>
      </template>
      <template v-else-if="category === 'secoundQs'">
        <li v-for="foodlist in bread" :key="foodlist.item">
          <p v-on:click="()=> category = foodlist.category">{{foodlist.item}}</p>
        </li>
      </template>
      <template v-else-if="category === 'rice'">
        <li v-for="foodlist in rice" :key="foodlist.item">
          <router-link to="/about">{{foodlist.item}}</router-link>
        </li>
      </template>
    </ul>
  </div>
  
</template>

<script>
export default {
  name: 'foodList',
  data:()=>{
    return{
      category: 'firstQs',
      firstQs: [
        {item: 'パン', category: 'bread'},
        {item: 'ご飯',category: 'rice'},
        {item: 'パスタ',category: 'pasta'},
        {item: 'フルーツ',category: 'fruit'},
      ],
      secoundQs: [
        [
          {item: 'ジャム'},
          {item: 'バター'},
          {item: 'チェコ'},
          {item: 'チーズ'},
        ],
        [
          {item: 'ミソ'},
          {item: 'シャケ'},
          {item: 'ふりかけ'},
          {item: '納豆'},
        ],
      ],
    }
  },
  methods: {
    changeState :function(index) {
      this.category = 'secoundQs';
      console.log(index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
  cursor: pointer;
}
a {
  color: #42b983;
}
</style>
