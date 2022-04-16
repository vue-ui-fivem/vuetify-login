<template>
	<v-app class="overflow-hidden">
		<v-app-bar app dark color="grey">
			<v-toolbar-title>Vue Login</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-btn rounded class="ma-3">Home</v-btn>
			<v-btn rounded class="ma-3">Login</v-btn>
			<v-btn rounded class="ma-3">About</v-btn>
			<v-btn rounded class="ma-3">Contact us</v-btn>
		</v-app-bar>

		<v-main color="black">
			<v-card class="mx-auto mt-9" dark width="500" >
				<v-card-title>Benike</v-card-title>
				<v-card-text>
					<v-text-field label="Username" prepend-icon="mdi-account-circle"/>
					<v-text-field label="Username" :type="showPassword ? 'text': 'password'" prepend-icon="mdi-lock" :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'" @click:append="showPassword = !showPassword"/>
				</v-card-text>

				<v-card-actions class="justify-center">
					<v-btn color="red">Register</v-btn>
					<v-btn color="success">Login</v-btn>
				</v-card-actions>
			</v-card>
		</v-main>

		
		<v-footer dark padless class="flex-column">
			<v-row class="ma-1">
				<v-btn v-for="link in links" :key="link" color="white" text rounded class="my-2"> {{ link }} </v-btn>
			</v-row>
			<v-col class="dark py-4 text-center white--text"> {{ new Date().getFullYear() }} — <strong>Vuetify</strong> </v-col>
		</v-footer>
	</v-app>
</template>


<script>
export default {
	data() {
		return{
			showPassword:false,
			links: [
				'Home',
				'About Us',
				'Team',
				'Services',
				'Blog',
				'Contact Us',
			],
		}
	}
}
</script>

<style>
html { overflow-y: auto }
</style>