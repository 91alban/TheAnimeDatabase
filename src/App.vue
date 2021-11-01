<template>
<div class="app">
	<div id="navigation-bar">
		<nav class="bg-indigo-600">
			<div class="p-8 mx-auto">
				<div class="flex justify-around items-center text-white">
					<router-link to="/">Home</router-link>
					<a href="/"><h1 class="hover:text-white text-4xl">The<strong>Anime</strong>Database</h1></a>
					<router-link to="/about">About</router-link>
				</div> 
			</div>
		</nav>
	</div>
</div>
  <router-view/>
</template>

<script>
import './assets/tailwind.css';

export default {

}
</script>


