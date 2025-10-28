<template>
	<h4 style="color: red">{{ nombredeporte }}</h4>
	<button v-on:click="seleccionarFavorito">Seleccionar Favorito</button>
</template>
<script>
	export default {
		name: "HijoDeporte",
		props: ["nombredeporte"],
		mounted() {
			console.log(this.nombredeporte);
		},
		methods: {
			seleccionarFavorito() {
				console.log("Soy el hijo " + this.nombredeporte);
				//PARA ENVIAR INFORMACION SE REALIZA A PARTIR DE LA LLAMADA
				//CON CADA PARAMETRO SEPARADO CON COMAS, DENTRO DEL METODO $emit
				this.$emit("seleccionarFavoritoParent", this.nombredeporte);
			},
		},
	};
</script>
