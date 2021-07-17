<template>
	<div class="container mt-5">
		<h1>Lista de contactos</h1>
		<ContactCard :prop1="valor" />
		<Modal @refrescando="refrescar" tituloModal="Agregar Contacto" />
		<!--
		<img alt="Vue logo" src="../assets/logo.png" />		
		<HelloWorld msg="Welcome to Your Vue.js App"/>
		--></div>
</template>

<script>
// @ is an alias to /src
import ContactCard from '@/components/ContactCard.vue';
import Modal from '@/components/Modal.vue';

export default {
	name: 'Home',

	data() {
		return {
			valor: {},
		};
	},
	components: {
		ContactCard,
		Modal,
	},
	methods: {
		refrescar(valor) {
			//console.log('refrescando' + JSON.stringify(valor));
			this.valor = valor;
		},
	},
};
</script>
