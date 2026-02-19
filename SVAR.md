# PGR301-eksamen-2026

OPPGAVE 1: 

Når teamet går fra en utvikler til flere. Er det viktig å lage et strukturert arbeidsflyt som sikrer til kvalitet og god samarbeid.

**Branch**: 
Teamet kan bruke en strategi for branch basert på github flow. Main skal alltid inneholde en produksjonsklar kode som er stabil. Hver medlem av teamet som utvikler vil gjøre det i egen feature branches.
Det er for å holde det trygt for at flere utviklere kan jobbe uten å påvirke hverandre. En branch vil opprettes hver gang en ny oppgave, forbedring eller bugfix startes. Navnene for branch skal være korte og beskrivende. Dette vil gi en lettere forståelse for hva som blir lagt inn. 

**Pull request prosess:**
Når man er ferdig med oppgaven sin i feature branch, skal det alltid opprettes en pull request før koden merges inn i main. Pull request er en viktig del for å kvalitets sikre i teamet. En pull request skal opprettes når en funksjonalitet er ferdig implentert og bygger uten feil. 
Pull request bør være begrenset eller små for at det skal være enklere å gjennomgå og redusere risikoen for at feil oppstår. Mindre pull request er enklere å oppdage problemer tidlig, men også å gi raskere beskjed. 
Alle pull request skal gjennomgås av minst en fra teamet. Dette er viktig for å sikre at koden fungerer som forventet. Kode review gjør det enklere å oppdage feil underveis.

**Branch protection**
Branch protection sørger for at alle endringer gjennomgår kvalitetssikring før de blir pushet til main. Dette er viktig fordi main alltid skal inneholde funksjonerende kode. Når flere utviklere jobber samtidig, kan det oppstå feil eller at uferdig kodet blir pushet direktet til hoved branchen.

Hva man kan gjøre for å sikre branch protection:
- **Push til main:** Man kan ikke pushe direkte til main. Alle endringer må sende pull request, og den må godkjennes før den går til main. 
- **Kode reviewer:** En fra teamet må godkjenne om pull request er sikret før den kan pushes. 
- **Branch oppdatering:** Om main har nye commits må man oppdatere branch før man sender en pull request. 
- **Automatiske sjekker:**

**Automatisering**
Automatisering skal settes opp med github actions for at kvaliteten skal opprettholdes uten manuelle steg. Disse automatiske sjekkene skal kjøre hver gang kode sendes inn for å klare å oppdage feil tidlig.

Bygg av applikasjon: 
- Prosjektet skal bygges opp automatisk for å sjekke at koden fungerer og at alle avhengigheter er satt opp riktig

Automatiske tester:
- Enhetstester kjøres automatisk for å sjekke at funksjonene virker som de skal. Om en test feiler, vil ikke pull request merges. 

Sikkerhetsskanning av docker-image:
- Når Docker-image bygges blir den scannet for sårbarheter før den kan brukes videre.

Docker build og push:
- Når kode merges til main, bygges en ny docker image automatisk og lastes opp til ett container registry. 

___

Oppgave 2: 

**FØR**

<img width="469" height="43" alt="dockerBefore" src="https://github.com/user-attachments/assets/a9e50a4a-5d8d-4e2f-a8c9-e71b542ddace" />






**ETTER**

<img width="582" height="45" alt="dockerAfter" src="https://github.com/user-attachments/assets/b6a41e1d-2d3a-493c-86ae-4da1c79f8058" />


Jeg testet docker image med kommandoen: 

docker build -t quiz-app .
docker run -p 8080:8080 \
-e AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID \
-e AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY \
quiz-app

Containeren startet opp og spring boot viste at porten kjørte. 

Docker container starter opp. Fant tilslutt at endepunktet var "http://localhost:8080/api/quiz/health". Hvor siden kom til "DevOps Quiz is Generator is running"


----

Oppgave 3:



____

Oppgave 4:

**Hvorfor blir DevOps viktigere når AI gjør oss produktive?**

Kunstlig intelligens som github copilot, chatGPT og claude har endret måten utviklere jobber. Oppgaver eller prosjekter som tidligere tok flere timer, kan i dag løses på minutter. Men med dette kommer det også usikkerheter, og enklere for feil å oppstå underveis.

For det første, AI kan genere kode på sekunder. Som vil si at det kommer mange endringer på kort tid. Selvom AI kommer med løsninger er det ikke alltid at det er trygt eller riktig. Derfor er det greit å ha gode DevOps rutiner, som gjør at man sikrer seg til en kode som gjør det den skal.

 





