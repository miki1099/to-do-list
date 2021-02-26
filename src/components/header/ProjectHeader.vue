<template>
    <header>
        <h1><slot></slot></h1>
    </header>
</template>

<style scoped>
	header {
		display: flex;
		justify-content: center;
		align-items: center;
		font-family: "Arial Black", sans-serif;
		font-size: 2em;
		height: 7rem;
		text-align: center;
		background-color: rgb(182, 32, 32);
		margin-top: 0;
		letter-spacing: -4px;
		color: aliceblue;
		width: 100%
	}
</style>