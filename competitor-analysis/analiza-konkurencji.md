# Research konkurencji: Z perspektywy IT: Jak pomóc mieszkańcom i turystom w odkrywaniu miasta? (Mikro-planowanie spacerów wspierane przez AI)

## Podsumowanie

Rynek odkrywania miasta i planowania spacerów obejmuje trzy główne obszary:
1. **Rozwiązania cyfrowe i aplikacje:** giganci nawigacyjni (Google Maps), aplikacje z audioprzewodnikami (VoiceMap, SmartGuide), platformy społecznościowe tras (komoot) oraz generatory planów oparte na AI (Wonderplan, Layla).
2. **Społeczności internetowe:** grupy na Facebooku, fora i wątki typu „top 10 ukrytych miejsc”, dostarczające unikalnych, ale niesformatowanych rekomendacji.
3. **Konkurencja tradycyjna:** stacjonarne punkty informacji turystycznej i drukowane mapki miejskie, oferujące wsparcie człowieka, lecz cechujące się brakiem elastyczności.

Na styku tych obszarów brakuje rozwiązania skupionego na mikro-momentach („tu i teraz”), które łączyłoby konwersacyjne AI z twardymi ograniczeniami czasoprzestrzennymi (np. pętla spacerowa na dokładnie 90 minut od bieżącej pozycji). Główna szansa dla projektu leży w precyzyjnym wyliczaniu tras „od drzwi do drzwi” w czasie rzeczywistym, automatyzacji selekcji niszowych miejsc z forów i grup oraz eliminacji ograniczeń papierowych przewodników na rzecz dynamicznego, zoptymalizowanego spaceru.

## Założenia

* **Zrozumienie projektu:** Projekt to aplikacja (mobilna lub webowa) z interfejsem NLP (naturalnego języka), która na wejściu przyjmuje aktualną lokalizację GPS, budżet czasowy (np. 2 godziny), punkt końcowy oraz nastrój użytkownika, a na wyjściu generuje zoptymalizowaną trasę pieszą, promując przy okazji lokalną gastronomię i mniej znane miejsca kultury.
* **Czego nie wiadomo (przyjęte założenia):**
* **Zasięg geograficzny:** Zakładam start na rynku polskim lub europejskim z docelową skalowalnością globalną (opartą na otwartych danych typu OpenStreetMap i API mapowych).
* **Model biznesowy:** Zakładam model B2B2C – darmowy dla spacerowiczów, monetyzowany przez opłaty od lokalnych kawiarni, galerii i instytucji za promowane umieszczenie na trasie (tzw. *sponsored pins* dopasowane kontekstowo).
* **Warstwa audio/treści:** Zakładam, że aplikacja generuje opisy miejsc dynamicznie (tekst lub TTS), zamiast polegać na ręcznie nagrywanych przez lektorów ścieżkach.



## Zestawienie konkurencji

Identyfikowane podmioty i alternatywy podzielono na 3 kategorie:
1. **Dedykowane aplikacje mobilne i platformy cyfrowe** (nawigacje, audioprzewodniki, planery AI).
2. **Grupy na Facebooku i fora internetowe** (społecznościowe wątki „top 10 miejsc, które warto odwiedzić”).
3. **Punkty informacyjne i mapki** (tradycyjne formy wsparcia turysty w terenie).

| Nazwa | Co robią | Typ (bezpośredni / pośredni) | Wyróżnik | Źródło |
| --- | --- | --- | --- | --- |
| **Citymapper (funkcja Super Duper Walk)** | Aplikacja do nawigacji miejskiej w dużych aglomeracjach. Posiada funkcję generowania losowych spacerów w wybranym czasie lub do konkretnego celu, z wyborem między trasą „główną” a „cichą/boczną”. Model freemium (subskrypcja Citymapper Club za dodatkowe funkcje). | Bezpośredni | Algorytmiczne generowanie pętli spacerowych z uwzględnieniem hałasu i natężenia ruchu pieszego. | Strona produktu / aplikacja Citymapper |
| **komoot** | Planer tras pieszych i rowerowych oparty na danych społecznościowych i OpenStreetMap. Pozwala wyznaczyć trasę z punktu A do B i dodawać rekomendowane przez innych punkty (Highlights). Zarabia na sprzedaży paczek map offline i subskrypcji Premium. | Pośredni | Bardzo dokładne dane o nawierzchni, przewyższeniach i estetyce trasy; silna społeczność. | komoot.com |
| **VoiceMap** | Marketplace z autorskimi spacerami audio tworzonymi przez lokalnych dziennikarzy, historyków i podcasterów. Odtwarzanie uruchamia się automatycznie po wejściu w strefę GPS. Zarabia na prowizji od sprzedanych tras (zwykle 3–10 USD za spacer). | Pośredni | Bardzo wysoka jakość merytoryczna i narracyjna opowieści o ukrytych zakątkach miast. | voicemap.me |
| **Atlas Obscura** | Globalny katalog nietypowych, ukrytych i dziwnych atrakcji turystycznych tworzony przez społeczność. Aplikacja pozwala przeglądać mapę „nietuzinkowych miejsc” wokół aktualnej pozycji. Zarabia na reklamach, książkach i zorganizowanych wycieczkach. | Pośredni | Największa na świecie ustrukturyzowana baza miejsc „poza utartym szlakiem” (off-the-beaten-path). | atlasobscura.com |
| **Go Jauntly** | Brytyjska aplikacja promująca codzienne spacery, zdrowie psychiczne i kontakt z naturą w miastach. Oferuje gotowe, krótkie trasy z opisami i zdjęciami oraz generowanie tras zielonych. Zarabia na subskrypcjach B2C i partnerstwach z samorządami. | Bezpośredni | Skupienie na mieszkańcach (well-being, zielone korytarze miejskie), a nie tylko na twardej turystyce. | gojauntly.com |
| **Questo** | Aplikacja zamieniająca zwiedzanie miast w gry miejskie (szukanie wskazówek, zagadki w terenie). Trasy są dostępne 24/7 na telefonie bez rezerwacji. Zarabia na sprzedaży pojedynczych gier i subskrypcji Questo Pass. | Pośredni | Grywalizacja spaceru; zmusza do zwracania uwagi na detale architektoniczne mijane po drodze. | questoapp.com |
| **Wonderplan / Layla (dawniej Roam Around)** | Generatory planów podróży oparte na LLM (AI). Użytkownik wpisuje miasto, liczbę dni, budżet i zainteresowania, a system tworzy harmonogram dzień po dniu. Zarabiają na afiliacji (hotele, bilety na GetYourGuide). | Pośredni | Pełne wykorzystanie NLP do rozumienia intencji i nastroju użytkownika. | wonderplan.ai / layla.ai |
| **Google Maps (Listy + AI / Immersive View)** | Globalny lider nawigacji. Umożliwia szukanie „co robić w pobliżu”, sprawdzanie obłożenia miejsc na żywo (Popular times) oraz godzin otwarcia. Zarabia na reklamach lokalnych firm (Google Ads). | Pośredni | Bezkonkurencyjna baza danych o godzinach otwarcia, natężeniu ruchu i recenzjach w czasie rzeczywistym. | maps.google.com |
| **Spotted by Locals** | Seria przewodników miejskich (aplikacja i blogi) tworzonych wyłącznie przez mieszkańców danego miasta, którzy mówią w lokalnym języku. Brak miejsc czysto turystycznych. Model płatny za pobranie przewodnika po mieście. | Pośredni | Ręczna selekcja małych kawiarni, galerii i parków; wysoka wiarygodność rekomendacji. | spottedbylocals.com |
| **Action Tour Guide / GPSMyCity** | Aplikacje zamieniające artykuły blogowe i klasyczne przewodniki w ścieżki spacerowe z nawigacją od punktu do punktu. Model freemium (płatny dostęp do nawigacji i wersji offline). | Pośredni | Ogromna liczba gotowych tras tematycznych (np. szlak kawiarni, szlak street artu) w tysiącach miast. | gpsmycity.com |
| **Grupy na Facebooku / Fora internetowe (wątki „Top 10 miejsc”, Reddit)** | Społecznościowe grupy dyskusyjne (np. grupy miejskie na FB, Reddit r/travel, fora podróżnicze). Użytkownicy pytają o polecenia lub przeglądają gotowe zestawienia „top 10 miejsc”. Inni członkowie społeczności dzielą się subiektywnymi, aktualnymi wskazówkami. | Pośredni (konkurencja społecznościowa) | Autentyczność, „żywe” rekomendacje mieszkańców i niszowe perełki; brak integracji z nawigacją, konieczność czasochłonnego ręcznego planowania trasy i odsiewania spamu. | Grupy FB (np. miejskie, ekspackie), Reddit, fora podróżnicze |
| **Punkty informacyjne / Mapki papierowe** | Tradycyjne miejskie punkty informacji turystycznej (InfoPunkty na dworcach, lotniskach, w centrach) oraz darmowe drukowane mapy i ulotki z wyznaczonymi trasami spacerowymi. | Pośredni (konkurencja tradycyjna / analogowa) | Bezpośredni kontakt z człowiekiem (doradcą), zerowa zależność od technologii (baterii, zasięgu); brak elastyczności, statyczność materiałów, ograniczone godziny otwarcia i promowanie głównie masowych atrakcji. | Miejskie centra informacji turystycznej, punkty na dworcach/lotniskach |

## Luki rynkowe

1. **Sztywność gotowych tras (problem „punktu startowego”)**
* **Opis:** Aplikacje takie jak VoiceMap, Sidewalk czy Questo wymagają od użytkownika udania się na konkretny punkt startowy (np. Rynek Główny), aby rozpocząć spacer. Jeśli ktoś jest na dworcu kolejowym lub pod biurem na obrzeżach centrum i ma tylko 1,5 godziny, dojazd do punktu startowego zjada połowę czasu.
* **Uzasadnienie:** Częsty zarzut w recenzjach aplikacji z audioprzewodnikami (App Store / Google Play) – trasy są liniowe i nie dopasowują się do miejsca, w którym użytkownik aktualnie stoi.


2. **Halucynacje przestrzenne i czasowe w planerach AI**
* **Opis:** Generatory oparte na LLM (np. Layla, ChatGPT, Wonderplan) potrafią świetnie dobrać miejsca do nastroju („klimatyczna kawiarnia i brutalistyczna architektura”), ale słabo radzą sobie z twardą geometrią miasta. Często proponują punkty oddalone od siebie o 40 minut marszu jako „krótki spacer” lub wysyłają ludzi do miejsc zamkniętych w danej godzinie.
* **Uzasadnienie:** Wątki na Reddit (np. r/travel, r/ArtificialIntelligence) regularnie wytykają, że plany z AI wymagają ręcznego przepisywania do Google Maps, bo kolejność punktów jest nielogiczna geograficznie.


3. **Zalew informacji i paraliż decyzyjny w Google Maps**
* **Opis:** Google Maps ma wszystkie dane, ale wymaga od użytkownika ręcznej pracy: wpisania frazy, przejrzenia dziesiątek pinezek, przeczytania recenzji, sprawdzenia godzin otwarcia i ręcznego ułożenia z tego trasy z kilkoma przystankami.
* **Uzasadnienie:** Użytkownik z okienkiem czasowym 90 minut traci 25 minut na samo szukanie i odsiewanie pułapek turystycznych od wartościowych miejsc.


4. **Brak narzędzi mikro-promocji „tu i teraz” dla lokalnych biznesów**
* **Opis:** Małe kawiarnie, rzemieślnicze piekarnie czy niszowe galerie nie mają szans przebić się w Google Maps ani na TripAdvisorze bez dużych budżetów reklamowych lub tysięcy recenzji. Jednocześnie nie mają jak zakomunikować przechodniom: „jesteśmy 200 metrów od ciebie, mamy wolne stoliki i świeżą partię wypieków”.
* **Uzasadnienie:** Systemy reklamowe gigantów faworyzują sieciówki i miejsca o ogromnym wolumenie wyszukiwań, pomijając kontekst pieszego, który po prostu przechodzi dwie ulice dalej.


5. **Chaos organizacyjny i brak logistyki w grupach na FB i na forach (listy „Top 10”)**
* **Opis:** Posty na forach i grupach na Facebooku z listami „top 10 miejsc, które warto odwiedzić” zawierają unikalne rekomendacje mieszkańców, lecz są całkowicie oderwane od logistyki spaceru. To zbiór punktów bez informacji o optymalnej kolejności zwiedzania, realnym czasie przejścia czy aktualnych godzinach otwarcia.
* **Uzasadnienie:** Użytkownik musi ręcznie przenosić polecenia z forów do nawigacji, sprawdzać dystanse i samodzielnie układać trasę, co przy ograniczonym czasie (np. 1–2 godziny) prowadzi do frustracji i rezygnacji ze zwiedzania.


6. **Statyczność, masowość i bariery tradycyjnej informacji turystycznej (punkty info i mapki)**
* **Opis:** Tradycyjne punkty informacyjne i papierowe mapki promują głównie masowe, powtarzalne atrakcje (np. zabytki staromiejskie). Nie adaptują się do nastroju, zainteresowań ani ograniczonego budżetu czasowego użytkownika. Ponadto są ograniczone godzinami pracy punktów (zwykle 9:00–17:00), a papierowe nośniki uniemożliwiają dynamiczne reagowanie na pogodę czy zmiany w terenie.
* **Uzasadnienie:** Młodzi podróżni i mieszkańcy rzadko korzystają z fizycznych punktów info ze względu na konieczność nadłożenia drogi, kolejki w sezonie oraz brak interaktywnej nawigacji prowadzącej krok po kroku.



## Co można zrobić więcej

Poniższe propozycje łączą profil techniczny projektu (AI + NLP + czas + lokalizacja) ze zidentyfikowanymi lukami, ułożone od największego wpływu na sukces produktu:

### 1. Silnik „Twardego Budżetu Czasowego” (Time-Boxed Loop Routing)

* **Co:** Zamiast generować listę miejsc, system musi działać od końca: przyjmuje punkt A (np. Dworzec), punkt B (ten sam Dworzec lub inne miejsce docelowe) oraz sztywne okno czasowe (np. 110 minut). Algorytm wylicza trasę tak, aby suma czasu marszu (np. 50 min) oraz szacowanego czasu spędzonego w punktach pośrednich (np. 30 min na kawę + 20 min na obejrzenie murali + 10 min bufora) idealnie zamknęła się w limicie.
* **Dlaczego:** Rozwiązuje główny ból podróżnych w tranzycie („boję się, że spóźnię się na pociąg”) i bezpośrednio odpowiada na lukę nr 1 i 2. Żaden popularny planer AI nie gwarantuje obecnie bezpiecznego powrotu na czas.
* **Trudność:** Średnia (wymaga spięcia LLM z silnikiem routingu typu Valhalla/OSRM/Mapbox Matrix API oraz narzucenia twardych wag czasowych na każdy typ POI).

### 2. Architektura RAG oparta na danych czasu rzeczywistego (Kontekst + Pogoda + Godziny otwarcia)

* **Co:** Zanim LLM wygeneruje propozycję spaceru z promptu użytkownika (np. „mam godzinę, chcę przejść spokojną okolicą i wypić dobre espresso”), system odpytuje bazę lokalną przefiltrowaną przez: aktualną godzinę (odrzuca zamknięte miejsca), pogodę (w deszczu priorytetyzuje pasaże, galerie i kawiarnie; w słońcu – parki i architekturę zewnętrzną) oraz porę dnia (po zmroku unika nieoświetlonych parków).
* **Dlaczego:** Eliminuje halucynacje planerów AI (luka nr 2) i buduje zaufanie. Użytkownik dostaje trasę, która jest fizycznie wykonalna w danej minucie.
* **Trudność:** Średnia/Wysoka (wymaga integracji i cachowania danych z Google Places API / Foursquare / OSM oraz API pogodowego, co przy dużej skali generuje koszty zapytań).

### 3. Tryb „Anty-Tłum” (Detour Routing dla mieszkańców i świadomych turystów)

* **Co:** Wykorzystanie warstw danych z OpenStreetMap (tagi określające typ ulicy, tereny zielone, strefy piesze, detale architektoniczne jak pomniki, kapliczki, murale) do wyznaczania tras celowo omijających główne arterie komunikacyjne i najbardziej zatłoczone deptaki, prowadząc równoległymi, cichymi uliczkami.
* **Dlaczego:** Bezpośrednio realizuje cel społeczny projektu i przyciąga mieszkańców, którzy znają główne ulice swojej dzielnicy, ale nigdy nie skręcili dwie przecznice wcześniej.
* **Trudność:** Wysoka (standardowe silniki nawigacji szukają trasy najkrótszej lub najszybszej; tutaj trzeba napisać własny profil wagowy dla grafu drogowego, tzw. *custom costing model*, premiujący estetykę i spokój kosztem długości trasy).

### 4. Kontekstowe Mikro-Oferty B2B (Live Local Perks)

* **Co:** Prosty panel dla lokalnych kawiarni, księgarni i małych muzeów, w którym mogą wrzucić „mikro-zachętę” dla spacerowiczów w godzinach mniejszego ruchu (np. „między 11:00 a 14:00 do każdej kawy mały rogalik dla osób na spacerze z aplikacji”). AI wplata taki punkt w trasę tylko wtedy, gdy pasuje on do zapytania użytkownika i leży w korytarzu jego spaceru.
* **Dlaczego:** Tworzy czytelny model biznesowy (luka nr 4) i daje lokalnym miejscom natychmiastowy, mierzalny zwrot (przychodzą realni ludzie z ulicy), a użytkownikowi daje poczucie odkrycia „sekretnego miejsca z bonusem”.
* **Trudność:** Niska technicznie (prosty system CRUD + weryfikacja kodem QR/PIN na miejscu), ale Wysoka operacyjnie (wymaga akwizycji lokalnych partnerów w danym mieście).

### 5. Dynamiczny Mikro-Przewodnik (Krótkie karty „Na co spojrzeć” zamiast długich nagrań)

* **Co:** Zamiast 5-minutowych wykładów historycznych, przy każdym punkcie trasy AI generuje 3-zdaniową pigułkę („Spójrz na balkon na drugim piętrze tej kamienicy – to jeden z ostatnich śladów...”).
* **Dlaczego:** Osoba mająca 1–2 godziny lub spacerująca dla relaksu nie chce słuchać akademickich wykładów ani wpatrywać się w ekran. Krótkie, konkretne wskazówki wizualne (podobne do mechaniki z Questo, ale bez konieczności rozwiązywania zagadek) utrzymują kontakt człowieka z miastem, a nie ze smartfonem.
* **Trudność:** Niska (odpowiednie promptowanie modelu językowego na podstawie zagregowanych danych o obiekcie z Wikipedii, rejestrów zabytków czy lokalnych portali).

## Zastrzeżenia

* **Ograniczenia dostępu do danych na żywo:** Raport opiera się na zagregowanej wiedzy o funkcjach i modelach biznesowych wymienionych platform. Dokładne stawki B2B (np. prowizje SmartGuide czy koszty partnerstw w Go Jauntly) nie są publicznie jawne i wymagają bezpośredniego kontaktu z działami sprzedaży tych firm.
* **Koszty API mapowych:** Przy projektowaniu architektury IT należy dokładnie zweryfikować aktualne cenniki Google Maps Platform (szczególnie Places API New oraz Routes API) vs alternatywy takie jak Mapbox, Radar czy self-hosted OpenStreetMap (OSRM/Valhalla), ponieważ przy częstym przeliczaniu tras AI koszty zapytań zewnętrznych mogą szybko przekroczyć przychody z fazy startowej projektu.
* **Lokalna konkurencja miejska:** W zależności od tego, w jakim mieście projekt wystartuje jako pierwszy (np. Warszawa, Kraków, Wrocław), należy dodatkowo sprawdzić darmowe aplikacje samorządowe i lokalne inicjatywy organizacji turystycznych, które nie są widoczne w globalnych zestawieniach, a mogą mieć podpisane umowy na wyłączność z lokalnymi instytucjami kultury.