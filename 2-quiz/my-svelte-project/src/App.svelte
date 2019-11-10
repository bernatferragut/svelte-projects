
<!-- JS -->
<script>
    import Question from './Question.svelte';
    import Answer from './Answer.svelte';
    import Points from './Points.svelte';

	let quizIndex = 0;
    const quiz = [
        {
            question : "Whether God Exist or not?",
            correctAnswer : 0,
            answers : [
                'Yes',
                'No'
            ]
        },
        {
            question : "What is God?",
            correctAnswer : 0,
            answers : [
                '?',
                'A'
            ]
        },
        {
            question : "Of What is god?",
            correctAnswer : 1,
            answers : [
                'All',
                'Nothing'
            ]
        },
        {
            question : "Why is God?",
            correctAnswer : 0,
            answers : [
                'No idea',
                'Look inside'
            ]
        },
        {
            question : "How much is God?",
            correctAnswer : 1,
            answers : [
                'Finite',
                'Infinite'
            ]
        },
        {
            question : "Of what kind is God?",
            correctAnswer : 0,
            answers : [
                'Unique',
                'Vulgar'
            ]
        },
        {
            question : "When is God?",
            correctAnswer : 0,
            answers : [
                'Now',
                'Always'
            ]
        },
        {
            question : "Where is God?",
            correctAnswer : 1,
            answers : [
                'Here',
                'Everywhere'
            ]
        },
        {
            question : "How and with who is God?",
            correctAnswer : 1,
            answers : [
                'Always',
                'All the time'
            ]
        }
	];

	let points = 0;
	
	function checkAnswerHandler() {
		const isCorrect =  quiz[quizIndex].answers.indexOf(answerText) === quiz[quizIndex].correctAnswer;

		if ( isCorrect ) {
			points += 1;
			quiz[quizIndex].question = 'Correct!';
		} else {
			quiz[quizIndex].question = 'wrong';
		}
		setTimeout( function() {
			quizIndex += 1;
		}, 3000)

	}

</script>

<!-- CSS -->
<style >
	/* .App {
		
	}

	.Answers {

	} */

</style>

<!-- HTML -->
<div class="App">
	<Points points = { points }/>
	<Question questionText = { quiz[quizIndex].question }/>
	<div class="Answers">
		<Answer answerText = { quiz[quizIndex].answers[0] checkAnswerHandler = "checkAnswerHandler" }/>
		<Answer answerText = { quiz[quizIndex].answers[1] checkAnswerHandler = "checkAnswerHandler" }/>
	</div>

</div>


