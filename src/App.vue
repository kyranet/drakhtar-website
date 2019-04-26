<template>
	<div id="app">
		<section class="hero is-dark is-large is-bold">
			<div class="hero-body">
				<div class="container">
					<img alt="Drakhtar Logo" src="./assets/drakhtar.png">
					<h2 class="subtitle">
						Un juego de estrategia por turnos en un tablero cuadriculado donde el jugador maneja un héroe y su ejército a lo largo de una historia.
					</h2>
				</div>
			</div>
		</section>

		<Story />
		<Trailer url="https://www.youtube.com/embed/o5zS-gGveMs"/>
		<Downloads />

		<h1 class="title">Equipo</h1>
		<TeamMember imageSRC="Members/Alejandro.jpg" name="Alejandro Plázer Arnaz"
			description="TBD."/>
		<TeamMember imageSRC="Members/Alvaro.jpg" name="Álvaro Carrasco Jurado"
			description="TBD."/>
		<TeamMember imageSRC="Members/Antonio.jpg" name="Antonio Román Cerezo"
			description="Amante de la música y de los videojuegos, programa más que duerme."/>
		<TeamMember imageSRC="Members/Carlos.jpg" name="Carlos María González Martínez"
			description="Plataformas y RPGs for life. Soy más de gameplay que de historia pero por alguna extraña razón soy un viciado de las novelas visuales."/>
		<TeamMember imageSRC="Members/Dani.jpg" name="Daniel García-Villarrubia López-Menchero"
			description="Aficionado de RPGs, sandbox y juegos con una fuerte narrativa. Memelord del condado de Guadalajara."/>
		<TeamMember imageSRC="Members/Gonzalo.jpg" name="Gonzalo Pérez Martín"
			description="Acerca de mí tengo el ordenador, el monitor y el ratón. Desarrollador en proceso y como parece personaje del GTA 6."/>
		<TeamMember imageSRC="Members/Javi.jpg" name="Javier Camacho Carrasco"
			description="TBD."/>
		<TeamMember imageSRC="Members/Miguel.jpg" name="Miguel Zhefan Ye Ye"
			description="Amante de una buena narrativa, el sonido hace maravillas aunque pocos lo sepan. Also f*** battle royales."/>
		<TeamMember imageSRC="Members/Omar.jpg" name="Omar Naranjo Caprachi"
			description="Jugador por vicio, desarrollador por oficio. Una buena historia es lo que hace un buen juego."/>
		<Footer />
	</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
// import HelloWorld from './components/HelloWorld.vue';
import Story from './components/Story.vue';
import Trailer from './components/Trailer.vue';
import Downloads from './components/Downloads.vue';
import Footer from './components/Footer.vue';
import TeamMember from './components/TeamMember.vue';

@Component({
	components: {
		Story,
		Trailer,
		Downloads,
		TeamMember,
		Footer,
		// HelloWorld,
	}
})
export default class App extends Vue {}
</script>

<style lang="scss">
@import "~bulma/sass/utilities/initial-variables";
$footer-background-color: $grey-darker;

@import "~bulma/sass/layout/footer";

a {
	color: $blue;
}

a:hover {
	color: $cyan;
}
</style>

<style>
#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 0px;
}
</style>
