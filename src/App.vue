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
const api = 'pwxKoDMnFt3cCGLpALZTAnw7ocv9f5WZ';

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
	methods: {
			async fetchNews() {
				try {
					const url = `https://api.nytimes.com/svc/topstories/v2/${this.section}.json?api-key=${api}`
					const response = await axios.get(url)
					const results = response.data.results
				} catch (err) {
					if (err.response) {
						// client received an error response (5xx, 4xx)
						console.log("Server Error:", err)
					} else if (err.request) {
						// client never received a response, or request never left
						console.log("Network Error:", err)
					} else {
						console.log("Client Error:", err)
					}
				}
		},
}
</script>
