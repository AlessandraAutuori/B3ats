# B3ATS — Heart Rate Intelligence Platform
### Product Requirements Document — v2.0
**Piattaforma B2B di Neuromanagement per Grandi Organizzazioni**

| Versione | Stato | Mercato Target | Classificazione |
|---|---|---|---|
| 2.0 — MVP+ | Bozza — Giugno 2026 | Big 4 / Consulenza | Confidenziale |

---

## 1. Executive Summary

B3ATS è una piattaforma B2B di neuromanagement che integra tre livelli di intelligenza organizzativa: misurazione biometrica continua tramite PPG (fotopletismografia via fotocamera smartphone), diagnostica psicometrica validata scientificamente, e un motore di intervento che eroga raccomandazioni personalizzate al dipendente e trasformazioni strutturali all'organizzazione.

Il prodotto si rivolge alle grandi società di consulenza — in prima istanza le Big 4 (Deloitte, PwC, EY, KPMG) — dove il capitale umano è l'unico asset generatore di ricavo e il burnout rappresenta una perdita economica diretta e misurabile.

### I Tre Livelli della Piattaforma

| | Livello | Output per il Dipendente | Output per l'Azienda |
|---|---|---|---|
| 1 | Diagnostica Biometrica — HRV via PPG | Readiness Score giornaliero (1–100) | Heatmap resilienza team aggregata |
| 2 | Diagnostica Psicometrica — OLBI + PSS-10 + BFI-10 | Profilo di Resilienza Iniziale (privato) | Composizione cognitiva del team (anonima) |
| 3 | Intervention Engine — Micro, Medio Termine, Organizzativo | Rescue Sessions e programmi strutturati | Report Organizzativi Mensili con raccomandazioni evidence-based |

### Proposta di Valore

| Riduzione Turnover | Ottimizzazione Staffing | Aumento Fatturato |
|---|---|---|
| Prevenzione burnout con mesi di anticipo. Costo evitato: fino al 150% della RAL per sostituzione di un Senior. | Decisioni di allocazione basate su dati di resilienza biometrica reale, non su percezioni soggettive. | Consulenti in stato cognitivo ottimale producono deliverable migliori in meno tempo, riducendo ore non fatturabili. |

---

## 2. Contesto e Problema

### Il Knowledge Worker sotto Pressione

Le società di consulenza operano in un ambiente ad altissimo carico cognitivo. La letteratura scientifica — in particolare gli studi pubblicati sul *Journal of Medical Internet Research* — classifica i consulenti come knowledge workers soggetti a pressioni paragonabili, in termini di impatto sul sistema nervoso autonomo, a quelle delle professioni tattiche o militari.

I principali vettori di stress identificati in questo contesto sono:

- **Overtime strutturale**: notti di lavoro prolungate che riducono la capacità di problem solving strategico fino al 30%.
- **Decision fatigue**: carico decisionale accumulato in meeting consecutivi e revisioni di deliverable ad alta pressione.
- **Effetto Lunedì Mattina**: crollo sistematico dell'HRV la domenica sera correlato allo stress da pianificazione settimanale.
- **Invisibilità del burnout**: i consulenti riconoscono i segnali di esaurimento in media il 30% più tardi rispetto a chi utilizza strumenti di monitoraggio biometrico.

### Il Gap nel Mercato

Le soluzioni di Corporate Wellness esistenti si posizionano come strumenti di benessere — fitness app, programmi EAP — con insufficiente capacità di convincere i budget decisionali di una Big 4. Mancano soluzioni che traducano dati biometrici e psicometrici in KPI di business comprensibili dai Partner e dai direttori HR: efficienza operativa, ottimizzazione dell'allocazione, rischio di turnover quantificato.

B3ATS colma questo gap posizionandosi come piattaforma di neuromanagement: non uno strumento di salute, ma un sistema di Business Intelligence per la gestione evidence-based del capitale umano.

---

## 3. Clinical Advisory Board

Il protocollo scientifico di B3ATS è sviluppato e supervisionato da un Clinical Advisory Board composto da due figure con competenze complementari e pubblicazioni peer-reviewed nel dominio di riferimento. Il Board ha funzione triplice: validazione dei protocolli di intervento, copertura della liability scientifica nei processi di acquisto enterprise, e posizionamento credibile nei confronti dei decision maker delle grandi organizzazioni.

| | Neuroscienziata — Co-fondatrice | Ricercatore HRV — Advisor Scientifico |
|---|---|---|
| **Ruolo formale** | Co-fondatrice e responsabile del protocollo psicometrico e neuroscientific | Advisor scientifico per la validazione della pipeline PPG-HRV e dei protocolli di intervento |
| **Contributo al prodotto** | Supervisione del modello diagnostico integrato (biometrico + psicometrico), disegno degli intervention protocol, responsabilità editoriale dei contenuti clinici nell'app | Validazione dell'algoritmo RMSSD, supervisione dei parametri di quality check del segnale PPG, revisione della letteratura scientifica citata nel pitch enterprise |
| **Valore nel pitch B2B** | Garanzia di solidità neuroscientifica del framework diagnostico, credibilità nei confronti dei comitati HR e dei responsabili del benessere organizzativo | Track record pubblicato sull'HRV: blindaggio scientifico nei confronti dei controlli di IT Security e Legal delle Big 4 che richiedono evidenze peer-reviewed |

> **Nota operativa**: Il Board si riunisce con cadenza trimestrale per la revisione dei protocolli e produce un *Annual Scientific Report* che attesta la validità e l'aggiornamento delle metodologie adottate. Questo documento è parte integrante del pacchetto contrattuale enterprise.

---

## 4. Tecnologia Core: PPG e Algoritmo HRV

### Fotopletismografia (PPG)

B3ATS utilizza la fotocamera posteriore e il flash dello smartphone per rilevare le variazioni microscopiche di colore del polpastrello a ogni afflusso di sangue. Questa tecnologia — denominata fotopletismografia ottica (PPG) — elimina completamente la necessità di hardware esterno. Ogni dipendente possiede già il dispositivo necessario, garantendo scalabilità immediata su migliaia di utenti con un semplice link di download.

### Pipeline di Elaborazione del Segnale

| | Fase | Descrizione |
|---|---|---|
| 1 | Acquisizione Video | Il flash posteriore si attiva. La fotocamera registra il flusso video del polpastrello a 30–60 fps per 60–120 secondi. |
| 2 | Isolamento Canale Rosso | Per ogni fotogramma viene estratta l'intensità media del canale rosso (RGB), che oscilla ritmicamente a ogni battito cardiaco. |
| 3 | Peak Detection | L'algoritmo filtra il rumore da micro-movimenti del dito e calcola la distanza in millisecondi tra picchi di pressione successivi (intervalli IBI — Inter-Beat Interval). |
| 4 | Calcolo RMSSD | Applicazione della formula RMSSD (radice quadrata della media delle differenze al quadrato tra battiti adiacenti), espressa in ms. Indice scientifico validato per sessioni brevi di 60–120 secondi. |

### Controllo Qualità del Segnale

Se l'algoritmo rileva un rapporto segnale/rumore insufficiente (movimento del dito, pressione irregolare, variazioni di luminosità ambientale), la sessione viene automaticamente invalidata. L'app mostra: *"Mantieni il dito fermo per 30 secondi per ottenere un dato accurato."*

> Un dato falsato è più dannoso dell'assenza di dato. Questo presidio è fondamentale per la credibilità scientifica della piattaforma.

---

## 5. Modulo Psicometrico

Il modulo psicometrico si attiva in onboarding e si ripete periodicamente, con logica di accesso e finalità distinte per il dipendente e per l'organizzazione. Tutti gli strumenti selezionati sono validati scientificamente, privi di restrizioni di licensing commerciale, e progettati per minimizzare il tempo di somministrazione in un contesto professionale ad alta pressione.

### 5.1 Layer Dipendente — Privato e Non Trasmesso all'Azienda

> I risultati dei test del Layer Dipendente sono crittografati lato dispositivo, non accessibili al backend aziendale in nessuna forma — né aggregata né anonima. Questo vincolo è **architetturale, non contrattuale**, e va comunicato esplicitamente nel pitch come garanzia tecnica, non solo come promessa.

#### OLBI — Oldenburg Burnout Inventory

Strumento gold standard per la misurazione del burnout lavorativo, sviluppato da Demerouti & Bakker. 16 item, due dimensioni: Esaurimento ed Engagement. Validato su popolazioni di knowledge workers europei. Completamente open access — nessun costo di licensing.

- **Frequenza di somministrazione**: Onboarding + ogni 30 giorni.
- **Output per il dipendente**: "Profilo di Resilienza Iniziale" — visualizzazione delle due dimensioni con confronto al benchmark del settore.
- **Utilizzo algoritmo**: Il punteggio OLBI è una delle variabili di input per la calibrazione della baseline del Readiness Score individuale.

#### PSS-10 — Perceived Stress Scale

10 item, misura lo stress percepito soggettivamente nell'ultimo mese. Strumento rapido (2 minuti), ampiamente citato in letteratura, libero da copyright. Complementa l'HRV con la dimensione soggettiva: permette di rilevare dissonanze diagnosticamente rilevanti (es. HRV alto ma stress percepito alto — indicatore di compensazione attiva).

- **Frequenza di somministrazione**: Onboarding + ogni 30 giorni, sfasato di 2 settimane rispetto all'OLBI.
- **Output per il dipendente**: Andamento del livello di stress percepito nel tempo, correlato ai trend HRV.

### 5.2 Layer HR / Team Dynamics — Aggregato e Anonimo

I dati del Layer HR vengono aggregati a livello di team (minimo 5 persone per garantire l'anonimizzazione statistica) e non sono mai riconducibili al singolo individuo. L'azienda non accede ai punteggi individuali in nessuna circostanza.

#### BFI-10 — Big Five Inventory (versione ultra-short)

10 item, misura le cinque dimensioni di personalità validate scientificamente: Apertura, Coscienziosità, Estroversione, Gradevolezza, Nevroticismo. Sviluppato da Rammstedt & John, completamente open access. Somministrato una volta in onboarding.

- **Output per l'HR Dashboard**: Mappa della composizione cognitiva del team per ogni progetto attivo.
- **Esempio di insight organizzativo**: *"Il Team M&A Milano presenta un'alta concentrazione di profili ad alto Nevroticismo e bassa Gradevolezza — configurazione ad alto rendimento ma ad alto rischio di conflitto sotto pressione prolungata. Raccomandazione: valutare un facilitatore esterno prima dell'avvio del progetto."*

> ⚠️ Il BFI-10 è uno strumento descrittivo, non diagnostico. I suoi output nell'HR Dashboard devono essere presentati come indicatori statistici di composizione del gruppo, mai come valutazioni individuali di idoneità professionale. Questa distinzione deve essere esplicitata nei T&C e nella formazione rivolta ai manager che accedono al pannello HR.

---

## 6. Architettura App Mobile — Interfaccia Dipendente

L'app mobile è lo strumento quotidiano del consulente. Ogni interazione è progettata per richiedere **meno di 2 minuti**, adattandosi alle agende fitte dell'ambiente Big 4. Il linguaggio dell'interfaccia è quello della performance professionale, mai quello clinico: nessun riferimento esplicito a stress, malattia o disagio psicologico è visibile in schermata.

### Schermata 1 — Onboarding & Login Enterprise

Login minimale con SSO Microsoft Azure Active Directory. Disclaimer privacy in posizione prominente:

> *"I tuoi dati biometrici e psicometrici grezzi appartengono esclusivamente a te. L'azienda riceve solo dati aggregati di team, anonimi e non riconducibili alla tua persona. Nessun superiore diretto ha accesso ai tuoi dati individuali."*

Alla prima apertura, l'app propone il modulo psicometrico di onboarding (OLBI + PSS-10 + BFI-10) con stima del tempo: *"10 minuti una tantum. Ti aiuta a calibrare il tuo profilo personale."*

### Schermata 2 — Dashboard Principale (Home)

| Stato | Visualizzazione e Messaggio |
|---|---|
| Mattina — test non eseguito | Pulsante circolare animato: *"Avvia Executive Check (60s)"* |
| Score Alto (Verde, >70) | *"Ottima prontezza cognitiva. Giornata ideale per modellazione finanziaria o presentazioni critiche."* |
| Score Medio (Ambra, 40–70) | *"Buona capacità operativa. Evita il multitasking su task ad alta complessità."* |
| Score Basso (Rosso, <40) | *"Carico biologico elevato. Blocca 15 minuti di focus time post-pranzo. Una Rescue Session è disponibile."* |

Sotto il punteggio appare una striscia con i prossimi 3 appuntamenti Outlook, con evidenziazione del meeting storicamente correlato a cali HRV.

### Schermata 3 — Misurazione PPG (60-Second Executive Check)

La schermata si oscura, il flash si attiva, un cerchio centrale funge da pacer di respirazione a frequenza di risonanza (5 secondi inspirazione / 5 secondi espirazione). Feedback in tempo reale sulla qualità del segnale. Al termine: micro-vibrazione aptica e transizione automatica.

### Schermata 4 — Report Post-Test & Intervention Engine

Il Readiness Score viene mostrato immediatamente. L'Intervention Engine seleziona automaticamente l'intervento più appropriato in base al punteggio e al contesto dell'agenda (vedi Sezione 7). L'utente può accettare l'intervento suggerito, scegliere tra le alternative, o chiudere.

### Schermata 5 — Trend & Storico Personale (Insights)

Grafico a linee settimanale e mensile dell'HRV e del Readiness Score, incrociato con il calendario lavorativo. Correlazioni automatiche evidenziate con linguaggio descrittivo:

> *"Nelle ultime 3 settimane il tuo Readiness Score è calato del 18% ogni giovedì in concomitanza con la chiusura del SAL di progetto."*

---

## 7. Intervention Engine

L'Intervention Engine è il cuore prescrittivo di B3ATS. Non propone interventi in modo casuale o a richiesta: seleziona e raccomanda il protocollo più appropriato in base a una matrice che incrocia il Readiness Score del giorno, il trend degli ultimi 7 giorni, e il contesto dell'agenda (meeting imminente, fine giornata, inizio settimana).

Questo approccio aumenta l'autorevolezza percepita del sistema e l'aderenza dell'utente: il consulente non deve scegliere cosa fare — riceve una prescrizione basata su dati.

### 7.1 Micro-Interventi (1–5 min) — Risposta Acuta

> **Umbrella label**: tutti i micro-interventi sono raggruppati nell'interfaccia sotto il nome **"Rescue Session"** — etichetta professionale riconoscibile e priva di connotazioni cliniche.

| Readiness Score | Intervento | Durata | Meccanismo Fisiologico |
|---|---|---|---|
| < 30 | Body Scan Guidato | 5 min | Downregolazione del sistema nervoso simpatico tramite consapevolezza corporea progressiva. |
| 30–50 | Respirazione Coerente (4.5–6 rpm) | 3 min | Attivazione del nervo vago e aumento rapido dell'HRV tramite respirazione a frequenza di risonanza cardiaca. |
| 50–70 | Box Breathing (4-4-4-4) | 2 min | Stabilizzazione del sistema nervoso autonomo e miglioramento del focus attentivo pre-task. |
| > 70 | Pre-Task Priming | 60 sec | Ancoraggio intenzionale prima di task ad alta complessità. Nessun intervento correttivo necessario. |

### 7.2 Programmi Strutturati a Medio Termine (2–4 Settimane)

Attivati automaticamente quando l'algoritmo rileva un trend negativo stabile per 7 o più giorni consecutivi. Il dipendente riceve una notifica:

> *"Il tuo sistema nervoso è in fase di recupero da 10 giorni. Ti propongo un percorso di 2 settimane: 5 minuti al giorno."*

#### Reset Protocol — 2 settimane

Sequenza giornaliera di 5 minuti che combina respirazione guidata e journaling strutturato su un prompt quotidiano. Base scientifica: protocollo derivato dall'Acceptance and Commitment Therapy (ACT), adattato per il contesto professionale ad alta pressione.

- **Esempio di prompt giornaliero**: *"Una cosa che hai controllato oggi. Una cosa che hai lasciato andare."*
- **Output per l'utente**: Grafico dell'andamento del tono vagale durante le 2 settimane con nota finale del sistema.

#### Deep Recovery Sprint — 4 settimane

Per Readiness Score cronicamente bassi (< 35 per 14+ giorni). Include micro-interventi quotidiani, obiettivi settimanali di igiene del sonno e attività fisica monitorati tramite self-report mattutino (3 domande, 60 secondi). Non richiede wearable aggiuntivi.

- **Auto-report mattutino**: Ore di sonno, qualità percepita del riposo, attività fisica nelle ultime 24h.
- **Feedback settimanale**: *"Questa settimana il tuo HRV lunedì mattina era mediamente più alto del 12% rispetto alla settimana scorsa. Il recupero sta funzionando."*

### 7.3 Contenuti Evidence-Based — Supervisione Advisory Board

Tutti i protocolli di intervento — testi guidati, sequenze di respirazione, prompt di journaling — sono redatti e approvati dal Clinical Advisory Board. Nessun contenuto viene pubblicato nell'app senza validazione scientifica documentata. Questo presidio è citabile esplicitamente nel processo di approvazione enterprise.

---

## 8. HR Dashboard & Organizational Intelligence

Il pannello web acquistato dalla Big 4 è accessibile ai Partner e ai responsabili HR. Visualizza esclusivamente dati aggregati e anonimi, con soglia minima di **5 dipendenti per team** prima che qualsiasi dato venga esposto. Nessun Partner può accedere all'HRV, ai punteggi psicometrici o al Readiness Score individuale di un dipendente — in nessuna forma, diretta o inferibile.

### 8.1 Modulo Burnout Alert

Mappa termica (heatmap) dell'organizzazione segmentata per area (Tax, Audit, Advisory) e per progetto attivo. Mostra la percentuale di Resilienza del Team — indice composito calcolato su HRV aggregato, trend OLBI di team e Readiness Score medio.

- **Alert automatico**: Attivato quando un team scende sotto la soglia di resilienza per 10 giorni consecutivi. Messaggio all'HR: *"Rischio Turnover Elevato su Progetto X — Bilanciare i carichi di lavoro."*
- **I nomi dei singoli consulenti**: Completamente oscurati in ogni visualizzazione, senza eccezioni.

### 8.2 Modulo Team Dynamics

Integra i dati BFI-10 aggregati con i trend HRV di team per fornire una lettura della composizione cognitiva di ogni gruppo di lavoro. Genera raccomandazioni automatiche prima dell'assegnazione di nuovi progetti:

> *"Il Team Advisory Roma 2 ha un'alta varianza nel profilo di Coscienziosità e un HRV aggregato in calo da 3 settimane. Assegnare un nuovo progetto critico in questo momento aumenta il rischio di degradazione della qualità. Raccomandazione: inserire una risorsa aggiuntiva o posticipare l'avvio di 2 settimane."*

### 8.3 Modulo Calendario & Stress

Attraverso l'integrazione con Outlook/Teams, la dashboard identifica pattern organizzativi correlati a cali sistematici dell'HRV:

> *"Il meeting ricorrente del venerdì pomeriggio (SAL di progetto, ore 17:00) abbassa l'HRV medio del team del 25% nelle successive 18 ore. Si raccomanda di spostarlo a giovedì mattina o di ridurne la durata a 45 minuti."*

### 8.4 Report Organizzativi Mensili — Tre Livelli di Raccomandazione

Ogni mese il sistema genera un Report Organizzativo con raccomandazioni strutturate su tre livelli di intervento:

#### Livello 1 — Raccomandazioni Strutturali (cambiamenti permanenti)
- Ridisegno dei meeting ricorrenti correlati a cali HRV sistematici.
- Revisione dei carichi di lavoro per team con resilienza cronicamente bassa.
- Inserimento di risorse aggiuntive prima dell'assegnazione di nuovi progetti ad alto rischio.

#### Livello 2 — Raccomandazioni di Intervento (azioni a 30–90 giorni)
- Team coaching per team con composizione BFI-10 a rischio conflitto sotto pressione.
- Workshop di regolazione del sistema nervoso per Service Line ad alto turnover, erogabili con provider certificati partner di B3ATS.
- Revisione del calendario dei deliverable per Service Line con HRV cronicamente basso nelle settimane di chiusura progetto.

#### Livello 3 — Raccomandazioni di Policy (cambiamenti sistemici)
- Politiche no-meeting per fasce orarie correlate a picchi di stress biometrico.
- Revisione del modello di staffing per team che mostrano HRV non recuperato nel weekend dopo oltre 3 settimane consecutive di overtime.
- Programmi di onboarding esteso per nuovi consulenti che mostrano baseline HRV significativamente sotto il benchmark del settore.

> ⚠️ Tutte le raccomandazioni organizzative vengono generate dall'algoritmo ma classificate esplicitamente come *"suggerimenti basati su dati aggregati"*, non come prescrizioni mediche o psicologiche. Il Report Mensile include in ogni pagina il disclaimer: *"I dati presentati sono indicatori statistici aggregati. Le decisioni organizzative rimangono di esclusiva competenza del management."*

---

## 9. Quadro Legale, Compliance e Posizionamento Normativo

Questa sezione definisce il perimetro giuridico entro cui B3ATS opera, i requisiti di conformità necessari per l'accesso al mercato enterprise europeo, e le misure di mitigazione del rischio legale adottate fin dall'architettura del prodotto. È redatta con l'obiettivo di **anticipare e superare i controlli Legal e IT Security delle Big 4**.

### 9.1 Qualificazione del Prodotto — Cosa B3ATS È e Cosa Non È

La corretta qualificazione giuridica del prodotto è il primo presidio di protezione legale. B3ATS deve essere posizionato in modo univoco e difendibile come strumento di supporto alla performance professionale, non come dispositivo medico o psicologico.

| B3ATS È | B3ATS NON È |
|---|---|
| Uno strumento di supporto alla performance professionale basato su dati biometrici e psicometrici aggregati. | Un dispositivo medico ai sensi del Regolamento UE 2017/745 (MDR). Non effettua diagnosi mediche. |
| Un sistema informativo che fornisce suggerimenti basati su pattern statistici. | Uno strumento psicologico diagnostico. Non sostituisce la valutazione clinica di uno psicologo o psichiatra. |
| Una piattaforma di Business Intelligence HR che elabora dati anonimi e aggregati per supportare decisioni organizzative. | Un sistema di sorveglianza individuale. Nessun dato individuale è accessibile all'organizzazione in nessuna forma. |
| Un sistema di informazione e sensibilizzazione personale che restituisce all'utente dati sul proprio stato fisiologico. | Un sostituto del supporto psicologico professionale. L'app include in modo permanente un riferimento a risorse di supporto professionale. |

### 9.2 GDPR e Trattamento dei Dati Biometrici

I dati HRV e i punteggi psicometrici individuali costituiscono **dati particolari** ai sensi dell'Art. 9 del Regolamento (UE) 2016/679 (GDPR). Il loro trattamento richiede conformità a requisiti specifici:

#### Base giuridica

Il trattamento si fonda sul **consenso esplicito e libero** dell'interessato (Art. 9(2)(a) GDPR). Il consenso è raccolto in onboarding tramite procedura separata e granulare — distinto dal contratto di lavoro e non condizionante il rapporto lavorativo. Il dipendente può revocare il consenso in qualsiasi momento senza conseguenze sul rapporto con il datore di lavoro.

> ⚠️ Il consenso non può essere validamente fornito se condizionato dal datore di lavoro (es. *"aderisci al programma B3ATS come parte del tuo percorso di onboarding aziendale"*). L'adesione deve essere volontaria, comunicata come facoltativa e priva di incentivi o disincentivi diretti. Questa condizione deve essere contrattualmente garantita dall'organizzazione cliente nei confronti dei propri dipendenti.

#### Architettura Privacy-by-Design

- **Crittografia end-to-end**: I dati biometrici grezzi vengono crittografati sul dispositivo prima di qualsiasi trasmissione. Il server non riceve mai dati in chiaro.
- **Anonimizzazione irreversibile**: I dati aggregati trasmessi all'HR Dashboard sono elaborati tramite algoritmi di anonimizzazione differenziale. Non è tecnicamente possibile ricostruire il dato individuale a partire dall'aggregato.
- **Minimizzazione dei dati**: B3ATS raccoglie esclusivamente i dati necessari alle finalità dichiarate. Nessun dato di localizzazione, nessuna registrazione audio o video oltre la sessione PPG, nessuna analisi del comportamento in app.
- **Data retention**: I dati grezzi individuali sono conservati sul dispositivo per un massimo di 90 giorni. I dati aggregati sul server sono conservati per un massimo di 24 mesi, salvo diversa indicazione contrattuale.
- **Diritti dell'interessato**: Accesso, rettifica, cancellazione, portabilità e opposizione al trattamento sono esercitabili in qualsiasi momento tramite interfaccia in-app, senza necessità di contattare il supporto.

#### Data Processing Agreement (DPA)

B3ATS agisce in qualità di **Responsabile del Trattamento** (Art. 28 GDPR) rispetto all'organizzazione cliente, che è il Titolare del Trattamento. Per ogni contratto enterprise viene stipulato un DPA separato che definisce: finalità e mezzi del trattamento, misure di sicurezza tecniche e organizzative, modalità di gestione delle violazioni (data breach notification entro 72 ore), e condizioni per il sub-trattamento da parte di fornitori terzi (es. infrastruttura cloud).

### 9.3 Normativa sui Dispositivi Medici (MDR)

Il Regolamento UE 2017/745 (MDR) si applica ai dispositivi destinati a diagnosi, prevenzione, monitoraggio, previsione, prognosi, trattamento o attenuazione di malattie. B3ATS **non rientra** in questa definizione per le seguenti ragioni documentate:

- B3ATS non effettua diagnosi di condizioni mediche o psicologiche. I punteggi prodotti (Readiness Score, OLBI, PSS-10) sono indicatori di benessere e performance, non classificazioni cliniche.
- B3ATS non è destinato a essere utilizzato per decisioni terapeutiche. L'app include un disclaimer permanente che invita a rivolgersi a un professionista della salute per qualsiasi preoccupazione di natura medica o psicologica.
- B3ATS non elabora segnali fisiologici per scopi medici. La misurazione PPG è finalizzata al calcolo di un indice di performance professionale, non alla valutazione di condizioni cardiologiche.

> ⚠️ Ai fini della documentazione per i controlli Legal delle Big 4, è consigliabile produrre un **parere legale formale** da uno studio specializzato in diritto sanitario e healthtech che attesti l'esenzione di B3ATS dall'ambito applicativo dell'MDR. Questo documento diventa parte del pacchetto contrattuale enterprise.

### 9.4 Responsabilità e Limitazione della Liability

I Termini e Condizioni di B3ATS devono includere le seguenti clausole, redatte con assistenza di un legale specializzato in healthtech:

#### Clausola di esclusione diagnostica
> *"B3ATS è uno strumento di supporto alla performance professionale. I dati, i punteggi e i suggerimenti forniti dall'applicazione sono elaborazioni statistiche basate su parametri fisiologici e psicometrici. Non costituiscono diagnosi mediche o psicologiche, non sostituiscono il parere di un medico, psicologo o altro professionista della salute, e non devono essere utilizzati come base per decisioni di carattere clinico o terapeutico. In caso di preoccupazioni relative alla propria salute fisica o mentale, l'utente è invitato a consultare un professionista qualificato."*

#### Clausola di responsabilità organizzativa
> *"L'organizzazione cliente (Titolare del Trattamento) è responsabile di garantire che l'utilizzo di B3ATS all'interno della propria struttura avvenga nel rispetto delle normative sul lavoro applicabili, incluse le disposizioni relative alla tutela della salute e sicurezza dei lavoratori (D.Lgs. 81/2008 e successive modifiche per il mercato italiano; normative equivalenti per gli altri paesi di operatività). B3ATS S.r.l. declina ogni responsabilità per utilizzi della piattaforma non conformi alle presenti condizioni o alle normative vigenti."*

#### Clausola di limitazione tecnica
> *"La misurazione PPG tramite fotocamera smartphone è soggetta a fattori di variabilità ambientale (luminosità, movimento, pressione del dito) che possono influenzare l'accuratezza del segnale. B3ATS incorpora algoritmi di controllo qualità del segnale che invalidano automaticamente le sessioni con rapporto segnale/rumore insufficiente. Tuttavia, l'utente è invitato a non basare decisioni rilevanti esclusivamente sui dati forniti dall'applicazione."*

### 9.5 Compliance Lavoristica

In diversi paesi europei il monitoraggio biometrico dei lavoratori — anche su base volontaria — richiede specifici adempimenti in materia di diritto del lavoro:

- **Italia**: Informativa e consultazione delle rappresentanze sindacali ai sensi dell'Art. 4 dello Statuto dei Lavoratori (L. 300/1970), se applicabile. Il consenso individuale non sostituisce l'accordo sindacale quando il monitoraggio è strutturale all'organizzazione del lavoro.
- **Francia**: Consultazione obbligatoria del Comité Social et Économique (CSE) per l'introduzione di strumenti di monitoraggio della salute dei lavoratori.
- **Germania**: Codeterminazione del Betriebsrat (consiglio aziendale) per qualsiasi sistema che possa influenzare le condizioni di lavoro o la valutazione dei dipendenti.

> ⚠️ Prima del deploy in qualsiasi organizzazione cliente, B3ATS deve richiedere attestazione scritta che gli adempimenti lavoristici applicabili nel paese di operatività siano stati completati. Questa attestazione diventa allegato contrattuale obbligatorio.

### 9.6 Requisiti di Sicurezza Informatica

| Requisito | Implementazione |
|---|---|
| Crittografia dati in transito | TLS 1.3 per tutte le comunicazioni client-server. Certificati gestiti tramite provider certificato (es. Let's Encrypt o CA aziendale). |
| Crittografia dati a riposo | AES-256 per tutti i dati archiviati su server. I dati sul dispositivo sono crittografati tramite le API native del sistema operativo (iOS Keychain / Android Keystore). |
| Autenticazione | SSO tramite Microsoft Azure Active Directory. MFA obbligatoria per l'accesso all'HR Dashboard. |
| Penetration testing | Test di sicurezza annuale condotto da un provider certificato terzo. Report disponibile per i controlli IT Security delle Big 4. |
| ISO 27001 | Obiettivo di certificazione entro 18 mesi dal lancio commerciale. Prerequisito per contratti enterprise oltre una certa soglia. |
| Data breach response | Procedura documentata di risposta agli incidenti con notification entro 72 ore al Titolare del Trattamento, in conformità con l'Art. 33 GDPR. |

---

## 10. UX Strategy & Adoption Framework

### Il Micro-Rito Aziendale

I consulenti Big 4 operano con agende fitte e una soglia di attenzione strutturalmente bassa verso il proprio benessere. La misurazione PPG deve diventare un **micro-rito quotidiano** percepito come normale quanto controllare la posta al mattino. Le leve di adozione comportamentale integrate nel prodotto:

| Leva | Implementazione |
|---|---|
| Identità professionale | Il test si chiama "Executive Check", non "stress test". Il linguaggio rispecchia la cultura della performance, non quella clinica. |
| Smart Prompts contestuali | Notifiche alle 8:30 prima dei meeting e dopo riunioni lunghe registrate in Outlook: *"De-briefing biologico di 1 minuto disponibile."* |
| Privacy visiva totale | Schermata di misurazione priva di grafici medici o testi allarmistici. Misurabile in open space senza disagio sociale. |
| Azioni integrate a frizione zero | I pulsanti del Report Post-Test agiscono direttamente su Outlook e Teams. Il cambiamento comportamentale non richiede sforzo aggiuntivo. |
| Prescrizione algoritmica | L'Intervention Engine seleziona l'intervento — l'utente non deve scegliere. Riduce il carico cognitivo e aumenta l'aderenza. |

---

## 11. Modello di Business

### Pricing Tier

| Tier | Contenuto e Prezzo Indicativo |
|---|---|
| **B3ATS Core** — 8–12 EUR/utente/mese | HRV via PPG + Readiness Score + Micro-interventi (Rescue Sessions). Accesso HR Dashboard base (heatmap resilienza). |
| **B3ATS Pro** — 18–22 EUR/utente/mese | Core + Modulo Psicometrico completo (OLBI, PSS-10, BFI-10) + Programmi strutturati a medio termine (Reset Protocol, Deep Recovery Sprint) + Team Dynamics Dashboard. |
| **B3ATS Enterprise** — 28–35 EUR/utente/mese + setup fee | Pro + Report Organizzativi Mensili con raccomandazioni a tre livelli + Integrazione calendario avanzata + Clinical Advisory Board report annuale + SLA dedicato + DPA personalizzato. |

### Strategia Go-to-Market: Pilota Sponsorizzato 90 Giorni

- **Target iniziale**: Team di 50 persone in una Service Line ad alto stress (es. M&A / Corporate Finance).
- **Obiettivo del pilota**: Dimostrare ROI misurabile — riduzione giorni di malattia, aumento punteggi di engagement, correlazione HRV/errori su deliverable.
- **Condizione di rinnovo**: Report ROI quantitativo presentato ai decision maker prima del rinnovo contrattuale esteso all'intera organizzazione.

### ROI Comunicabile ai Decision Maker

| Voce di Costo Evitato | Riferimento Scientifico / Benchmark |
|---|---|
| Sostituzione consulente Senior o Manager | Fino al 150% della RAL tra reclutamento e formazione. |
| Calo performance cognitiva da overtime | Riduzione fino al 30% della capacità di problem solving strategico (letteratura peer-reviewed). |
| Anticipo rilevamento burnout | 30% di anticipo rispetto all'auto-percezione soggettiva (Journal of Medical Internet Research). |
| Riduzione assenteismo | I programmi di biofeedback HRV in contesti corporate mostrano riduzioni del 15–20% dei giorni di malattia (studi pilota su knowledge workers europei). |

---

## 12. Roadmap MVP

### Stack Tecnologico

- **Framework mobile**: Flutter o React Native — librerie open source per fotocamera/flash e calcolo BPM.
- **Algoritmo HRV**: Librerie validate accademicamente per elaborazione IBI → RMSSD. Nessun rischio di riscrivere la matematica di base.
- **Backend**: Architettura serverless (Firebase o AWS Amplify) per contenere i costi operativi nella fase di validazione.
- **HR Dashboard**: Web app React. Accessibile da browser aziendale senza installazione aggiuntiva.

### Fasi di Sviluppo

| Fase | Timeline | Deliverable Chiave |
|---|---|---|
| Fase 0 — Algoritmo | Settimane 1–3 | Prototipo PPG → RMSSD validato su 10 persone. Soglia di accuratezza: ±5 ms rispetto a fascia cardio ECG di riferimento. |
| Fase 1 — App Core | Settimane 4–8 | App mobile (iOS + Android): misurazione, Readiness Score, Rescue Sessions. Modulo psicometrico OLBI + PSS-10. |
| Fase 2 — Beta Test | Settimane 9–10 | Beta con 10 consulenti in ambiente reale. Focus su stabilità segnale, surriscaldamento flash, UX in open space, aderenza agli interventi. |
| Fase 3 — Pro Layer | Settimane 11–14 | BFI-10, programmi a medio termine (Reset Protocol, Deep Recovery Sprint), HR Dashboard con Team Dynamics. |
| Fase 4 — Enterprise | Mese 4–6 | Report Organizzativi Mensili, integrazione calendario avanzata, DPA enterprise, parere legale MDR, pilota su 50 utenti Big 4. |

### Rischi e Mitigazioni

| Rischio | Impatto | Mitigazione |
|---|---|---|
| Qualità segnale PPG in condizioni non ideali | Alto | Algoritmo quality check con invalidazione automatica e feedback immediato. Soglia minima di qualità non negoziabile. |
| Resistenza culturale alla condivisione dati biometrici | Alto | Disclaimer prominente, anonimizzazione architetturale (non contrattuale), nessun dato visibile ai superiori. Adesione volontaria esplicitamente garantita. |
| Cicli di vendita B2B lunghi nelle Big 4 | Medio | Pilota gratuito o a costo ridotto per il primo contratto. Focus su singolo sponsor interno (HR Director o Managing Partner). |
| Rischio classificazione come dispositivo medico (MDR) | Medio | Parere legale formale da studio specializzato healthtech incluso nel pacchetto enterprise. Posizionamento accurato nei T&C fin dall'MVP. |
| Surriscaldamento flash smartphone | Basso | Sessione limitata a 60 secondi. Controllo termico software con avviso automatico al raggiungimento della soglia. |

---

*B3ATS — Confidenziale — v2.0 — Giugno 2026*
