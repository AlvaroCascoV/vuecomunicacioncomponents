<template>
	<h2 style="color: blue">Numero Hijo: {{ numero }}</h2>
	<button v-on:click="sumarNumeros">Sumar {{ numero }}</button>
</template>
<script>
	export default {
		name: "HijoNumero",
		props: ["numero"],
		data() {
			return {
				resultado: 0,
			};
		},
		methods: {
			sumarNumeros() {
				this.$emit("sumar", this.numero);
			},
		},
	};
</script>
