<template>
  <div id="app">
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
          <td> <img src="person.pictureUrl" alt="contact1Pic" /> </td>
          <td> {{ person.name }}</td>
          <td> {{ person.popularity }}</td>
          <td v-if = "wonOscar === true"> Trophy </td>
          <td v-else> X </td>
          <td v-if = "wonEmmy === true"> Trophy </td>
          <td v-else> X </td>
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
        return contacts.slice(0,30)
      }
    }
}
</script>


