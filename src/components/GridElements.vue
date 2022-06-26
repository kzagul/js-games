<template>
  <div class="game-field">
    <div class="row" v-on:click="makeMove">
      <SquareElement id="field1" />
      <SquareElement id="field2" />
      <SquareElement id="field3" />
    </div>
    <div class="row">
      <SquareElement id="field1" />
      <SquareElement id="field2" />
      <SquareElement id="field3" />
    </div>
    <div class="row">
      <SquareElement id="field1" />
      <SquareElement id="field2" />
      <SquareElement id="field3" />
    </div>
  </div>
</template>

<script>
import SquareElement from "./SquareElement.vue";

export default {
  name: "App",
  props: {
    tics: Array,
  },
  components: {
    SquareElement,
  },
  methods: {
    hide(e) {
      let target = e.target;
      if (target.tagName != "SquareElement") return
      else console.log("working...")
    },
    makeMove: function (event) {
        let target = event.target
      // `this` внутри методов указывает на экземпляр Vue
      alert('Привет!')
      // `event` — нативное событие DOM
      if (event) {
        alert(target)
        
      }
      target.style.visibility = 'hidden';
      this.OnHandleClick(target).style.visibility = 'hidden';
    }
  },
};
</script>

<style>
.game-field {
  display: flex;
  flex-direction: column;
}
.row {
  display: flex;
  justify-content: center;
}

/* #field1{
    background-color: brown;
} */
</style>
