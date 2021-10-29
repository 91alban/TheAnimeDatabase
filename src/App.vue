<template>
<div class="app">
	<div class="container">
		<div id="navigation-bar">
			<nav>
				<ul>
					<li><router-link to="/">Home</router-link></li>
					<li><router-link to="/about">About</router-link></li>
					<li><h1>The<strong>Anime</strong>Database</h1></li>
				</ul>
			</nav>
		</div>
	</div>
</div>
  <router-view/>
</template>

<script>

</script>


<style lang="scss">
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-family: 'Fira Sans', sans-serif;
}
a {
	text-decoration: none;
}
h1 {
		color: #888;
		font-size: 42px;
		font-weight: 400;
		text-align: center;
		text-transform: uppercase;
		margin-top: 30px;
		margin-bottom: 30px;
		strong {
			color: #ffffff;
		}
		&:hover {
			color: #ffffff;
		}
	}
.container {
  width: 100%;
  display: inline-block;
}
nav {
	overflow: hidden;
	background-color: #333;
	position: relative;
	top: 0;
	width: 100%;
	ul {
		text-align: center;
		list-style-type: none;
		margin: 0;
		padding: 15px;
		li {
			display: inline;
			font-family: "Fira Sans", sans-serif;
			font-size: 17px;
			a {
				color: #f2f2f2;
				text-decoration: none;
				padding: 14px;
				&:hover {
					background-color: #111;
				}
			}
		}
	}
}
</style>
