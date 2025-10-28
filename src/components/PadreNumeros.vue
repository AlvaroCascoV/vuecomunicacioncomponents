<template>
	<h1>Padre numeros</h1>
	<h2 style="color: red">La suma es: {{ suma }}</h2>
	<button v-on:click="generarAlea">Nuevo numero</button>
	<div v-for="num in numeros" :key="num">
		<HijoNumero :numero="num" v-on:sumar="sumar" />
	</div>
</template>
<script>
	import HijoNumero from "./HijoNumero.vue";

	export default {
		name: "PadreNumeros",
		components: {
			HijoNumero,
		},
		data() {
			return {
				numeros: [5, 9, 12, 56, 42],
				suma: null,
			};
		},
		methods: {
			generarAlea() {
				let numeroAlea = Math.floor(Math.random() * 100) + 1;
				this.numeros.push(numeroAlea);
			},
			sumar(numero) {
				this.suma += numero;
			},
		},
	};
</script>
