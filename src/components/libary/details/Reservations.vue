<template>
	<div class="card" v-if="material">
		<div class="card-header">
			<h4 class="card-title mb-0">Reserveringen</h4>
		</div>
		<div class="card-body">
			<table
				class="table mx-0 table-striped border-top mb-0 table-hover border"
				v-if="material.reservations && Object.values(material.reservations).length"
			>
				<thead class>
					<tr>
						<th class="ps-4">#</th>
						<th>Gebruiker</th>
						<th>Hoeveelheid</th>
						<th>Prijs</th>

						<th class="text-center">Betaald</th>
						<th class="text-end pe-4">Acties</th>
					</tr>
				</thead>
				<tbody>
					<ReservationAdmin
						v-for="(reservation, key, i) of material.reservations"
						:key="i"
						:reservation="reservation"
						:material="material"
						:index="i"
					/>
				</tbody>
			</table>
			<p v-else>Er zijn nog geen reserveringen voor dit materiaal.</p>
		</div>
	</div>
</template>

<script>
import ReservationAdmin from "@/components/dashboard/reservations/ReservationAdmin.vue";

export default {
	props: ["material"],
	components: { ReservationAdmin },
};
</script>
