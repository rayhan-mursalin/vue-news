<template>
	<Layout>
		<p>Main content goes here</p>
	</Layout>
</template>

<script>
import Layout from "./components/Layout.vue"
import NewsFilter from "./components/NewsFilter.vue"
import NewsList from "./components/NewsList.vue"
import axios from "axios"

export default {
	name: 'App',
	components: {
		Layout,
		NewsFilter,
		NewsList
	},
}
</script>
