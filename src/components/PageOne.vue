<script setup>
	import FormContainer from "./FormContainer.vue";
	import Form from "./Form.vue";
	import Input from "./Input.vue";
	import Progress from "./Progress.vue";
	import Buttons from "./Buttons.vue";
	import { useVuelidate } from "@vuelidate/core";
	import {
		helpers,
		required,
		minLength,
		maxLength,
	} from "@vuelidate/validators";
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

	const submitForm = () => {
		const isFormCorrect = v.value.$validate();
		console.log(state.value.secondName);
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
						v-model:first-name="state.firstName"
						@emit-blur="v.firstName.$touch"
					>
						<template v-slot:field-name>First Name</template>
						<template v-slot:error>{{
							v.firstName.$error
								? v.firstName.$errors[0].$message
								: ""
						}}</template>
					</Input>

					<Input v-model:second-name="state.secondName">
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
