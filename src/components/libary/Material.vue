<template>
	<router-link
		class="item d-table-row"
		:to="`${$route.fullPath}/${material.id}`"
		v-if="material.unitAvalible > 0"
	>
		<td>
			<MaterialThumbnail :images="material.images" :width="50" :height="50" />
		</td>
		<td>{{ material.name }}</td>
		<td class="d-none d-md-table-cell">{{ material.type }}</td>
		<td class="d-none d-md-table-cell">{{ material.length }}</td>
		<td class="d-none d-md-table-cell">{{ material.width }}</td>
		<td class="d-none d-md-table-cell">{{ material.thickness }}</td>
		<td>
			€{{ material.price }}
			<span class="d-none d-md-block"> per {{ material.priceUnit }}</span>
		</td>
	</router-link>
</template>

<script>
import MaterialThumbnail from "@/components/libary/MaterialThumbnail.vue";

export default {
	props: ["material"],
	components: { MaterialThumbnail },
	methods: {
		toItem() {
			this.$router.push(`${this.$route.fullPath}/${this.material.id}`);
		},
	},
};
</script>

<style lang="scss" scoped>
.item {
	cursor: pointer;
	text-decoration: none;
	color: #66615b;
	border-color: #ccc;
	&:hover {
		background: #f4f3ef;
	}
	&:nth-child(odd) {
		background: #f2f2f2;
	}
}
</style>
