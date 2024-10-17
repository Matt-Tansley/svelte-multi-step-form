<script>
    import FormStep from './FormStep.svelte';
    // State of multi-step form
	const stepNames = ['Step 1', 'Step 2', 'Step 3'];
	let activeStep = 0;

    const adjustFormStep = (increment) => {
		activeStep = activeStep + increment;
	};

</script>

<main class="container">
    <h1>My bada** multi-step form</h1>

    <FormStep stepName={stepNames[activeStep]} />

<!-- Step buttons -->
<div>
    <button color="blue" on:click={() => adjustFormStep(-1)} disabled={activeStep == 0}
        >Prev</button
    >
    <button
        color="blue"
        on:click={() => adjustFormStep(1)}
        disabled={activeStep == stepNames.length - 1}>Next</button
    >
</div>
</main>

