<template>
	<div>
		<ul id="menu">
			<li>
				<router-link to="/">Deportes</router-link>
				|
			</li>
			<li>
				<router-link to="/comics">Comics</router-link>
				|
			</li>
			<li>
				<router-link to="/numeros">Numeros</router-link>
				|
			</li>
			<li>
				<router-link to="/numerodoble">Doble SIN</router-link>
				|
			</li>
			<li v-for="num in numeros" :key="num">
				<router-link :to="'/numerodoble/' + num">
					Doble de {{ num }}
				</router-link>
				|
			</li>
		</ul>
	</div>
</template>
<script>
	export default {
		name: "MenuComponent",
		data() {
			return {
				numeros: [77, 33, 22],
			};
		},
	};
</script>
<style>
	ul#menu li {
		display: inline;
	}
</style>
