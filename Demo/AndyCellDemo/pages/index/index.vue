<template>
	<view class="content">
		<adCell text="普通"></adCell>
		<adCell text="点击事件" @click="onClick"></adCell>
		<adCell text="隐藏箭头" showArrow="false"></adCell>
		<adCell icon="/static/logo.png" text="带图标"></adCell>
		<adCell text="支持滑动" :swipeOptions="options" @swipeClick="swipeClick(item, $event)" @swipeChange="swipeChange"></adCell>
		<adCell text="主文本" detail="副文本"></adCell>
		<adCell text="右侧另外添加自定义View" note="可以自定义按钮或角标等等">
			<view class="customView" @click="customClick">自定义View</view>
		</adCell>
		<adCell text="主文本超出会点点点主文本超出会点点点主文本超出会点点点主文本超出会点点点主文本超出会点点点主文本超出会点点点"></adCell>
		<adCell detail="副文本超出也会点点点副文本超出也会点点点副文本超出也会点点点副文本超出也会点点点副文本超出也会点点点"></adCell>
		<adCell text="主文本副文本同时超出主文本副文本同时超出主文本副文本同时超出" detail="主文本副文本同时超出主文本副文本同时超出主文本副文本同时超出"></adCell>
		<adCell text="必填符号" mustInput="true" detail="副文本"></adCell>
		<adCell text="下面可以有6条子文本" detail="副文本" note="子文本1" note1="子文本2" note2="子文本3" note3="子文本4" note4="子文本5" note5="子文本6"></adCell>
		<adCell text="子文本超出都可以换行" :swipeOptions="options" detail="副文本" note="子文本1子文本1子文本1子文本1子文本1子文本1子文本1子文本1子文本1子文本1" note1="子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2子文本2"></adCell>
	</view>
</template>

<script>
	import adCell from '@/component/andy-adcell/andy-adcell.vue';
	export default {
		components:{adCell},
		data() {
			return {
				// 滑动数据
				options:[
					{
						text: '删除',
						style: {
							backgroundColor: '#dd524d'
						}
					},{
						text: '设置',
						style: {
							backgroundColor: '#2B85D8'
						}
					}
				]
			}
		},
		onLoad() {

		},
		methods: {
			// 点击事件
			onClick: function(e) {
				uni.showToast({
					icon: 'none',
					title: '点击事件'
				});
			},
			// 自定义View点击
			customClick: function(e) {
				uni.showToast({
					icon: 'none',
					title: '点击了自定义的View'
				});
			},
			// 滑动后点击按钮
			swipeClick: function(item, e){
				uni.showToast({
					icon: 'none',
					title: '当前点击的是第'+e.index+'个按钮，点击内容是: '+e.content.text
				});
			},
			// 滑动状态改变
			swipeChange: function(open){
				uni.showToast({
					icon: 'none',
					title: '当前开启状态：'+ open
				});
			},
		}
	}
</script>

<style>
	.content {
		width: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding-bottom: constant(safe-area-inset-bottom);
		padding-bottom: env(safe-area-inset-bottom);
	}
	
	.customView {
		color: #FFFFFF;
		text-align: center;
		width: 150upx;
		height: 50upx;
		line-height: 50upx;
		border-radius: 10upx;
		background-color: #007AFF;
	}
</style>
