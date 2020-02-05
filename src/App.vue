<template>
<div>
  <div id="slogan" class="text-center">
    <h1>FixGenerator Domains</h1>
    <br>
    <h6 class="text-secondy">Gerador de nomes / Vue.js, GraphQL e Nodejs</h6>
    <h6 class="text-secondy">by Flávio Ribeiro</h6>
  </div>
  <div id="main">
    <DomainList></DomainList>
  </div>
  
  
</div>
</template>
<script>
import "bootstrap/dist/css/bootstrap.css";
import "font-awesome/css/font-awesome.css";
import DomainList from "./components/DomainList";

export default {
	name: "app",
	components: {
		DomainList
	}
};
</script>

<style>
#main {

  background-color: #f1f1f1;
  padding-top: 30px;
  padding-bottom: 30px;

}
#slogan {

  margin-top: 30px;
  margin-bottom: 30px;

}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
