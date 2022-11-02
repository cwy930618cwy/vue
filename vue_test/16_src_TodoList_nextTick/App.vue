<template>
	<div class="home">
		<div id="box">
			<div v-for="(item, index) in boxArray" :key="index">
				{{ item }}
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				boxArray: [1, 2, 3],
			};
		},
		mounted() {
			this.boxArray = [4, 5, 6, 7, 8, 9];
			this.$nextTick(() => {
				console.log('所有box的宽度为：', getComputedStyle(box).width)
			});
		},
	};
</script>

<style>
#box {
	border: 1px solid red;
	display: inline-block;
}
#box > div {
	display: inline-block;
	width: 100px;
	height: 100px;
}
</style>
