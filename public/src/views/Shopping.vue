<template>

	<div>
		<top-bar>
			<div class="title">购物车</div>
		</top-bar>
		<shopping-product v-for="n in 10" ></shopping-product>
		<div class="shoppingbar flex">
			<div class="shoppingbar-sumbit">
				<check-box></check-box>
				<span>全选</span>
			</div>
			<div class="bar-right flex-item">
				总计:
				<span>￥{{sum}}</span>
			</div>
			<div class="shoppingbar-buy">
				去结算<span>({{count}})</span>
			</div>
		</div>
	</div>

</template>

<script>
	import TopBar from "@/components/TopBar.vue";
	import CheckBox from "@/components/CheckBox.vue";
	import ShoppingProduct from "@/components/ShoppingProduct";
	export default {
		data() {
			return {
				sum: 0,
				count: 0
			}
		},
		components: {
			TopBar,
			CheckBox,
			ShoppingProduct
		}
	}
</script>

<style>
	.title {
		height: 0.88rem;
		line-height: 0.88rem;
		font-size: 0.36rem;
		color: #333;
		text-align: center;
	}
	
	.shoppingbar {
		z-index: 99999;
		width: 100%;
		position: fixed;
		left: 0;
		bottom: 0;
		height: 1rem;
		background-color: #FFFFFF;
	}
	
	.shoppingbar:before {
		content: "";
		position: absolute;
		z-index: 1;
		pointer-events: none;
		background-color: #ddd;
		height: 1px;
		left: 0;
		right: 0;
		top: 0;
	}
	.shoppingbar-sumbit {
		width: 0.8rem;
		padding-top: 0.64rem;
		font-size: 0.2rem;
		text-align: center;
		height: 0.3rem;
		color: #999;
		position: relative;
	}
	.shoppingbar-sumbit .check-box {
		position: absolute;
		left: 50%;
		top: 0.2rem;
		content: "";
		margin-left: -0.2rem;
	}
	.bar-right {
		padding-top: 0.2rem;
		font-weight: 700;
		line-height: 1em;
		height: 1rem;
		text-align: right;
		float: left;
		font-size: 0.32rem;
	}
	.shoppingbar-buy {
		float: right;
		display: block;
		width: 2.2rem;
		height: 1rem;
		margin-left: 0.2rem;
		line-height: 1rem;
		font-size: 0.32rem;
		text-align: center;
		font-weight: 700;
		background: #e4393c;
		color: #fff;
	}
	.bar-right span{
		color: #e93b3d;
	}
</style>