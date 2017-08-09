<template>
  <div id="app">
    <md-card>
      <md-card-header>
        <div class="md-title">
          Material Desing with Vue.js 2 Demo
        </div>
        <div class="md-subhed">
          by Michu
        </div>
      </md-card-header>
      <md-card-content>
        <md-button class="md-raised md-primary" v-on:click="fillTable">Fill Table</md-button>
        <md-button class="md-raised md-primary" v-on:click="clearTable">Clear Table</md-button>
      </md-card-content>
      <md-table>
        <md-table-header>
          <md-table-row>
            <md-table-head>First Name</md-table-head>
            <md-table-head>Last Name</md-table-head>
            <md-table-head>Email</md-table-head>
          </md-table-row>
        </md-table-header>
        <md-table-body>
          <md-table-row v-for="contact in contacts">
            <md-table-cell>{{contact.firstName}}</md-table-cell>
            <md-table-cell>{{contact.lastName}}</md-table-cell>
            <md-table-cell>{{contact.email}}</md-table-cell>
          </md-table-row>
        </md-table-body>
      </md-table>
    </md-card>

  </div>
</template>

<script>


export default {
  name: 'app',
  components: {

  },
  data: function(){
    return{
        contacts: []
    }
  },
  methods: {
    fillTable: function(){
      this.contacts.push({firstName: 'Michu', lastName: 'Stroz', email: 'a@b.pl'});
      this.contacts.push({firstName: 'Jan', lastName: 'Kowalski', email: 'c@b.pl'});
      this.contacts.push({firstName: 'Ula', lastName: 'Brzydula', email: 'd@b.pl'});
    },
    clearTable: function(){
      this.contacts.splice(0, this.contacts.length);
    }
  }
}
</script>

<style>
#app {
  margin-top: 60px;
  margin-left: 30px;
  margin-right: 30px;
}
</style>
