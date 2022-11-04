<template>
	<div class="hello">
		<div>
			<img src="/assets/logo.png">
		</div>
		<div v-if="selectedHero" class="hero-card">
			<div class="portrait-wrapper">
				<img :src="`/assets/hero-portraits/${this.selectedHero.heroPortrait}`" class="hero-portrait">
			</div>
			<div class="info-wrapper">
				<div class="hero-info">
					<img :src="'/assets/hero-icons/' + selectedHero.heroIcon" class="hero-icon">
					<div class="content">
						{{selectedHero.name}}
					</div>
				</div>
				<div class="hero-info">
					<RoleDisplay :role="selectedHero.role"></RoleDisplay>
					<div class="content">
						{{ selectedHero.role }}
					</div>
				</div>
				<div v-if="selectedHero.lineOne" class="hero-info">
					<div class="content">
						{{ selectedHero.lineOne }}
					</div>
				</div>
				<div v-if="selectedHero.lineTwo" class="hero-info">
					<div class="content">
						{{ selectedHero.lineTwo }}
					</div>
				</div>
				<div v-if="selectedHero.lineThree" class="hero-info">
					<div class="content">
						{{ selectedHero.lineThree }}
					</div>
				</div>
				<div v-if="selectedHero.lineFour" class="hero-info">
					<div class="content">
						{{ selectedHero.lineFour }}
					</div>
				</div>
			</div>
		</div>
		<button @click="selectHero">I NEED A HERO</button>
	</div>
</template>

<script>
import heroesData from '../hero-data.json'
import RoleDisplay from './RoleDisplay'

export default {
	name: 'Main',
	data () {
		return {
			selectedHero : false,
			heroes: heroesData.heroes
		}
	},
	methods: {
		selectHero() {
			this.selectedHero = this.heroes[Math.floor(Math.random() * this.heroes.length)]
		}
	},
	components: { RoleDisplay }
}
</script>

<style>
html {
	background: url("~/assets/ow-heroes-bg.jpg") no-repeat top center;
	background-color: #d0c7dc;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100vw;
    height: 100vh;
}
.hero-icon {
	height: 100%;
}
.hero-info {
	height: 2em;
	display: flex;
	border-radius: 5px;
	background: rgba(40, 53, 79, 0.9);
	color: white;
	justify-content: left;
	align-items: center;
	padding: 0.2em;
	margin-bottom: 2.5px;
	margin-top: 2.5px;
	width: 100%;
}
.hero-info * {
	margin-left: 0.5em;
}

.info-wrapper {
	display: flex;
	flex-grow: 1;
	flex-wrap: wrap;
	align-content: center;
}

.hero-card {
	display: flex;
	border-radius: 5px;
	background: white;
	padding: 0.5em 0.5em 0.5em 0.5em;
	margin: 2em 2em 0 2em;
	min-height: 16.5em;
	align-items: center;
}
.portrait-wrapper {
	background: url("~/assets/hero-portrait-bg.jpg");
	border-radius: 5px;
	margin-right: 0.5em;
	width: 10em;
	height: 16.5em;
}

.hero-portrait {
	width: 10em;
	height: 16.5em;
	/* background-size: cover; */
}

button {
	margin-top: 1em;
}
</style>
