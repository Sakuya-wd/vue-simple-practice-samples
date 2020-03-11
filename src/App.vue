<template>
  <div id="app">
    <hello-component></hello-component>
    <p>
      <input type="text" v-model="message">
    </p>
    <p>
      <input type="text" v-model="message">
    </p>
    <ul>
      <li v-for="value in user">{{ value }}</li>
    </ul>
    <hr>
    <ul>
      <li v-for="(value,key) in user">{{ key }} : {{ value }}</li>
    </ul>
    <hr>
    <ul>
      <li v-for="(v,k) in user">{{ k }} : {{ v }}</li>
    </ul>
    <ol>
      <li v-for="color in colors">{{ color }}</li>
    </ol>
    <p v-show="toggle">
      <!--v-showはDOMレベルでは削除されない、cssのdisply:noneを操作している-->
      Hello(v-show)
    </p>

    <p>
      {{ message }}
    </p>
    <p>
      {{ count }}
    </p>
    <p>
      {{ user.prefecture }}
    </p>
    <p>
      {{ colors[1] }}
    </p>
    <button v-on:click="onclick">クリック</button>
    <h1>
      {{ now }}
    </h1>
  </div>
</template>

<script>
import HelloComponent from "./components/HelloComponent"

export default {
  components: {
    HelloComponent
  },
  data:function(){
    return {
      now: '',
      toggle: true,
      message: 'Hello Vue.js!',
      count: 10,
      user: {
        lastName: 'Yamada',
        firdtName: 'taro',
        prefecture: 'Tokyo',
      },
      colors: ['Red','Green','Blue'],
    }
  },
  methods: {
    onclick: function(){
      this.now = new Date().toLocaleString();
    }
  }
  //データバインディング（データと描画を同期）
  //ディレクティブ（v-で始まるもの、日本語で指示という意味、Vue.jsになんらかの指示をだす仕組み）
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
