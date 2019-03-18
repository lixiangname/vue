<template>

	<div class="product">
		<top-bar>

			<ul class="flex top-bar-list">
				<li class="flex-item" :class="{active:navIndex==index}" v-for="(item,index) in nav" :key="index" @click="navIndex=index;"> 
					<span v-text="item.title"></span>
				</li>
			</ul>

		</top-bar>

		<!--https://item.m.jd.com/product/3668211.html?pps=reclike.FO4O605%3AFOFO4O37F8F33O13O6%3ACOF0415O2443O1FO8O7FFF5021813FOFO00226A83F53DE68050-->
		<h1>商品详情页{{$route.params.id}}</h1>
	</div>

</template>

<script>
	import TopBar from "@/components/TopBar";
	export default {

		data() {
			return {
				navIndex:0,
				nav:[{title:'商品'},{title:'评价'},{title:'详情'},{title:'推荐'}],
			};
		},
		components: {
			TopBar
		},
		created() {
			// 当前路由
			console.log(this.$route);
			console.log(this.$router);
		}

	}
</script>

<style>
	.top-bar-list {
		margin: 0;
		padding: 0;
		list-style: none;
		text-align: center;
		line-height: 0.9rem;
	}
	
	.top-bar-list li {
		font-size: 0.28rem;
	}
	
	.top-bar-list li.active span{
		color: #e4393c;
		padding-left: 0.26rem;
		background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAYBAMAAAABjmA/AAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAnUExURek7PUdwTO49Peg6Peo6Puc6Pek6POk6POg6POg7PeY8POg6POk6PApBjXgAAAANdFJOU/8ADttQPYvEqJYqW/KuifCQAAAAjklEQVQI10XOsRGCQBAF0D8eA6Imn4ERMh0tgDE2UDqgA2Ij7UA6gA6MjCnB0vzLBlxw92Z379+B/F7DgwQraI3C05AQc0ElfBCac40NOlzIE2LUuJM5gtpHMtPxc+yW1tuH15j8+hYHD1yhdPQoHO3yKG+GSNgbXsI81AocgNS+qlgLFwrrGNjFdFS9tj82HhIeoIR1QQAAAABJRU5ErkJggg==) no-repeat 0;
		background-size: 0.16rem;
	}
</style>