# EDENBERG-OS: Intelligent Affärssystem för AI-driven Operation

## 🎯 Vad är EDENBERG-OS?

EDENBERG-OS är ett integrerat operativsystem för Edenbergs verksamhet, byggt på AI-teknologi och automatisering. Systemet kombinerar flera specialiserade agenter som arbetar tillsammans för att effektivisera affärsprocesser inom försäljning, projekt, ekonomi, marknad, service och administration.

Systemet är **en digital organisation** där varje agent har ett specifikt ansvarsområde och kan samarbeta med andra agenter för att lösa komplexa affärsuppgifter.

---

## 💡 Syfte

EDENBERG-OS är utformat för att:

- **Automatisera** repetitiva affärsprocesser
- **Öka effektiviteten** genom AI-driven beslutsfattande
- **Säkerställa konsistens** i kommunikation och dokumentation
- **Minska manuellt arbete** för medarbetare
- **Skapa databas** av kunskap och processer
- **Möjliggöra skalning** av verksamheten utan proportionell ökad resursbehov

---

## 🤖 Hur AI-Agenterna Fungerar

### Agenternas Uppgifter

Systemet består av 8 specialiserade agenter:

| Agent | Kod | Ansvarsområde |
|-------|------|---------------|
| **VD-Agenten** | `01_VD_AGENT` | Strategisk övervakning, rapporter, affärsbeslut |
| **Offert-Agenten** | `02_OFFERT_AGENT` | Offerthantering, prisberäkning, försäljningsunderlag |
| **Service-Koordinator** | `03_SERVICEKOORDINATOR` | Kundsupport, serviceärenden, kundkommunikation |
| **Projekt-Agenten** | `04_PROJEKT_AGENT` | Projektplanering, tidsplan, resursallokering |
| **Ekonomi-Agenten** | `05_EKONOMI_AGENT` | Fakturering, bokföring, ekonomisk rapportering |
| **Marknad-Agenten** | `06_MARKNAD_AGENT` | Marknadsanalys, kampanjer, kundinsikter |
| **MEPS-Agenten** | `07_MEPS_AGENT` | Materialplanering, lagerstyrning, inköp |
| **Dokument-Agenten** | `08_DOKUMENT_AGENT` | Dokumenthantering, arkivering, sökning |

### Agentens Arbetscykel

```
1. INPUT
   └─ Mottar uppgift/data från användare eller annan agent

2. ANALYS
   └─ Analyserar mot relevanta regler och context
   └─ Konsulterar COMPANY_CONTEXT och SYSTEM_RULES
   └─ Identifierar relevanta mallar och tidigare dokument

3. BESLUT
   └─ Fattar beslut baserat på träning och regler
   └─ Flaggar osäkerheter för manuell granskning

4. GENERERING
   └─ Skapar eller uppdaterar dokument/data
   └─ Använder namnstandard och versionering
   └─ Lägger till metadata och spårning

5. VALIDERING
   └─ Kontrollerar mot systemregler
   └─ Säkerställer kvalitet och format

6. OUTPUT
   └─ Levererar resultat
   └─ Uppdaterar relevant dokumentbank
   └─ Informerar andra agenter vid behov
```

### Agent-till-Agent Kommunikation

Agenter kan automatiskt begära information från varandra:

- **Offert-Agent** → **MEPS-Agent**: "Vilken är lagerstatus för artikel XYZ?"
- **Projekt-Agent** → **Ekonomi-Agent**: "Vilken är kostnadsestimatet för resurser?"
- **Service-Koordinator** → **Dokument-Agent**: "Hämta senaste serviceprotokoll för kund ABC"

---

## 🏗️ Systemarkitektur

### Fysisk Struktur

```
EDENBERG-OS/
│
├── AGENT-SYSTEM (01-08)
│   ├── 01_VD_AGENT/
│   │   ├── prompts/
│   │   ├── rules.md
│   │   └── context.md
│   ├── 02_OFFERT_AGENT/
│   ├── 03_SERVICEKOORDINATOR/
│   ├── 04_PROJEKT_AGENT/
│   ├── 05_EKONOMI_AGENT/
│   ├── 06_MARKNAD_AGENT/
│   ├── 07_MEPS_AGENT/
│   └── 08_DOKUMENT_AGENT/
│
├── INFRASTRUKTUR & RESURSER (20-90)
│   ├── 20_DOKUMENTBANK/       → Alla genererade dokument sparas här
│   ├── 30_MALLAR/             → Dokumentmallar för varje agent
│   ├── 40_PRISLISTOR/         → Aktuella priser och rabattsystem
│   ├── 50_KPI_SYSTEM/         → Nyckeltal och mätindikatorer
│   ├── 60_DASHBOARDS/         → Visualiseringar och rapporter
│   ├── 70_AUTOMATIONER/       → Automatiserade arbetsflöden
│   ├── 80_API/                → API-gränssnitt för integrationer
│   └── 90_PROMPT_LIBRARY/     → Centraliserade prompter och instruktioner
│
└── SYSTEMKONFIGURATION
    ├── README.md              → Du läser detta!
    ├── SYSTEM_RULES.md        → Regler för alla agenter
    └── COMPANY_CONTEXT.md     → Edenbergs affärskontext
```

### Datflöde

```
ANVÄNDARE
    ↓
AGENT (mottar uppgift)
    ├→ Läser: SYSTEM_RULES.md + COMPANY_CONTEXT.md
    ├→ Söker: DOKUMENTBANK + MALLAR + PRISLISTOR
    ├→ Kan kontakta: Andra agenter
    └→ Använder: PROMPT_LIBRARY för instruktioner
    ↓
OUTPUT (dokument, data, svar)
    ├→ Sparas i: 20_DOKUMENTBANK/
    ├→ Uppdaterar: Relevanta system (KPI, Dashboard, API)
    └→ Informerar: Berörda agenter/användare
```

---

## 👥 Ansvarsfördelning

### Primärt Ansvar per Agent

**VD-Agenten (01)**
- Övervakar systemhälsa och nyckeltal
- Genererar rapporter för ledning
- Escalerar kritiska problem
- Strategisk vägledning för andra agenter

**Offert-Agenten (02)**
- Skapar och hanterar offerter
- Beräknar priser baserat på PRISLISTOR
- Håller dialog med kunder om förfrågningar
- Uppdaterar försäljningsfunnel

**Service-Koordinatorn (03)**
- Mottar och registrerar serviceärenden
- Tilldelar till rätt team/agent
- Upprätthåller kundkommunikation
- Säkerställer kvalitet på service

**Projekt-Agenten (04)**
- Planerar och schemalägger projekt
- Hanterar resursallokering
- Övervakar projektstatus
- Rapporterar avvikelser

**Ekonomi-Agenten (05)**
- Hanterar fakturering och betalningar
- Bokför transaktioner
- Skapar ekonomiska rapporter
- Säkerställer compliance

**Marknad-Agenten (06)**
- Analyserar marknadstrends
- Planerar marknadsaktiviteter
- Analyserar konkurrensläge
- Genererar kundinsikter

**MEPS-Agenten (07)**
- Planerar materialbehovet
- Hanterar lagersaldo
- Initierar inköpsorder
- Optimerar lagerkostnader

**Dokument-Agenten (08)**
- Indexerar alla skapade dokument
- Möjliggör sökning och hämtning
- Organisersar dokumentbank
- Hanterar versionshistorik

### Gränsöverskridande Ansvar

Vissa uppgifter kräver samarbete mellan agenter:

- **Offert → Ekonomi**: Priskalkyl med skatter och rabatter
- **Projekt → MEPS**: Materialbehovsplanering
- **Projekt → Ekonomi**: Budgetöversikt
- **Service → Dokument**: Hämtning av serviceprotokoll
- **VD → Alla**: Informationssamlande för rapporter

---

## 📁 Hur Dokument Sparas

### Dokumentflöde

1. **Generering**: Agent skapar dokument enligt mall
2. **Metadata**: Dokument taggas med:
   - Agent som skapade det
   - Datum och tid
   - Version
   - Relevanta kopplingar (kund, projekt, produkt)
3. **Lagring**: Sparas i `20_DOKUMENTBANK/`
4. **Indexering**: Dokument-Agenten indexerar för sökning
5. **Arkivering**: Gamla dokument arkiveras enligt policy

### Dokumentbank-Struktur

```
20_DOKUMENTBANK/
├── OFFERTER/
│   ├── 2026/
│   │   ├── 202605/
│   │   │   └── OFF_2026_05_001_KUNDNAMN.pdf
│   │   └── 202606/
│   └── 2025/
│
├── PROJEKT/
│   ├── PJKT_2026_001_PROJEKTNAMN/
│   │   ├── Planeringsunderlag/
│   │   ├── Statusrapporter/
│   │   └── Slutrapport/
│
├── FAKTURER/
│   ├── 2026/
│   │   └── FAK_2026_05_0001.pdf
│
├── SERVICE/
│   ├── SERVICEPROTOKOLL/
│   ├── KUNDÄRENDEN/
│   └── LÖSNINGAR/
│
├── RAPPORTER/
│   ├── MÅNADSRAPPORTER/
│   ├── ÅRSRAPPORTER/
│   └── SPECIALRAPPORTER/
│
└── MARKNADSANALYS/
    ├── TRENDRAPPORTER/
    └── KONKURRENSANALYS/
```

---

## 📋 Namnstandard

All namngivning följer ett konsekvent system för att underlätta sökning och organisation.

### Grundprinciper

- **Använd versaler** för prefix
- **Använd understreck** som separator
- **Inkludera datum** i format YYYYMMDD där relevant
- **Ord separeras** med mellanslag eller bindestreck

### Agent-specifika Prefix

```
OF_    = Offert (Offert-Agent)
PJKT_  = Projekt (Projekt-Agent)
FAK_   = Faktura (Ekonomi-Agent)
SR_    = Serviceärende/Serviceprotokoll (Service-Koordinator)
KPI_   = Nyckeltal (VD-Agent)
MKT_   = Marknad (Marknad-Agent)
MAT_   = Material/MEPS (MEPS-Agent)
DOK_   = Dokument/Allmänt (Dokument-Agent)
```

### Namngivningsexempel

| Dokumenttyp | Format | Exempel |
|-------------|--------|---------|
| Offert | `OF_YYYY_MM_NNN_KUNDNAMN` | `OF_2026_05_001_ACME_AB` |
| Projekt | `PJKT_YYYY_NNN_NAMN` | `PJKT_2026_001_WEBSHOP_MIGRATION` |
| Faktura | `FAK_YYYY_MM_NNNN` | `FAK_2026_05_0042` |
| Serviceärende | `SR_YYYY_MM_NNN_KUNDNAMN` | `SR_2026_05_015_TEKNIKS_AB` |
| KPI-Rapport | `KPI_YYYY_MM` | `KPI_2026_05` |
| Marknadsrapport | `MKT_YYYY_MM_TEMA` | `MKT_2026_05_SOMMARKAMPANJ` |
| Materialplan | `MAT_YYYY_MM_PROJEKT` | `MAT_2026_05_PJKT_001` |

### Filformat & Extensions

```
.pdf     = Slutgiltiga dokument för utskrift/arkiv
.docx    = Dokument under redigering
.xlsx    = Datasamlingar och kalkyl
.json    = Strukturerad data och konfigurationer
.md      = Dokumentation och processärbeslut
```

---

## 🔄 Versionshantering

### Versionsnummering

Alla dokument följer **Semantic Versioning**: `MAJOR.MINOR.PATCH`

```
1.0.0  = Första releaserad version
1.1.0  = Minor update (nya funktioner, bakåtkompatibel)
1.1.1  = Patch (bugfix, liten ändring)
2.0.0  = Major version (breaking changes)
```

### Versioningskonvention

**I filnamn:**
```
OF_2026_05_001_ACME_AB_v1.0.0.pdf
```

**I metadata/dokumentinfo:**
```
Dokument: Offert ACME AB
Version: 1.0.0
Skapad: 2026-05-18
Uppdaterad: 2026-05-18
Status: GODKÄND
Skapare: Offert-Agent
```

### Versionshistorik

Varje dokuments historik sparas:

```
Version 1.0.0 (2026-05-18): Initial offert
Version 1.1.0 (2026-05-19): Uppdaterade priser enligt kampanj
Version 1.1.1 (2026-05-20): Korrigerad rabatt för artikel XYZ
Version 2.0.0 (2026-05-22): Reviderad omfattning - nytt scope
```

### Hantering av Uppdateringar

1. **Mindre ändringar** (justering av text, stavfel) → PATCH
2. **Nya delar eller funktioner** (ny rabatt, nya villkor) → MINOR
3. **Fundamental omarbetning** (annat scope, nya produkter) → MAJOR

### Giltighet

- Endast den **senaste versionen** är officiell
- Tidigare versioner sparas för historik och revision
- Om nyare version finns → använd alltid den nya
- Vid tvivel om version → kontakta Dokument-Agenten

---

## ✅ Regler för AI-Genererat Material

### Kvalitetsstandarder

All material som genereras av agenter **måste uppfylla**:

#### 1. **Korrekthet**
- ✓ Information måste vara faktiskt korrekt
- ✓ Priser måste matcha aktuella PRISLISTOR
- ✓ Kundinformation måste vara uppdaterad
- ✗ Aldrig gissa på fakta - flagga osäkerheter

#### 2. **Relevans**
- ✓ Innehållet måste direkt adressera uppgiften
- ✓ Informationen måste vara applicerbar
- ✓ Onödig padding eller fyllnadstext är förbjuden
- ✗ Undvik irrelevanta tangenter

#### 3. **Språk & Stil**
- ✓ **Svenska** är standardspråket (om inte annat specifieras)
- ✓ Professionell ton för externa dokument
- ✓ Tydligt och begripligt språk
- ✓ Korrekta stavning och grammatik
- ✗ Slang eller oprofessionell terminologi är förbjuden

#### 4. **Konsistens**
- ✓ Följ etablerade mallar
- ✓ Använd samma terminologi som tidigare dokument
- ✓ Håll samma formatering
- ✓ Referera till tidigare beslut på samma sätt
- ✗ Avvikelser måste godkännas av VD-Agenten

#### 5. **Transparens**
- ✓ Markera tydligt vad som är AI-genererat
- ✓ Visa antaganden och källor
- ✓ Notera osäkerheter och begränsningar
- ✓ Inkludera revisions-trail
- ✗ Försök aldrig att dölja att materialet är AI-genererat

### Innehållsregler

#### Offerter & Prissättning
- Måste baseras på PRISLISTOR i `40_PRISLISTOR/`
- Rabatter kan endast ges enligt godkänd rabattskalka
- Leveranstider måste verifieras med MEPS
- Betalningsvillkor måste följa ekonomi-policys

#### Projekt & Tidsplaner
- Måste inkludera buffer för oväntade problem
- Resursbehov måste vara realistiska
- Milstolpar måste vara mätbara
- Risker måste identifieras och dokumenteras

#### Kundkommunikation
- Alltid professionell och respektfull ton
- Håll löften och tidsplaner
- Escalera problem omedelbar
- Dokumentera alla viktiga diskussioner

#### Finansiella Dokument
- Måste vara revisionsspårbara
- Alla belopp måste kunna verifieras
- Följ redovisningsstandarder (BAS/IFRS)
- Teckna ansvar för felaktig information

### Godkännandeprocess

**Innan publikation måste AI-genererat material godkännas:**

1. **Automatisk validering** (systemregler)
   - Formatering ✓
   - Namngivning ✓
   - Metadata ✓

2. **Agentvalidering** (relevant agent)
   - Logik och innehåll ✓
   - Konsistens ✓
   - Lämplighet ✓

3. **Manuell granskning** (vid behov)
   - Första gången för ny dokumenttyp
   - Högvärdiga transaktioner (>100k SEK)
   - Kundkommunikation med anledning
   - Strategiska dokument

4. **VD-Godkännande** (vid behov)
   - Strategiska beslut
   - Nya policys
   - Större avvikelser från standard

### Osäkerhet & Escalation

Om en agent är osäker på något:

1. **Flagga problemet** - Markera dokumentet som "REVIEW NEEDED"
2. **Dokumentera osäkerheten** - Beskriv vad som är oklart
3. **Referera till källa** - Vilken information saknas?
4. **Vänta på godkännande** - Publicera INTE innan godkännande
5. **Eskalera vid behov** - Kontakta VD-Agenten om kritiskt

### Etik & Compliance

Alla agenter måste:

- ✓ Respektera persondata (GDPR)
- ✓ Skydda affärshemligheter
- ✓ Följa juridiska krav och regler
- ✓ Undvika intressekonflikter
- ✓ Rapportera misstänkta överträdelser
- ✗ Aldrig leverera material av dålig kvalitet medvetet
- ✗ Aldrig användas för vilseledande information

---

## 🚀 Kom Igång

### För en Ny Agent

1. **Läs detta dokument** (README.md)
2. **Läs SYSTEM_RULES.md** för detaljerade regler
3. **Läs COMPANY_CONTEXT.md** för affärskontext
4. **Granska din agents folder** i motsvarande nummer-mapp
5. **Studera relevanta mallar** i `30_MALLAR/`
6. **Testa på en lågrisk uppgift** innan full produktion

### För Manuell Granskning

1. Öppna `20_DOKUMENTBANK/` för att granska resultat
2. Kontrollera mot relevanta mallar
3. Validera mot COMPANY_CONTEXT
4. Godkänn eller begär ändringar

### Support & Felsökning

- **Frågor om system**: Kontakta VD-Agenten
- **Dokumentationsproblem**: Kontakta Dokument-Agenten
- **Tekniska problem**: Se `70_AUTOMATIONER/` för troubleshooting

---

## 📊 System Metrics

EDENBERG-OS övervakas kontinuerligt via:

- **KPI-Systemet** (`50_KPI_SYSTEM/`): Nyckeltal uppdateras dagligen
- **Dashboards** (`60_DASHBOARDS/`): Realtidsöversikt av systemhälsa
- **Rapporter**: Månatliga och årliga analyser

---

## 📝 Versionering av Denna README

- **Version**: 1.0.0
- **Uppdaterad**: 2026-05-18
- **Skapad av**: Edenberg System Admin
- **Status**: AKTIV

Ändringar i denna README kräver godkännande från VD och dokumenteras i versionhistoriken.

---

**EDENBERG-OS är din digitala samarbetspartner. Tillsammans skapar vi effektivitet, kvalitet och tillväxt. 🚀**
