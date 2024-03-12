<script>
	import Navigation from '$lib/components/navigation.svelte';
	import Footer from '$lib/components/footer.svelte';

	let questions = [
		'Czy pijesz alkohol prawie codziennie?',

		'Czy znajomi lub rodzina wyrażali zaniepokojenie Twoim piciem?',
		'Czy piłeś alkohol zaraz po przebudzeniu się?',
		'Czy piłeś kiedykolwiek alkohol w tajemnicy?',

		'Czy zdarzyło Ci się nie pamiętać wydarzeń z poprzedniej nocy z powodu picia?',

		'Czy czujesz się winny lub wstydliwy po piciu?',
		'Czy alkohol wpływa negatywnie na Twoją wydajność w pracy lub w szkole?',
		'Czy kontynuowałeś picie mimo świadomości, że powoduje to problemy zdrowotne?',
		'Czy zrezygnowałeś z aktywności lub zainteresowań z powodu alkoholu?',
		'Czy próbowałeś ograniczyć ilość alkoholu, którą pijesz, i nie udało się to?',

		'Czy zwiększyła się Twoja tolerancja na alkohol, tzn. potrzebujesz więcej alkoholu, aby poczuć jego efekty?',
		'Czy zdarzyło Ci się pić alkohol w niebezpiecznych sytuacjach (np. przed prowadzeniem pojazdu)?'
	];

	let responses = Array.from({ length: questions.length }, () => 0);
	let questionErrors = Array.from({ length: questions.length }, () => '');

	let email = '';

	let EmailError = '';

	let formError = '';

	let isLoading = false;

	let totalScoreTry = '';
	let scoreTry = '';
	/**
	 * @param {string} email
	 */
	function validateEmail(email) {
		return /^([a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,})$/i.test(email);
	}

	/**
	 * @param {string} mobile
	 */

	/**
	 * @param {string} name
	 */

	/**
	 * @param {string | any[]} responses
	 */
	function validateForm(responses) {
		let hasError = false;
		for (let i = 0; i < responses.length; i++) {
			if (responses[i] == 0) {
				questionErrors[i] = 'Wybierz odpowiedź.';
				hasError = true;
			} else {
				questionErrors[i] = '';
			}
		}
		return !hasError;
	}

	/**
	 * @param {{ preventDefault: () => void; }} event
	 */
	async function submitForm(event) {
		event.preventDefault();
		// @ts-ignore
		let role;
		const isFormValid = validateForm(responses);
		const isEmailValid = validateEmail(email);

		if (!isFormValid) {
			formError = 'Odpowiedz na wszystkie pytania.';
		} else {
			formError = '';
		}

		if (!isEmailValid) {
			if (email == '') {
				EmailError = 'Podaj swój adres mailowy.';
			} else {
				EmailError = 'Niewazny adres email';
			}
		} else EmailError = '';

		if (!isFormValid || !isEmailValid) {
			return; // Don't proceed if any of the validations fail.
		}
		isLoading = true;

		// If all validations pass, clear error messages.
		EmailError = '';

		formError = '';

		//let ops = q2 + q5 + q7 + q10 + q11 + q12 + q13 + q15 + q17 + q18;
		//let vision = q1 + q3 + q4 + q6 + q8 + q9 + q14 + q16 + q19 + q20;

		// Calculate ops by summing specific elements from responses
		let ops =
			responses[1] + // q2
			responses[4] + // q5
			responses[6] + // q7
			responses[9] + // q10
			responses[10] + // q11
			responses[11] + // q12
			responses[12] + // q13
			responses[14] + // q15
			responses[16] + // q17
			responses[17]; // q18

		// Calculate vision by summing specific elements from responses
		let vision =
			responses[0] + // q1
			responses[2] + // q3
			responses[3] + // q4
			responses[5] + // q6
			responses[7] + // q8
			responses[8] + // q9
			responses[13] + // q14
			responses[15] + // q16
			responses[18] + // q19
			responses[19]; // q20

		let totalScore = responses.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
		scoreTry = totalScore.replace(/[^T]/g, '').length;

		scoreTry >= 3 ? (role = 'problem') : scoreTry < 3 ? (role = 'nieproblem') : undefined;

		let keyValueData = questions.map((question, index) => ({
			question,
			response: responses[index]
		}));
		const questionResponses = {};

		for (const item of keyValueData) {
			// @ts-ignore
			questionResponses[item.question] = item.response;
		}

		analytics.track('Quiz Completed', {
			email: { email },
			score: { scoreTry },
			classification: { role },
			title: 'some title'
		});
		analytics.identify(email, {
			email: { email },
			score: { scoreTry },
			classification: { role }
		});

		


		window.location.href = `https://gorman.pl/${role}`;
		console.log(totalScore);
		console.log(scoreTry);
	}
</script>

<svelte:head>
	<title>Czy jestem alkoholikiem?</title>
	<meta name="description" content="Quiz i kwestonariusz zeby zobaczyc czy jestem alkoholikiem" />
</svelte:head>

<Navigation />

<div class="bg-[#FFFDF5] font-soehne text-black pt-10">
	<div class="w-11/12 md:w-1/3 mx-auto">
		<h1 class="text-2xl font-bold mt-10">Czy jestem alkoholikiem?</h1>
		<p class="mt-10 mx-2 text-lg">
			Witaj! Te 12 pytań pomoze Ci dowiedzieć się czy jesteś alkoholikiem. Powinno to zająć mniej
			niz 6 minut. Twoje odpowiedzi pozostaną poufne.
		</p>
		<form class="mt-10">
			{#each questions as question, index}
				<div class="mt-10 mx-2">
					<p class="text-slate-500">Pytanie {index + 1}</p>
					<h2 class="text-xl font-bold mb-5">{question}</h2>

					<div class="flex flex-row">
						{#each ['TAK', 'NIE'] as value, answer}
							<input
								type="radio"
								id={`q${index + 1}${value}`}
								required={responses[index] === value}
								name={`q${index + 1}`}
								{value}
								bind:group={responses[index]}
							/>
							<label for={`q${index + 1}${value}`}>{value}</label>
						{/each}
					</div>
					{#if questionErrors[index] !== ''}
						<p class="text-red-500 text-sm mt-2 p-2 bg-red-100 border border-red-300 rounded">
							{questionErrors[index]}
						</p>
					{/if}
				</div>
			{/each}

			<div class="mt-10 text-xl">
				<label class="font-bold" for="email">Email:</label>
				<input type="email" id="email" size="30" required bind:value={email} />
				{#if EmailError}
					<p class="text-red-500 text-sm mt-2 p-2 bg-red-100 border border-red-300 rounded">
						{EmailError}
					</p>
				{/if}
			</div>

			<button
				class="border border-black border-2 rounded my-20 mx-2 font-bold w-full h-12 text-Black"
				on:click={submitForm}>Pokaż mój wynik</button
			>

			{#if formError}
				<p
					class="text-red-500 text-sm mt-[-60px] p-2 mx-2 w-full bg-red-100 border border-red-300 rounded"
				>
					{formError}
				</p>
			{/if}
		</form>
		<div class="loading-spinner" style={isLoading ? 'display: flex;' : 'display: none;'}>
			<!-- Loader HTML/CSS -->
			<div class="spinner" />
		</div>
	</div>
</div>
<Footer />

<style>
	input[type='radio'] {
		display: none;
	}
	input[type='radio'] + label {
		border: 2px solid black;

		cursor: pointer;
		display: block;
		height: 62px;
		min-width: 48%;
		text-align: center;
		line-height: 62px;
		margin-right: 0.5em;
		border-radius: 5px;
	}
	input[type='radio']:checked + label {
		border: 2px solid black;
		background-color: #dbd6b5;
		color: black;
	}

	input[type='email'] {
		width: 100%;
		background-color: #fffdf5;
		border: 0px solid black;
		border-bottom: solid black;
		text-align: left;
	}

	/* Styles for the loading spinner */
	.loading-spinner {
		display: none; /* Hide the loader by default */
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 0, 0, 0.5);
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.spinner {
		border: 4px solid rgba(255, 255, 255, 0.3);
		border-left: 4px solid #ffffff;
		border-radius: 50%;
		width: 32px;
		height: 32px;
		animation: spin 1s linear infinite;
	}

	@keyframes spin {
		0% {
			transform: rotate(0deg);
		}
		100% {
			transform: rotate(360deg);
		}
	}
</style>
