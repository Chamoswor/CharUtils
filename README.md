# SerialBufferLibrary

SerialBufferLibrary er et Arduino-bibliotek designet for å forenkle håndtering av data som skal konverteres til char og legges i en buffer, samt parsing av data som sendes over Serial-kommunikasjon. Dette biblioteket tilbyr to hovedfunksjoner:

1. **Bufferhåndtering**:
   - Konverterer variabler til char.
   - Legger data i en buffer.
   - Skriver bufferet til en OLED-skjerm og tømmer bufferet.

2. **Serial-parsing**:
   - Parser data sendt over Serial ved hjelp av en definert pakkeformat (start, separator og slutt).

## Innhold

```
SerialBufferLibrary/
├─── keywords.txt
├─── library.properties
├─── examples
│    ├─── BasicUsage
│    │    ├─── BasicUsage.ino
│    ├─── AdvancedParsing
│         ├─── AdvancedParsing.ino
├─── src
│    ├─── SerialBuffer.h
│    ├─── SerialBuffer.cpp
│    ├─── Parser.h
│    ├─── Parser.cpp
├─── test
     ├─── test_serialbuffer.ino
```

## Installasjon

1. Last ned biblioteket som en ZIP-fil.
2. Åpne Arduino IDE.
3. Gå til **Sketch > Include Library > Add .ZIP Library...**.
4. Velg den nedlastede ZIP-filen og legg til biblioteket.

## Bruk

### Bufferhåndtering
```cpp
#include "SerialBuffer.h"

SerialBuffer buffer;

void setup() {
  buffer.init();
  buffer.add("Temperatur: ");
  buffer.add(23.5); // Legger til en float-verdi.
  buffer.printToOLED();
}

void loop() {
  // Ingen spesiell logikk i dette eksemplet.
}
```

### Serial Parsing
```cpp
#include "Parser.h"

Parser parser;

void setup() {
  Serial.begin(9600);
  parser.setDelimiters('<', ',', '>'); // Start, separator og slutt.
}

void loop() {
  if (Serial.available()) {
    String packet = Serial.readStringUntil('\n');
    parser.parse(packet);

    String value1 = parser.getValue(0); // Hent første verdi.
    String value2 = parser.getValue(1); // Hent andre verdi.

    Serial.print("Value 1: ");
    Serial.println(value1);
    Serial.print("Value 2: ");
    Serial.println(value2);
  }
}
```

## Eksempler

Eksempler på bruk finner du i `examples`-mappen:

1. **BasicUsage**: Viser hvordan du bruker bufferhåndtering og skriver til OLED.
2. **AdvancedParsing**: Demonstrerer parsing av Serial-data.

## Lisens

Dette biblioteket er tilgjengelig under MIT-lisensen. Se `LICENSE`-filen for mer informasjon.
