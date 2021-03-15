<template>
	<div class="brandBorder" draggable="false">
		<div>A</div>
		<div>红桃</div>
	</div>
</template>

<script>
	export default {
		
	}
</script>

<style>
	.brandBorder{
    display: inline-block;
    width: 135px;
    margin-top: 1%;
    height: 80%;
    border: 1px solid;
    border-radius: 5px;
    text-align: left;
    padding: 2px;
    position: absolute;
    background: #FFF;
		background-image: url(../assets/2.jpg);
    bottom: 0px;
		cursor: pointer;
		
	}
	.brandBorder div{
		
		color: red;
	}
	
</style>
