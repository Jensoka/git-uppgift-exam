## Verisionshantering vs vanliga filer

**Vad är versionshantering och vad är den stora skillnaden mellan att spara en fil via editorns vanliga sparaknapp och att spara ändringar i Git?**
**Förklara vad som menas med att Git sparar en tidslinje av frysta ögonblicksbilder (commits). Vad bevisar det faktum att du när som helst kan klicka på din allra första commit på GitHub och fortfarande se alla tre TODO kvar i koden, trots att filen på din dator ser helt annorlunda ut idag?**

Verisionshantering är ett lokalt utvecklarverktyg som innebär att spara ändringar i en historik vi kan rulla tillbaka till. Vi kan se verisionshantering som en loggbok, med permanenta punkter av sparad historik genom tiden, från den senaste versionen till vägen hur vi kom dit.
När vi sparar en fil via editorns vanliga sparknapp (ctrl + s) så skriver våra nya ändringar över de gamla, denna metod för att spara lämnar oss utan en logg av ändringar, vilket försvårar vårat arbete skulle vi behöva rulla tillbaka misstag. Sparar vi däremot genom git kan vi spara en ögonblicksbild (commit) vi enkelt kan titta tillbaks på.
Att vi kan gå in på våra Github och se våran allra första commit med tre TODOS, bevisar att commits inte skriver över ändringar, utan har bevarat våra tidigare versioner.


## Arbetsytan, Staging och Commits

**Beskriv vad kommandona git status, git add och git commit gör i det dagliga arbetsflödet och när du kör dem.
Förklara relationen mellan arbetsytan (arket på skrivbordet), staging (kuvertet) och commit (arkivlådan). Förklara också varför Git protesterar med no changes added to commit om man har ändrat filen i editorn och försöker köra git commit direkt utan git add.**

Git status är rapporten över våran arbetsyta (arket på skrivbordet). Ändrade filer visas som untracked och har ännu inte valts och sparats i våran historik.

Git add är kommandot vi använder för att välja ut filererna och förebereda dom för commit genom att ta en överblicksbild. Vi stagear filerna och lägger dom i ett kuvert. 

Git commit kör vi för att försegla överblicksbilden och skapa en permanent punk i våran historik av änringar, vi lägger kuvertet i arkivlådan.

Kör i en git commit utan git add protesterar Git med ett felmeddelande, det är för att commit letar endast efter filer som ligger i staging (kuvertet), Ligger filen fortfarande kvar ute på arbetsytan (skrivbordet) finns det inget i kuvertet att arkivera, därför är det viktigt att vi först lägger till filerna medgit add.

## Lådan hemma vs Montern på GitHub

**Vad är skillnaden mellan mappen på din dator och repot på GitHub, och vad gör kommandot git push?
Förklara konceptet med de två rummen / minnesytorna (lådan hemma på datorn vs glasmontern på GitHub). Förklara varför git push svarar Everything up-to-date om du har ändrat i koden men glömt att staga och committa innan du kör push.**

Mappen på våran datorn är enbart den lokala versionen av vårat projekt, medans repot på Gitgub finns är sparat i en molntjänst. Det tillåter oss att hämta projektet smidigt på andra enheter eller dela med andra. För att lägga upp vårat projekt på github kör vi git push kommandot inne i vårat lokal projekt.
Man kan se våran lokala mapp som en låda som innehåller det förseglade kuvertet, vårat publika repo på Github är glasmontern, den är tom tills vi bär dit en kopia (push).

Ändrar vi våran kod utan att stagea eller commita innan vi kör git push, kommer Git att svara "Everything up-to-date". Detta därför att git push letar endast efter våran låda med kuvertet, finns ändringarna endast kvar på skrivbordet har inget kuvert förseglats, och det finns inget nytt att bära in till montern.