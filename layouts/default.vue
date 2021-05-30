<template>
	<div class="main">
		<div id="nav">
			<Navbar />
			<Footer :vertical="vertical" />
		</div>
		<Nuxt />
	</div>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
import Footer from '@/components/Footer.vue'
export default {
	name: "default",
	components: {
		Navbar,
		Footer
	},
	data() {
		return {
			vertical: false
		}
	},
	watch:{
    	$route (){
			//to, from
			//set here the initial value for new routes
        	this.vertical = false
    	}
	},
}
</script>

<style lang="scss">
#__layout .main {
	height: 100vh;
}
</style>
