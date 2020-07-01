# Datagenerering til DigDirCamp 2020

av Bjørn Christian Weinbach, DigDir Campar.

## Bakgrunn

I sommar skal me lage ein applikasjon som skal demonstrere korleis tilgang til eins eigne persondata kan gjere det enklare å navigere i den norske offentlege sektor, spesielt for ungdom. Denne dataen er ikkje tilgjengeleg vha API i dag og vi er nøydd å generere denne dataen sjølv. Denne jupyter notebooken inneheld python-kode for generering av syntetiske data for ein populasjon som blei brukt som ein del av forarbeidet til prosjektet til DigDir Camparane i 2020.

## Åpne datasett som blir brukt

Postnummer: https://data.norge.no/datasets/5e6847ba-156d-4e14-85d3-8d7f8b727523

Norske navn: https://no.wikipedia.org/wiki/Liste_over_norske_mannsnavn , https://no.wikipedia.org/wiki/Liste_over_norske_kvinnenavn og https://no.wikipedia.org/wiki/Liste_over_norske_etternavn

## Genereringsalgoritmen

Itererer over ein liste med kjende personnummer som er reservert for testing. Namn og etternamn er tilfeldig sampla frå datasett over norske namn og etternamn. Postnummer og poststad er tilfeldig sampla frå datasett over postnummer.

### VIGO-data
For å lagre vigo-data om ein person blir tilfeldige karakterar og fråver sampla. Karakterar er tilfeldigt tatt i intervallet 1-6 og fråver er normalfordelt rundt 5% med standardavvik på 3%. Hittil er det kun faga RLE, Naturfag og Matematikk som er implementert.

## Helse-data
For å lagre helse-data om ein person er det pr.idag (1 Juli 2020) kun eit tilfeldig fastlegenavn og legesenter på den staden som personen bur i som i dag er tilgjengeleg  for generering.
