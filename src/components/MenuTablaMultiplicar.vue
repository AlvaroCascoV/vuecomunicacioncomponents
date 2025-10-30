<template>
	<div>
		<ul id="menu">
			<li>
				<router-link to="/">Home</router-link>
				|
			</li>
			<li v-for="num in numeros" :key="num">
				<router-link :to="'/tabla/' + num">Tabla de {{ num }}</router-link>
				|
			</li>
		</ul>
	</div>
</template>
<script>
	export default {
		name: "MenuTablaMultiplicar",
		data() {
			return {
				numeros: [],
			};
		},
		mounted() {
			for (let i = 0; i < 5; i++) {
				this.numeros.push(Math.floor(Math.random() * 100) + 1);
			}
		},
	};
</script>
<style>
	ul#menu li {
		display: inline;
	}
</style>
