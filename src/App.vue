<template>
	<div id="app">
		<el-carousel :interval="4000" type="card" height="400px">
			<el-carousel-item v-for="item in 6" :key="item">
				<h3 class="medium">{{ item }}</h3>
			</el-carousel-item>
		</el-carousel>
		<div class="block">
			<span class="demonstration">默认不区分颜色</span>
			<el-rate v-model="value1"></el-rate>
		</div>
		<div class="block">
			<span class="demonstration">区分颜色</span>
			<el-rate v-model="value2" :colors="colors">
			</el-rate>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'App',
		data() {
			return {
				value1: null,
				value2: null,
				colors: ['#99A9BF', '#F7BA2A',
					'#FF9900'] // 等同于 { 2: '#99A9BF', 4: { value: '#F7BA2A', excluded: true }, 5: '#FF9900' }
			}
		}
	}
</script>

<style>
	.el-carousel__item h3 {
		color: #475669;
		font-size: 14px;
		opacity: 0.75;
		line-height: 200px;
		margin: 0;
	}

	.el-carousel__item:nth-child(2n) {
		background-color: #99a9bf;
	}

	.el-carousel__item:nth-child(2n+1) {
		background-color: #d3dce6;
	}
</style>
