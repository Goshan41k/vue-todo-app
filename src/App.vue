<template>
  <div class="container">
    <Header />
    <Logo />
    <router-view />
  </div>
</template>

<script>
import { mapActions } from 'vuex';
import Header from './components/Header';
import Logo from './components/Logo';
export default {
  name: 'App',
  components: {
    Header,
    Logo,
  },
  methods: {
    ...mapActions(['fetchTaskById']),
  },
};
</script>

<style lang="scss">
$textColor: #314252;
$whiteColor: #ffffff;
$grayColorLight: #eeeeee;
$grayColor: #e1e1e1;
$grayColorDark: #757575;
$greenColor: #3fba83;
$greenColorLight: #bae6d5;
$greenColorLight2: #c7ebdf;

* {
  font-family: 'Trebuchet MS';
  font-size: 20px;
  color: $textColor;
}

body {
  padding: 0;
  margin: 0;
}

.container {
  background: $whiteColor;
  width: 100%;
  height: 100vh;
  display: grid;
  grid-template-areas:
    'header logo'
    'header main';
  grid-template-columns: 250px 1fr;
  grid-template-rows: 70px 1fr;
}
@media all and (max-width: 768px) {
  .container {
    grid-template-columns: 150px 1fr;
    // grid-template-rows: 60px 1fr;
  }
}
@media all and (max-width: 460px) {
  .container {
    grid-template-columns: 90px 1fr;
    // grid-template-rows: 50px 1fr;
  }
}
</style>
