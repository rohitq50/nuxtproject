<template>
	<header>
		<div class="menu-btn">
			<span class="menu-btn__burger"></span>
		</div>
		<nav class="nav">
			<ul class="menu-nav">
				<li :class="['menu-nav__item', activePath == '/' ? 'active' : '']">
					<nuxt-link to="/" @click.prevent="activePath = '/'" class="link menu-nav__link">Home</nuxt-link>
					<!-- <a href="#" class="menu-nav__link"  @click.prevent="navigate('/')" >Home</a> -->
				</li>
				<li :class="['menu-nav__item', activePath == '/about' ? 'active' : '']">
					<nuxt-link to="/about"  @click="activePath = '/about'" class="link menu-nav__link">About Me</nuxt-link>
					<!-- <a href="#" class="menu-nav__link"  @click.prevent="navigate('/about')">About Me</a> -->
				</li>
				<li :class="['menu-nav__item', activePath == '/projects' ? 'active' : '']">
					<nuxt-link to="/projects"  @click.prevent="activePath = '/project'" class="link menu-nav__link">My Projects</nuxt-link>
					<!-- <a href="#" class="menu-nav__link"  @click.prevent="navigate('/projects')">My Projects</a> -->
				</li>
				<li :class="['menu-nav__item', activePath == '/contact' ? 'active' : '']">
					<nuxt-link to="/contact"  @click.prevent="activePath = '/contact'" class="link menu-nav__link">Contact Me</nuxt-link>
					<!-- <a href="#" class="menu-nav__link"  @click.prevent="navigate('/contact')">Contact Me</a> -->
				</li>
			</ul>
		</nav>
	</header>
</template>

<script>
export default {
	name: 'Navbar',
	data() {
		return {
			activePath: '/'
		}
	},
	created() {
		this.navigate(window.location.pathname)
	},
	methods: {
		navigate(path) {
			this.activePath = path
			this.$router.push({path: path})
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
