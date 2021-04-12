<template>
	<Layout>
		<p>Main content goes here</p>
	</Layout>
</template>

<script>
import Layout from "./components/Layout.vue"
import NewsList from "./components/NewsList.vue"

export default {
	name: 'App',
	components: {
		Layout,
		NewsList
	},
}
</script>
