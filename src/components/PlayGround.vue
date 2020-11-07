<template>
  <div>
    <div class="header">
      <img src="../assets/logo.png" alt="" height="40" />
      <h3>Vue Workshop!</h3>
    </div>
    <div class="playground-content">
        <div class="nav-menu" v-if="!excercise">
          <button @click="selectExcercise(1)" :class="{ active: excercise === 1 }">
            1. Tracking State and Updating Template
          </button>
          <button @click="selectExcercise(2)" :class="{ active: excercise === 2 }">
            2. Setting methods and binding events
          </button>
          <button @click="selectExcercise(3)" :class="{ active: excercise === 3 }">
            3. Two-Way Data Binding
          </button>
        </div>
        <component :is="`excercise-${excercise}`" v-bind="{onReturn: backMenu}"></component>
    </div>
  </div>
</template>

<script>
import excercise1 from "../excercises/1/1";
import excercise2 from "../excercises/2/2";
import excercise3 from "../excercises/3/3";

export default {
  name: "PlayGround",
  components: {
    excercise1,
    excercise2,
    excercise3,
  },
  data() {
    return {
      excercise: null,
    };
  },
  methods: {
    selectExcercise(num) {
      this.excercise = num;
    },
    backMenu() {
      this.excercise = null;
    }
  },
};
</script>

<style>
.playground-content {
  margin-top: 80px;
}
.header {
  position: fixed;
  top: 0;
  left: 0;
  background: white;
  box-shadow: 0 3px 3px rgba(0, 0, 0, 0.2);
  width: 100%;
  display: flex;
  align-items: center;
  padding: 5px 10px;
}
.nav-menu {
  display: block;
  text-align: left;
  margin-bottom: 30px;
}
.nav-menu button {
  background: transparent;
  border: 0;
  font-size: 16px;
  display: block;
  cursor: pointer;
  outline: none;

}
.nav-menu button.active {
  color: #42b983;
}
</style>