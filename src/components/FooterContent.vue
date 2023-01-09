<template>
  <v-footer class="pa-6" color="black" dark>
		<v-row class="justify-center pa-6">
			<v-btn v-for="social in socials" 
				:key="social[0]" 
				class="mx-4" 
				dark 
				icon 
				:href="social[1]" 
				target="external"
			>
				<v-icon size="24px">
					{{ social[0] }}
				</v-icon>
			</v-btn>
		</v-row>
		<v-col class="text-center" cols="12">
			{{ new Date().getFullYear() }} — <strong>tEykamp</strong>
		</v-col>
		<v-row class="d-flex justify-end">
			<v-btn
				x-small
				dark
				outlined
				rounded
				href="https://github.com/teykamp/earthstory/issues" 
				target="_blank"
			>Feedback</v-btn>
		</v-row>
  </v-footer>
</template>

<script>
export default {
	name: 'FooterContent',
	data() {
		return {
			socials: [
				['mdi-github', 'https://github.com/teykamp'],
				['mdi-xml', 'https://github.com/teykamp/earthstory'],
			],
		}
	},
}
</script>