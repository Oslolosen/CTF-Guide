# CTF-Guide

## Kali Linux på en VM:

1. Installer VMWare Workstation på ditt operativsystem ved å besøke denne lenken: [VMWare download](https://www.vmware.com/nordics/products/workstation-player/workstation-player-evaluation.html)
    
2. Last ned ISO-filen som finnes øverst på denne siden: [ISO-file](https://www.kali.org/get-kali/#kali-installer-images)
    
3. Åpne VMWare-programmet, gå til "File", deretter "Create a New Virtual Machine".
    
4. Velg alternativet "Use ISO Image" og velg ISO-bildet du nettopp lastet ned.
    
5. Deretter kan du starte VM-en, men vi anbefaler at du tildeler minst 4 GB RAM til den.
    

## Kali Linux WSL:

Anbefaler å bruke "Windows Terminal" og ikke "cmd". Windows terminal har flere funksjoner som å autokopiere tekst som blir markert. Den har også mulighet for tabs. 
"Windows Terminal" finnes i Microsoft Store.

##### Slå på WSL:
1. Søk etter "Turn Windows features on or off"
2. Slå på "Virtual Machine Platform" og "Windows Subsystem for Linux"
3. Restart

##### Installere Kali WSL:
1. Søk etter Kali i Microsoft Store
2. Trykk "Get"
3. Du kan nå åpne Kali WSL i Windows Terminal som en egen tab


### Kali Linux Docker på en Debian Linux-maskin:

1. Oppdater pakkelisten ved å kjøre følgende kommando: 
	
	`sudo apt update`
    
2. Installer Docker ved å kjøre følgende kommando: 
    
    `sudo apt install docker.io`
    
3. Aktiver Docker-tjenesten og start den ved oppstart med disse kommandoene:
    
    `sudo systemctl enable docker --now`
    
4. Legg til brukeren din i Docker-gruppen for å unngå å bruke sudo hver gang:
    
    `sudo usermod -aG docker $USER`
    
5. Last ned Kali Linux Docker-bildet ved å bruke følgende kommando:
    
    `docker pull docker.io/kalilinux/kali-rolling`
    
6. Kjør Kali Linux i Docker-containeren med denne kommandoen:
    
    `docker run kalilinux/kali-rolling`
    
7. For å se en liste over alle Docker-containere, bruk denne kommandoen:
    
    `docker container list --all`
    
8. For å starte en tidligere opprettet Docker-container, bruk denne kommandoen:
    
    `docker start <container id>`
    
9. For å koble deg til en kjørende Docker-container, laste ned alle verktøyene og lage en bruker:
	 `docker attach <container id>` \
	 `apt-get install kali-linux-all` \
	 `adduser <navn>` \
	 `usermod -aG sudo <navn>` \
	 `su <navn>`


## Verktøy:

Ghidra: Ghidra er et fantastisk verktøy for dekompilering av kompilerte filer.

JohnTheRipper og Hashcat: Disse verktøyene er spesielt nyttige for å bryte passordhasher. JohnTheRipper er litt enklere å bruke, mens Hashcat regnes som det beste alternativet på grunn av det støttes for en rekke forskjellige hashfunksjoner.

Wireshark: Wireshark er et verktøy som lar deg analysere nettverkspakker, også kjent som PCAP-filer. Den har et grafisk grensesnitt og inkluderer også kommandolinjeverktøyet tshark for å ekstrahere spesifikke pakker.

GDB (GNU Debugger): Dette verktøyet er en debugger som gir deg muligheten til å inspisere minnet under kjøring av et program. Det er spesielt nyttig for Pwn (exploit) oppgaver, som Buffer Overflow.

Python og en teksteditor: Å ha Python tilgjengelig for å skrive raske skript som kan utføre spesifikke oppgaver, er alltid nyttig. Jeg personlig anbefaler Visual Studio Code som en teksteditor.

CyberChef: CyberChef er et program som kan dekode forskjellige "dataspråk", noe som er nyttig når du må oversette encodinger til lesbar tekst. Heldigvis er dette verktøyet webbasert. [CyberChef](https://gchq.github.io/CyberChef/)

ChatGPT: Selv om ChatGPT kan være nyttig, er det viktig å bruke den ansvarlig under CTF-oppgaver, da hacking og exploit-forsøk kan være involvert. Det er lurt å ha en god dialog med ChatGPT før du bruker den i slike sammenhenger. (Denne settningen er ordrett fra sjefen sjøl)

### Nyttige nettsider
#### Generelt (Har alle kategorier)
[picoCTF](https://play.picoctf.org/practice)
[foreverCTF](https://forever.isss.io/challenges)
[HackTheBox Challenges](https://app.hackthebox.com/challenges)

#### Lær Linux kommandoer
[OverTheWire](https://overthewire.org/wargames/bandit/)

#### Kryptografi
[CryptoHack](https://cryptohack.org/)

#### Web
[PortSwigger](https://portswigger.net/web-security)

#### Binary Exploitation (PWN)
[Exploit.Education](https://exploit.education/protostar/) (Gjør oppgavene samtidig som du ser på [LiveOverflow](https://www.youtube.com/watch?v=T03idxny9jE&list=PLhixgUqwRTjxglIswKp9mpkfPNfHkzyeN&index=13) på YouTube som går igjennom oppgavene og forklarer)\
[PWN.college](https://pwn.college/dojos) (Har kurs innen assembly, webservers, reversing, buffer overflows)

#### Forensics og Incident Response (IR)
[BlueTeamLabs](https://blueteamlabs.online/)

#### Pentesting
[HackTheBox](https://app.hackthebox.com/machines)

#### Læringsmoduler
[TryHackMe](https://tryhackme.com/)
[HackTheBox Academy](https://academy.hackthebox.com/)

#### YouTube-kanaler
[John Hammond](https://www.youtube.com/@_JohnHammond)\
[NetworkChuck](https://www.youtube.com/@NetworkChuck)\
[LiveOverflow](https://www.youtube.com/@LiveOverflow)\
[IPSec](https://www.youtube.com/@ippsec)
