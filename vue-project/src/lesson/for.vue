<template>
<table>
  <thead>
    <tr>
      <th>id</th><th>app id</th><th>billing id</th><th>price</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(item, index) in billings" :key="index">
      <td>{{item.id}}</td><td>{{item.appID}}</td><td>{{item.billingID}}</td><td>{{item.price}}</td>
    </tr>
  </tbody>
</table>
</template>

<script scoped lang="ts">
export default {
  data(){
    return {
      billings: [
        {id:"1", appID:"aaa", billingID:"billingID1", price:"$2.3"},
        {id:"2", appID:"bbb", billingID:"billingID2", price:"$2.4"},
        {id:"3", appID:"ccc", billingID:"billingID3", price:"$2.5"},
        {id:"4", appID:"ddd", billingID:"billingID4", price:"$2.6"},
      ],
    }
  },
}
</script>
