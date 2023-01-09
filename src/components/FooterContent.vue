<template>
  <v-footer class="pt-6 pb-6" :color="backgroundColor" dark>
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
		<v-row class="d-flex justify-space-between align-end">
			<v-card :color="backgroundColor" dark>
				<v-row>
					<div class="d-flex text-overline align-center pl-6">Tools:</div>
					
					<v-col v-for="tool in tools" :key="tool[0]">
						<v-btn icon :href="tool[1]" target="_blank">
							<v-img :src="tool[0]" max-height="20" max-width="20" contain></v-img>
						</v-btn>
					</v-col>
				</v-row>
			</v-card>
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
			backgroundColor: 'black',
			tools: [['https://vue2-leaflet.netlify.app/logo.png', 'https://vue2-leaflet.netlify.app/'], 
				['https://cdn.vuetifyjs.com/docs/images/logos/vuetify-logo-v3-dark.svg', 'https://next.vuetifyjs.com/en/'], 
				['https://cdn.freebiesupply.com/logos/large/2x/vue-9-logo-png-transparent.png', 'https://vuejs.org/'], 
				['https://s3.amazonaws.com/images.seroundtable.com/google-maps-icon-1580992464.png', 'https://www.google.com/maps']
						],
		}
	},
}
</script>