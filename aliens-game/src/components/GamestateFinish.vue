<template>
	<div class="modal">
		<div>
			<h2 v-if="uiState === 'won'">You won!</h2>
			<h2 v-else>You lost</h2>
			<div class="center">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					viewBox="0 0 131 131"
					aria-labelledby="face"
					role="presentation"
					width="70"
					height="70"
				>
					<title id="face">Face Icon</title>
					<defs></defs>
					<circle class="cls-1" cx="65.5" cy="65.5" r="64" />
					<circle class="cls-2" cx="95" cy="65.8" r="7.5" />
					<circle class="cls-2" cx="36" cy="65.8" r="7.5" />
					<path
						:class="[uiState === 'lost' ? 'frown' : '', 'cls3']"
						d="M51,97s6,10,23,10S95,97,95,97"
						transform="translate(-8.5 -5.5)"
					/>
				</svg>
			</div>
			<button @click="restartGame">Let's play again</button>
		</div>
	</div>
</template>

<script>
import { mapMutations } from 'vuex';

export default {
	props: ['uiState'],
	methods: {
		...mapMutations(['restartGame']),
	},
};
</script>

<style scoped>
.frown {
  transform: rotate(180deg);
  transform-origin: 50% 50%;
}

.modal {
	padding-right: 100px;
	padding-left: 100px;
	text-align: center;
}

.center {
	display: flex;
	align-items: center;
	justify-content: center;
	margin-bottom: 1rem;
}

.cls-1 {
	fill: #fbb040;
	stroke: #231f20;
}

.cls-1,
.cls-3 {
	stroke-miterlimit: 10;
	stroke-width: 3px;
}

.cls-2 {
	fill: #231f20;
}

.cls-3 {
	fill: none;
	stroke: #be1e2d;
}
</style>