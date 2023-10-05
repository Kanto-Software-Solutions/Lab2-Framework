<template>
	<div class="container">
		<h2>Profesor</h2>
		<div class="d-flex justify-content-between">
			<a type="button" class="btn btn-primary" style="margin: 5px" href="/principal">Inicio</a>
			<a type="button" class="btn btn-primary" style="margin: 5px" href="/profesor/crear-curso">Añadir curso</a>
			<a type="button" class="btn btn-danger" style="margin: 5px" href="/"> Salir </a>
		</div>
		<router-view></router-view>
	</div>
</template>
  
<script>
import { getAuthenticationToken } from '@/dataStorage';

export default {
	name: "Home",
	beforeCreate() {
		if (!getAuthenticationToken()) {
			this.$router.push({ name: 'login' })
		}
	}
}
</script>
  
<style></style>