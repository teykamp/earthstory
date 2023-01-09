<template>
  <v-footer class="pa-6" color="black" dark>
		<v-row class="justify-center pa-6">
			<v-btn v-for="social in socials" 
			:key="social" 
			class="mx-4" 
			dark 
			icon 
			:href="social[1]" 
			target="external">
				<v-icon size="24px">
					{{ social[0] }}
				</v-icon>
			</v-btn>
		</v-row>
		<v-col class="text-center" cols="12">
			{{ new Date().getFullYear() }} — <strong>tEykamp</strong>
		</v-col>
  </v-footer>
</template>

<script>
export default {
	name: 'FooterContent',
	data() {
		return {
			socials: [
				['mdi-github', 'https://github.com/teykamp'],
				['mdi-file-code', 'https://github.com/teykamp/earthstory'],
			],
		}
	},
}
</script>