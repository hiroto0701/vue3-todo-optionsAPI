<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      title: 'ONE OK ROCK',
      message: 'We are OORer!!!',
      isRed: true,
      input: {
        firstName: '',
        lastName: '',
        isMember: true,
      },
      users: [
        {
          firstName: 'Takahiro',
          lastName: 'Moriuchi',
          isMember: true
        },
        {
          firstName: 'Hiroto',
          lastName: 'Inagaki',
          isMember: false
        },
        {
          firstName: 'Toru',
          lastName: 'Yamashita',
          isMember: true
        },
        {
          firstName: 'Oneokrock',
          lastName: 'Ryota',
          isMember: true
        },
        {
          firstName: 'Oneokrock',
          lastName: 'Tomoya',
          isMember: true
        },
      ]
    }
  },
  methods: {
    addUser() {
      this.users.push(this.input)
      this.input = {
        firstName: '',
        lastName: '',
        isMember: true
      }
    },
  }
}
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>


  <h1 :title="message" :class="{ red: isRed }">{{ title }}</h1>
  <p>{{ message }}</p>
  <input type="text" v-model="input.firstName" />
  <input type="text" v-model="input.lastName" />
  <input type="checkbox" v-model="input.isMember" />
  <button @click="addUser">ユーザを追加する</button>
  <h2>ONE OK ROCKメンバーデータ</h2>
  <div v-for="user in users">
    <p>Name: {{ user.firstName + ' ' + user.lastName }}</p>
    <p v-if="user.isMember">メンバーです</p>
    <p v-else>偽物です</p>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.red {
  color: red;
}
</style>
