<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <HelloWorld msg="Welcome to Vue.js App"/> -->
  <div id="app">
    {{ fullName }}
  </div>
  <div>
    <strong>Followers: </strong>{{ followers }}
  </div>
  <button @click="followUser">Follow</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data() {
    return {
      content: 'content',

      followers: 0,
      user: {
        id: 1,
        firstName: 'John',
        lastName: 'Cena',
        email: 'johncena@gmail.com',
        isAmin: true,
      },
    };
  },
  watch: {
    followers(newFollowerCount, oldFollowerCount){
      if(oldFollowerCount < newFollowerCount){
        console.log(`${this.user.firstName} has gained a follower!`)
      }
    }
  },
  // beforeCreated - data and event is not setting up
  beforeCreate() {
    // console.log('beforeCreate Hook');
    // console.log(this.content);
  },
  // created - components, data
  created() {
    // console.log('Created Hook');
    // console.log(this.content);
    // console.log('This Object:');
    // console.log(this);
    // console.log('This $el:');
    // console.log(this.$el);
  },

  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
  },
  methods: {
    followUser() {
      this.followers++;
    },
  },
  // mounted: everything is already run - components, data, el
  mounted() {
    this.followUser();
    // console.log('This Object:');
    // console.log(this);
    // console.log('This $el:');
    // console.log(this.$el);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
