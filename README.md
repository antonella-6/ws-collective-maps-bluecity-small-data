# Dataset di small data partecipativi sulla gestione dei rifiuti (Progetto Innosuisse Bluecity – Lugano)
Dataset anonimizzato generato durante le attività partecipative del workshop “Pixel Urbani”,svoltosi dal 16 al 18 luglio 2025 e realizzato dall’Istituto Design della SUPSI nel contesto del progetto Innosuisse *Bluecity*.

---

## 1. Contesto del progetto
Il dataset *Buecity_small_data_mappe_collettive_rifiuti_urbani_lugano.csv* è stato sviluppato nell’ambito del progetto **Innosuisse Bluecity**, dedicato alla ricerca sulle *digital twin city* e sul ruolo dei dati nel supporto ai processi decisionali urbani.

All’interno del progetto, l’Istituto Design della SUPSI ha collaborato con la Città di Lugano per esplorare il potenziale di raccolta degli **small data**, ovvero dati generati direttamente dalle pratiche quotidiane delle persone, spesso raccolti con metodologie partecipative, altamente situati e granulari. Gli small data permettono di integrare la dimensione esperienziale e locale nei sistemi informativi urbani, offrendo un contributo complementare rispetto ai big data istituzionali.

La raccolta dei dati è avvenuta durante il workshop partecipativo **Pixel Urbani** (Lugano LongLake Festival 2025, 16 - 18 Luglio), in cui i cittadini hanno:

- compilato mappe fisiche delle abitudini di smaltimento dei rifiuti,
- tracciato percorsi verso punti di raccolta,
- annotato orari, distanze, attività correlate e criticità,
- rappresentato frequenze settimanali per diverse tipologie di rifiuti.

Un paper dedicato alla concettualizzazione degli small data nel progetto Bluecity è disponibile come **preprint su Zenodo**:

> **Autuori, A. (2025). _Seeing-thinking-sharing-sensing small data: A participatory framework to connect citizens' experiences with urban governance._ Zenodo.**  
> DOI: https://doi.org/10.5281/zenodo.17813817  
> *(Preprint · under blind peer review · la venue sarà resa pubblica al termine della revisione.)*
---

## 2. Contenuto del dataset
Il dataset comprende **24 istanze**, una per partecipante, e contiene informazioni relative a:

- quartiere di provenienza (non identificante),
- punto di raccolta utilizzato (pseudonimizzato),
- mezzo di trasporto e distanza percorsa,
- orari di smaltimento,
- composizione del nucleo familiare (persone e animali),
- attività svolte durante lo spostamento,
- osservazioni e problemi percepiti,
- frequenze settimanali di smaltimento per 7 tipologie di rifiuti,
- immagini anonimizzate delle mappe fisiche,
- link alle immagini archiviate in repository pubblico.

La struttura completa e le definizioni tecniche sono presenti nel file csv *Data Dictionary_ws_collective_maps_small_data_bluecity*.

---

## 3. File inclusi

```text
WS-Collective-Maps-FAIR/
├─ ws_collective_maps_small_data_bluecity.csv
├─ data_dictionary_ws_collective_maps.csv
├─ README.md
├─ mappa_anonimizzata/
│  ├─ mappa_01.png
│  ├─ mappa_02.png
│  └─ ...
├─ paper_small_data_bluecity_preprint.pdf (opzionale)
└─ mappatura_punti_raccolta_interno.xlsx (NON pubblicato)
```

---

## 4. Privacy e conformità alla nLPD

Il dataset originale conteneva dati personali diretti e indiretti legati alle abitudini di smaltimento dei rifiuti dei partecipanti.  
La versione rilasciata è stata preparata applicando i principi di **privacy by design**, **minimizzazione**, **proporzionalità** e **accountability** richiesti dalla **Legge federale svizzera sulla protezione dei dati (nLPD)**.

### 4.1 Anonimizzazione (dati personali diretti)
È stata rimossa integralmente la variabile **Punto_partenza (via di domicilio)** perché:

- costituisce un dato personale diretto ai sensi della nLPD;
- in alcuni casi includeva il numero civico;
- combinata con orario, distanza e composizione del nucleo familiare avrebbe potuto permettere identificazione indiretta;
- può essere incrociata con registri comunali (registro abitazioni).

L’indirizzo originale è conservato esclusivamente in archivio interno protetto, non sincronizzato in cloud e accessibile solo ai ricercatori autorizzati.

Sono inoltre state anonimizzate:

- annotazioni testuali contenenti riferimenti a luoghi reali,
- immagini delle mappe con offuscamento selettivo (vie, civici, percorsi).

---

### 4.2 Pseudonimizzazione (dati potenzialmente identificanti)

La variabile “Punto_arrivo” (ecocentro/ecopunto) è stata pseudonimizzata perché:

- non è un dato personale diretto,
- **ma è potenzialmente identificante se combinato con quartiere, distanza, orario e nucleo familiare**,
- la Città di Lugano registra gli accessi agli ecocentri tramite **Ecocard**, quindi esiste un rischio concreto di matching.

Per ridurre tale rischio senza perdere il valore informativo della variabile, è stata adottata la seguente codifica:

- **ECOCxx** = Ecocentro comunale  
- **ECOPxx** = Ecopunto di quartiere

La mappatura con i nomi reali è conservata nel file **mappatura_punti_raccolta_interno.xlsx**, non incluso nel dataset pubblico.

---

### 4.3 Minimizzazione
- Rimossi tutti i dati non indispensabili allo scopo del dataset.  
- Eliminati campi ridondanti, aggregati o non standardizzati.  
- Rimosse interpretazioni soggettive delle ricercatrici.  
- Mantenute solo variabili non identificanti.

---

## 5. Licenza
Questo dataset è distribuito con licenza:  
**Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)**  
→ puoi usarlo, adattarlo e condividerlo solo per scopi **non commerciali**, con attribuzione.

---

## 6. Repository previsto
- **Zenodo** come repository principale (assegnazione DOI, conservazione a lungo termine).  
- **OneDrive pubblico** come mirror per le immagini anonimizzate.

---

## 7. Struttura del dataset (overview)

Le variabili presenti nel dataset pubblico sono:

- `ID`  
- `Quartiere`  
- `Punto_arrivo_codificato`  
- `Mezzo_trasporto`  
- `Distanza_punto_raccolta_m`  
- `orario_smistamento_24h`  
- `orari_smistamento_numero`  
- `numero_persone_nucleo`  
- `numero_animali_domestici`  
- `attività_correlate`  
- `osservazioni_generali`  
- `Rsu`  
- `Organico`  
- `Pet`  
- `Vetro`  
- `Carta-Cartone`  
- `Alluminio`  
- `Batterie`  
- `mappa_anonimizzata_link`  

La definizione tecnica completa (tipi, origine, privacy) è contenuta nel **data_dictionary_ws_collective_maps.csv**.

---

## 8. Metodologia di raccolta e di decodifica

### A) Metodologia di raccolta (Workshop partecipativo)
La raccolta dei dati è avvenuta durante il workshop **Pixel Urbani** svoltosi dal 16 al 18 luglio 2025, nel contesto del Lugano Long Lake Festival, dove i partecipanti hanno svolto attività di co-creazione utilizzando materiali fisici e strumenti digitali. Le operazioni sono state:

- **Compilazione di mappe fisiche** tramite materiali predisposti (icone, sticker, categorie, legende).  
- **Identificazione del punto di raccolta** sulla mappa della città e uso di materiali fisici per rappresentare percorsi, attività o criticità.  
- **Tracciamento dei percorsi e misurazione delle distanze** tramite Google Maps su tablet forniti dal team di ricerca.  
- **Stampa immediata della mappa digitale** tramite stampante termica per garantire a ogni partecipante un supporto fisico su cui lavorare.  
- **Annotazioni testuali** (attività correlate, commenti, mancanze) inserite direttamente dai partecipanti tramite post-it posizionati sulle mappe fisiche.  
- **Rappresentazione delle frequenze settimanali dei rifiuti** (RSU, PET, organico, vetro, ecc.) compilata tramite sticker e indicatori grafici specifici.  

Questa fase ha prodotto **24 mappe fisiche**, ciascuna combinata con percorsi digitali e annotazioni cartacee.

---

### B) Metodologia di decodifica e digitalizzazione (lavoro di ricerca)
Dopo il workshop, il team di ricerca ha effettuato un processo strutturato di trasformazione dei materiali fisici in un dataset digitale:

- **Trascrizione manuale** delle informazioni presenti sulle mappe fisiche (percorsi, distanze, punti di raccolta).  
- **Trascrizione e normalizzazione di tutte le annotazioni testuali** (post-it), suddivise in due variabili:  
  - `attività_correlate`  
  - `osservazioni_generali`  
- **Derivazione delle frequenze settimanali di smaltimento** per ciascuna tipologia di rifiuto, sulla base delle icone e dei simboli applicati dai partecipanti.  
- **Digitalizzazione delle mappe fisiche** tramite scansione e salvataggio in formato PNG.  
- **Anonimizzazione visiva**: offuscamento manuale di tutte le informazioni sensibili (vie, civici, percorsi riconducibili all’indirizzo).  
- **Pseudonimizzazione dei punti di raccolta** tramite codici ECOCxx/ECOPxx.  
- **Verifica incrociata** dei dati tra mappe, annotazioni e foglio digitale per garantire coerenza e minimizzare errori di trascrizione.  
- **Standardizzazione** di formati, categorie e codifica secondo criteri FAIR.

Questa fase ha prodotto il dataset digitale strutturato, completamente anonimizzato e conforme alla nLPD.

---

## 9. Pulizia e trasformazioni (processo FAIR)

Le principali operazioni di data cleaning sono state:

- standardizzazione dei nomi delle colonne e dei formati (FAIR compliance),
- rimozione di variabili sensibili e ridondanti,
- pseudonimizzazione del punto di raccolta (ECOC/ECOP),
- revisione e pulizia delle annotazioni testuali,
- separazione tra `attività_correlate` e `osservazioni_generali`,
- formattazione uniforme degli orari in `HH:MM`,
- derivazione della variabile `orari_smistamento_numero`,
- conversione delle frequenze settimanali secondo scala standardizzata:  
  - `1` = una volta a settimana  
  - `0.5` = una volta ogni due settimane  
  - `0.25` = una volta ogni quattro settimane  
- anonimizzazione visiva delle mappe fisiche,
- verifica manuale per assicurare assenza di riferimenti identificativi.

---

## 10. Rischi etici e tecnici

### Etici
- possibile re-identificazione tramite matching (indirizzo + orario + quartiere + distanza),
- sensibilità delle pratiche domestiche rappresentate,
- responsabilità etica nel trattamento di contributi volontari dei cittadini,

### Tecnici
- dimensione campione limitata (n=24),
- trascrizione manuale da materiali fisici (possibili errori o variabilità),
- eterogeneità delle annotazioni testuali,
- differenze nella qualità grafica delle mappe fisiche,
- necessità di armonizzazione e standardizzazione.

---

## 11. Curatela dei dati

- **Data Steward:** *Antonella Autuori (SUPSI, Istituto Design); Ginevra Terenghi (SUPSI, Istituto Design)*  
- **Data Curator:** *Antonella Autuori (SUPSI, Istituto Design); Ginevra Terenghi (SUPSI, Istituto Design)*
- **Data Owner:** SUPSI – Dipartimento Ambiente Costruzioni e Design, Istituto Design
- **Affiliazione istituzionale:** SUPSI – Dipartimento Ambiente Costruzioni e Design, Istituto Design
- **Workshop facilitato da:** Collaboratori e collaboratrici dell'Istituto Design della SUPSI di Mendrisio: Antonella Autuori; Ginevra Terenghi; Giovanni Profeta; Luca Draisci; Alice Mioni; Matteo Subet
- **Raccolta dati:** Lugano, LongLake Festival – 16/18 Luglio 2025  
- **Versione FAIR del dataset:** 2025  
- **Publisher:** Zenodo
- **Paper correlato:** *Seeing, thinking, sharing, sensing small data. A participatory framework to connect citizens' experiences with urban governance (Preprint / under blind peer review. La venue sarà resa pubblica dopo la conclusione del processo di revisione.)*

---

## 12. Contatti
Antonella Autuori
SUPSI – Istituto Design  
Area Interaction Design  
Email: *antonella.autuori@supsi.ch*

---
