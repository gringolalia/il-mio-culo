<template lang="pug">
v-container(fluid)
	v-slide-y-transition(mode='out-in')
		v-layout(column align-center)
			img.my-5(src='@/assets/biohazard.svg' alt='Netflix Vueing Habits' width='150px')
			h1 Honorary San Pavlovians
			h2.mb-3 The Hunger Poets of Old New York
			v-btn.white--text(large color="secondary") 
				i.material-icons.mr-2 waves
				| O Gai Saber
			blockquote
				footer.
					
					
</template>


<style scoped>
h1, h2 {
	font-weight: normal;
}
ul {
	list-style-type: none;
	padding: 0;
}
li {
	display: inline-block;
	margin: 0 10px;
}
a {
	color: #42b983;
}
</style>
