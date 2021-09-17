<div id="splash_screen">
	<div id="loading">
		<div id="loading_bar" />
	</div>
	<br />
	<h3 id="loading_text">Loading 0%</h3>
</div>

<style>
	#splash_screen {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;

		position: absolute;

		top: 0;
		left: 0;

		width: 100%;
		height: 100%;

		background-color: white;
	}
	#loading {
		display: flex;
		justify-content: center;

		width: 30%;
		padding: 2px;

		border: 2px solid black;

		border-radius: 3px;
	}
	#loading_bar {
		height: 10px;
		background-color: rgb(255, 102, 51);

		border-radius: 3px;
	}
</style>
