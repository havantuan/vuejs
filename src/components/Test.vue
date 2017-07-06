<template>
  <div class="test">
    <span v-html="title"></span>
    <input type="text" v-model="myfavote"/>
    <h2>{{myfavote}}</h2>
    <p v-if="showName" v-text="user.firstname+user.lastname"></p>
    <p v-else v-text="user.firstname"></p>
    <ul>
        <li v-for="item in items" >{{item.title}}</li>
    </ul>
    <button v-on:click="hello">Say Hello</button><br>
    <input v-on:keyup="keypress" v-on:keyup.enter="enterHit" type="text"/>
    <hr>
    <lable>First name</lable><input type="text" v-model="user.firstname"><br>
    <lable>last name</lable><input type="text" v-model="user.lastname"><br>
    <h2>{{fullname}}</h2>
  </div>
</template>

<script>
  export default {
    name: 'test',
    data(){
      return {
        title: '<h1>Hello Word</h1>',
        myfavote: '',
        user: {
          firstname: 'Tuan',
          lastname: 'DepZai'
        },
        showName: true,
        items: [
          {title: 'one'},
          {title: 'two'},
          {title: 'three'},
          {title: 'four'},
          {title: 'five'}
        ]
      }
    },
    methods: {
       hello(){
         alert('Hello');
       },
       keypress(e){
        console.log(e.target.value);
       },
       enterHit(){
        alert('finish key press !');
       }
    },
    computed: {
        fullname(){
            return this.user.lastname +' '+ this.user.firstname;
        }
    }
  }
</script>
<style scoped>

</style>
