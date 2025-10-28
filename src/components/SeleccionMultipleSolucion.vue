<template>
	<div>
		<h1>Seleccion Multiple</h1>
		<form v-on:submit.prevent="mostrarSeleccionados">
			<multiselect
				v-model="seleccionados"
				:options="options"
				:close-on-select="false"
				multiple
			></multiselect>
			<button>Mostrar seleccionados</button>
		</form>
		<div v-if="mostrar">
			<ul v-for="seleccionado in seleccionados" :key="seleccionado">
				<span>{{ seleccionado }}</span>
			</ul>
		</div>
	</div>
</template>

<script>
	import Multiselect from "vue-multiselect";

	export default {
		name: "SeleccionMultipleSolucion",
		components: { Multiselect },
		data() {
			return {
				seleccionados: null,
				mostrar: null,
				options: [
					"Elemento 1",
					"Elemento 2",
					"Elemento 3",
					"Elemento 4",
					"Elemento 5",
					"Elemento 6",
					"Elemento 7",
					"Elemento 8",
					"Elemento 9",
					"Elemento 10",
				],
			};
		},
		methods: {
			mostrarSeleccionados() {
				this.mostrar = 1;
			},
		},
	};
</script>
<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>
