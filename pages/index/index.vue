<template>
	<view class="content">
		<image v-for="index in 3" :key='index' src="../../static/test.png" style="width: 750rpx; height: 1136rpx;" mode="scaleToFill"></image>
		<!-- 在页面最下方添加站位视图，高度等于 tabBar 的高度 -->
		<view class="edgeInsetBottom" :style="{ height : tabbarHeight + 'px'}"></view>
		<!-- 绝对定位的视图需要考虑 tabBar 遮挡的问题，bottom 应该加上 tabBar 的高度 -->
		<view class="fixedView"></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabbarHeight: 0
			}
		},
		onReady() {
			// 获取 tabBar 的高度
			this.tabbarHeight = uni.getSystemInfoSync().windowBottom;
		}
	}
</script>

<style>
	.content {
		background-color: #FFFFFF;
		line-height: 0;
	}

	.edgeInsetBottom {
		width: 750rpx;
		background-color: #FFFFFF;
	}

	.fixedView {
		background-color: #4CD964;
		position: fixed;
		width: 750rpx;
		height: 30px;
		bottom: var(--window-bottom);
	}
</style>
