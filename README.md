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

For å lagre vigo-data om ein person bli ein python klasse brukt til å lage tilfeldige karakterar og fråver. Karakterar er tilfeldigt tatt i intervallet 1-6 og fråver er normalfordelt rundt 5% med standardavvik på 3%. Hittil er det kun faga RLE, Naturfag og Matematikk som er implementert.

## Helse-norge data

Helse-norge data er delt opp i 4 deler. Fastlege, Resepter, Legetimer og Vaksiner. Alle desse har i drupal sine eigne routinger som returnerer data av den aktuelle typen

### Fastlege

Genererer tilfeldig navn, legekontor og telefonnummer for å være fastlege til eit gitt personnummer.

### Resepter

For eit gitt perssonnummer, trekk ut ein tilfeldig resept fra datasettet medisin.csv og gi det ein tilfeldig dato.

### Legetime

For eit gitt personnummer, opprett ein tilfeldig lege, dato for legetime, type legetime og sjukehus + stad. Alle sampla frå datasett i csv filer.

### Vaksiner

For eit gitt personnummer, opprett tilfeldige vaksinetyper sampla frå datasett og sett vaksinasjonsdato til å være ein tilfeldig dato.

## Lånekassen-data

Jupyter notebooken genererer data over forskjellige typer stipend. Kva stipend som blir satt for ein person er binomisk fordelt med prosentvis sannsynligheit basert på statistikk fra lånekassen  (https://data.lanekassen.no/statistikk/temasider/videregaaende-utdanning/). 

## Skatteetaten-data

 Skatteetaten data sampler tilfeldige inntekter i ein skeiv fordeling der medianverdi er 20000 og gjennomsnitt er 30000. Skatt er utrekna trinnvis fra 50000 opp til 100000. I tilegg er selskap som henter skattekort tilfeldige selskap fra Noregs 500 største bedrifter.
 
## Digipost

Fir eit gitt perssonnummer, lag tilfeldige brev det emnet og avssender er sampla fra datasett medan innholdet er automatisk generert.
