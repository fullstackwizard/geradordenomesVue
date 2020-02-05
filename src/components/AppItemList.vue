<template>
  <div>
    <h5> {{title}} <span class="badge badge-info">{{ items.length }}</span></h5>
    <div class="card">
        <div class="card-body">
            <ul class="list-group">
                <li class="list-group-item" v-for="item in items" v-bind:key="item">
                    {{ item }} 
                    <button v-on:click="deleteItem(item)" class="btn btn-info pull-right"><span class="fa fa-trash"></span></button>
                </li>
            </ul>
            <br>
            <div class="input-group">
                <input type="text" v-model="item" v-on:keyup.enter="addItem(item)" class="form-control" placeholder="Digite o item">
                <div class="input-group-append">
                    <button v-on:click="addItem(item)" class="btn btn-info"><span class="fa fa-plus"></span></button>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>
<script>
export default {
	name: "AppItemList",
	props: ["title", "items"],
	data() {
		return {
			item: ""
		};
	},
	methods: {
		addItem(item){
			this.$emit("addItem", item);
			this.item = "";
		},
		deleteItem(item){
			this.$emit("deleteItem", item);
			this.item = "";
		}
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
