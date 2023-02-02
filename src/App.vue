<script setup lang="ts">
import { onMounted } from "vue";
import { themeChange } from "theme-change";

const themes = ["default", "dark", "pink"];

onMounted(() => {
	themeChange(false);
});
</script>

<template>
	<div>
		<button data-set-theme="">default</button>
		<button data-set-theme="dark">dark</button>
		<button data-set-theme="pink">pink</button>
	</div>

	<div
		style="
			height: 500px;
			background: #fff;
			margin: 20px;
			color: var(--my-color);
		"
	>
		hello world
	</div>
</template>
