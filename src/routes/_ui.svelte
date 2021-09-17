<script>
	import SVG from "$lib/svg.svelte"

	let fulscreen = false
	let menu = false
	let speed = 1
</script>

    <div id="ui">
		<div class="btn" id="menu" class:menu on:click={() => {menu = !menu}}>
			<SVG type="angle" size=20 />
		</div>
        <div class="btn" id="fullScreen" on:click={() => {fulscreen = !fulscreen}}>
			<SVG type={fulscreen ? "fullscreen_close" : "fullscreen_open"} size =25 />
		</div>

        <div class="panel01" class:menu>
            <div class="btn" id="showAnnotation">
				<SVG type="info" size =30 />
			</div>
            <div class="btn" id="autoRotate">
				<SVG type="rotate" size =30 />
			</div>
			<div class="btn" id="autoRotateDirection">
				<SVG type="direction" size=20 />
			</div>
            <div class="btn" id="autoRotateSpeed"on:click={
			() => {
				speed = speed + 1
				if (speed > 3){

					speed = 1;
				}
				
				}
			}>
				<SVG type={`speed${speed}`} size={15 + (speed - 1) * 7.5} />
			</div>
			
			<div  class="btn color">
				<input type="color" id="color">

			</div>
        </div>
    </div>



	<style>
	
		#ui {
			position: absolute;
			inset: 0;

			pointer-events: none;
		}

		.btn {
			display: flex;
			align-items: center;
			justify-content: center;

			width: 50px;
			height: 50px;

			border-radius: 50%;
			background-size: contain;

			cursor: pointer;
			pointer-events: auto;
			
			/* background-color: transparent; */
			background-color: white;
			
			border: 3px solid;

			transition: all 200ms ease-in-out;
			
		}
		.btn:hover{
			background-color: black;
			fill: white;
			
		}

		
		#menu,
		#fullScreen {
			position: absolute;
			top: var(--pad);
		}
		#menu {
			left: var(--pad);
			transform: rotate(-90deg);
		}
		#menu.menu{
			transform: rotate(90deg);
		}
		#fullScreen {
			right: var(--pad);
		}
		
		
		.panel01 {
			display: none;
			flex-direction: column;

			position: absolute;
			
			top: calc(var(--btnSize) + var(--pad) * 2);
			left: var(--pad);

			gap: 10px;
		}
		
		.panel01.menu{
			display: flex;
		}
		
		.color{
			overflow: hidden;
		}
		input{
			cursor: pointer;
			pointer-events: auto;			
		}
		
		input[type="color"] {
			-webkit-appearance: none;
			border: none;
			width: 50px;
			height: 50px;
		}
		input[type="color"]::-webkit-color-swatch-wrapper {
			padding: 0;
		}
		input[type="color"]::-webkit-color-swatch {
			border: none;
		}
	</style>


