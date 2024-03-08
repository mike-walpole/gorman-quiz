<script>
	let stay = '';
	let room = '';
	let detoks = '';
	let email = '';
	let name = '';
	let mobile = '';

	//let EmailError = '';

	/* function validateEmail(email) {
		return /^([a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,})$/i.test(email);
	} */

	async function submitForm(event) {
		event.preventDefault();

		// @ts-ignore

		/*const isEmailValid = validateEmail(email);

		if (!isEmailValid) {
			if (email == '') {
				EmailError = 'Podaj swój adres mailowy.';
			} else {
				EmailError = 'Niewazny adres email';
			}
		} else EmailError = ''; */
		let razem = stay + room + detoks;
		analytics.identify(email, {
			email: { email },
			name: { name },
			phone: { mobile },
			stay_payment: { stay },
			room_addon: { room },
			detoks: { detoks },
			razem: { razem }
		});

		analytics.track('Reservation', {
			email: { email },
			name: { name },
			phone: { mobile },
			stay_payment: { stay },
			room_addon: { room },
			detoks: { detoks },
			razem: { razem }
		});

		window.location.href = `/payment`;

		console.log(email, name, mobile, stay, room, detoks);

		console.log(razem);
	}
</script>

<svelte:head />

<div class="bg-[#FFFDF5] text-black pt-10">
	<div class="w-11/12 md:max-w-4xl mx-auto">
		<a href="https://gorman.pl"><img class="w-32" src="/gorman-horizontal.webp" alt="logo" /> </a>
		<h1 class="text-4xl font-bold mx-2 mt-10">
			Zarezerwój swój pobyt. <span class="text-slate-500" />
		</h1>
		<p class="mt-2 mx-2 text-lg mb-20">już od 3,900 zł / miesiąc w MediRatach</p>

		<form>
          
			<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
				<div>
					<h1 class="md:hidden text-2xl font-bold mx-2 mt-10 mb-5">
						Długość pobytu. <span class="text-slate-500"
							>Wybierz jak długo chcesz zostać w ośrodku</span
						>
					</h1>
					<img class="w-full" src="/exterior1.webp" alt="outside of PCTU" />
				</div>
				<div class="flex flex-col">
					<h1 class="hidden md:block text-2xl font-bold mx-2 mb-10">
						Długość pobytu. <span class="text-slate-500"
							>Wybierz jak długo chcesz zostać w ośrodku</span
						>
					</h1>
					<input type="radio" id="q1" name="length" value={13900} bind:group={stay} />
					<label for="q1"
						>4 tygodnie <span class="text-slate-500 text-sm">już od 13,990 zł</span></label
					>
					<input type="radio" id="q2" name="length" value={19900} bind:group={stay} />
					<label for="q2"
						>8 tygodni <span class="text-slate-500 text-sm">już od 19,990 zł</span></label
					>
				</div>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-20">
				<div>
					<h1 class="md:hidden text-2xl font-bold mx-2 mt-10 mb-5">
						Pokój. <span class="text-slate-500">Wybierz jaki pokój chcesz na Twój pobyt</span>
					</h1>
					<img class="w-full" src="/room1.webp" alt="outside of PCTU" />
				</div>
				<div class="flex flex-col">
					<h1 class="hidden md:block text-2xl font-bold mx-2 mb-10">
						Pokój. <span class="text-slate-500">Wybierz jaki pokój chcesz na Twój pobyt</span>
					</h1>
					<input type="radio" id="q3" name="room" value={0} bind:group={room} />
					<label for="q3">2 osobowy <span class="text-slate-500 text-sm">w cenie</span></label>
					<input type="radio" id="q4" name="room" value={2490} bind:group={room} />
					<label for="q4"
						>1 osobowy <span class="text-slate-500 text-sm">już od 2,490 zł</span></label
					>
				</div>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-20">
				<div>
					<h1 class="md:hidden text-2xl font-bold mx-2 mt-10 mb-5">
						Detoks. <span class="text-slate-500"
							>Wybierz czy chcesz detoks witaminowo-minerałowy</span
						>
					</h1>
					<img class="w-full" src="/room2.webp" alt="outside of PCTU" />
				</div>
				<div class="flex flex-col">
					<h1 class="hidden md:block text-2xl font-bold mx-2 mb-10">
						Detoks. <span class="text-slate-500"
							>Wybierz czy chcesz detoks witaminowo-minerałowy</span
						>
					</h1>
					<input type="radio" id="q5" name="detoks" value={0} bind:group={detoks} />
					<label for="q5">Nie, dziękuję <span class="text-slate-500 text-sm" /></label>
					<input type="radio" id="q6" name="detoks" value={1490} bind:group={detoks} />
					<label for="q6"
						>Tak, proszę! <span class="text-slate-500 text-sm">już od 1,490 zł</span></label
					>
				</div>
			</div>

			<div class="mt-10 text-xl">
				<div class="grid grid-cols-1 md:grid-cols-2">
					<div />
					<div>
						<h1 class="text-2xl font-bold mx-2 mt-10">
							Imie i nazwisko. <span class="text-slate-500">Twoje dane są poufne</span>
						</h1>
						<input type="text" bind:value={name} />
						<h1 class="text-2xl font-bold mx-2 mt-10">
							Email. <span class="text-slate-500">Tu dostaniesz potwierdzenie rezerwacji </span>
						</h1>
						<input type="email" bind:value={email} />
						<!--
						{#if EmailError}
							<p class="text-red-500 text-sm mt-2 p-2 bg-red-100 border border-red-300 rounded">
								{EmailError}
							</p>
						{/if}
-->
						<h1 class="text-2xl font-bold mx-2 mt-10">
							Telefon. <span class="text-slate-500">Wyślimy Ci informacje na ten numer</span>
						</h1>
						<input type="tel" bind:value={mobile} />
					</div>
				</div>

				<div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-20">
					<div />

					<button on:click={submitForm} class="w-full bg-black text-white p-5 font-bold mb-20"
						>Przejdź do płatności
					</button>
				</div>

				<div />
			</div>
		</form>
	</div>
</div>

<style>
	input[type='radio'] {
		display: none;
	}
	input[type='radio'] + label {
		border: 1px solid gray;

		cursor: pointer;
		display: block;
		height: 62px;
		min-width: 48%;
		text-align: center;
		line-height: 62px;
		margin-right: 0.5em;
		border-radius: 5px;
		margin-bottom: 10px;
	}
	input[type='radio']:checked + label {
		border: 1px solid black;
		background-color: #dbd6b5;
		color: black;
	}

	input[type='email'] {
		width: 100%;
		background-color: #fffdf5;
		border: 0px solid #fffdf5;
		border-bottom: solid 1px #1d1c1c;
		text-align: left;
	}
	input[type='text'] {
		width: 100%;
		background-color: #fffdf5;
		border: 0px solid #fffdf5;
		border-bottom: 1px solid #1d1c1c;
		text-align: left;
	}
	input[type='tel'] {
		width: 100%;
		background-color: #fffdf5;
		border: 0px solid #fffdf5;
		border-bottom: 1px solid #1d1c1c;
		text-align: left;
	}
</style>
