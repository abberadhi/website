---
views:
    flash:
        region: flash
        template: default/image
        data:
            src: "image/snapvt19/windows-cowsay.png?c=800,200,0,0&w=1100&sharpen"
author:
    - mos
category:
    - labbmiljo
    - windows
    - bash
revision:
    "2024-08-23": "(I, mos) Genomgången och uppdaterad inför ht24."
    "2024-08-06": "(H, aar) la till stycke om vanliga fel och att man ska kolla att användarnamn inte är root."
    "2022-08-17": "(G, mos) Om wsl redan är installerat, lade till video."
    "2022-08-16": "(F, mos) Uppdaterad till senaste installationsrutinen för WSL."
    "2020-04-29": "(E, mos) Lade till unzip som kommando att installera (krävs av composer)."
    "2019-08-22": "(D, aurora) Översedd inför HT19 och Windows 10 v1903."
    "2019-01-16": "(C, mos) Förtydligande om var filer bör sparas och hur atom startas, bort med stycket om atom."
    "2019-01-13": "(B, mos) Lade till installation av nödvändiga paket."
    "2019-01-08": "(A, mos) Uppdaterad installationsprocess för 1803."
...
Installera Bash i Windows med WSL och Ubuntu
==================================

[FIGURE src=image/kunskap/installera-wsl/cowsay.png?w=c5 class="right"]

Så här gör du för att installera Bash med Ubuntu i Windows via WSL samt tar hjälp av pakethanteraren och installerar det som behövs för att komma igång med kurserna.

<!--more-->



Mer information {#pre}
-------------------------------

Denna artikel bygger på informationen som finns att läsa i "[Windows Subsystem for Linux Documentation](https://docs.microsoft.com/en-us/windows/wsl/)". Om du tappar bort dig eller behöver extra information så kan du gå och läsa den större artikeln i lugn och ro.

Läs vidare för den "snabba vägen" att komma igång med Bash/WSL i Windows.


<!-- 
Översikt av artikeln {#video}
---------------------------------

Det finns en video som visar hur Mikael jobbar igenom delar av denna artikel. Du kan titta igenom videon som ett komplement när du själv jobbar igenom artikeln.

[YOUTUBE src="njUTrRS6uiU" width=700 caption="Mikael jobbar igenom huvuddelarna i denna artikel."]
-->



Förutsättning {#pre}
-------------------------------

Du behöver minst Windows 10 version 2004 eller högre (Build 19041 och högre) eller Windows 11.

Dubbelkolla att du har en Windows build 19041, eller senare, genom att trycka `Windows key + R` och köra programmet `winver`.

[FIGURE src=image/snap22/winver_19041.png caption="Build 19041 eller högre behöver vara installerad."]

Om du har äldre version av Windows så rekommenderas att du uppdaterar tll senaste utgåvan.

Alternativet är att välja ett annat sätt att installera WSL, för detaljer se dess dokumentationen i "[Install Linux on Windows with WSL](https://docs.microsoft.com/en-us/windows/wsl/install)".



Installera WSL {#install}
-------------------------------

WSL finns med i din Windows installation men du behöver initiera det på följande sätt.



### Installera kommandot wsl {#wsl}

Kommandot `wsl.exe` behövs för att aktivera de funktioner som krävs för att köra WSL och för att installera Ubuntu-distributionen av Linux inuti Windows.

Starta terminalen PowerShell och kör följande kommando för att initiera kommandot `wsl.exe`.

```
wsl --install
```

Den kan se ut så här, precis innan du startar installationen genom att trycka ENTER.

[FIGURE src=image/kunskap/installera-wsl/wsl-install.png?w=w3 caption="Skriv in kommandot för att installera wsl i PowerShell."]

När kommandot är klart så startar du om din maskin.



#### Vanliga fel {#fel}

Det är ganska vanligt att man får fel när man kör kommandot ovanför. Här kan ni se de fel vi har stött på tidigare och lösningar på dem.

- [Error: 0x80370114 The operation could not be started because a required feature is not installed](https://github.com/dbwebb-se/python/issues/44#issuecomment-1688061083)
- [Error : 0x80004002 - No such interface supported](https://github.com/dbwebb-se/python/issues/44#issuecomment-1689479751)
- [Failed to attach disk, ERROR_FILE_NOT_FOUND](https://github.com/dbwebb-se/python/issues/44#issuecomment-1691101806)
- [Error : 0x80370102 - Enable virtualization i BIOS](https://github.com/dbwebb-se/python/issues/44#issuecomment-1691142414)

Om ditt fel inte finns med i listan kan du kolla om det finns med här [Kända fel och lösningar](https://github.com/dbwebb-se/python/issues/44).

Hittar du inte din felkod eller ditt problem så letar du vidare i "[Troubleshooting Windows Subsystem for Linux: Installation issues](https://learn.microsoft.com/en-us/windows/wsl/troubleshooting#installation-issues)". Sök efter din felkod.

Du kan även skriva i Discord chatten, men se alltid om du kan hitta en referens till din felkod först.



### Installera Ubuntu i WSL {#installubuntu}

När maskinen har bootat kan du återigen öppna PowerShell och köra följande kommandon för att se att processen gick bra.

```
wsl --list --online
```

Det kan se ut ungefär så här.

[FIGURE src=image/kunskap/installera-wsl/wsl-list-online.png?w=w3 caption="WSL är installerat och du kan nu installera Linux distributionen Ubuntu."]

Vi väljer att installera distributionen för Ubuntu.

```
wsl --install --distribution Ubuntu
```

[FIGURE src=image/kunskap/installera-wsl/wsl-install-ubuntu.png?w=w3 caption="Förberedd för att installera distributionen Ubuntu i WSL."]

I slutet av processen skall du skapa en användare och ett lösenord i Ubuntu. Detta är din specifika användare inuti Ubuntu och har inget att göra med din Windows-användare. Välj ett kort användarnamn och ett kort lösenord så blir det smidigt att använda. Använd inte mellanslag eller svenska tecken i användarnamnet.

[FIGURE src=image/kunskap/installera-wsl/wsl-install-ubuntu-done.png?w=w3 caption="Så här ser resultatet ut när du är klar med att installera Ubuntu i WSL."]

Om det står något i stil med `root@desktop:~#` (det är `root` du ska ha utkik efter) istället för användarnamnet du valde (på bilden är det `mos`), då behöver du göra om installationen så att ditt användarnamn skapas korrekt. Avinstallera först WSL genom att öppna PowerShell och kör kommandot `wsl --unregister Ubuntu`. Gör sen om installationen och skriv in användarnamn och lösenord när det efterfrågas.

Nu är du klar med installationen av Ubuntu i WSL i Windows och du har tillgång till en bash-terminal som krävs för kurserna.



### Starta Ubuntu {#start}

Du kan nu starta Ubuntu genom att köra kommandot `ubuntu` via sökfältet eller via `Windows key + R`.

Det kan se ut så här.

[FIGURE src=image/kunskap/installera-wsl/start-ubuntu.png?w=w3 caption="Nu har du tillgång till en bash terminal, via Ubuntu och WSL."]

Du har nu en Linux-terminal, en bash terminal, i din Windows.

Fortsätt nu att konfigurera din terminal.



Pakethantering {#paket}
------------------------------

För att installera program så använder du en pakethanterare som heter `apt`. Med den kan du installera paket, tjänster och programvaror i din terminal.



### Uppdatera och uppgradera {#update}

Vi börjar med att uppdatera installationen med senaste informationen om de paket som finns och vi uppgraderar systemet till att använda senaste versionen av paketen.

```text
sudo apt update && sudo apt -y upgrade
```

När du kör ett kommando med `sudo` så kör du det som root-användaren med extra behörigheter. När du installerar med pakethanteraren behöver du göra det.

Det tar en liten stund att uppgradera.



### Copy & paste mellan Windows och terminalen {#copypaste}

När du vill kopiera text mellan Windows och terminalen kan du markera texten och trycka `ctrl-c`, för att pasta texten kan du trycka `ctrl-v`.



### Installera nödvändiga paket {#nodvandig}

Vi skall installera ett par paket som gör din vardag enklare. Det är paket som används i kurserna och vi vill försäkra oss om att de är installerade.

```text
sudo apt install wget curl ssh rsync git unzip
```

Här är en kort förklaring till de olika kommandona.

| Kommando | Förklaring |
|----------|------------|
| wget     | Ladda ned resurser från nätet/webben. |
| curl     | Alternativ till wget. |
| ssh      | SSH klient och server, används för att koppla upp mot externa servrar. |
| rsync    | Kopiera/synka innehåll i kataloger, lokalt och mellan servrar. |
| git      | Klient till versionshanteringssystemet git. |
| unzip    | Zippar upp filer som är paketerade. |



### Manualsidor och man man {#man}

Manualsidor är källan till kunskap i en Linux terminal.

```text
man curl
```

Om programmet `man` inte finns installerat så installerar du det.

```text
sudo apt install man
```

Man kan söka efter de programpaket som går att installera.

```text
sudo apt-cache search curl
```

Vänd dig till manualsidan för att veta hur du använder ett kommando.

Du kan också använda optionen `--help` alternativt `-h`, många kommandon stödjer den switchen för att visa hur man använder kommandot.

```text
curl --help
```



### Installera cowsay {#cowsay}

För att testa pakethanteraren kan du installera paketet `cowsay` som är ett litet skoj-paket.

```text
sudo apt install cowsay
```

Nu kan vi köra programmet.

```text
cowsay "Hej alla programmerare!"
```

[FIGURE src=image/kunskap/installera-wsl/cowsay.png?w=w3 caption="Kul med terminalprogram i bash med Ubuntu och WSL."]

Vill du vet mer om programmet så öppnar du dess manualsida.



Öppna filväljaren och texteditorn {#open}
------------------------------

När du är i terminalen kan du öppna vissa Windows-applikationer som till exempel filväljaren och texteditorn. Det kan vara ett bra hjälpmedel att öppna dem i den katalogen där man står för tillfället.



### Öppna Explorer från terminalen {#explorer}

Prova att öppna filväljaren i den katalog du står i terminalen, punkten refererar till den katalog du för tillfället står i.

```text
explorer.exe .
```

Du kan även prova att flytta till din hemmakatalog och skriva ut nuvarande sökväg till katalogen där du befinner dig.

Flytta till din hemmakatalog i WSL.

```
cd
```

Visa sökvägen till den katalog där du nu befinner dig i.

```
pwd
```

Det kan se ut så här.

[FIGURE src=image/kunskap/installera-wsl/open-explorer.png?w=w3 caption="Öppna explorer för att se filträdet inuti WSL."]

Nu öppnas filväljaren och visar filerna i katalogen samt en sökväg till dem.

[FIGURE src=image/kunskap/installera-wsl/explorer.png?w=w3 caption="Nu kan du gå igenom filerna och filträdet som finns i WSL."]

Om du inte ser filändelser eller dolda filer och kataloger i din Explorer så kan du behöva konfigurera det via "Options -> View" och klicka i enligt följande.

* Klicka i
    * "Display the full path in the title bar"
    * "Show hidden files, folders and drives"
* Klicka bort
    * "Hide extensions for known filetypes"

Via explorer kan du enkelt kopiera filer och kataloger mellan filstrukturen i Windows och filstrukturen i WSL.



### Öppna VSCode från terminalen {#open-vscode}

Se till att du har installerat Visual Studio Code och att du kan öppna den som en Windowsapplikation. Om du installerar vscode så behöver du även starta om terminalen så att den kan hitta kommandot.

<!--
GAMMAL INFO?
För att öppna VSCode från terminalen behöver du installera ett tillägg i VSCode.

[FIGURE src=image/vscode/vscode-wsl.png?w=w3 caption="Installera Remote - WSL i VSCode."]

Gör som bilden visar, gå till fliken för tillägg, sök på "wsl" och installera "Remote - WSL". Efter det behöver du starta om terminalen.
-->

Nu kan du starta vscode inuti WSL så här. Första gången du gör det kommer den installera det som behövs och det tar lite längre tid.

```text
code .
```

Det kan se ut så här.

[FIGURE src=image/kunskap/installera-wsl/code.png?w=w3 caption="Nu kan du titta och redigera filerna som finns i WSL via vscode."]

Nu kan du redigera filer som ligger inuti din WSL instans.



Var finns Windows hemma-katalog? {#winhome}
------------------------------

Du kör Linux i ett eget system där du har speciella Linux-användare och ett filsystem för Linux. Din installation fungerar som ett eget system, ett subsystem inuti Windows. Därav namnet "Windows Subsystem for Linux (WSL)".

Du kan komma åt ditt vanliga Windows filsystem, din "vanliga" `C:`, och på det sättet dela filer mellan Linux och Windows. Du hittar dina Windows-filsystem under katalogen `/mnt`.

Du kan använda kommandot `ls` för att lista de kataloger som ligger under katalogen `/mnt`. I mitt fall ligger där katalogen `c` som innehåller alla filerna på min `C:`.

```text
cd /mnt
pwd
ls -l
```

Kommandot `pwd` visar dig den katalogen du står i för tillfället.

Tänk på katalogstrukturen som ett träd. Katalogen `.` är nuvarande katalog och katalogen `..` är katalogen ovanför. Vill du gå ett steg upp i katalogstrukturen så skriver du alltså `cd ..`.

```text
# Gå ett steg ned i katalogstrukturen, i en underkatalog
cd c
pwd
ls -l

# Gå ett steg upp i katalogstrukturen
cd ..
pwd
ls -l
```

Sökvägen till min hemmakatalog i Windows blir då `/mnt/c/Users/mos/` om min Windowsanvändare heter "mos" och om jag har en engelsk installation av Windows.



### Skapa länk till Windows hemmakatalog {#lnswinhome}

För att göra det enkelt att nå filerna i din Windows hemma-katalog så kan du skapa en symbolisk länk i din hemmakatalog.

Börja med att gå tillbaka till din hemmakatalog i terminalen.

```text
cd
```

Nu kan du skapa en symbolisk länk till din Windows hemmakatalog med kommandot `ln -s`.

```text
ln -s /mnt/c/Users/mos/ winhome
ls -l
```

Nu kan jag enkelt nå mina filer som ligger hos min Windows-användare samt eventuellt kopiera över en backup till min Windows-katalog.

```text
# Flytta till min windows home, när jag står i min Linux hemmakatalog
cd winhome
pwd
ls

# Flytta till min hemmakatalog i Linux
cd
pwd
ls
```

Om det inte fungerar kan du radera den symboliska länken och börja om.

```text
cd
rm winhome
```

När du jobbar med kurserna rekommenderas det att du sparar alla filerna i WSL miljön. Det gör det enklast att nå dem via både WSL och texteditorn. Men se till att du har backup på filerna och att du kopierar dem till ett säkert ställa, om något går fel.



Avslutningsvis {#avslutning}
------------------------------

Det finns mycket att lära om WSL, Bash och Ubuntu. Lek runt med din terminal för att lära dig hur det fungerar.


<!--

Bra att ha {#braattha}
------------------------------

Följande tips kan göra din bekantskap lite trevligare med Linux och bash-terminalen för Windows.


### Tabba men utan ljud {#tab}

När du använder terminalen kan du ofta använda tangenten `tab` för att låta terminalen själv leta upp filer och applikationer till dig.

Prova att skriva `cow` och sedan klicka på tab-tangenten och se vad som händer.

Terminalen kommer att leta reda på kommandon som börjar på `cow` och visa dem för dig.

Prova sedan att skriva `ls w` och klicka tab.

Terminalen kommer att fylla i med det fil- eller katalognamn som matchar bokstaven.

Prova att börja använda tab och du kommer att slippa skriva en massa tecken på tangentbordet.

Dock, ibland får du ett irriterande signal, ett beep, varje gång du tabbar. Det vill vi ta bort på följande vis.

Gå till din hemmakatalog och redigera filen `.bashrc` med din texteditor och sist i filen lägger du till raden `bind 'set bell-style none'`.

Börja med att öppna filen i texteditorn (skapa processen i bakgrunden med `&` så blockar du inte terminalen)

```text
code ~/.bashrc &
```

[FIGURE src=image/snap22/ubuntu_start_code_bashrc.png?w=w3 caption="Öppna filen .bashrc med din texteditor."]

Lägg till följande rad sist i filen.

```text
bind 'set bell-style none'
```

[FIGURE src=image/snap22/ubuntu_edit_bashrc.png?w=w3 caption="Redigera konfigurationsfilen .bashrc och lägg till kommandot för att stänga av beepet."]

Spara filen i texteditorn. Gå nu till terminalen och läs in filen ("sourca filen") för att aktivera ändringen du gjorde.

```text
source .bashrc
```

[FIGURE src=image/snap22/ubuntu_source_bashrc.png?w=w3 caption="Aktivera ändringen genom att sourca konfigurationsfilen .bashrc."]

Nu bör beepet försvinna när du använder tab-tangenten. Nu kan du tabba på.
-->

<!--
### Sudo utan lösenord {#sudo}

För att slippa skriva lösenord varje gång du skriver kommandot `sudo` så kan du lägga en fil i katalogen `/etc/sudoers.d/` och döpa filen till ditt användarnamn. Filen skall innehålla en rad likt denna (där min användare är "mos").

```text
mos ALL=NOPASSWD: ALL
```

Följande kommandorad skapar en sådan fil för din användare.

```bash
sudo bash -c "echo '$USER ALL=NOPASSWD: ALL' > /etc/sudoers.d/$USER && cat /etc/sudoers.d/$USER"
```

Pröva nu att köra sudo, till exempel `sudo ls /`, så bör det fungera utan att du behöver ange lösenord.

Här är en forumtråd som hanterar [sudo utan lösenord](t/4327).
-->
