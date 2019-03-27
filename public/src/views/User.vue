<template>
	
	<div class="user">
		<top-bar>
			<div class="title">我的京东</div>
		</top-bar>
		<div class="usernav">
			<div class="userblock">
				<div class="userheard">
				</div>
				<div class="user-name"></div>
			</div>
		</div>
		<tab-bar></tab-bar>
	
	</div>
	
</template>

<script>
	import TabBar from "@/components/TabBar.vue";
	import TopBar from "@/components/TopBar.vue";
	export default{
		components:{
			TabBar,
			TopBar
		}
	}
	
</script>

<style>
	body{
		background-color: #666 !important;
	}
	.user .title {
		text-align: center;
		line-height: 0.88rem;
		font-size: 0.36rem;
		color: #333;
	}
	.usernav{
		    padding: 10px;
    background-color: #fff;
    height: 140px;
	}
	.userblock{
		
	}
	.userheard{}
	.user-name{}
</style>