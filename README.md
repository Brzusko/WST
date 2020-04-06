# **Wonderful School Trip**
## Wstęp
Do zrobienia
## Potrzebne linki

__GDD__ : [Google docs](https://docs.google.com/document/d/1m_PcRiv0f7K9YNpDN1JVTNS7Sc3cjDWaITU1rdoOhZs/edit?usp=sharing "https://docs.google.com/document/d/1m_PcRiv0f7K9YNpDN1JVTNS7Sc3cjDWaITU1rdoOhZs/edit?usp=sharing")
__Assety, które jeszcze nie są zawarte w projektcie__ :
__Aktualne, grywalne demo__:

## Pliki projektu
### Struktura plików w projektcie

```
- Główny katalog
- - Scenes # Są tutaj przechowywane główne sceny gry
- - - Scenes/Levels # Sceny poziomów gry
- - - - Scenes/Levels/MainHall # Scena dla przykłada, np główna sala od wst
- - - Scenes/Props # Sceny z elementami otoczenia, oraz itemami do wykorzystania
- - - Scenes/Props/Chairs # Dla przykladu katalog zwiazany z krzeslami
- - - Scenes/Characters # Sceny z postaciami w grze
- - - - Scenes/Characters/Playable_Characters # Grywalne postacie z gier
- - - - Scenes/Characters/NPCs # Niegrywalne postacie takie jak Upper, albo potwór co nasz goni
- - - - Scenes/Characters/NPCs/Upper # Katalog związany z npc o nazwie Upper
- - - - - Scenes/Characters/NPCs/Upper/Resources # Pliki utworzone przez godot'a
- - - - - Scenes/Characters/NPCs/Upper/Scripts # 
- - - Scenes/TestScenes # Katalog ze scenami do testowania
- - - - Scenes/Wojtek # Katalog ze scenami testowymi od Wojtka
- - - - Scenes/Maciek # itd
- - Sprites # Katalog związany z grafikami w grze
- - - Sprites/Character # Katalog, gdzie są przechowywane sprity od Character'a. 
- - - - Sprites/Resources # Katalog, gdzie są przechowywane pliki utworzone przez godot'a
w formacie .tres (Czyli text resources, text oznacza, że dane są zapisane w UNICODE)
- - UI # Katalog gdzie są przechowywane sceny z UI
- - - UI/MainMenu # Katalog gdzie jest przechowywana scena MainMenu
- - - - UI/MainMenu/Resources # ta sama sytuacja co w spritach
- - - - UI/MainMenu/Scritps # skrypty od UI
- - Systems # Katalog, gdzie są przechowywane singletony, sceny, skrypty, resource od systemów
Np. System Dialogów, System przechowywania informacji itd.
- - Fonts # Katalog z fontami
- - Dialogs # Katalog gdzie są przechowywane dialogi w jsonie
- - ShadersAndMaterials # Katalog który zawiera programy wykonywane po stronie karty graficznej
System dialogów jest do zaprojektowania.
- - ITD
```

### Zasady tworzenia struktur w plikach
Pierwszą sprawą jest nazewnictwo. Nazwy plików, katalogów nazywamy zgodnie z ich przeznaczeniem. Starajcie się używać angielskich nazw.

__Przykład__:
Dla katalogów używacie tzw. CammelCase'a: `SuperCharacter`
Kluczowe składowe nazwy w plikach oddzielacie znakiem `_`: `main_character_sprite.png`

---
Drugą sprawą jest tworzenie nowych struktór folderów, oraz plików. Tworzycie jeśli na serio musicie nową strukturę dodać do projektu. Po utworzeniu danej struktury koniecznie dopisujecie ją w nagłówku "Struktura plików w projektcie", w takiej samej formie. Koniecznie dopiszcie mały komentarz do czego ta struktura służy

__Przykład__ :
```
- - Music # Katalog związany z plikami/scenami dzwiękowymi
- - - Music/PzykadowyFolderZeScena
- - - Music/PrzykładowyFolderZeScena/Scena.tscn
- - - - Music/PrzykładowyFolderZeScena/Resources # Katalog z utworzonymi plikami przez godota
- - - - Music/PrzykładowyFolderZeScena/Scripts # Skrypty związane ze scena "Scena.tscn"
```

## Branch'e

### Czym jest branch
Tutaj odsyłam do artykułu: [https://git-scm.com/book/pl/v2/Ga%C5%82%C4%99zie-Gita-Czym-jest-ga%C5%82%C4%85%C5%BA](https://git-scm.com/book/pl/v2/Ga%C5%82%C4%99zie-Gita-Czym-jest-ga%C5%82%C4%85%C5%BA)

__Zasada master brancha__:
Master branch przechowuje zatwierdzone zmiany przez Wojtka, które wprowadziliście do gry.
__Nikt, ale to dosłownie nikt oprócz Wojtka nie może wprowadzać zmian na masterze.__
Nieuzasadnione działanie na branchu, może powodować konflikt dla reszty osób, które pracują nad projektem. Dzięki temu czas na skończenie gry wydłuży się przez likwidowanie konfliktów w plikach. Jeśli chcecie zatwierdzić zmiany do Master'a to piszcie do Wojtka w tej sprawie, albo robicie merge request'a na stronie projektu.

## Kontrybucja
__Ogólna kontrybucja__
Tutaj nie będę sie zbytnio rozpisywał. Starajcie się pracować jak najmniejszych scenach, czyli jak tworzycie jakaś duża skomplikowaną strukture, to ją rozbijacie na pare podscen i później łączycie w jedną całość. Dodatkowo nie grzebajcie w plikach, nad którymi pracują inne osoby z teamu. Dzięki temu unikniemy zbędnych konfliktów w plikach. Jeśli chcecie testować większą mechanike, to tworzycie sobie osobną scene testową w katalogu:
```
- - - Scenes/TestScenes/TwojeImie
``` 
___
__Skrypty__
Sytuacja ze skryptami wygląda troszeczkę inaczej. Przy implementacji jakiegoś systemu/mechaniki koniecznie dokumentujcie każdą metodę(funkcja w nodzie/klasie), zmienne, atrybuty dostępu, relacje między innymi nodami oraz sygnały w specjalnym pliku. Owy plik musicie utworzyć w katalogu ze sceną o nazwie `DOCS.md`.
Rozszerzenie .md jest formatem pliku od tzw. markdown'a. Ten format pozwala na skrócenie pisania, oraz formatowanie dokumentów za pomocą specjalnych znaków. Strony internetowe interpretują plik i później wypluwają HTML'a, który możecie przeglądać(Przykladem jest ten `README.md`, który jest wyświetlany na stronie głównej projektu). Wracając do dokumentacji. Jest ona bardzo potrzebna, jeśli kto będzie chciał zmodyfikować wasz skrypt(np. w celu usunięcia jakiegoś bug'a). Dobrze napisana dokumentacja skraca czas siedzienia i rozmyślania "co autor miał na myśli". Innym atutem jest to, że w Godocie można tworzyć dziedziczone sceny na podstawie innych, więc jest wymagana znajomość jak działa scena nadrzędna. 

__Edytor do plików .md__: [https://stackedit.io/app](https://stackedit.io/app)
__Poradnik do formatowania plików .md__: [https://www.markdowntutorial.com/](https://www.markdowntutorial.com/)

__Przykład struktury katalogu__:
```
- - - - - Scenes/Characters/NPCs/Upper # Katalog od sceny npc Upper'a
- - - - - Scenes/Characters/NPCs/Upper/DOCS.md # Plik od dokumentacji
- - - - - - Scenes/Charaacters/NPCs/Uppser/Scripts # Skrypty od Upper'a
```


# Reszta pojawi się później