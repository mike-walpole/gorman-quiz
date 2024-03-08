<script>
	import { Navbar, NavBrand, NavHamburger, NavUl, NavLi, Button } from 'flowbite-svelte';
	import Abc from '../../lib/components/Abc.svelte';
	import Bottom from '../../lib/components/Bottom.svelte';
	import Navigation from '../../lib/components/navigation.svelte';
	import Footer from '../../lib/components/footer.svelte';
</script>

<svelte:head>
	<title>Mam problem z alkoholem</title>
	<meta name="description" content="Odpowiedź na to czy jestem alkoholikiem" />
</svelte:head>

<section class="bg-[#FFFDF5] text-black pt-12">
	<Navigation />

	<div class="w-11/12 max-w-4xl mx-auto border-t-[1px] border-black text-black mt-12">
		<div class="grid grid-cols-1 md:grid-cols-2 gap-x-24 mt-5">
			<div class="col-span-1 md:w-2/3 text-black font-bold font-heldane text-5xl mb-5 md:mb-0">
				Jaki jest mój wynik?
			</div>

			<div class="text-black font-soehne col-span-1">
				<p class=" text-black font-soehne">
					Jeśli odpowiedzialeś TAK na trzy lub więcej pytań jest bardzo prawdopodobne że masz
					trudnościami związane z alkoholem. Ale tak naprawde tylko Ty mozesz przyznać czy jesteś
					Alkoholikiem. <br /> Przyznanie się do problemu to najtrudniejszy i najważniejszy krok na drodze
					do zdrowienia. Pamiętaj ze uzależnienie od alkoholu to choroba, a nie wybór czy brak silnej
					woli. Leczenie może być skuteczne i może prowadzić do trwałej zmiany. Pamietaj że poproszenie
					o pomoc to znak siły, a nie słabości.
				</p>
				<Button href="tel:+48789360379" class="w-full mt-6 border bg-[#911B53]  outline-white ">
					<span>
						<svg
							class="w-4 h-4 text-text dark:text-black"
							aria-hidden="true"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 18 18"
						>
							<path
								stroke="currentColor"
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="m16.344 12.168-1.4-1.4a1.98 1.98 0 0 0-2.8 0l-.7.7a1.98 1.98 0 0 1-2.8 0l-2.1-2.1a1.98 1.98 0 0 1 0-2.8l.7-.7a1.981 1.981 0 0 0 0-2.8l-1.4-1.4a1.828 1.828 0 0 0-2.8 0C-.638 5.323 1.1 9.542 4.78 13.22c3.68 3.678 7.9 5.418 11.564 1.752a1.828 1.828 0 0 0 0-2.804Z"
							/>
						</svg>
					</span>
					<p class="ml-2" />
					Zadzwoń teraz 24h</Button
				>
			</div>
		</div>
	</div>

	<div class="w-11/12 max-w-4xl mx-auto border-t-[1px] border-black mt-12">
		<div class="grid grid-cols-1 md:grid-cols-2 gap-x-24 mt-5">
			<div class="col-span-1 md:w-2/3 text-black font-bold font-heldane text-5xl mb-5 md:mb-0">
				Co moge teraz zrobić?
			</div>
			<div class="text-black font-soehne col-span-1">
				<ul class="mb-3">
					<span class="underline">Przyznanie się do problemu:</span> To może być najtrudniejszy krok,
					ale jest kluczowy. Przyznanie się przed sobą, że potrzebujesz pomocy, jest podstawą do zmiany.
				</ul>
				<ul class="mb-3">
					<span class="underline">Profesjonalna pomoc:</span> Skontaktuj się z profesjonalistą w dziedzinie
					leczenia uzależnień. Może to być terapeuta, psychiatra, lekarz rodzinny lub specjalistyczne
					centrum, takie jak nasze.
				</ul>
				<ul class="mb-3">
					<span class="underline">Dołącz do grupy wsparcia:</span> Grupy wsparcia, takie jak Anonimowi
					Alkoholicy, mogą zaoferować wsparcie i zrozumienie od osób, które przechodzą przez podobne
					doświadczenia.
				</ul>
				<ul class="mb-3">
					<span class="underline">Ustal małe cele:</span> Postaw sobie małe, osiągalne cele, takie jak
					np. jeden dzień bez alkoholu, a następnie wydłużaj ten czas. Każdy dzień bez picia jest sukcesem.
				</ul>
				<ul class="mb-3">
					<span class="underline">Rozważ leczenie ambulatoryjne lub stacjonarne:</span> W zależności
					od Twojej sytyuacji rozważ terapię ambulatoryjną (odbywającą się w ciągu dnia) lub stacjonarną
					(zakwaterowanie w ośrodku).
				</ul>
			</div>
		</div>
	</div>

	<div class="w-11/12 max-w-4xl mx-auto border-t-[1px] border-black mt-12 pb-12">
		<div class="grid grid-cols-1 md:grid-cols-2 gap-x-24 mt-5">
			<div class="col-span-1 md:w-2/3 text-black font-bold font-heldane text-5xl mb-5 md:mb-0">
				Gdzie mogę znaleźć pomoc?
			</div>

			<div class="text-black font-soehne col-span-1">
				<p class=" text-black font-soehne">
					W Polskim Centrum Terapii Uzależnień rozumiemy wyzwania, przed którymi stoisz, i jesteśmy
					przygotowani, aby Cię wesprzeć. Nasz zespół specjalistów może zaoferować profesjonalną
					pomoc i wsparcie, które będą dostosowane do Twoich indywidualnych potrzeb.
				</p>
				<p class=" mt-6 text-black font-soehne">
					Pamiętaj,że każdy krok, który podejmujesz w kierunku zdrowienia, jest ważny. Jesteśmy
					tutaj, aby Ci w tym pomóc i zapewnić potrzebne zasoby oraz wsparcie. Nie musisz
					przechodzić przez to samotnie.
				</p>
			</div>
		</div>
	</div>
</section>

<Footer />
