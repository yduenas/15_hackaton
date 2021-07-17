<template>
	<div class="container">
		<h1>Contacto - {{ $route.params.id }}</h1>
		<section>
			<p>Informacion del contacto</p>
			<h2 @click="detalle">Nombre: {{ contacto.nombre }}</h2>
			<!--
			<img alt="Vue logo" :src="contacto.url" />
			-->
			<img alt="Vue logo" src="../assets/silueta.jpg" />

			<p>Telefono: {{ contacto.telefono }}</p>
			<p>Correo: {{ contacto.correo }}</p>
			<!--
			<router-link :to="`/contactos/`">Regresar</router-link>
			-->
			<div class="col-6">
				<router-link :to="`/`" class="btn btn-green">Regresar</router-link>
			</div>
		</section>
	</div>
</template>

<script>
export default {
	data() {
		return {
			message: 'Hola',
			contacto: {},
		};
	},
	methods: {
		async getContacto() {
			const contacto = 'this.$route.params.id ';
			const data = await fetch(
				`http://localhost:3000/contactos/${this.$route.params.id}`
			);
			const info = await data.json();
			this.contacto = info;
			console.log(info);
		},
		detalle() {
			alert('Diste click en el nombre de : ' + this.contacto.name);
		},
	},
	created() {
		this.getContacto();
	},
};
</script>

<style scoped>
h2 {
	font-size: 30px;
}
</style>
