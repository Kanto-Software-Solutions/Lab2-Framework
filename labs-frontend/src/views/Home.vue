<template>
	<div class="container mt-2">
		<h1>Kanto software solutions</h1>
			<div class="d-flex justify-content-between w-100">
				<a type="button" class="btn btn-primary" style="margin: 5px" href="/principal">Inicio</a>
				<a type="button" class="btn btn-primary" style="margin: 5px" href="/mis-cursos">Mis cursos</a>
				<a type="button" class="btn btn-primary" style="margin: 5px" href="/principal/roles">Mis roles</a>
				<a type="button" class="btn btn-primary" style="margin: 5px" href="/principal/nuevo-rol">Agregar rol</a>
				<a type="button" class="btn btn-warning" style="margin: 5px" href="/profesor">Area Docente</a>
				<a type="button" class="btn btn-danger" style="margin: 5px" href="/">Salir</a>
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
