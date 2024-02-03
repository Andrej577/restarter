# Restarter

Aplikacija Restarter namijenjena je automatskom ponovnom pokretanju određenih servisa na Windows operativnom sustavu. Aplikacija je testirana na Windows 10 unutar virtualnog okruženja i koristi .NET Framework verzije 4.7.2.

### Funkcionalnosti

- Automatsko ponovno pokretanje servisa prema definiranim postavkama.
- Zapisivanje pokretanja i ponovnog pokretanja servisa u log datoteku (`log.txt`).
- Konfiguracija vremenskih intervala za ponovno pokretanje servisa u konfiguracijskoj datoteci (`services.json`).

### Koraci za instalaciju

1. **Preuzimanje aplikacije**: Preuzmite izvorni kod ili instalacijski paket aplikacije.
2. **Postavljanje konfiguracije**: Uredite `services.json` datoteku kako biste definirali servise koji će biti ponovno pokrenuti.
3. **Instalacija servisa**: Koristite `InstallUtil.exe` za instalaciju servisa:

   ```bash
   C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe C:\putanja\do\Restarter.exe
   ```

4. **Pokretanje servisa**: Pokrenite instalirani servis pomoću alata za upravljanje servisima, Windows Services Administrative tool, ili naredbom:

   ```bash
   net start RestarterService
   ```

### Konfiguracija (`services.json`)

U datoteci `services.json` definirajte servise za ponovno pokretanje. Evo primjera konfiguracije:

```json
{
  "Services": ["ImeServisa1", "ImeServisa2"]
}
```

### Log Datoteka (`log.txt`)

Datoteka `log.txt` zapisuje informacije o pokretanju i ponovnom pokretanju servisa. Primjer zapisa u log datoteci:

```
2024-02-10 12:45:00 - Servis 'ImeServisa1' je pokrenut.
2024-02-10 13:15:00 - Pokušavam ponovno pokrenuti servis: 'ImeServisa1'.
2024-02-10 13:15:10 - Ponovno pokrenut servis: 'ImeServisa1'.
```

### Dodatne Informacije

- Aplikacija je testirana na Windows 10 i može zahtijevati administratorske privilegije za upravljanje servisima.
- Ako dođe do problema tijekom instalacije ili pokretanja, provjerite jesu li ispravne verzije .NET Frameworka i `InstallUtil.exe` alata.

### Napomena o Autoru

Autor ove aplikacije trenutno stječe iskustvo u programiranju i istražuje različite jezike i alate. Ova aplikacija služi isključivo u edukativne svrhe i kao rezultat osobnog učenja. Moguće su greške i ograničenja koje treba uzeti u obzir prilikom razmatranja ove aplikacije.

### Licence

Ova aplikacija je objavljena bez određene licence, a sva prava zadržava autor. Molimo vas da pažljivo razmotrite uvjete prije korištenja ove aplikacije u bilo kojem kontekstu.
