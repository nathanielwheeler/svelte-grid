<script>
	import { onMount } from 'svelte'

	function makeRows(rows, cols) {
		const gridContainer = document.getElementById("grid-container");
		gridContainer.style.setProperty('--grid-rows', rows);
		gridContainer.style.setProperty('--grid-cols', cols);
		// TODO revise this function to give each cell an XY coordinate in the form of '.cell-X-Y'
		for (let c = 0; c < (rows * cols); c++) {
			let cell = document.createElement("div");
			cell.innerText = (c + 1);
			cell.className = `grid-cell cell-${c + 1}` // This gives a way to refer to coordinates by number
			gridContainer.appendChild(cell);
		};
	};

	onMount(fn => {
		makeRows(8, 8);
	})

</script>

<div id="grid-container"></div>