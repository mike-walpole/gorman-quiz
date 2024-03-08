<script>
	import Abc from '../../lib/components/Abc.svelte';
	import Bottom from '../../lib/components/Bottom.svelte';
	import Navigation from '../../lib/components/navigation.svelte';
	import Footer from '../../lib/components/footer.svelte';
</script>

<svelte:head>
	<title>Nie mam problemu z alkoholem</title>
	<meta name="description" content="Masz szczęście ze nie jestes alkoholikiem" />
</svelte:head>

<section class="bg-[#FFFDF5] text-black pt-12">
	<Navigation />

	<section class="bg-[#FFFDF5] pt-12">
		<div class="w-11/12 max-w-4xl mx-auto" />
		<div class="w-11/12 max-w-4xl mx-auto border-t-[1px] border-black">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-24 mt-5">
				<div class="col-span-1 max-w-4xl text-black font-heldane text-5xl font-bold mb-5 md:mb-0">
					Jaki jest mój wynik?
				</div>

				<div class="text-black font-soehne col-span-1">
					<p class=" text-black font-soehne">
						Dziękujemy za poświęcenie czasu na wypełnienie kwestionariusza. Na podstawie podanych
						przez Ciebie odpowiedzi, wygląda na to, że Twoje obecne nawyki picia alkoholu nie
						wskazują na uzależnienie. To świetna wiadomość!
					</p>
				</div>
			</div>
		</div>

		<div class="w-11/12 max-w-4xl mx-auto border-t-[1px] border-black mt-12">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-24 mt-5">
				<div class="col-span-1 md:w-2/3 text-black font-heldane font-bold text-5xl mb-5 md:mb-0">
					Co moge teraz zrobić?
				</div>
				<div class="text-black font-soehne col-span-1">
					<ul class="mb-3">
						<span class="underline">Zachowaj Zdrowe Nawyki:</span> To, że obecnie nie masz problemu z
						alkoholem, nie oznacza, że nie powinieneś być świadomy swoich nawyków picia.
					</ul>
					<ul class="mb-3">
						<span class="underline">Monitoruj Nawyki:</span> Bądź świadomy, ile i jak często pijesz.
						Zwracaj uwagę na sytuacje, w których pijesz, i unikaj picia z niewłaściwych powodów, takich
						jak radzenie sobie ze stresem.
					</ul>
					<ul class="mb-3">
						<span class="underline">Wsparcie Społeczne: </span> Utrzymuj silne relacje z rodziną i przyjaciółmi,
						którzy wspierają Twoje zdrowe wybory.
					</ul>
					<ul class="mb-3">
						<span class="underline">Znajdź Równowagę:</span> Postaw sobie małe, osiągalne cele, takie
						jak np. jeden dzień bez alkoholu, a następnie wydłużaj ten czas. Każdy dzień bez picia jest
						sukcesem.
					</ul>
					<ul class="mb-3">
						<span class="underline">Bądź Wzorem:</span> Możesz również służyć jako wzór dla innych, pokazując,
						że odpowiedzialne picie alkoholu jest możliwe. Pamiętaj, że Twoje zdrowe nawyki mogą mieć
						pozytywny wpływ na ludzi w Twoim otoczeniu.
					</ul>
				</div>
			</div>
		</div>

		<div class="w-11/12 max-w-4xl mx-auto border-t-[1px] border-black mt-12">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-24 mt-5">
				<div class="col-span-1 md:w-2/3 text-black font-heldane font-bold text-5xl mb-5 md:mb-0">
					Jak mogę pomóc znajomemu / rodzinie którzy mogą mieć problem?
				</div>

				<div class="text-black font-soehne col-span-1">
					<p class=" text-black font-soehne">
						W Polskim Centrum Terapii Uzależnień rozumiemy wyzwania, przed którymi stoją, i jesteśmy
						przygotowani, aby ich wesprzeć. Nasz zespół specjalistów może zaoferować profesjonalną
						pomoc i wsparcie, które będą dostosowane do ich indywidualnych potrzeb.
					</p>
					<p class=" mt-6 text-black font-soehne">
						Pamiętaj,że każdy krok, który podejmują w kierunku zdrowienia, jest ważny. Jesteśmy
						tutaj, aby im w tym pomóc i zapewnić potrzebne zasoby oraz wsparcie. Nie muszą
						przechodzić przez to samotnie!
					</p>

					<a href="tel:+48789360379">
						<button
							class="border border-black my-20 mx-0 font-bold w-full h-12 bg-[#911B53] text-white"
						>
							Kliknij tu żeby zadzwonić teraz</button
						>
					</a>
				</div>
			</div>
		</div>
	</section>
</section>
<Footer />
