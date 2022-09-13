<template>
  <div id="app">
    <table>
      <thead>
        <tr>
          <th> Picture </th>
          <th> Name </th>
          <th> Popularity</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for = "(person,index) in topFiveContacts" :key="index" >
          <td> <image src="person.pictureUrl" alt="contact1Pic" /> </td>
          <td> {{ person.name }}</td>
          <td> {{ person.popularity }}</td>
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
        return contacts.slice(0,6)
      }
    }
}
</script>


