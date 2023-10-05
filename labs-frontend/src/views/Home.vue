<template>
	<div class="container-fluid mt-2">
		<h1>Bienvenido al dummy</h1>
		<div class="row">
			<div class="d-flex">
				<a type="button" class="btn btn-primary" style="margin: 5px" href="/principal">PRINCIPAL</a>
				<a type="button" class="btn btn-primary" style="margin: 5px" href="/mis-cursos">VER MIS CURSOS</a>
				<a type="button" class="btn btn-primary" style="margin: 5px" href="/principal/roles">VER MIS ROLES</a>
				<a type="button" class="btn btn-primary" style="margin: 5px" href="/principal/nuevo-rol">NUEVO ROL</a>
				<a type="button" class="btn btn-danger" style="margin: 5px" href="/"> SALIR </a>
			</div>
			<router-view></router-view>
		</div>
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
