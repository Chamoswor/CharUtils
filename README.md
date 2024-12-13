# SerialBufferLibrary

SerialBufferLibrary er et Arduino-bibliotek designet for å forenkle håndtering av data som skal konverteres til char og legges i en buffer, samt parsing av data som sendes over Serial-kommunikasjon. Dette biblioteket tilbyr to hovedfunksjoner:

1. **Bufferhåndtering**:
   - Konverterer variabler til char.
   - Legger data i en buffer.
   - Skriver bufferet til en OLED-skjerm og tømmer bufferet.

2. **Serial-parsing**:
   - Parser data sendt over Serial ved hjelp av en definert pakkeformat (start, separator og slutt).

## Installasjon

### Arduino IDE

1. Last ned biblioteket som en ZIP-fil.
2. Åpne Arduino IDE.
3. Gå til **Sketch > Include Library > Add .ZIP Library...**.
4. Velg den nedlastede ZIP-filen og legg til biblioteket.

### PlatformIO

1. Åpne ditt PlatformIO-prosjekt i en teksteditor eller IDE som støtter PlatformIO.
2. Naviger til `platformio.ini`-filen.
3. Legg til følgende linje under `[env:your_environment]` for å inkludere biblioteket:

   ```ini
   lib_deps =
     https://github.com/Chamoswor/CharUtils.git
   ```
4. Lagre `platformio.ini` og bygg prosjektet. PlatformIO vil automatisk laste ned og inkludere biblioteket.

## Bruk

### Bufferhåndtering
```cpp
#include "CharUtils.h"

ClassName name;

void setup() {
   // ingenting enda
}

void loop() {
  // ingenting enda
}
```

### Serial Parsing
```cpp
#include "name.h"

ClassName name;

void setup() {
   // ingenting enda
}

void loop() {
   // ingenting enda
}
```

## Eksempler

Eksempler på bruk finner du i `examples`-mappen:

1. **Name**: forklaring
2. **Name**: forklaring

## Lisens

Dette biblioteket er tilgjengelig under MIT-lisensen. Se `LICENSE`-filen for mer informasjon.
