<script lang="ts">
	import { page } from '$app/stores';
	import logo from './logo.png';

	let orgName = '강일동 어린음악대';
</script>

<header>
	<div class="corner-left">
		<img src={logo} alt="Logo" />
		<h1>{orgName}</h1>
	</div>

	<div class="corner-right">
		<!-- TODO put something else here? github link? -->
	</div>
</header>

<style lang="scss">
	$background: rgba(255, 255, 255, 0.7);

	header {
		display: flex;
		justify-content: space-between;
		height: 6em;
		background: global.$primary-color;
	}

	.corner-left,
	.corner-right {
		height: 100%;
		padding-left: 2%;
		padding-right: 2%;
		display: flex;
		flex-direction: row;
		align-items: center;
		img {
			width: 100%;
			height: 100%;
			object-fit: contain;
		}
		h1 {
			line-height: 1;
			white-space: nowrap;
			margin-left: 1em;
			margin-right: 1em;
		}
	}

	.corner-left > img {
		object-position: left center;
	}
	.corner-right > img {
		object-position: right center;
	}

	nav {
		display: flex;
		justify-content: center;
	}

	svg {
		width: 2em;
		height: 3em;
		display: block;
	}

	path {
		fill: $background;
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: $background;
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;

		&.active::before {
			$size: 6px;
			content: '';
			width: 0;
			height: 0;
			position: absolute;
			top: 0;
			left: calc(50% - $size);
			border: $size solid transparent;
			border-top: $size solid global.$accent-color;
		}
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 1em;
		color: var(--heading-color);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: global.$accent-color;
	}
</style>
