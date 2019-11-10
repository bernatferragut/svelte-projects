
<!-- JS -->
<script>
	export let answerText;
	export let checkAnswerHandler;
</script>

<!-- CSS -->
<style >
	.Answer {
		
	}

</style>

<!-- HTML -->
<button on:click = { ()=>checkAnswerHandler(answerText) } class="Answer">
	{ answerText }
</button>
