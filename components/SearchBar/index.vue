<template name="SearchBar">
	<view class="nav-box bg-gradual-blue">
		<view class="nav-search">
			<text class="nav-search-icon text-gray cuIcon-search"></text>
			<input 
			class="nav-input" 
			type="text" 
			value=""
			confirm-type="search"
			@input="onKeyInput"
			@confirm="onKeyDown"
			/>
		</view>
	</view>
</template>

<script>
	export default {
		name: "SearchBar",
		props:{},
		data() {
			return {
				inputValue: '',
			}
		},
		methods:{
			onKeyInput: function (e) {
				this.inputValue = e.target.value;
			},
			onKeyDown: function (e) {
				this.$emit('returnData', e.target.value);
			}
		}
	}
</script>

<style>
	@import url('./index.css');
</style>
