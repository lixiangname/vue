<template>
	<header>
		<div class="top-bar flex">
			<div class="back" @click="$router.go(-1);">
				<span class="icon-back"></span>
			</div>
			<div class="solt flex-item">
				<slot></slot>
			</div>

			<div class="menu" @click="show=true;">
				<div class="mask" v-show="show" @click.stop="show=false;"></div>
				<span class="icon-menu"></span>

				<ul class="menu-list" v-show="show">
					<li v-for="(item,index) in menu" :key="index">
						<router-link :to="item.url">
							<span class="fa" :class="item.icon"></span>
							<strong v-text="item.title"></strong>
						</router-link>
					</li>

				</ul>
			</div>
		</div>
		<div style="height:0.9rem;"></div>
	</header>
</template>

<script>
	import "@/assets/css/font-awesome.css";
	export default {

		data() {
			return {
				show: false,
				menu: [{
					icon: 'fa-home',
					title: '首页',
					url: '/'
				}, {
					icon: 'fa-search',
					title: '分类搜索',
					url: '/category'
				}, {
					icon: 'fa-user',
					title: '我的京东',
					url: '/user'
				}, {
					icon: 'fa fa-paw',
					title: '浏览记录',
					url: '#'
				}, {
					icon: 'fa-heart-o',
					title: '我的关注',
					url: '#'
				}, {
					icon: 'fa-share',
					title: '分享',
					url: '#'
				}],
			}
		}

	}
</script>

<style>
	.top-bar {
		height: 0.9rem;
		width: 100%;
		position: fixed;
		top: 0;
		left: 0;
		background-color: #FFFFFF;
		border-bottom: 1px solid #e5e5e5;
		z-index: 1000;
	}
	
	.top-bar .solt {
		padding: 0px 0.6rem;
	}
	
	.top-bar .icon-back {
		display: block;
		margin: 0.24rem 0 0 0.2rem;
		width: 0.4rem;
		height: 0.4rem;
		background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACgAAAAoCAYAAACM/rhtAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyhpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNi1jMDY3IDc5LjE1Nzc0NywgMjAxNS8wMy8zMC0yMzo0MDo0MiAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIDIwMTUgKE1hY2ludG9zaCkiIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6NzRCQTEyN0IzOTcwMTFFODk1OEZCOEVCMEE2QUU1NkUiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6NzRCQTEyN0MzOTcwMTFFODk1OEZCOEVCMEE2QUU1NkUiPiA8eG1wTU06RGVyaXZlZEZyb20gc3RSZWY6aW5zdGFuY2VJRD0ieG1wLmlpZDo3NEJBMTI3OTM5NzAxMUU4OTU4RkI4RUIwQTZBRTU2RSIgc3RSZWY6ZG9jdW1lbnRJRD0ieG1wLmRpZDo3NEJBMTI3QTM5NzAxMUU4OTU4RkI4RUIwQTZBRTU2RSIvPiA8L3JkZjpEZXNjcmlwdGlvbj4gPC9yZGY6UkRGPiA8L3g6eG1wbWV0YT4gPD94cGFja2V0IGVuZD0iciI/PulQWg8AAAF/SURBVHja7Ni9SsRAEAfwnd1wldiIlqK1td4LiL7CFQaFCHZWgmVqH+GK4FejryA+gPcA9vZ2YnVkd5yAcBLOYJKZ3UWyRbIchPsxSzb/HUBEFfPQKvIxAP89MGn7wPHpuTLOtXoGMdl1WF4rUBug9cX25tpdnufRVHBssXxGhTu0Y6yjs1P6bRTLEo9Lp56ohquLasKcbk5sifvgAMBRRc5oWoau4FIcfRJOaPoQ+i1uwt2H3mZYcdxAdhwnUATHBRTDcQBFcX2B4rg+QC+4rsA9X7gunzpQ1j7S3QuudQWz7HKFjjBbNXNR4QhaYcMCi+LqkwxvtbSX0SWNJVGjAZhQ1T4W8Qk11e2GpkexRP5ZotVBHUmXWwlk122mCZnGAPwV+b3caQxAL0iOsCCK5IpbYkjOwCqC5I787EiJQxMrUurY2YScxNI8Woq0qKZtUpR062NmQB/+RALgqM3/+mgevRhI9imMvVIcewdtqtbH/M8BdOhRD8DA40uAAQDL2thNJDxLvAAAAABJRU5ErkJggg==) no-repeat 50%;
		background-position: 0 0;
		background-size: contain;
	}
	
	.top-bar .icon-menu {
		display: block;
		margin: 0.24rem 0.24rem 0.24rem 0.2rem;
		width: 0.4rem;
		height: 0.4rem;
		background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEgAAAAMCAYAAAG2I8urAAAAAXNSR0IArs4c6QAAAddJREFUSA3VVr1OwzAQto0oqgQPABszD4BY4TVIfwR0aBgQb8ALIAbSoVD1J7wGrFRiAokVsbGwMSAVCXPn4PSSxklMGol6SM539913/jnbjEFzGu0j/GOTUvJACr5Owx0L5SBZVxtqDffbqbel7gNqG6K441ABglN3PyJ9YBHKk2qZXNVdzcJVJAwJzR92IvmgjlLH7RSrBhNPAwPohs508FqPf5wIjQVhOtg0xrgNA1GsQIW5yZ7ZFrVwTA+XIaLm/M4feHsRXUKnDOzSy+s7Lnclxrf59PhwFtPNdMvACn/orTGYEcpWXals0L5JLgOrtnGwx/k54+x51L/c4ZxPq8iUza9+3liss1vY57uUdzTwRJ6kysDi6RBJBhOrNY/vaYJGuQRscrlKtmVMIstQEJucEJenWbxGe0GsmKkodQZ1royExFAGVlVZq3Wy/jn5uknaT4ofkqxWlve73Ys3kk9hcRF4oerhtieXeeqoOWv5g3yrmRoHjIvCC6cQnM95m41vVkybWDa+c+YVeHllxQztNr4hyCDYxLLxNdCFaptY4CvwZo8/PcJgVIBzSPlSXQF5UXjDF716iTbdQ8b4AZxJwb2qZlv2Rn3vOs9L5C/z9d95fwDELzC7i+rQHQAAAABJRU5ErkJggg==) no-repeat 50%;
		background-size: 0.4rem;
	}
	
	.top-bar .menu {
		position: relative;
	}
	
	.mask {
		position: fixed;
		top: 0;
		bottom: 0;
		left: 0;
		right: 0;
		z-index: 999;
		/*background-color: red;*/
	}
	
	.menu-list {
		position: absolute;
		top: 1.1rem;
		right: 0.2rem;
		z-index: 1000;
		border-radius: 4px;
		width: 2.5rem;
		background: rgba(0, 0, 0, .9);
		list-style: none;
		margin: 0;
		padding: 0;
	}
	
	.menu-list:before {
		position: absolute;
		top: -0.1rem;
		right: 0.1rem;
		width: 0.21rem;
		height: 0.1rem;
		background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABIAAAAJCAYAAAFI2EyZAAAAAXNSR0IArs4c6QAAAIVJREFUKBWVkN0NgDAIhDFu4SauZRyjcSxHcQ57pWdA6ENJWn78OCoiamf3guDpR2uLy2oSEQX9/YmEfs8N9NAFw7CjRfHaYkkbXH11mf7dXmuYcPObhfBymgMJWSCAgDLgDzJPvV0x4mmzAniNPakg981JgEZ7J0N/1aAwodCMAHvpm+ALCRYgJABhMPUAAAAASUVORK5CYII=) no-repeat 50%;
		background-size: 100% 100%;
		content: "";
	}
	
	.menu-list li {
		position: relative;
		margin-left: 0.8rem;
		border-bottom: 1px solid hsla(0, 0%, 100%, .2);
		height: 0.8rem;
		line-height: 0.8rem;
	}
	
	.menu-list li a {
		display: block;
		border: 0;
		width: 100%;
		font-size: 0.28rem;
		color: #fff;
	}
	
	.menu-list span.fa {
		position: absolute;
		top: 0;
		left: -0.8rem;
		width: 0.8rem;
		height: 0.8rem;
		line-height: 0.8rem;
		text-align: center;
		font-size: 0.3rem;
	}
	
	.menu-list li strong {
		font-weight: 400;
		font-size: 0.28rem;
		color: #fff;
	}
</style>