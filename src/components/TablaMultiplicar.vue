<template>
	<div style="justify-items: center">
		<h2 style="color: red">{{ mensaje }}</h2>
		<table border="1">
			<thead>
				<tr>
					<th>Operacion</th>
					<th>Resultado</th>
				</tr>
			</thead>
			<tbody v-html="tabla"></tbody>
		</table>
	</div>
</template>

<script>
	export default {
		name: "TablaMultiplicar",
		data() {
			return {
				mensaje: "",
				tabla: "",
			};
		},
		mounted() {
			let numero = this.$route.params.numero;

			this.generarTabla(numero);
		},
		methods: {
			generarTabla(num) {
				let aux = "";
				for (let i = 1; i <= 10; i++) {
					let operacion = num + "*" + i;
					let resultado = num * i;
					aux +=
						"<tr><td>" + operacion + "</td><td>" + resultado + "</td></tr>";
				}
				this.tabla = aux;
			},
		},
		watch: {
			"$route.params.numero"(nextVal, oldVal) {
				if (nextVal != oldVal) {
					this.mensaje = "Tabla del " + this.$route.params.numero;
					this.generarTabla(nextVal);
				}
			},
		},
	};
</script>

<style></style>
