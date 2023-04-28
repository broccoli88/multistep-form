<script setup>
	import FormContainer from "./FormContainer.vue";
	import Form from "./Form.vue";
	import Input from "./Input.vue";
	import Progress from "./Progress.vue";
	import Buttons from "./Buttons.vue";
	import { useVuelidate } from "@vuelidate/core";
	import { required, minLength, maxLength } from "@vuelidate/validators";
	import { ref } from "vue";

	const state = ref({
		firstName: "",
		secondName: "",
		lastName: "",
	});

	const rules = {
		firstName: {
			required,
			minLength: minLength(3),
			maxLength: maxLength(15),
		},
		secondName: {
			required,
			minLength: minLength(3),
			maxLength: maxLength(15),
		},
		lastName: {
			required,
			minLength: minLength(3),
			maxLength: maxLength(15),
		},
	};
	const v = useVuelidate(rules, state);

	const firstName = ref("");
	const firstNameError = ref("");

	const submitForm = async () => {
		const isFormCorrect = await v.value.$validate();
		firstNameError.value = v.value.firstName.$errors[0].$message;
		console.log(v.value.firstName);
		if (!isFormCorrect) return;
	};
</script>

<template>
	<FormContainer>
		<template v-slot:form>
			<Form @submit-form="submitForm">
				<template v-slot:legend> Page One </template>
				<template v-slot:inputs>
					<Input
						v-model:first-name="firstName"
						:first-name-error="firstNameError"
					>
						<template v-slot:field-name>First Name</template>
						<template v-slot:error>{{ firstNameError }}</template>
					</Input>

					<Input>
						<template v-slot:field-name>Second Name</template>
					</Input>
					<Input>
						<template v-slot:field-name>Last Name</template>
					</Input>
					<Buttons />
				</template>
			</Form>

			<Progress />
		</template>
	</FormContainer>
</template>
