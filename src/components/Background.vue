<script lang="ts">
	import { defineComponent } from "vue";
	export default defineComponent({});
</script>

««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
	<div class="circles">
		<svg class="circle1 circle" >
			<circle cx="250" cy="250" r="250"></circle>
		</svg>
		<svg class="circle2 circle" >
			<circle cx="250" cy="250" r="250"></circle>
		</svg>
		<svg class="circle3 circle" >
			<circle cx="250" cy="250" r="250"></circle>
		</svg>
		<svg class="circle4 circle" >
			<circle cx="250" cy="250" r="250"></circle>
		</svg>
		<svg class="circle5 circle" >
			<circle cx="250" cy="250" r="250"></circle>
		</svg>
	</div>
</template>

««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style>
	.circles {
		width: 250;
		height: 250;
		position: fixed;
		top: 0;
       
		z-index: 1;
		background-color: #102510AA;
		& .circle {
            position: absolute;
             
		}
		& .circle1 {
		}
		& .circle2 {
			
		}
		& .circle3 {
			
		}
		& .circle4 {
			
		}
		& .circle5 {
			
		}
	}
</style>
