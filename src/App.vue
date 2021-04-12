<template>
	<Layout>
		<h2 class="mb-8 text-4xl font-bold text-center capitalize">
			News Section : <span class="text-green-700">{{ section }}</span>
		</h2>
		<NewsFilter v-model="section" :fetch="fetchNews" />
		<NewsList :posts="posts" />
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
	data() {
		return {
			section: "home",
			posts: [],
		}
	},
}
</script>
