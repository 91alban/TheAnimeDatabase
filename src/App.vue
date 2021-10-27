<template>
<div class="app">
</div>
  <div id="nav">
    <!-- <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> -->
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
header {
	padding-top: 50px;
	padding-bottom: 50px;
	h1 {
		color: #888;
		font-size: 42px;
		font-weight: 400;
		text-align: center;
		text-transform: uppercase;
		margin-bottom: 30px;
		strong {
			color: #313131;
		}
		&:hover {
			color: #313131;
		}
	}
	.search-box {
		display: flex;
		justify-content: center;
		padding-left: 30px;
		padding-right: 30px;
		.search-field {
			appearance: none;
			background: none;
			border: none;
			outline: none;
			background-color: #F3F3F3;
			box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.15);
			display: block;
			width: 100%;
			max-width: 600px;
			padding: 15px;
			border-radius: 8px;
			color: #313131;
			font-size: 20px;
			transition: 0.4s;
			&::placeholder {
				color: #AAA;
			}
			&:focus, &:valid {
				color: #FFF;
				background-color: #313131;
				box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.15);
			}
		}
	}
}
main {
	max-width: 1200px;
	margin: 0 auto;
	padding-left: 30px;
	padding-right: 30px;
	.cards {
		display: flex;
		flex-wrap: wrap;
		margin: 0 -8px;
	}
}
</style>
