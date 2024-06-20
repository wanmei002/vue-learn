<style>
th {
  width: 5%;
  border-bottom: 1px solid black;
}
</style>
<template>
  <div>
    <input type="text" v-model="keyword" />
    <input type="text" v-model="sortType" />
    <button @click="insertData"> 插入数据 </button>
  </div>
  <table>
    <thead>
      <tr>
        <th>id</th><th>app id</th><th>billing id</th><th> price </th>
      </tr>
    </thead>
    <tbody>
    <tr v-for="(item, index) of sortBillings" :key="item.id">
      <td>{{item.id}}</td><td> {{item.appID}} </td><td>{{item.billingID}}</td><td>{{item.price}}</td>
    </tr>
    </tbody>
  </table>
</template>

<script scoped>
export default {
  data(){
    return {
      billings: [
        {id:"1", appID:"aaa", billingID:"billingID1", price:2.3},
        {id:"2", appID:"bbb", billingID:"billingID2", price:2.4},
        {id:"3", appID:"ccc", billingID:"billingID3", price:2.5},
        {id:"4", appID:"ddd", billingID:"billingID4", price:2.6},
      ],
      keyword: "",
      sortType: 0
    }
  },

  methods: {
    insertData(){
      this.billings.splice(1, 0, {"id":"5", "appID":"eee", "billingID":"billingID5", "price":2.7},);
    },
  },

  computed: {
    sortBillings: {
      get(){
        console.log("in sortBillings")
        const arr = this.billings.filter((p)=>{
          console.log("keyword ", this.keyword)
          if (this.keyword === "") {
            return true
          }
          return p.appID.indexOf(this.keyword) === -1
        })
        console.log("sort1", arr)
        // sort
        if (this.sortType) {
          arr.sort((a,b) => {
            return this.sortType === 1 ? a.price-b.price : b.price-a.price
          })
        }
        console.log(arr)
        return arr
      },
    }
  }
}
</script>
