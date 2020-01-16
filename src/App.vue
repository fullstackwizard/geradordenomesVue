<template>
<div>
  <div id="slogan" class="text-center">
    <h1>FixGenerator Names Generate</h1>
    <br>
    <h6 class="text-secondy">Gerador de nomes / Vue.js, GraphQL e Nodejs</h6>
    <h6 class="text-secondy">by Flávio Ribeiro</h6>
  </div>
  <div id="main">
    <div class="container">
      <div class="row">
        <div class="col-md">
        <h5>Prefixos <span class="badge badge-info">{{ prefixes.length }}</span></h5>
          <div class="card">
            <div class="card-body">
              <ul class="list-group">
                <li class="list-group-item" v-for="prefix in prefixes" v-bind:key="prefix">
                  {{ prefix }}
                  <button v-on:click="deletePrefix(prefix)" class="btn btn-info pull-right"><span class="fa fa-trash"></span></button>
                </li>
              </ul>
              <br>
              <div class="input-group">
                <input type="text" v-model="prefix" v-on:keyup.enter="addPrefix(prefix)" class="form-control" placeholder="Digite o prefixo">
                <div class="input-group-append">
                  <button v-on:click="addPrefix(prefix)" class="btn btn-info"><span class="fa fa-plus"></span></button>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col-md">
        <h5>Sufixos <span class="badge badge-info">{{ sufixes.length }}</span></h5>
        <div class="card">
            <div class="card-body">
              <ul class="list-group">
                <li class="list-group-item" v-for="sufix in sufixes" v-bind:key="sufix">
                  {{ sufix }}
                  <button v-on:click="deleteSufix(sufix)" class="btn btn-info pull-right"><span class="fa fa-trash"></span></button>
                </li>
              </ul>
              <br>
              <div class="input-group">
                <input type="text" v-model="sufix" v-on:keyup.enter="addSufix(sufix)" class="form-control" placeholder="Digite o Sufixo">
                <div class="input-group-append">
                  <button v-on:click="addSufix(sufix)" class="btn btn-info"><span class="fa fa-plus"></span></button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <br>
      <h5>Domains <span class="badge badge-info">{{ domains.length }}</span></h5>
      <div class="card">
        <div class="card-body">
          <ul class="list-group">
            <li class="list-group-item" v-for="domain in domains" v-bind:key="domain" >
              {{ domain }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</div>
</template>
<script>
import "bootstrap/dist/css/bootstrap.css";
import "font-awesome/css/font-awesome.css";

export default {
	name: "app",
	data: function(){
		return {
      prefix: "",
      sufix: "",
			prefixes: ["Air", "Jet", "Flight"],
			sufixes: ["Hub", "Station", "Mart"],
			domains: ["AirHub", "AirStation", "AirMart", "JetHub", "JetStation", "JetMart", "FlightHub", "FlightStation", "FlightMart"]
		};
	},
  methods: {
    addPrefix(prefix) {
      this.prefixes.push(prefix);
      this.prefix = "";
      this.generate();
    },
    deletePrefix(prefix){
      this.prefixes.splice(this.prefixes.indexOf(prefix), 1);
    },
    addSufix(sufix) {
      this.sufixes.push(sufix);
      this.sufix = "";
      this.generate();
    },
    deleteSufix(sufix){
      this.sufixes.splice(this.sufixes.indexOf(sufix), 1);
    },
    generate(){
      this.domains = [];
      for(const prefix of this.prefixes){
        for(const sufix of this.sufixes){
          this.domains.push(prefix + " " + sufix);
        }
      }
    }
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
