<template>
  <div id="app">
    <h1> IronContacts</h1>
    <button @click="">Add Random Contact </button>
    <table>
      <thead>
        <tr>
          <th> Picture </th>
          <th> Name </th>
          <th> Popularity</th>
          <th> Won an Oscar</th>
          <th> Won an Emmy</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for = "(person,index) in topFiveContacts" :key="index" >
          <td> <img :src="person.pictureUrl" alt="contactPic" /> </td>
          <td> {{ person.name }}</td>
          <td> {{ person.popularity }}</td>
          <td> <img v-if = "person.wonOscar" src="https://img.freepik.com/premium-vector/trophy-cup-flat-vector-icon-simple-winner-symbol-gold-illustration-isolated-white-background_157943-469.jpg?w=2000" alt="trophy"/> </td>
          <td> <img v-if = "person.wonEmmy" src="https://img.freepik.com/premium-vector/trophy-cup-flat-vector-icon-simple-winner-symbol-gold-illustration-isolated-white-background_157943-469.jpg?w=2000" alt="trophy"/> </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  import contacts from "./contacts.json"

  export default {
    name: "App",
    computed: {
      topFiveContacts() {
        return contacts.slice(0,5)
      }
    }
    method: {

    }
}
</script>

<style scoped>
  h1 {
    text-align: center;
    font-weight: 700px;
  }
img {
  width: 100px;
  height: 100px;
}
</style>

