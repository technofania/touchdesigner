# TouchDesigner – pliki do zajęć

Projekty `.toe` z zajęć z TouchDesignera. Każdy plik to osobna lekcja: sieć
operatorów z opisami (notatki *annotate*) przy każdym kroku. Otwierasz plik,
czytasz notatki od góry i zmieniasz parametry, żeby zobaczyć, co się dzieje.



| Plik | Temat | Czego się nauczysz |
|---|---|---|
| [`topy_opisane_github.toe`](topy_opisane_github.toe) | **TOP – obraz** | generatory (noise, ramp, circle, text, constant), filtry i to, że ich kolejność zmienia wynik, over vs composite i tryby mieszania, matte, alfa z pliku, transform / crop / res, animacja wyrażeniami (`absTime.seconds`) |
| [`chopy_github.toe`](chopy_github.toe) | **CHOP – sygnały i ruch** | LFO, noise, mysz, klawiatura, lag (bezwładność), mapowanie zakresów, sterowanie obrazem kanałami, audio reactive, widmo FFT i odwrotnie – obraz zamieniony na kanały |
| [`SOP_podstawy_github.toe`](SOP_podstawy_github.toe) | **SOP – geometria 3D** | kamera, światło, geo i render TOP; podstawowe bryły, merge, copy (powielanie na punktach), twist i noise na geometrii, rozdzielczość i wireframe, głośność dźwięku animująca kształt |
| [`Instancje_podstawy_github.toe`](Instancje_podstawy_github.toe) | **Instancing – podstawy** | jedna bryła narysowana setki razy: grid jako rozkład, pattern CHOP jako funkcja ruchu, tabela DAT jako lista pozycji, kolor i wielkość z TOPa |
| [`instancje_github.toe`](instancje_github.toe) | **Instancing – dalej** | instancje sterowane obrazem (jasność piksela = głębokość), kolor z obrazu, analiza dźwięku |
| [`OSC_ZIGSIM_github.toe`](OSC_ZIGSIM_github.toe) | **OSC – telefon steruje obrazem** | dane z czujników telefonu przez Wi-Fi, mapowanie zakresów, circle z feedbackiem (ślad, który się kręci i zmienia kolor), symetria z kalejdoskopu,  |

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


