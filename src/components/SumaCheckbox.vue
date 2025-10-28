<template>
	<div>
		<h1>Ejemplo Checkbox</h1>
		<form v-on:submit.prevent="generarAlea">
			<button>Generar Checkbox</button>
			<div id="containercheckbox">
				<label v-for="(numero, index) in numeros" :key="index">
					<input
						type="checkbox"
						:value="numero"
						v-model="seleccionados"
						@change="calcularSuma"
					/>
					{{ numero }}
				</label>
			</div>
			<div id="containersuma">
				<h2 style="color: blue">La suma seleccionada es: {{ suma }}</h2>
			</div>
		</form>
	</div>
</template>

<script>
	export default {
		name: "SumaCheckbox",
		data() {
			return {
				numeros: [],
				seleccionados: [],
				suma: 0,
			};
		},
		methods: {
			generarAlea() {
				this.numeros = [];
				this.seleccionados = [];
				this.suma = 0;
				for (let i = 0; i <= 8; i++) {
					let numero = Math.floor(Math.random() * 100) + 1;
					this.numeros.push(numero);
				}
			},
			calcularSuma() {
				this.suma = 0;
				for (let i = 0; i < this.seleccionados.length; i++) {
					this.suma += parseInt(this.seleccionados[i]);
				}
			},
		},
	};
</script>

<style></style>
