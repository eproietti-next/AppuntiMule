
# Anypoint Platform Development - Fundamentals - Part 1


## The new IT Operating Model

Il Modello operativo IT consiste nello **sviluppo di asset riutilizabili**. 

La chiave della strategia è  **emphatic consumption as much as production**. Gli asset riutilizzabili non sono solo per il mantenimento del sistema, ma per riutilizzarli nel prodotto finale.

Il modello operativo classico presenta alcuni problemi come:

- Opportunità limitate di riutilizzo
- Mancanza di un forte accoppiamento = fragilità
- Difficile da governare

**Le API moderne sono componibili**

Devono essere:

- Accessibili/scopribili attraverso il self-service
- Prodotte e progettate per essere facilmente fruibili
- Facilmente gestibili per sicurezza, scalabilità e prestazioni

Invece di costruire un unico servizio, costruiamo un gruppo di API che sono di diverso tipo:

- **System APIs**, che si connettono alle risorse (db, salesforce, sap )
- **Process APIs**, che elaborano il file da utilizzare per il client 
- **Experience APIs** come delle applicazioni WEB

Ad esempio, costruiamo un API per un e-commerce su Internet. Se dopo qualche mese arriva una richiesta dal cliente per costruire un'applicazione mobile, dobbiamo solo preoccuparci dell'ultimo livello (Experience APIs)

Lo scopo di questo approccio è di riutilizzare l'intera applicazione, implementando solo le funzionalità richieste per la parte mobile.

Per applicare e promuovere questo metodo di lavoro abbiamo il:
### C4E (central for Enablement):
C4E, acronimo di "Center for Enablement" o "Centro di Abilitazione", è un'organizzazione interna all'azienda che supporta e facilita l'adozione di approcci e tecnologie specifiche in tutta l'organizzazione.

Il C4E è un team specializzato che agisce come un punto centrale di competenza per fornire risorse, consulenza, formazione e supporto per un determinato settore o iniziativa aziendale. Può essere creato per guidare l'adozione di determinate pratiche o tecnologie come l'API-led connectivity, DevOps, cloud computing o altri settori strategici.


### API Moderne
Le API moderne sono scopribili, accessibili, progettate per essere scalabili e performanti.
Forniscono le informazioni necessarie per comunicare con i software, definendo:

1. Operations
2. Inputs
3. Outputs
4. Underlyng data types

**NB:** Definiscono funzionalità indipendenti dalle implementazioni. 

### Differenza tra API e servizi web

Le API possono essere servizi web, proxy o documentazione delle API.

Tuttavia, ci sono molte differenze tra le API e i servizi web. I servizi web sono un metodo di comunicazione tra due sistemi software che consente loro di scambiare dati su Internet.

Il termine "Web Service" ha diversi significati simili, ma differenti:

- **Web Service API:**
Describe how to interact with the web service. descrive come interagire con il servizio web. Potrebbe essere definita esplicitamente o meno. Potrebbe essere un testo in qualsiasi tipo di file.
- **Web service interface:**  è il codice che fornisce la struttura all'applicazione, quindi implementa l'API.
- **Web service implementation:** il codice e l'applicazione stessa che forniscono il servizio.

**Due tipi di web service**   

1. **SOAP:** più complesso, richiede due protocolli, SOAP per la codifica e decodifica e HTTP o altri protocolli per il trasporto.
2. **RESTful:** tipo semplice utilizzato per servizi web basati su REST (Representational State Transfer).

### REST Representational State Transfer
REST (Representational State Transfer) è uno stile architetturale in cui i client e i server scambiano rappresentazioni di risorse utilizzando HTTP.

REST è **stateless** (senza stato): il server non ricorda lo stato del client dalle richieste precedenti, ma il client può memorizzare nella cache le risposte precedenti per evitare chiamate ripetute.

REST utilizza **richieste HTTP**.

I metodi di richiesta HTTP (*HTTP request methods*) indicano quale operazione deve essere eseguita sull'oggetto identificato dall'URL:

- (GET)/companies: returns list of companies
- (GET)/companies?country=France:returns list of companies where country is France 🇫🇷 
- (GET)/companies/3:returns company at index 3
- (POST)/companies with JSON:method to add companies
- (DELETE)/companies/3: to delete company at index 3
- (PUT)/companies/3 with json: in http body replace company identifies or creat

### HTTP METHODS 
1. **GET**: ottiene una rappresentazione di una risorsa dal server.
2. **POST**: crea una nuova risorsa sul server.
3. **PUT**: aggiorna una risorsa esistente sul server o crea una risorsa se non esiste.
4. **DELETE**: elimina una risorsa dal server.
5. **PATCH**: aggiorna parzialmente una risorsa esistente sul server.
6. **HEAD**: ottiene solo le informazioni sull'intestazione di una risorsa senza recuperarne il contenuto.
7. **OPTIONS**: ottiene le opzioni di comunicazione disponibili per una risorsa.
8. **TRACE**: esegue un test di loopback diagnostico lungo il percorso verso il server.

I servizi web restituiscono dati in formati di tipo **json o xml**.

Json(Javascript Object Notation) is light, human readable and supports collections and maps

### Learning about APIs
Possiamo apprendere di più sulle API attraverso:

- **Documentazione delle API:** un elenco di risorse che fornisce informazioni sulla specifica API.
Portali delle API: forniscono agli sviluppatori un luogo centralizzato in cui possono trovare tutte le informazioni sulla documentazione di una specifica API, inclusi tutorial, esempi, modalità di registrazione dell'applicazione e test. Un esempio di portale delle API è APIs.guru.
- **Directory e Marketplace:** come *APIs.guru* consentono di trovare e scoprire diverse API disponibili, fornendo informazioni sulle funzionalità, la documentazione e la modalità di utilizzo delle API stesse.

Possiamo chiamare una REST API utilizzando **Postman**, che è uno strumento popolare per testare e interagire con le API. 

Le API possono essere sicure o non sicure:

- Le API non sicure sono pubbliche e non richiedono autenticazione per accedere ad esse.
- Le API sicure richiedono autenticazione, ad esempio utilizzando un token OAuth, per garantire che solo gli utenti autorizzati possano accedere alle risorse protette.

### Risponse HTTP comuni
- 200 ok
- 201 created
- 304 not modified
- 400 bad request
- 401 unauthorized 
- 404 resource not found 
- 500 server error

### API-LED connectivity (3 layer)
La chiave è produrre risorse scopribili e utilizzabili, creando un'API che i developer possano trovare e desiderare di utilizzare.

Si inizia adottando un approccio di progettazione basato sull'API, assicurandoci di avere una progettazione corretta prima di investire nella sua realizzazione.

**Cicla di vita dello sviluppo delle API:**

1. **API specification **
	- Design
	- Simulate 
	- Feedback
	- Validate
2. **Simulate stage** --> Web Service with API (Contract)
	- Build
	- Test
3. **Deploying and managing the Web service**
	- API Version
	- Policy to secure it
	- Deploy and register the web service
	- Monitoring the operation 
	- Analyze and report on the usage
	- Troubleshoot
	- Scale 
	- Respond to the changing need to restart the life cycle


## Introducing to anypoint platform

Anypoint Platform è una piattaforma unificata che comprende tutti i componenti per l'intero ciclo di vita delle API, dalla progettazione alla distrubuzione e gestione. 

La piattaforma include strumenti per creare API moderne ed è composta da:

1. **Anypoint Design Center**: qui possiamo creare l'API, definire le operazioni, gli input, gli output e i tipi di dati sottostanti.
2. **Anypoint Exchange**,  rende le nostre API scopribili e accessibili ad altri sviluppatori. Possiamo condividere la documentazione, gli esempi e le risorse correlate all'API.
3. **Anypoint Managment Center**, onsente la gestione delle API per garantire sicurezza, scalabilità e prestazioni ottimali. Possiamo applicare politiche di sicurezza, monitorare l'utilizzo e analizzare le metriche di performance.

Anypoint consente di progettare e distribuire le API ovunque, sia su ambienti personalizzati dei clienti, su Cloud privati o tramite **CloudHub**, una soluzione **iPaaS** completamente gestita fornita da Mulesoft. L'applicazione mantiene le stesse opzioni di connettività, indipendentemente dall'ambiente di distribuzione scelto.

> N.B: iPaaS, acronimo di Integration Platform as a Service, è una piattaforma cloud che fornisce servizi di integrazione per consentire l'interconnessione tra applicazioni e sistemi diversi. Si tratta di una soluzione di integrazione basata su cloud che offre funzionalità di middleware per facilitare lo scambio di dati e l'integrazione tra varie applicazioni, sia all'interno di un'organizzazione che tra organizzazioni diverse.

### Benefit of Application Network
I benefici dell'Application Network basato sulla connettività API-led includono:

- **Velocità di consegna**: grazie alla progettazione modulare delle API, è possibile sviluppare e distribuire in modo rapido e agile nuove funzionalità.
- **Visibilità operativa**: attraverso strumenti di monitoraggio e analisi, è possibile ottenere una visione dettagliata delle prestazioni delle API e delle integrazioni, consentendo azioni proattive per garantire un funzionamento ottimale.
- **Sicurezza integrata**: l'approccio "secure by design" consente di applicare politiche di sicurezza coerenti in tutte le API e di gestire l'autenticazione, l'autorizzazione e la protezione dei dati sensibili.
- **Architettura futura**: l'Application Network offre una base solida per la crescita e l'evoluzione, consentendo di integrare facilmente nuove applicazioni e sistemi nel tempo.

### Ottenere successo con Anypoint Platform: Mulesoft Catalyst 
Mulesoft Catalyst è l'approccio di Mulesoft per il successo del cliente e si basa su tre pilastri fondamentali:

1. **Identificare gli obiettivi aziendali con indicatori chiave di prestazione (**KPI**) e allineare gli stakeholder:** In questa fase, si lavora con il cliente per comprendere gli obiettivi di business e definire i KPI che saranno utilizzati per valutare il successo del progetto. Vengono coinvolte le parti interessate chiave per garantire un allineamento completo.

2. **Consegna tecnologica:** Questo pilastro si concentra sull'utilizzo di Anypoint Platform per fornire la soluzione tecnologica. Si crea il progetto utilizzando gli strumenti e le funzionalità offerte da Anypoint Platform per sviluppare, integrare e gestire le API. Questo comprende la progettazione, lo sviluppo, la distribuzione e il monitoraggio delle API.

3. **Abilitazione dell'organizzazione:** Questo pilastro si concentra sull'assicurarsi che l'organizzazione sia pronta ad utilizzare ed adottare Anypoint Platform in modo efficace. Vengono creati i Centri di Abilitazione (Center for Enablement) per supportare l'organizzazione nel processo di adozione della piattaforma. Si fornisce anche il supporto interno necessario e si offre formazione per garantire che gli utenti siano in grado di utilizzare Anypoint Platform in modo efficiente.

Per ciascun pilastro, ci sono diverse fasi per ottenere il successo:

1. **Focus sulla pianificazione:** In questa fase si lavora con il cliente per definire gli obiettivi, identificare i KPI e coinvolgere le parti interessate chiave. Si stabilisce una strategia di progetto chiara e si pianifica l'implementazione.

2. **Stabilire le basi:** In questa fase si crea l'infrastruttura e l'ambiente necessari per l'utilizzo di Anypoint Platform. Si configurano i sistemi, si implementano le best practice e si stabiliscono le linee guida per lo sviluppo delle API.

3. **Costruire per scalare:** In questa fase si sviluppano e implementano le API, si integrano i sistemi e si testa la soluzione. Si fa attenzione a garantire la scalabilità e l'affidabilità del sistema.

4. **Misurare l'impatto:** In questa fase si valuta l'impatto della soluzione implementata, si monitora l'utilizzo delle API e si misurano i risultati rispetto ai KPI definiti. Si apportano eventuali miglioramenti e si ottimizza la soluzione in base ai risultati ottenuti.

Attraverso questo approccio, Mulesoft Catalyst mira a garantire il successo del cliente nell'utilizzo di Anypoint Platform per soddisfare le proprie esigenze di integrazione.

> *[Immagine: Table Achieving Success](https://github.com/esantoro-next/Mulesoft_Courses/blob/main/img/Table_Achieving_Success.png?raw=true)*

## Introduzione ai componenti di Anypoint Platform

Durante il ciclo di sviluppo delle API, ci sono diversi strumenti che supportano ciascuna fase:

- **API Designer:** Utilizzato per descrivere il contratto che fornisce tutti i dettagli sulle operazioni, gli input e gli output dell'API.
- **API Console & Mocking Service:** Permette di interagire con e simulare l'API. Consente di testare le chiamate e vedere come l'API risponde senza la necessità di implementarla completamente.
- **Exchange:** Consente di pubblicare la specifica dell'API, creando automaticamente un portale API che la rende scopribile dagli altri stakeholder. Questo permette loro di fornire feedback sull'API e di accedere a tutta la documentazione correlata.
- **API Notebook:** Aggiunto al portale API per combinare la documentazione con codice JavaScript per dimostrare come l'API può soddisfare diversi casi d'uso. È possibile eseguire il codice direttamente nel notebook per vedere i risultati e comprendere meglio come utilizzare l'API.

L'output di questi componenti è una **Validate API Specification**, creata utilizzando **RAML**

La fase successiva, dopo aver creato il RAML, è l' **API Implementation** utilizzando **Anypoint Studio**.
Volendo possiamo utilizzare anche Composer, uno strumento basato sul web che non richiede la scrittura di codice.

Dopo l'implementazione, passiamo all'ultima fase: **API managment**.

Il Management delle API è composto da:
 
- **API Manager**: utilizzato per creare un'applicazione proxy che stabilisce una versione iniziale della specifica dell'API e consente di aggiornarla, gestire e proteggere l'API tramite policy che controllano l'accesso e le richieste.
- **RunTime Manager**: utilizzato per distribuire e registrare il servizio web e monitorarne le prestazioni. Possiamo anche utilizzare _*Anypoint Monitoring*_, che ci fornisce diverse informazioni come visibilità delle prestazioni, strumenti di visualizzazione dei dati, problemi e analisi dei log.
- **API Analytics**: fornisce analisi e report sull'utilizzo dell'applicazione.
- **Visualizer**: fornisce una visualizzazione in tempo reale della rete delle applicazioni e aiuta a individuare rapidamente eventuali problemi.

I passaggi finali in questo ciclo sono ripetere queste fasi per aggiornare la Specifica dell'API.


Per quanto riguarda gli asset riutilizzabili, abbiamo Anypoint Exchange. Esso fornisce a tutti gli utenti la possibilità di scoprire e utilizzare autonomamente queste API o altri asset tramite Anypoint Studio. Abbiamo due metodi di ricerca disponibili:

1. Legacy
2. Functional

Quando viene pubblicata un'API REST su Exchange, viene automaticamente creato un portale API per essa. Un portale API offre le seguenti funzionalità:

- Documentazione API generata automaticamente
- Console API per consumare e testare le API
- Endpoint API generato automaticamente che utilizza un servizio di simulazione per consentire il test dell'API senza doverla implementare

I portali API possono essere condivisi con utenti interni ed esterni.

Quando pubblichiamo un'API su Exchange, viene automaticamente creato un connettore. Esso può essere utilizzato nelle applicazioni Mule per chiamare quell'API. **Rest Connect** è la tecnologia che esegue questa conversione.

**Ecco un esempio:**

> Un team di IT centrale pubblica template di API su Exchange. Il resto del team crea il progetto utilizzando quelle API e quindi carica il proprio progetto su Exchange.
> 
> In questo modo, Anypoint Exchange semplifica la condivisione e il riutilizzo delle risorse, consentendo ai team di sviluppo di creare progetti basati su API già esistenti e condividere i loro progetti con gli altri utenti tramite Exchange.

### Design Center
Il Design Center include due componenti: l'API Designer e Anypoint Studio.

**API Designer** è uno strumento che ti permette di progettare e documentare le tue API. Fornisce un'interfaccia user-friendly in cui puoi definire le operazioni, gli input, gli output e i tipi di dati sottostanti della tua API. Puoi anche specificare il comportamento e i dettagli di configurazione della tua API. L'API Designer ti aiuta a creare un contratto API chiaro e ben strutturato.

**Anypoint Studio** è un ambiente di sviluppo integrato (IDE) fornito da MuleSoft. Viene utilizzato per creare applicazioni Mule, che sono applicazioni Java interne che implementano la logica e le funzionalità dell'API. Anypoint Studio fornisce un'interfaccia grafica per progettare, sviluppare e testare le applicazioni Mule. Offre una vasta gamma di connettori e componenti predefiniti che possono essere utilizzati per integrare vari sistemi e tecnologie.

### Mule Runtime
**È una piattaforma leggera per l'integrazione** e l'automazione che consente agli sviluppatori di connettere rapidamente e facilmente le applicazioni, consentendo lo scambio di dati tra di esse.

- Funziona come un sistema di transito per il trasporto dei dati tra le applicazioni (Mule)
- Può connettere tutti i sistemi, inclusi servizi web, JMS, JDBC, HTTP...

**Svincola le integrazioni point-to-point** facendo sì che tutte le applicazioni comunichino con un runtime di Mule anziché direttamente tra loro.

**Impone politiche per la governance delle API.**

**Can be deployed anywhere**, può integrare ed orchestrare eventi in tempo reale o in batch ed offre una connettività universale.

## Designing API 

Diversi metodi per progettare le API includono:

1. **Hand coding**: Questo metodo prevede la scrittura del codice sorgente dell'API direttamente utilizzando un linguaggio di programmazione. Gli sviluppatori creano manualmente tutte le funzionalità e le specifiche dell'API.

2. **API Blueprint documentation**: API Blueprint è un formato di documentazione che utilizza una sintassi semplice per descrivere l'API. Questo metodo si basa sulla creazione di documentazione chiara e strutturata per definire l'interfaccia dell'API.

3. **Markdown**: Markdown è un formato di testo semplice che permette di scrivere documentazione leggibile e formattata per le API. È spesso combinato con strumenti di generazione di documentazione per creare documenti strutturati.

4. **OpenAPI Specification (OAS)**: OpenAPI Spec è una specifica basata su JSON o YAML che descrive in dettaglio l'API, inclusi endpoint, parametri, risposte e schemi dei dati. È uno standard ampiamente utilizzato per la progettazione delle API e può essere utilizzato per generare automaticamente il codice sorgente dell'API.

5. **AsyncAPI**: AsyncAPI è un linguaggio di descrizione delle interfacce dei messaggi per le API asincrone. È supportato da Anypoint Design Center e permette di definire le operazioni e gli eventi che possono essere scambiati tra le applicazioni.

6. **RAML**: RAML (RESTful API Modeling Language) è un linguaggio di modellazione delle API che consente di descrivere in modo dichiarativo l'interfaccia dell'API. È simile ad altri formati come OpenAPI Spec ma ha una sintassi leggermente diversa.


### Indtroduzione al RAML
RAML è un modo semplice, strutturato e sintetico per descrivere le API RESTful.

È un software open source, sviluppato per aiutare l'ecosistema delle API attuale e promuovere il riutilizzo, generando automaticamente la documentazione, creando endpoint simulati e fornendo interfacce per le implementazioni delle API.

RAML si basa su standard ampiamente utilizzati come JSON e utilizza un formato dati leggibile dall'uomo, in cui la **gerarchia** delle strutture dati è **specificata tramite indentazione**.

Le risorse sono gli oggetti identificati dall'URL, e tutte le risorse iniziano con "/".

I metodi e i parametri sono annidati sotto una risorsa, e le risorse nidificate vengono utilizzate per sottosezioni più specifiche.
Infine, i parametri URI sono racchiusi tra parentesi graffe "{}".

[_Esempio RAML_](https://raw.githubusercontent.com/esantoro-next/Mulesoft_Courses/main/img/RAML_Example.png)

### Using RAML to define specification 

Response must be a map of one or more HTTP status codes. For each response, specify possible return data types along with description and example

```
#%RAML 1.0
title: My API
version: 1.0

/{ID}:
  get:
    responses:
      200:
        body:
          application/json:
            type: AmericanFlight
            examples:
              output:
                ID: 1
                code: ER38sd
                price: 400
                departureDate: 2017/07/26
                origin: CLE
                destination: SFO
                emptySeats: 0
                plane:
                  type: Boeing 737
                  totalSeats: 150

```

For a request similary specify the possible request data types along with description and examples

```
/{ID}:
  get:
  post:
    body:
      application/ison:
        type: AmericanFlight
        examples:
          input:
            ID: 1
            code: ER38sd
            price: 400
            departureDate: 2017/07/26
            origin: CLE
            destination: SFO
            emptySeats: 0
            plane:
              type: Boeing 737
              totalSeats: 150

```

**NB**: Possiamo utilizzare l'esempio per un singolo dato o gli esempi per rappresentare più istanze di dati.

### Engaging with users
To build a successful API you should define it iteratively, getting feedback from developers on usability and funcionality

To do this we can use API portals in Exchange, in private for internal developers or in public portal for the others

In pratic we publish our RAML API spec and other assets to Exchange from API Designer. When we public them, we can specify their statre: 
- Development: still in the iterative design process
- Stable: ready for consumption

API portals are automatically created for REST APIs added to Exchange

## Building APIs

Ci sono due fasi per la creazione delle API. La specifica RAML può essere utilizzata per creare l'implementazione dell'API.

Per iniziare, partiamo dalle applicazioni **Mule 4**.

Un'applicazione Mule è una sequenza di **Mule event processors**, organizzati in **flows**.

Un flow ha tre aree principali:

1. L'area di origine controlla come viene attivato il flow.
2. L'area di processo, attraverso i *Mule event processors*, controlla ciò che il flow deve fare.
3. La gestione degli errori.

Un'applicazione Mule è costituita da una serie di file XML che contengono più flows.

La source inizializza l'esecuzione del flow. Successivamente, i dati e i metadati vengono elaborati, trasformati, filtrati e arricchiti dai **Mule event processors**.

I dati strutturati trasmessi dalla source dei dati vengono chiamati **Mule Event**e hanno due elementi principali: il **Mule Message** e le **Variabili**

Il **Mule Message** è composto da altri due elementi: gli **Attributes** e il **Payload**:

1. Gli "Attributes" contengono i metadati che descrivono i dettagli sul payload.
2. Il "Payload" contiene i dati effettivi da elaborare.

Ad esempio, se viene inviata una richiesta HTTP POST all'applicazione, il payload conterrà i dati per creare nuove risorse, mentre gli attributi conterranno i parametri e gli header.

### Creare applicazioni Mule in Anypoint Studio

Anypoint Studio si basa sull'IDE Eclipse e ti consente di creare applicazioni Mule utilizzando elementi grafici e visualizzazioni XML. 

Include strumenti predefiniti per connettere API, protocolli e servizi popolari. Dispone di un framework e un linguaggio per la trasformazione dei dati e offre la possibilità di modificare e sincronizzare le specifiche delle API con Anypoint Platform. Puoi anche runnare, eseguire il debug e distribuire applicazioni Mule.

L'interfaccia di Anypoint Studio si basa su un concetto di layout chiamato **Prospectives**. Ogni prospectives contiene **panels** e ogni panels contiene **views**.

Ci sono 3 prospectives: una per lo sviluppo, una per le API e una per il design.

Le app Mule vengono create utilizzando **connectors** e **processors** che sono presenti nella palette. È possibile caricare nuove risorse.

È anche possibile implementare test automatici utilizzando **MUnit**, che è completamente integrato in Anypoint Studio.

### Connecting Data

**Database Connector**

- Può connettersi a quasi tutti i database relazionali JDBC.
- Configura l'URL e il driver JDBC.
- Dobbiamo eseguire una query per ottenere i dati dal database.

Per la maggior parte delle operazioni, gran parte della configurazione è racchiusa in un elemento globale separato, che rappresenta una configurazione riutilizzabile che può essere utilizzata da molte operazioni.

### Trasforming Data

Per rendere i dati leggibili utilizziamo **DataWeave 2.0**: è il linguaggio di espressione di Mule per accedere, interrogare e trasformare i dati dell'evento Mule.

È completamente integrato con Studio e dispone di un'interfaccia grafica con sviluppo consapevole del payload. Il componente **Trasform Message** viene utilizzato per questo tipo di trasformazione.

Per i test, possiamo utilizzare DataWeave Playground, un ambiente interattivo nel browser per la simulazione.

### Creating Restful Interface
Possiamo creare l'interfaccia RESTful manualmente o automaticamente utilizzando **APIkit** e la specifica API creata in precedenza.

APIkit può creare automaticamente un'interfaccia a partire dalla definizione API RAML, sia per progetti nuovi che esistenti.

Genera un flusso di routing principale e flussi per ciascuna delle risorse/metodi dell'API.

### Connecting interfaces to implementations 

Per collegare le interfacce alle implementazioni, è possibile suddividere i flussi complessi in flussi più piccoli per favorire il riutilizzo del codice. Questo processo rende le viste grafiche e l'XML più leggibili e facilita i test con MUnit.

Tutti i flussi sono identificati da un nome e possono essere chiamati tramite il componente **Flow Reference** in altri flussi.

Infine, Anypoint Studio può elencare tutti i riferimenti ai flussi o sottoflussi in un progetto.

### Sincronizzazione delle modifiche alla specifica dell'API tra Studio e Platform

La funzionalità di **API Sync** di Anypoint Studio consente di:

1. Estrarre la specifica dalla Design Center in Studio
 - È anche possibile avviare la creazione della specifica dell'API da zero in Studio
- Modificare la specifica offline in Anypoint Studio
- Aggiornare le modifiche nella Design Center
- Pubblicare la nuova versione dell'asset API su Exchange

Ciò consente di sviluppare le applicazioni Mule seguendo le pratiche di sviluppo del ciclo di vita delle API direttamente da Anypoint Studio.

Se una specifica dell'API cambia in Exchange, l'interfaccia dell'API generata in Anypoint Studio può essere aggiornata.

 - **Nota bene**: I flussi che sono già stati modificati non vengono sovrascritti.

La prospettiva di **API Design** include la scheda di staging di Git. Infatti, dietro le quinte, viene utilizzato un sistema di controllo versione GIT per estrarre, caricare e unire i rami effettuati sulla specifica dell'API.

Se qualcuno modifica la versione nella Design Center mentre si sta lavorando sulla stessa versione localmente, viene generato un **conflitto** in Git: è necessario indicare a Git come applicare le modifiche su una versione modificata.

## Deploying and Managing APIs

Ci sono 3 opzioni principali per distribuire un'applicazione Mule:

1. **CloudHub**: viene utilizzato come macchina virtuale su AWS. È completamente gestito, multi-tenant e molto sicuro.
2. **Mule runtimes** ospitati dal cliente.
3. **Anypoint runtime fabric**: è un servizio di contenitori ospitato dal cliente per il piano di runtime.


### Vantaggi di CloudHub

- Semplicità: non è necessario gestire l'hardware, fornisce infrastrutture per DNS e bilanciamento del carico, e riceve aggiornamenti software continui.
- Elevata sicurezza
- Disponibilità globale

### Vantaggi del Customer-hosted

- Facile da installare
- Richiede risorse minime
- Può eseguire più applicazioni contemporaneamente
- Può essere gestito da Runtime Manager nell'ambiente ospitato da MuleSoft o nell'ambiente ospitato dal cliente nella piattaforma Anypoint


### **Anypoint Runtime Fabric** 

Si tratta di un modello di distribuzione del piano di esecuzione (runtime plane):

- Sicurezza e affidabilità attraverso l'isolamento tra le applicazioni
- Ridistribuzioni senza tempi di inattività
- Failover automatico delle applicazioni
- Esecuzione di più versioni di Mule Runtime contemporaneamente
- Immagini di runtime containerizzate supportate da MuleSoft

### Viewing Deployed Apps with ***Visualizer***

L'accesso in tempo reale alle informazioni sull'architettura dell'applicazione. Organizzando le API in diversi diagrammi di relazione, otteniamo una visione dell'architettura dell'applicazione che si adatta al nostro ruolo. Ciò favorisce la coerenza nell'architettura a livelli e ci consente di visualizzare rapidamente eventuali problemi.

I dati del diagramma sono sicuri e vengono aggiornati automaticamente e dinamicamente, garantendo che abbiamo accesso alle informazioni più aggiornate sull'architettura delle nostre app e sulle loro connessioni.

### Anypoint Monitoring

### Monitoraggio Anypoint

Il monitoraggio Anypoint fornisce visibilità sulle integrazioni all'interno della rete delle tue applicazioni. Dispone di diversi strumenti di monitoraggio progettati per ridurre il tempo necessario per identificare e risolvere problemi attraverso:

- Aggregazione e mappatura delle metriche: consente di raccogliere e visualizzare le metriche delle tue integrazioni in un'unica vista, consentendo di identificare facilmente i punti critici e le performance delle tue applicazioni.
- Configurazione di dashboard e avvisi: puoi configurare dashboard personalizzate per visualizzare le metriche più rilevanti per il tuo ambiente, oltre a impostare avvisi per essere notificato in caso di anomalie o situazioni critiche.
- Archiviazione e ricerca dei log: il monitoraggio Anypoint consente di archiviare e ricercare i dati di log generati dalle tue applicazioni, semplificando l'analisi dei problemi e la risoluzione dei bug.

Questi strumenti ti aiutano a monitorare e ottimizzare le tue integrazioni, garantendo prestazioni affidabili e una risoluzione rapida dei problemi.

### Create API proxy

Utilizzato per gestire l'accesso al nostro servizio web tramite un **API gateway**.

Un API Gateway è un runtime progettato e ottimizzato per ospitare un'API o per aprire una connessione a un'API implementata su un altro runtime. È incluso come parte del runtime Mule e separa le preoccupazioni di organizzazione dall'implementazione.

- Determina quale traffico è autorizzato a passare ai servizi backend dell'API
- Misura il traffico in transito
- Registra tutte le transazioni
- Applica le politiche di runtime per imporre le governance come il limite di velocità, il throttling e la memorizzazione nella cache

L'API Gateway consente di gestire e proteggere l'accesso all'API, garantendo la sicurezza, la tracciabilità e l'applicazione delle politiche di gestione del traffico necessarie per una governance efficace delle API.

### Restricting Access to api

**API Manager** viene utilizzato per gestire l'accesso alle API tramite i proxy delle API, definisce i livelli degli SLA (Service Level Agreement) e applica le politiche di runtime. Possiamo far rispettare tali politiche tramite l'API Gateway.

**API Autodiscover** è un meccanismo che consente a un'applicazione Mule distribuita di scaricare le politiche dall'API Manager e agire come proprio proxy.

Ci sono anche **politiche predefinite** per casi d'uso comuni come:
- Limitazione della velocità
- Controllo dei picchi di traffico
- Sicurezza

Possiamo anche definire politiche personalizzate utilizzando XML e YAML, applicare più politiche e impostare l'ordine di esecuzione. Infine, possiamo definire politiche automatiche per conformarsi ai requisiti comuni.

### Granting access to APIs

Per accedere a un'API che è limitata da una politica basata su SLA, i consumatori devono registrare la loro applicazione su Exchange. Attraverso il pulsante "Richiedi accesso", selezionano un livello (TIER) e richiedono l'accesso. Una volta approvata, ottengono le credenziali di accesso e devono includere queste credenziali di autenticazione nelle chiamate effettuate all'API.

Il proprietario dell'API riceve una notifica e può quindi approvare o rifiutare la richiesta di accesso.

### Adding Client ID enforcement to API specifications 

Per aggiungere l'applicazione dei vincoli del client ID alle specifiche dell'API, è necessario aggiungere i campi `client_id` e `client_secret `nell'intestazione di ogni chiamata all'API. Pertanto, è necessario modificare le specifiche dell'API.

# Anypoint Platform Development - Fundamentals - Part 2

## Viewing information about Mule 4 event

Per visualizzare le informazioni sugli eventi di Mule 4, abbiamo due metodi: durante la fase di progettazione con **DataSense** o durante l'esecuzione del runtime.

- DataSense è la scoperta proattiva dei metadati da risorse interne ed esterne e li rende disponibili tramite DataSense Explore, tramite il componente Transform Message e anche durante la scrittura di espressioni utilizzando l'autocompletamento.

In DataSense abbiamo notifiche (indica se DataSense sta raggiungendo il timeout) e indicatori (fornisce informazioni sullo stato e consente a DataSense di riavviarsi se necessario) per eventuali problemi.

Durante l'esecuzione, possiamo vedere gli eventi di Mule effettuando una richiesta e visualizzandoli nella finestra della console, con un browser / Postman e con il file di log:

- Il componente **Log** aiuta a gestire e debuggare le applicazioni registrando informazioni importanti come messaggi di errore, payload e notifiche di stato. Possiamo anche registrare messaggi personalizzati.

### Debubbing applications with Mule

Il debugger è un processo separato che comunica con il runtime di Mule utilizzando la porta 6666 (che può essere modificata). Durante il debug, l'applicazione può essere interrotta utilizzando dei punti di interruzione (che possono essere gestiti nella lista dei punti di interruzione).

Ciò ci consente di eseguire il debug passo-passo della nostra applicazione Mule.

### Tracking event data with debugger

Quando vengono effettuate chiamate a risorse esterne da un flusso in Mule, l'oggetto evento viene inviato alla risorsa esterna tramite un componente di connessione appropriato. 

L'oggetto evento può contenere dati come i parametri della richiesta, l'URL di destinazione e gli header. Una volta che la risorsa esterna ha elaborato la richiesta e restituito una risposta, l'oggetto evento viene aggiornato con i dati della risposta, come il corpo della risposta e gli header di risposta.
 
Utilizzando il debugger di Mule, è possibile tracciare l'oggetto evento durante questo processo e visualizzare le modifiche apportate ad esso. Ciò consente di controllare come l'oggetto evento viene trasformato e arricchito durante il flusso e di individuare eventuali problemi o anomalie durante l'interazione con le risorse esterne.

### Setting request and response data

Per impostare i dati della richiesta e della risposta, possiamo utilizzare diverse opzioni in Mule.

- Per impostare il payload della richiesta, possiamo utilizzare il componente "Set Payload" che consente di specificare il contenuto del corpo della richiesta.

- Per personalizzare la risposta HTTP, possiamo utilizzare il componente "HTTP Listener Response" per modificare il contenuto del corpo della risposta, gli header e altri parametri.

- Nel componente "HTTP Request" possiamo modificare il corpo della richiesta, gli header e i parametri di query o di form.

Queste opzioni ci consentono di gestire in modo flessibile i dati delle richieste e delle risposte, adattandoli alle nostre esigenze specifiche durante l'elaborazione delle API.

### Using DataWeave expression to read and write event data

DataWeave è un linguaggio di espressioni "case-sensitive" che consente di accedere al contenuto di un evento Mule, compresi il payload, gli attributi e le variabili. Possiamo scrivere **espressioni DataWeave** nelle proprietà di qualsiasi processore o elemento globale.

Le espressioni DataWeave possono essere valutate in due modi principali:

- In script autonomi utilizzando il processore "Transform Message".
- Nelle proprietà delle espressioni inline, racchiuse tra #[].

Utilizzando le espressioni DataWeave, possiamo accedere a tutte le parti di un evento Mule:

- Server
- Istanza Mule
- Applicazione Mule
- Flusso Mule:
   - Messaggio: `#[message.payload]`
   - Attributi: `#[attributes.queryParams.param1]`
   - Payload: `#[payload]`
   - Variabili: `#[vars.foo]`

A volte possiamo accedere allo stesso valore utilizzando diverse espressioni DataWeave, ad esempio:

- `#[message.attributes.method] = #[attributes.method] = POST`
- `#[attributes.headers.host] = mulesoft.org`
- `#[attributes.header['user-agent']] = Mozilla`
- `#[message.payload.id] = #[payload.id] = ``#[payload['id']] = abcdef`
- `#[payload.itemsTotal] = 200.34`

I selettori vengono utilizzati per accedere alle informazioni in oggetti e array. Ad esempio:

- Valore di una coppia chiave:valore --> `#[payload.name]`
- Valore all'indice selezionato in un array --> `#[payload[0].name]`
- Array con valori delle chiavi:valori --> `#[payload.*name]`
- Array con valori delle chiavi:valori (valori discendenti) --> #`[payload..zip]`

**Operations**: 

- *Arithmetic* +,-,/,* --> `#[payload.age * 2]`
- *Equality* ==,!=, ~= --> `#[payload.name == "max"]`
- *Relational* >,>=,<,<=, is --> `#[payload.age > 30]`
- *Conditional* and,or,not --> `#[payload.name == "max"] and #[payload.sur == "Mule"]`
- *Type coercion* as --> `[(payload.age as Number) * 2]`
- *Default value* default --> `#[payloas.type default "student"]`

Le **variabili** possono essere create utilizzando il componente "Set Variable" e utilizzate con la parola chiave "vars".

## Structure Mule Applications

### Encapsulating processors into subflows

L'utilizzo di flussi (flows) rende l'aspetto grafico più intuitivo, il codice XML più leggibile, favorisce il riutilizzo del codice e semplifica i test.

I flussi senza una sorgente di eventi sono chiamati flussi privati (*private flows*). Per creare un sottoflusso, possiamo farlo manualmente trascinando un componente **Scope**. Per richiamare un flusso da un altro, possiamo utilizzare il componente **FlowReference**. Tuttavia, se lo estraiamo automaticamente, dovremo fare manualmente il lavoro di collegamento.

L'utilizzo di FlowReference avviene in modo sincrono.

### Asynchronus queues
Nel metodo asincrono, i dati non vengono restituiti.

Il **VM Connector** può essere utilizzato per effettuare chiamate asincrone tra flussi. Ci consente di aumentare il livello di parallelismo o comunicare con altre applicazioni che utilizzano lo stesso dominio.

Da notare che il componente **VM Publish Consume** ha un tempo di attesa simile a FlowReference, mentre il componente **VM Publish** è asincrono e i dati non vengono restituiti.

### Organizing mule application files

Per organizzare i file dell'applicazione Mule, separiamo l'interfaccia dall'implementazione, ma possiamo creare ulteriori file per rendere il progetto più leggibile e facile da gestire. Di solito creiamo file di configurazione che possono essere utilizzati per incapsulare tutti gli elementi globali riutilizzabili.

Possiamo anche separare le funzionalità in file diversi.

Possiamo creare un **progetto di dominio** utilizzato per condividere elementi di configurazione globali tra le applicazioni. Creiamo un progetto di dominio Mule e associamo l'applicazione Mule a un dominio.

### Organizing and Parameterizing application properties

Mule può essere configurato per utilizzare il **property placeholder** per sostituire dinamicamente i valori statici con i valori memorizzati in un file .yaml o .properties.

Ecco i passaggi per utilizzare i sostituti di proprietà:

1. Creare un file YAML o .properties.
2. Impostare i valori in modo gerarchico.
3. Creare l'elemento globale "Configuration properties".

I sostituti di proprietà hanno due formati:

- `${db.port}` per la configurazione degli elementi e dei processori degli eventi.
- `{port: Mule::p('db.port')}` nell'espressione DataWeave.

I property placeholder possono essere sovrascritti dalle proprietà di sistema quando si effettua il deployment in diversi ambienti su CloudHub. Possono anche essere impostati utilizzando i parametri JVM da Anypoint Studio o dalla riga di comando.

### Organizing Mule project files
**Maven** è uno strumento per la costruzione e la gestione di progetti basati su Java.

La struttura corretta delle directory per un progetto Maven è la seguente:

```
project-name
├── src
│   ├── main
│   │   ├── java
│   │   ├── resources
│   │   └── webapp
│   └── test
│       ├── java
│       ├── resources
│       └── webapp
└── pom.xml
```

Il file POM (Project Object Model) è un file XML che contiene le informazioni di configurazione del progetto Maven, come le dipendenze, i plugin e le impostazioni di compilazione.

Puoi configurare il tuo progetto Maven modificando il file POM.xml e specificando le dipendenze, i plugin e le altre impostazioni necessarie per la compilazione e la gestione del tuo progetto.

### Managing metadata for a project
Nel contesto di MuleSoft, il **Metadata Editor** è uno strumento che consente di definire metadati per un'applicazione. I metadati forniscono informazioni descrittive aggiuntive sull'applicazione, come la sua versione, la descrizione, gli autori, le dipendenze e altre informazioni pertinenti.

L'editor dei metadati offre un'interfaccia grafica per definire e gestire i metadati dell'applicazione in modo intuitivo. È possibile accedere all'editor dei metadati all'interno di Anypoint Studio, che è l'ambiente di sviluppo integrato (IDE) fornito da MuleSoft.

Per definire i metadati dell'applicazione, è possibile aprire il file **application-types.xml** nel Metadata Editor e compilare i campi appropriati con le informazioni desiderate. I metadati definiti in questo modo saranno associati all'applicazione e saranno accessibili tramite API o altre operazioni di gestione dell'applicazione.

**N.B:** Definire metadati per un'applicazione può essere utile per organizzare e descrivere l'applicazione stessa, facilitando la comprensione e la gestione da parte degli sviluppatori e degli operatori di sistema.

## Consuming Web services

### Consume REST web-service

Nel contesto di MuleSoft, esiste un sistema che semplifica l'integrazione con API RESTful presenti su Exchange tramite il generatore di connettori REST Connect. Questo strumento richiede solo i nomi delle operazioni dell'API e, utilizzando i metadati disponibili su Exchange, genera automaticamente il connettore con i relativi endpoint e configurazioni predefinite. Inoltre, grazie all'utilizzo di DataSense, è possibile ottenere informazioni sulle strutture dei dati in modo automatico, semplificando ulteriormente l'integrazione.

Tuttavia, se non è disponibile un connettore specifico su Exchange per un particolare servizio web RESTful, è possibile utilizzare il componente HTTP Request con il metodo GET. In questo caso, sarà necessario configurare manualmente l'URL del servizio REST e definire i dati di esempio e lo schema per abilitare DataSense e consentire la visualizzazione delle strutture dei dati.

È importante notare che in caso di errori, i messaggi di errore prodotti dal connettore REST Connect includeranno il nome specifico dell'API, mentre nel caso del componente HTTP Request, gli errori saranno associati al componente HTTP stesso.

### Consume SOAP web-service

Se non è disponibile un connettore specifico su Exchange, è possibile utilizzare il connettore Web Service Consumer per integrarsi con un servizio web SOAP. Di seguito sono elencati i passaggi per utilizzare questo connettore:

1. Aggiungere il connettore Web Service Consumer al progetto Mule.
2. Configurare il connettore come elemento globale nel file di configurazione, specificando la posizione del file WSDL che definisce il servizio web SOAP.
3. Utilizzare il componente "Consume" del connettore per invocare le operazioni SOAP desiderate.
4. Se l'operazione richiede parametri di input, è possibile utilizzare il componente "Transform Message" per trasformare e passare i dati necessari. I parametri disponibili saranno rilevati automaticamente da DataSense, semplificando la configurazione.

È importante notare che il connettore Web Service Consumer è specifico per l'integrazione con servizi web SOAP e richiede l'utilizzo del file WSDL per definire la struttura e le operazioni del servizio.

## Controlling event flow

Per creare un'interfaccia unica per le diverse compagnie aeree, puoi utilizzare le seguenti tecniche:

1. Combinare i risultati di tutte le compagnie aeree: Effettua richieste individuali a ciascuna API delle compagnie aeree e unisci i risultati in una singola risposta da restituire al client.

2. Restituire voli per una singola compagnia o tutti combinati: Fornisci un'opzione per consentire al client di specificare la compagnia aerea preferita o richiedere voli da tutte le compagnie disponibili. In base alla scelta del client, instrada la richiesta all'API corrispondente o aggrega i dati di tutte le compagnie aeree.

Puoi utilizzare le funzionalità di MuleSoft, come l'elaborazione parallela degli eventi e la logica di routing, per implementare queste tecniche e gestire le chiamate alle diverse API delle compagnie aeree.

### Routing Events

Ci sono altri 4 componenti di controllo del flusso che consentono di instradare gli eventi:

1. **Choice** (Scelta)
   - Esegue una singola route in base a una condizione logica - condizione 1, 2... o predefinita.
2. **First Successful** (Primo esito positivo)
   - Esegue le route in sequenza finché una di esse ha successo.
3. **Round Robin** (Rotazione)
   - Esegue una sola route selezionandola iterativamente da una lista mantenuta durante le esecuzioni. Funziona come un bilanciamento del carico.
4. **Scatter-Gather** (Raccolta distribuita)
   - Esegue tutte le route contemporaneamente e poi unisce i risultati in un oggetto di oggetti. Contiene una chiave che rappresenta l'indice.

Questi componenti di routing consentono di definire la logica di routing degli eventi in modo flessibile, consentendo di prendere decisioni basate su condizioni, eseguire route sequenziali o parallele e gestire i risultati in modi diversi.


### Multicasting Events

La tecnica di **Multicasting** consente di inviare un singolo evento a più destinazioni contemporaneamente. Funziona inviando copie dell'evento originale a più destinazioni senza modificarne il contenuto. 

In pratica, il componente di Multicasting riceve un evento in ingresso e lo replica in più flussi paralleli, consentendo a ciascun flusso di elaborare l'evento in modo indipendente. Ciò può essere utile quando è necessario inviare lo stesso evento a più destinazioni o eseguire più elaborazioni simultaneamente.

L'uso del Multicasting permette di migliorare la scalabilità e la flessibilità delle applicazioni, consentendo di eseguire operazioni parallele su eventi simili o di inviare eventi a più destinazioni senza dover duplicare l'elaborazione.

### Validate Events to catch potential error

Possiamo utilizzare i Modelli di Validazione (**Validation Models**). Essi forniscono un modo per verificare se determinate condizioni sono soddisfatte e lanciano un errore di validazione se la validazione fallisce.

## Handling Errors

Gli errori possono essere gestiti a diversi livelli in Mule: a livello di applicazione, a livello di flusso e a livello di processore.

- **A livello di applicazione**, è possibile definire un gestore degli errori globale che si applica a tutti i flussi dell'applicazione. Questo gestore può catturare gli errori che si verificano in qualsiasi punto dell'applicazione e definire azioni da intraprendere per gestirli.

- **A livello di flusso**, è possibile definire gestori degli errori specifici per singoli flussi. Questi gestori possono catturare gli errori che si verificano solo in quel particolare flusso e definire azioni personalizzate per gestirli.

- **A livello di processore**, è possibile aggiungere gestori degli errori direttamente ai singoli processori. Questi gestori possono catturare gli errori specifici che si verificano durante l'esecuzione di quel processore e definire azioni specifiche da intraprendere.

La gestione degli errori consente di definire comportamenti personalizzati per gestire gli errori, ad esempio inviare una risposta di errore al chiamante, registrare l'errore in un log, riprovare l'operazione o eseguire altre azioni di recupero.

### Reviewing the default handling of messagging errors

**Comportamento predefinito**: Quando si verifica un errore, il processo si interrompe e l'evento viene passato al primo processore nell'Error Handler, che è un gestore degli errori di flusso.

Tutte le applicazioni Mule hanno un **default error handler** (gestore degli errori predefinito) il cui comportamento è interrompere l'esecuzione del flusso e registrare informazioni sull'errore. Non può essere configurato.

Quando si verifica un errore, viene creato un oggetto di errore con diverse proprietà come .description e .errorType.

Gli ErrorTypes sono identificati da uno spazio dei nomi e un identificatore:

- HTTP:UNAUTHORIZED (non autorizzato)
- HTTP:CONNECTIVITY (problemi di connessione)
- VALIDATION:INVALID_BOOLEAN (valore booleano non valido)

Ogni oggetto di errore ha un tipo di errore padre che viene utilizzato per tracciare la chiave dell'errore.

Esistono due tipi di errore:

- Generale (può essere gestito):
	- Any (qualsiasi)
		- Unknown (sconosciuto)
		- Transformation (trasformazione)
		- Routing (instradamento)
		- Connectivity (connettività)
			- Retry_Exhausted (riprova esaurita)
		- Expression (espressione)
		- Security (sicurezza)
			- Client_Security (sicurezza del client)
			- Server_Security (sicurezza del server)
- Critico (non può essere gestito):
	- Fatal (fatale)
	- Overload (sovraccarico)
	
### Creazione degli Error Handlers

Per gestire gli errori, è possibile aggiungere uno scope all'interno di un flusso. Ci sono due tipi di scope per la gestione degli errori:

- **On Error Propagate** (Propagazione dell'errore)
	- Tutti i processori all'interno dello scope di gestione degli errori vengono eseguiti.
	- Alla fine dello scope:
		- Il resto del flusso che ha generato l'errore non viene eseguito.
		- L'errore viene *ripropagato al livello successivo e gestito lì*.
	- Se si tratta di un listener HTTP, viene restituita una risposta di **errore**.
- **On Error Continue** (Continua in caso di errore)
	- Tutti i processori all'interno dello scope di gestione degli errori vengono eseguiti.
	- Alla fine dello scope:
		- Il resto del flusso che ha generato l'errore non viene eseguito.
		- L'errore *viene passato al livello successivo come se l'esecuzione del flusso fosse stata completata con successo*.
	- Se si tratta di un listener HTTP, viene restituita una risposta **di successo**.

In entrambi i casi, lo scope di gestione degli errori consente di definire i processori da eseguire in caso di errore e di gestire l'errore in modo appropriato.


### Handling errors at the application level

Per gestire gli errori a livello di applicazione, possiamo creare un gestore predefinito degli errori (**error handler**) dell'applicazione. Questo gestore degli errori viene eseguito quando non è disponibile un gestore specifico degli errori all'interno di un flusso.

L'error handler predefinito ci permette di definire un insieme di processori che saranno eseguiti quando si verifica un errore a livello di applicazione. Questi processori possono includere registrazioni, trasformazioni degli errori, invio di notifiche o qualsiasi altra logica di gestione degli errori necessaria.

Configurando l'error handler predefinito dell'applicazione, ci assicuriamo che gli errori non gestiti che si verificano all'interno dell'applicazione vengano catturati e elaborati secondo il flusso di gestione degli errori definito. Questo aiuta a centralizzare la logica di gestione degli errori e a fornire una gestione degli errori coerente in tutta l'applicazione.

### Handling specific types of errors

Se abbiamo più di uno scope di gestione degli errori, è necessario specificare quale errore dovrebbe essere gestito da ciascuno di essi. L'ordine in cui sono definiti gli scope è importante, poiché Mule valuta gli scope nell'ordine in cui sono elencati. Il primo scope che corrisponde all'errore verrà eseguito, mentre gli altri scope successivi non saranno considerati.

Se un errore non corrisponde a nessuno dei criteri definiti negli scope, passerà al gestore predefinito degli errori di Mule. È quindi importante definire attentamente gli scope di gestione degli errori e l'ordine in cui sono elencati, in modo da garantire che gli errori siano gestiti correttamente nell'applicazione.

### Handling errors at the flow level 
Tutti i flussi, ad eccezione dei subflussi, hanno i propri gestori degli errori. Ciò significa che è possibile definire uno o più scope di gestione degli errori all'interno di ogni flusso per gestire gli errori specifici che si verificano in quel flusso.

### Handling errors at the process level 

Gestire gli errori a livello di processo significa utilizzare uno scope di gestione degli errori per incapsulare un gruppo di processori all'interno di un blocco **try-catch**. Questo consente di gestire gli errori che si verificano durante l'esecuzione di quei processori in modo specifico.

Nel blocco **try** del processo, vengono eseguiti i processori desiderati. Se si verifica un errore durante l'esecuzione di uno di questi processori, il controllo passa al blocco "catch" corrispondente nel gestore degli errori del processo.

All'interno del blocco **catch**, è possibile definire le azioni da intraprendere per gestire l'errore. Ciò può includere la registrazione di informazioni sull'errore, l'invio di notifiche, il ripristino delle risorse o qualsiasi altra azione di gestione degli errori necessaria.

Gestire gli errori a livello di processo consente di affrontare specificamente gli errori che si verificano all'interno di quel processo, fornendo un controllo più granulare e una gestione più mirata degli errori.

### Mapping errors to custom error types

Per gestire il troubleshooting, è possibile personalizzare la gestione degli errori per ogni tipo di errore utilizzando un namespace univoco. Ciò consente di definire azioni specifiche da intraprendere per ciascun tipo di errore, come registrazione dettagliata dell'errore, notifiche di avviso e azioni correttive. 

L'utilizzo di namespace univoci semplifica il processo di troubleshooting, consentendo di identificare e affrontare rapidamente problemi specifici associati a ciascun tipo di errore.

### Reviewing and integrating with APIkit error handling

APIkit include anche un sistema di gestione degli errori integrato. Questo sistema offre la possibilità di gestire gli errori specifici delle API in modo più strutturato e semplificato. Durante la progettazione delle API con APIkit, è possibile definire gli errori associati a ciascuna operazione API e stabilire come gestirli.

Quando si verifica un errore durante l'esecuzione di un'operazione API, il sistema di gestione degli errori di APIkit entra in azione. È possibile definire le azioni da intraprendere per ciascun tipo di errore, ad esempio restituire una risposta di errore specifica, registrare un log dettagliato dell'errore o inviare una notifica. Questo consente di gestire in modo più efficiente gli errori delle API e di fornire una migliore esperienza agli sviluppatori e agli utenti delle API.

### Handling System Errors

Gli errori di sistema sono errori che si verificano a livello di sistema quando non è coinvolto alcun evento Mule. Questi errori possono verificarsi durante l'avvio dell'applicazione o quando si verifica un errore di connessione a un sistema esterno.

La gestione degli errori di sistema avviene tramite una strategia di gestione degli errori di sistema, che non è configurabile. Questa strategia registra gli errori e, nel caso di fallimenti di connessione, esegue la **reconnection strategy** (*strategia di riconnessione*) per tentare di ripristinare la connessione con il sistema esterno.

La gestione degli errori di sistema aiuta a gestire in modo efficiente gli errori critici a livello di sistema, assicurando una maggiore affidabilità delle applicazioni integrate.

## Writing DataWeave Trasformation

Il comando `map` viene utilizzato per applicare una trasformazione a ciascun elemento in un array. L'input può essere un oggetto JSON o Java, e viene restituito un array di elementi trasformati.

Con il comando `map`, possiamo utilizzare il simbolo "$" per:

- `$$` si riferisce all'indice o alla chiave dell'elemento
- `$` si riferisce al valore dell'elemento

È importante notare che nella funzione `map` possiamo anche passare parametri. Ad esempio:

```
payload map (user, index) -> {
    num: index,
    fname: user.firstname,
    lname: user.lastname
}
```

La funzione `map` itera su tutti gli elementi dell'array e passa ciascun elemento a una "lambda function" (funzione anonima) che esegue la trasformazione desiderata.

### Transform complex XML Data stucture

Quando si mappano gli elementi di un array (JSON o Java) in XML, poiché XML non supporta nativamente gli array, è necessario avvolgere la funzione `map` tra `{()}`. In questo modo:

- `{}` definisce l'oggetto XML
- `()` trasforma ogni elemento dell'array in una coppia chiave/valore


Ecco un esempio:

```
output application/xml
---
users:{(payload map (user, index) -> {
	user: {
		num: index,
		fname: user.firstname,
		lname: user.lastname
	}
}
)}
```

In questo caso, la funzione `map` itera sugli elementi dell'array `payload` e restituisce una struttura XML che rappresenta ciascun elemento dell'array come un elemento `<user>`, con le relative proprietà come sottoelementi.

### Defining and using variable and functions 

Possiamo creare variabili globali utilizzando la parola chiave **var** e assegnando loro una costante o un'espressione lambda. Le variabili globali possono essere referenziate ovunque nel corpo del codice.

**NB**: DataWeave è un linguaggio di programmazione funzionale in cui le variabili si comportano come funzioni.

Esempio:

```
output application/xml
var mname = "the"
var mname2 = () -> "other",
var lname = (aString) -> upper(aString)
---
name:{
	first: payload.fName,
	middle1: mname,
	middle2: mname2(),
	lastname: lname(payload.lastname)
}
```

Possiamo anche utilizzare la direttiva **fun**, una sintassi simile alla classica funzione.

```
output application/xml
fun lname(aString) = upper(aString)
---
name{
	first: payload.fName,
	last: lname(payload.lastname)
}
```

Possiamo anche utilizzare variabili locali all'interno del corpo del messaggio utilizzando la parola chiave **do**.

```
do { var name = payload.firstname ++ " " ++ payload.lastname --- name}
```

In questo caso, la variabile **name** viene definita all'interno del blocco **do** e può essere utilizzata all'interno dello stesso blocco per elaborare il messaggio.

### Formatting and coercing data

Possiamo modificare il tipo di dati utilizzando la parola chiave **as**, che viene chiamata "Coercion" in DataWeave.

Ad esempio, se abbiamo una variabile **someDate** e vogliamo convertirla in un tipo di dato DateTime con un formato specifico, possiamo utilizzare l'opzione **format**.

```
someDate as DateTime {format: "yyyyMMddHHmm"}
```

In questo modo, stiamo coercento la variabile **someDate** nel tipo di dato DateTime e specificando il formato desiderato come "yyyyMMddHHmm". Ciò ci consente di formattare la data secondo le nostre esigenze durante la trasformazione dei dati in DataWeave.

### Tipi di dati personalizzati

Possiamo dichiararli usando la parola chiave **type** nell'intestazione.

```
output application/json
type Ourdateformat = DateTime {format: "ddMMyyyy"}
---
someDate: payload.departureDate as Ourdateformat
```

Possiamo anche utilizzare classi Java per convertire i dati o definire classi personalizzate usando la parola chiave **class**.

**Specificare in linea**

customer: payload.User as Object {class: "my.company.User"}

**Definire un tipo di dati personalizzato da utilizzare**

```
type User = Object {class: "my.company.User"}
---
customer: payload.User as User
```

### Using Dataweave functions

Le funzioni con 2 parametri possono essere invocate con 2 sintassi:

- `#[contains(payload, "max")]`
- `#[payload contains "max"]`

Le funzioni in tutti gli altri moduli devono essere importate.

Importa una funzione in un modulo:
- import dasherize from dw::core::Strings

**Esempi di funzioni**

```
planeType: dasherize(upper(replace(object.planeType,/(Boing)/) with "Boeing"))
```

### Looking up data by calling flow

La parola chiave **lookup** ci permette di eseguire un altro flusso all'interno della nostra applicazione.

```
{a: lookup("myFlow", {b:"Hello"})} 
```

- Il primo argomento è il nome del flusso da chiamare (non è possibile chiamare sottoflussi)
- Il secondo argomento è il payload da inviare al flusso come mappa
- Quello che il flusso restituisce come payload è ciò che l'espressione restituisce

## Triggering Flows

Per avviare i flussi in risposta a eventi specifici, possiamo utilizzare diversi trigger o meccanismi di attivazione:

1. **Message Source Trigger**: Un flusso può essere attivato in risposta all'arrivo di un messaggio su una determinata sorgente, ad esempio un listener HTTP o un listener di code.

2. **Timer Trigger**: Un flusso può essere attivato in base a un intervallo di tempo predefinito, ad esempio ogni 5 minuti o ogni giorno alle 8:00.

3. **Scheduler Trigger**: Un flusso può essere attivato in base a un programma di pianificazione predefinito, ad esempio ogni lunedì alle 10:00 o il primo giorno di ogni mese.

4. **Custom Event Trigger**: Possiamo creare trigger personalizzati per attivare un flusso in base a eventi specifici all'interno dell'applicazione. Ad esempio, potremmo definire un trigger per avviare un flusso quando un certo stato cambia o quando si verifica una determinata condizione.

L'attivazione dei flussi può essere configurata utilizzando i componenti e le opzioni appropriate all'interno dell'applicazione Mule.

### Reading and writing files

Per leggere e scrivere file in Mule, abbiamo a disposizione diversi connettori che supportano operazioni come il matching dei file, il blocco dei file, sovrascrittura, aggiunta e la generazione di nuovi file. I quattro connettori principali per lavorare con i file sono:

1. **File Connector**: Per lavorare con il file system localmente montato.
2. **FTP Connector**: Per lavorare con server FTP (File Transfer Protocol).
3. **FTPS Connector**: Per lavorare con server FTPS (FTP over SSL/TLS).
4. **SFTP Connector**: Per lavorare con server SFTP (SSH File Transfer Protocol).

Possiamo attivare un flusso utilizzando il modulo **On New or Updated File**. Questo modulo permette di monitorare una directory specifica per la creazione o l'aggiornamento di nuovi file e avviare il flusso corrispondente in risposta a tali eventi.

Attraverso questi connettori e moduli, Mule ci offre un'ampia gamma di funzionalità per lavorare con i file in modo flessibile e affidabile all'interno delle nostre applicazioni.

### Synchronizing data with watermarks

La sincronizzazione dei dati con i **watermark** consente di monitorare se sono stati aggiunti nuovi record a file o database. Durante la prima esecuzione, tutti i dati vengono sincronizzati, mentre nelle esecuzioni successive vengono sincronizzati solo i dati aggiunti successivamente.

Per fare ciò, durante la prima sincronizzazione viene memorizzato il valore più alto di un determinato campo per qualsiasi elemento nel set di dati. Successivamente, durante le sincronizzazioni successive, viene recuperato quel valore e confrontato con il valore di ciascun elemento per determinare se è il più grande.

Di solito, il campo utilizzato per l'ordinamento è un identificatore del record o un timestamp di creazione/modifica. Questo identificatore viene chiamato "watermark".

Il processo di watermarking può essere configurato per recuperare, confrontare e memorizzare automaticamente l'identificatore che determina quali dati elaborare. È anche possibile eseguire questa operazione manualmente. L'applicazione controlla periodicamente la presenza di nuovi dati da sincronizzare.

### Using listeners with automatic watermarking

Nel caso dell'ascoltatore "On New and Updated File" sono disponibili due watermark predefiniti: "CREATED_TIMESTAMP" e "MODIFIED_TIMESTAMP". Questi watermark vengono utilizzati per tenere traccia della data di creazione e modifica dei file, consentendo di filtrare i file in base a queste informazioni durante il polling.

Nel caso del connettore del database, quando si lavora con una tabella, è possibile specificare la tabella stessa, la colonna watermark (utilizzata per filtrare il contenuto della tabella durante il polling) e la colonna ID. Queste informazioni vengono utilizzate per determinare quali righe della tabella devono essere considerate durante il processo di watermarking.

In entrambi i casi, l'utilizzo dei watermark permette di sincronizzare e filtrare in modo efficiente i dati in base a criteri temporali, come la data di creazione o modifica dei file o il valore di una colonna specifica in una tabella del database.

### Publishing and consuming JMS

**JMS (Java Messaging Service)** è un protocollo ampiamente utilizzato per la comunicazione asincrona tra applicazioni utilizzando un middleware chiamato JMS Broker.

Con JMS, è possibile stabilire una comunicazione **uno a molti** tramite la sottoscrizione e la pubblicazione su argomenti, o una comunicazione "punto a punto" con un singolo sistema.

In MuleSoft, possiamo utilizzare il componente JMS per interagire con il JMS Broker. Questo componente ci consente di inviare messaggi a una coda o pubblicarli su un argomento nel sistema JMS. Possiamo anche sottoscriverci a un argomento o leggere messaggi da una coda utilizzando il componente JMS.

L'utilizzo del componente JMS ci consente di implementare pattern di messaggistica come Publish/Subscribe per la comunicazione tra sistemi distribuiti o per implementare scenari di comunicazione punto a punto.

Per utilizzare il componente JMS, è necessario configurarlo fornendo le informazioni di connessione al JMS Broker, come l'URL, le credenziali di accesso e il nome dell'argomento o della coda desiderati. Una volta configurato, il componente JMS ci consente di scambiare messaggi asincroni tra le applicazioni in modo affidabile e scalabile.

## Processing Records

### Processing Items in a collection with for Each Scope

Il componente **For Each Scope** ci consente di elaborare elementi individuali all'interno di una collezione in modo sequenziale. Con questo componente, possiamo suddividere una collezione all'interno di un payload e processare singoli elementi uno dopo l'altro.

All' interno del "For Each Scope", ogni elemento viene inviato in una serie di processori che vengono eseguiti in modo sequenziale. Questo ci permette di applicare una logica specifica a ciascun elemento della collezione.

È importante notare che il "For Each Scope" viene utilizzato principalmente per l'elaborazione e la manipolazione dei dati, piuttosto che per la modifica diretta del payload. Ogni elemento viene elaborato individualmente, ma il payload originale non viene modificato.

Questo componente è particolarmente utile quando è necessario applicare una logica specifica a ciascun elemento di una collezione, come l'invio di una richiesta HTTP per ogni elemento o l'esecuzione di una trasformazione personalizzata.

### Processing Records eith the Batch Job Scope

La funzionalità **Batch Job Scope** è disponibile solo nella versione Enterprise Edition di MuleSoft. Questo componente consente di suddividere messaggi di grandi dimensioni in record che vengono elaborati in modo asincrono in un lavoro di batch.

Il Batch Job Scope è stato progettato appositamente per l'elaborazione di set di dati ed offre diverse funzionalità:

- Suddivide i messaggi di grandi dimensioni o in streaming in record individuali.
- Esegue azioni su ogni record.
- Gestisce i fallimenti a livello di record che si verificano, evitando l'interruzione del lavoro di batch.
- Fornisce un rapporto sul risultato dell'elaborazione.
- Eventualmente, invia l'output elaborato ad altri sistemi o code.

Il Batch Job Scope è suddiviso in tre fasi:

1. Load and Dispatch (implicita)
   - Suddivide il payload in una collezione di record.
   - Crea una coda persistente e memorizza ogni record al suo interno.

2. Process (obbligatoria)
   - Elabora in modo asincrono i record.
   - Contiene una o più fasi di batch (batch steps).

3. On Complete (opzionale)
   - Fornisce un riepilogo dei record elaborati.
   - Fornisce informazioni sui record che hanno generato errori per consentire la risoluzione dei problemi.

I record di batch vengono messi in coda e pianificati in blocchi di 100 per migliorare le prestazioni.

L'errore di gestione può essere configurato in tre modalità:
- Interrompere l'elaborazione.
- Continuare l'elaborazione.
- Continuare l'elaborazione fino al raggiungimento del numero massimo di record falliti.

### Using filtering and aggregation in a batch step 

Nel componente Batch Step, sono disponibili due attributi per filtrare i record:

1. **Accept Expression**: Espressione utilizzata per filtrare i record all'interno del batch step. Solo i record che soddisfano l'espressione verranno elaborati.

2. **Accept Policy**: Politica di accettazione dei record all'interno del batch step. Ci sono tre opzioni disponibili:

   - **ALL**: Tutti i record che soddisfano l'espressione di accettazione verranno elaborati.
   - **NO_FAILURE**: Solo i record che soddisfano l'espressione di accettazione e che non hanno avuto errori verranno elaborati.
   - **ONLY_FAILURE**: Solo i record che soddisfano l'espressione di accettazione e che hanno avuto errori verranno elaborati.

Queste opzioni consentono di filtrare i record in base a determinati criteri e definire quali record devono essere elaborati durante l'esecuzione del batch step.

***END - GOOD JOB***
  