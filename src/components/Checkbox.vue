<template>
	<div class="form-check text-start">
		<label class="form-check-label">
			<input class="form-check-input" type="checkbox" :checked="check" @click="setCheck" />

			<span class="form-check-sign">
				<transition name="fade">
					<i class="fas fa-check" v-if="check"></i>
				</transition>
			</span>
			Ik accepteer
			<router-link :to="link" target="_blank">de voorwaarden</router-link>.
		</label>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				check: false
			};
		},
		methods: {
			setCheck() {
				this.check = !this.check;
				this.$emit("toggleCheck", this.check);
			}
		},
		emits: ["toggleCheck"],
		props: ["link"]
	};
</script>

<style lang="scss" scoped>
	.form-check .form-check-sign > i {
		color: white;
		font-size: 15px;
		position: absolute;
		top: 4px;
		left: 4px;
	}

	.form-check input[type="checkbox"]:checked + .form-check-sign:after {
		opacity: 0;
	}

	.fade-enter-active,
	.fade-leave-active {
		transition: opacity 0.5s;
	}
	.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
		opacity: 0;
	}
</style>