<template>
	<div class="shopping-product">
		<div class="product-select">
			<check-box></check-box>
		</div>
		<div class="product-image">
			<img src="https://img10.360buyimg.com/mobilecms/s117x117_jfs/t1/22965/4/12454/235761/5c983056Edbdeb7af/a462bc4028c3f3d5.jpg!q70.dpg.webp" />
		</div>
		<div class="product-title">
			耐克NIKE 男子 休闲鞋 TANJUN 运动鞋 812654-011黑色44码
		</div>
		<div class="product-sumbit">
			<div class="product-sumbit-price left">
				￥368.00
			</div>
			<div class=" product-sumbit-button right">
				<span>-</span>
				<span>1</span>
				<span>+</span>
			</div>
		</div>
	</div>
</template>

<script>
	import CheckBox from "@/components/CheckBox.vue";
	export default {
		data() {
			return {}
		},
		components: {
			CheckBox,
		}
	}
</script>

<style>
	.shopping-product {
		z-index: 1;
		position: relative;
		min-height: 1.5rem;
		padding: 0.1rem 0.2rem 0.3rem 2.56rem;
		background: #fff;
	}
	
	.product-select {
		position: absolute;
		top: 0.7rem;
		left: 0.3rem
	}
	
	.product-image img {
		position: absolute;
		left: 0.86rem;
		top: 0.1rem;
		display: block;
		width: 1.5rem;
		height: 1.5rem;
	}
	
	.product-title {
		font-size: 14px;
		margin-bottom: 5px;
		word-break: break-all
	}
	
	.product-sumbit-price {
		color: #e93b3d;
		font-size:0.3rem;
		
	}
	
	.product-sumbit-button {
		position: relative;
		display: block;
		width: 2rem;
		border-radius: 4px;
		overflow: hidden;
		background-color: #f7f7f7;
	}
	
	.product-sumbit-button span {
		position: relative;
		float: left;
		width: 0.6rem;
		height: 0.6rem;
		line-height: 0.6rem;
		text-align: center;
		display: inline-block;
	}
</style>