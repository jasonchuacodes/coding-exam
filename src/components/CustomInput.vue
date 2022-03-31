<template>
  First Name: 
	<input type="text" 
		:value="firstName" 
		@input="$emit('update:first-name', $event.target.value)"
		placeholder="Enter first name"
	>
	Last Name: 
	<input type="text" 
		:value="lastName" 
		@input="$emit('update:last-name', $event.target.value)"
		placeholder="Enter last name"
	>
	
</template>
<script>
export default {
	props: {
		firstName: String,
		lastName: String
	},
	emits: ['update:first-name', 'update:last-name'],
}
</script>