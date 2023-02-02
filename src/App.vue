<script setup lang="ts">
import { onMounted } from "vue";
let theme = "default";

const changeThemes = ($theme?: string) => {
	theme = $theme || "default";
	const link = createLink();
	link.href = `src/themes/${theme}.css`;
	return theme;
};

const createLink = (() => {
	let link: HTMLLinkElement | null = null;
	return () => {
		if (link) {
			return link;
		}
		link = document.createElement("link");
		link.rel = "stylesheet";
		link.type = "text/css";
		(document.querySelector("head") as HTMLElement).appendChild(link);
		return link;
	};
})();
</script>

<template>
	<div>
		<button @click="changeThemes('default')">default</button>
		<button @click="changeThemes('dark')">dark</button>
		<button @click="changeThemes('pink')">pink</button>
	</div>

	<div class="box">hello world</div>
</template>
<style>
body {
	background-color: var(--my-color);
}
.box {
	height: 500px;
	background: #fff;
	margin: 20px;
	border: 1px solid #000;
	color: var(--my-color);
}
</style>
