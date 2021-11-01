<template>
<div class="app">
	<div id="navigation-bar ">
		<nav class="bg-gray-100">
			<div class="px-8 mx-auto">
				<div class="flex justify-around">
					<router-link to="/">Home</router-link>
					<a href="/"><h1>The<strong>Anime</strong>Database</h1></a>
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


