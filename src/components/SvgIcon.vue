<template>
  <svg class="icon" :class="{ 'icon-spin': spin }">
    <use :xlink:href="`#${icon}`" />
  </svg>
</template>

<script>
export default {
	name: 'SvgIcon',
	props: {
		icon: {
			type: String,
			required: true,
		},
		spin: {
			type: Boolean,
			default: false,
		},
	},
}
</script>

<style>
svg.icon {
  width: 1em;
	height: 1em;
  vertical-align: middle;
  margin-bottom: 0.125em;
	fill: currentColor;
}

svg.icon-spin {
	animation: icon-spin 2s infinite linear;
}

@keyframes icon-spin {
	from {
		transform: rotate(0deg);
	}
	to {
		transform: rotate(359deg);
	}
}
</style>
