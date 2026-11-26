# TouchDesigner – pliki do zajęć

Projekty `.toe` z zajęć z TouchDesignera. Każdy plik to osobna lekcja: sieć
operatorów z opisami (notatki *annotate*) przy każdym kroku. Otwierasz plik,
czytasz notatki od góry i zmieniasz parametry, żeby zobaczyć, co się dzieje.

## Jak zacząć

1. Zainstaluj [TouchDesigner](https://derivative.ca/download). Wystarczy darmowa
   licencja Non-Commercial. Pliki są zapisane w wersji 2025.32460; starsze
   wersje mogą ich nie otworzyć.
2. Pobierz plik: kliknij go na liście powyżej, potem **Download raw file**.
   Wszystkie naraz: zielony przycisk **Code → Download ZIP**.
3. Otwórz `.toe` w TouchDesignerze. Jeśli sieć jest poza ekranem, najedź na nią
   myszą i naciśnij **H**.

Filmy, dźwięki i modele w ćwiczeniach pochodzą z przykładów wbudowanych
w TouchDesignera, więc nic nie trzeba dociągać.

**Poruszanie się po sieci:** kółko myszy – przybliżanie, środkowy przycisk –
przesuwanie, **I** na zaznaczonym komponencie – wejście do środka, **U** – wyjście
poziom wyżej. Kliknięcie w kropkę w prawym dolnym rogu operatora włącza podgląd
na nodzie.

## Lekcje

Proponowana kolejność – od obrazu, przez sygnały, do 3D i danych z telefonu.

| Plik | Temat | Czego się nauczysz |
|---|---|---|
| [`topy_opisane_github.toe`](topy_opisane_github.toe) | **TOP – obraz** | generatory (noise, ramp, circle, text, constant), filtry i to, że ich kolejność zmienia wynik, over vs composite i tryby mieszania, matte, alfa z pliku, transform / crop / res, animacja wyrażeniami (`absTime.seconds`) |
| [`chopy_github.toe`](chopy_github.toe) | **CHOP – sygnały i ruch** | 17 opisanych sekcji: LFO, noise, mysz, klawiatura, lag (bezwładność), mapowanie zakresów, sterowanie obrazem kanałami, audio reactive, widmo FFT i odwrotnie – obraz zamieniony na kanały |
| [`SOP_podstawy_github.toe`](SOP_podstawy_github.toe) | **SOP – geometria 3D** | kamera, światło, geo i render TOP; podstawowe bryły, merge, copy (powielanie na punktach), twist i noise na geometrii, rozdzielczość i wireframe, głośność dźwięku animująca kształt |
| [`Instancje_podstawy_github.toe`](Instancje_podstawy_github.toe) | **Instancing – podstawy** | jedna bryła narysowana setki razy: grid jako rozkład, pattern CHOP jako funkcja ruchu, tabela DAT jako lista pozycji, kolor i wielkość z TOP-a |
| [`instancje_github.toe`](instancje_github.toe) | **Instancing – dalej** | instancje sterowane obrazem (jasność piksela = głębokość), kolor z obrazu, przełączanie układów klawiaturą (keyboard in, count, switch), analiza dźwięku, prosta animacja kamery |
| [`OSC_ZIGSIM_github.toe`](OSC_ZIGSIM_github.toe) | **OSC – telefon steruje obrazem** | dane z czujników telefonu przez Wi-Fi, mapowanie zakresów, pędzel z feedbackiem (ślad, który się kręci i zmienia kolor), symetria jak w kalejdoskopie, potrząśnięcie telefonem losuje kolor (pierwszy skrypt Python) |

## OSC_ZIGSIM – konfiguracja telefonu

Potrzebna jest aplikacja **ZIG SIM** (iOS / Android). Telefon i komputer muszą być
w tej samej sieci Wi-Fi.

W ZIG SIM, zakładka **Settings**:

| Ustawienie | Wartość |
|---|---|
| Data Destination | OTHER APP |
| Protocol | UDP |
| Message Format | OSC |
| IP Address | adres komputera (Windows: `cmd` → `ipconfig` → linia IPv4) |
| Port Number | **8888** |

Zakładka **Sensor**: włącz **Gravity** i **Accel**, potem **Start**.

W TouchDesignerze sprawdź `oscin1` – po chwili pojawią się kanały `gravity1`,
`accel1` itd. Przechylenie telefonu przesuwa pędzel, mocne potrząśnięcie zmienia
jego kolor.

Bez telefonu: w `switch1` ustaw **Index = 1** – wtedy pędzlem steruje mysz,
a lewy przycisk zmienia kolor. `window1` → **Open** wysyła obraz na osobne okno,
np. na projektor.

Nie ma żadnych kanałów w `oscin1`? Najczęściej to zapora Windows blokująca
TouchDesignera w sieci prywatnej, inny port w ZIG SIM albo telefon w innej
sieci (np. na danych komórkowych).

## Powiązane

- [rplidar-windows](https://github.com/technofania/rplidar-windows) – lidar RPLIDAR
  w TouchDesignerze: wykrywanie i śledzenie ludzi.
