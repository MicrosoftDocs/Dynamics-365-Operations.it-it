---
title: Analisi di Commerce (anteprima)
description: Questo argomento spiega come installare e utilizzare la funzionalità di analisi in Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 11/23/2021
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 8cfe2af756315b5be3eb22d99376a96166fffc52
ms.sourcegitcommit: f9fca3d55b47e615e5ef64669dab184e057ec234
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2021
ms.locfileid: "7862775"
---
# <a name="commerce-analytics-preview"></a>Analisi di Commerce (anteprima)

[!include [banner](includes/banner.md)]

Questo argomento spiega come installare Analisi di Commerce (anteprima), la funzionalità di analisi funzionale inclusa in Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>Dimostrazione live di Analisi di Commerce (anteprima)

Puoi provare una [demo live di Analisi di Commerce (anteprima)](https://aka.ms/CommerceAnalyticsDemo).

![Riepilogo di Analisi di Commerce (anteprima)](media/CommerceAnalytics_Summary.png)
![Pagamenti di Analisi di Commerce (anteprima)](media/CommerceAnalytics_Payments.png)
![Attività web di Analisi di Commerce (anteprima)](media/CommerceAnalytics_WebActivity.png)


## <a name="commerce-analytics-preview-system-architecture"></a>Architettura del sistema di Analisi di Commerce (anteprima)

### <a name="key-components"></a>Componenti principali

Analisi di Commerce (anteprima) è costituito dai seguenti componenti chiave:

- Report Power BI interattivi predefiniti
- Viste SQL in Analisi di Azure Synapse
- Dati di entità e ontologia in Azure Data Lake
- Dati non elaborati in Data Lake

![Componenti chiave dell'architettura del sistema di Analisi di Commerce](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>Flusso di dati

#### <a name="step-1-data-generation"></a>Passaggio 1: generazione dei dati

I dati hanno origine come dati transazionali o dati comportamentali da una delle seguenti origini:

- Un call center associato utilizza il client Commerce HQ per elaborare gli ordini di vendita.
- Un cassiere presso il punto vendita (POS) elabora le transazioni di vendita.
- Le vendite vengono create in applicazioni personalizzate utilizzando Headless Commerce (Commerce Scale Unit).
- Un acquirente di e-commerce naviga sul tuo sito di e-commerce.
- Un acquirente di e-commerce effettua un ordine sul tuo sito di e-commerce.
- I dati sono prodotti da altri sistemi, come Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>Fase 2: Inserimento e pre-elaborazione

I dati transazionali vanno a Commerce HQ direttamente (nel caso di ordini acquisiti direttamente nel client Commerce HQ) o tramite Commerce Scale Unit (nel caso di ordini acquisiti presso il POS, nell'e-commerce o in client personalizzati che utilizzano Headless Commerce).

La funzionalità Esporta in Data Lake viene quindi utilizzata per copiare i dati transazionali nel data lake come dati non elaborati. Nel data lake, i dati non elaborati sono archiviati nella cartella Tabelle.

I dati dell'attività web di e-commerce vengono inviati direttamente al data lake. Dati prodotti da altri sistemi, come Dynamics 365 Connected Spaces, vengono inviati direttamente al data lake da tali sistemi.

#### <a name="step-3-transformation-and-aggregation"></a>Passaggio 3: trasformazione e aggregazione

Dopo che i dati non elaborati sono nel tuo data lake, il servizio di Analisi di Commerce li legge, li trasforma, li aggrega e li riscrive nel data lake sotto forma di entità logiche (nella cartella Entità) e metriche aggregate (nella cartella Ontologie).

#### <a name="step-4-querying"></a>Passaggio 4: query

Analisi di Azure Synapse viene utilizzato per eseguire query sui dati nel data lake tramite un'interfaccia Transact-SQL (T-SQL). Questa interfaccia include viste SQL. Le viste SQL consentono le query federate dei dati nel data lake, direttamente tramite un client T-SQL (per analisi ad hoc) o tramite uno strumento di visualizzazione come Power BI.

#### <a name="step-5-modeling-and-serving"></a>Passaggio 5: modellare e servire

Dati interrogati da Analisi di Azure Synapse vanno nel modello semantico di Power BI. A seconda del tipo di dati, vengono periodicamente importati in memoria in Power BI o interrogati direttamente in fase di esecuzione.

Infine, i dati sono resi elementi visivi in Power BI, in modo che gli utenti possano visualizzarli e interagire con essi.

## <a name="commerce-analytics-preview-functional-overview"></a>Panoramica delle funzionalità di Analisi di Commerce (anteprima)

### <a name="summary"></a>Riepilogo

L'app modello Analisi di Commerce include le seguenti pagine di report principali:

1. [Filtri di primo livello](#TopLevelFilters)
2. [Prodotti](#ProductsPage)
3. [Clienti](#CustomersPage)
4. [Canali](#ChannelsPage)
5. [Vendite](#SalesPage)
6. [Margini](#MarginsPage)
7. [Resi](#ReturnsPage)
8. [Sconti](#DiscountsPage)
9. [Pagamenti](#PaymentsPage)
10. [Clienti](#CustomersPage)
11. [Confronto](#ComparisonPage)
12. [Attività Web](#WebActivityPage)
13. [Attività web - Filtro di primo livello](#WebActivityTopLevelFilters)

####  <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Filtri di primo livello

- Impostazioni data

    - Anno
    - Trimestre
    - Mese
    - Settimana
    - Giorno

- Impostazioni canale

    - Persona giuridica
    - Tipo di canale
    - Tipo di cliente
    - Tipo vendite
    - Canale
    - Gerarchia organizzativa

- Impostazioni prodotto

    - Gerarchia di categorie
    - Categoria

####  <a name="products"></a><a name="ProductsPage"></a> Prodotti

- Vendite
- Margine
- Resi

####  <a name="customers"></a><a name="CustomersPage"></a> Clienti

- Vendite
- Margine
- Resi

#### <a name="channels"></a><a name="ChannelsPage"></a> Canali

- Vendite
- Margine
- Resi

### <a name="sales"></a>Vendite <a name="SalesPage"></a>

- Per ubicazione di consegna
- Per canale/negozio/terminale
- In base al dipendente
- Per data
- Per ora
- Per categoria prodotto

### <a name="margins"></a><a name="MarginsPage"></a> Margini

- Per ubicazione di consegna
- Sottoprodotto
- Per data

### <a name="returns"></a><a name="ReturnsPage"></a> Resi

- Reso per importo

    - In base a punto vendita
    - Sottoprodotto
    - Per data

- Reso per transazione

    - In base a punto vendita
    - Sottoprodotto
    - Per data

### <a name="discounts"></a><a name="DiscountsPage"></a> Sconti

- In base a punto vendita
- Sottoprodotto
- Per data
- Scomposizione

    - Persona giuridica
    - Punto vendita
    - Tipo di sconto
    - Nome sconto
    - Prodotto

### <a name="payments"></a><a name="PaymentsPage"></a> Pagamenti

- Per canale/terminale
- Per tipo/metodo di pagamento
- Per data
- Scomposizione

    - Persona giuridica
    - Tipo di canale
    - Punto vendita
    - Terminale
    - Metodo di pagamento

### <a name="customers"></a><a name="CustomersPage"></a> Clienti

- Valore di durata (LTV)

    LTV viene calcolato in base all'importo totale che un cliente spende in tutti i canali di vendita Dynamics 365 Commerce (inclusi POS, e-commerce e call center).

- Recency

    La recency viene calcolata in base al numero di giorni dall'ultimo coinvolgimento transazionale di un cliente con l'organizzazione. Attualmente, la recency non considera i segnali di coinvolgimento non transazionali, come l'attività di navigazione nell'e-commerce.

- Frequenza

    La frequenza viene calcolata in base al coinvolgimento transazionale di un cliente con l'organizzazione. Attualmente, la frequenza non considera i segnali di coinvolgimento non transazionali, come l'attività di navigazione nell'e-commerce.

- Durata relazione

    La durata della relazione viene calcolata in base al numero di giorni trascorsi dalla creazione del record del cliente nel sistema.

- Conteggio transazioni

### <a name="comparison"></a><a name="ComparisonPage"></a> Confronto

- Confronto prodotti per periodo di tempo

    - Vendite e differenza di vendita
    - Margine e differenza di margine

- Cliente per periodo di tempo

    - Vendite e differenza di vendita
    - Margine e differenza di margine

### <a name="web-activity"></a><a name="WebActivityPage"></a> Attività Web

#### <a name="top-level-filters"></a><a name="WebActivityTopLevelFilters"></a> Filtri di primo livello

- Intervallo di date
- Tipo di canale
- Canale
- Gerarchia di categorie

#### <a name="acquisitions"></a>Acquisizioni

- Visualizzazioni delle pagine

    - Per paese o area geografica
    - Sottoprodotto
    - Per stato di accesso dell'utente
    - Per data

- Ordini di e-commerce
- Tasso di conversione

    - Per data

- Grafico a imbuto di conversione

    - Visualizzazione della pagina per tipo di pagina (home page, pagina della categoria o pagina dei dettagli del prodotto)
    - Aggiungi al carrello
    - Pagamento
    - Acquisto

#### <a name="sessions"></a>Sessioni

Una sessione è un episodio della visita di un utente al tuo sito di e-commerce. Una sessione si considera conclusa dopo 30 minuti di inattività o 24 ore di utilizzo attivo.

- Per paese o area geografica
- Per origine (referente esterno)
- Per stato di accesso dell'utente
- Conteggio sessioni

    - Per data
    - Per pagina di ingresso

- Ordine per sessione

    - Per data

- Frequenza di rimbalzo della sessione

    Un rimbalzo di sessione è una sessione in cui un utente esce immediatamente dopo aver visitato il tuo sito di e-commerce. Per ulteriori informazioni, vedi [Frequenza di rimbalzo](https://en.wikipedia.org/wiki/Bounce_rate).

- Clic per sessione

#### <a name="visitors"></a>Visitatori

Un visitatore anonimo sul tuo sito di e-commerce viene identificato in modo univoco in base al browser specifico e allo specifico dispositivo che l'utente sta utilizzando. Analisi di Commerce non tiene traccia dei visitatori anonimi su browser o dispositivi diversi. Un visitatore anonimo che utilizza lo stesso browser sullo stesso dispositivo viene identificato in modo univoco in più sessioni utente, fino a quando i dati memorizzati nella cache del browser non vengono cancellati o non trascorre un periodo (in genere 12 mesi), a seconda dell'evento che si verifica prima.

Se i visitatori navigano nel tuo sito di e-commerce e hanno effettuato l'accesso, Analisi di Commerce può fornire ulteriori informazioni. Queste informazioni si basano sulla relazione esistente che la tua organizzazione ha con i visitatori a seguito dei loro precedenti acquisti in tutti i canali di vendita di Dynamics 365 Commerce (inclusi POS, e-commerce e call center). Le informazioni aggiuntive includono recency, durata della relazione, valore di durata e dati sulla frequenza.

- Margine deil visitatori
- Ordini medi dei visitatori
- Vendite medie dei visitatori
- Numero di visitatori di e-commerce

    - Per data
    - Per posizione

        Attualmente, Analisi di Commerce può fornire solo granularità a livello di paese/area geografica per le informazioni sulla posizione per i visitatori di e-commerce.

    - Per recency

        La recency viene calcolata in base al numero di giorni dall'ultimo coinvolgimento transazionale di un cliente con l'organizzazione. Attualmente, la recency non considera i segnali di coinvolgimento non transazionali, come l'attività di navigazione nell'e-commerce.

    - Per durata relazione

        La durata della relazione viene calcolata in base al numero di giorni trascorsi dalla creazione del record del cliente nel sistema.

    - Per valore di durata (LTV)

        LTV viene calcolato in base all'importo totale che un cliente spende in tutti i canali di vendita Dynamics 365 Commerce (inclusi POS, e-commerce e call center).

    - Per frequenza

        La frequenza viene calcolata in base al coinvolgimento transazionale di un cliente con l'organizzazione. Attualmente, la frequenza non considera i segnali di coinvolgimento non transazionali, come l'attività di navigazione nell'e-commerce.

#### <a name="impressions"></a>Impressioni

Un'impressione è una singola visualizzazione di un oggetto visivo prodotto da parte di un visitatore di e-commerce. Ad esempio, un visitatore di un e-commerce va alla home page del tuo sito di e-commerce e visualizza un prodotto di tappetino da yoga in modulo di elenco **I più venduti**. Il visitatore visualizza quindi lo stesso prodotto del tappetino da yoga in un modulo di elenco **Scelti per te**. In questo caso, ci sono due impressioni del prodotto. 

Attualmente, le impressioni vengono tracciate nelle seguenti visualizzazioni:

- Elenchi (ad esempio, **Elementi consigliati**, **I più venduti**, **Scelti per te**, e **Di tendenza**)
- Modulo carrello
- Contenitore dei risultati di ricerca
- Contenitore dei risultati di ricerca di categoria

Attualmente, i prodotti di cui viene eseguito il rendering in un modulo carosello o in oggetti visivi personalizzati non vengono conteggiati nelle metriche relative alle impressioni.

La pagina **Report impressioni** include le seguenti metriche:

- Conteggio impressioni

    - Per tipo di pagina e modulo

        Il tipo di pagina è il tipo generico di pagina definito per ogni pagina del tuo sito di e-commerce. Il tipo di modulo è il tipo di modulo oggetto visivo di e-commerce in cui viene mostrato il prodotto.

        Per visualizzare le impressioni per modulo, potrebbe essere necessario eseguire il drill-down nella pagina e negli oggetti visivi del modulo.

    - Sottoprodotto
    - Per stato di accesso dell'utente
    - Per data

- Conteggio clic impressioni

    Un clic sull'impressione si verifica quando un visitatore di un e-commerce seleziona un oggetto visivo del prodotto. In genere, il visitatore viene quindi indirizzato alla pagina dei dettagli del prodotto.

- Percentuale di clic impressioni (CTR)

    Il CTR viene calcolato come il numero totale di clic sulle impressioni diviso per il numero totale di impressioni.

## <a name="commerce-analytics-preview-installation"></a>Installazione di Analisi di Commerce (anteprima)

> [!NOTE]
> Analisi di Commerce (anteprima) è disponibile in anteprima nelle aree geografiche Stati Uniti, Canada, Regno Unito, Europa, Asia sud-orientale, Asia orientale, Australia e Giappone. Se il tuo ambiente Finance and Operations si trova in una di queste aree, puoi abilitare questa funzione nel tuo ambiente usando Microsoft Dynamics Lifecycle Services (LCS). Prima di poter utilizzare questa funzione, vedi [Configurare l'esportazione in Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Abilitare e configurare Analisi di Commerce (anteprima)

Per installare Analisi di Commerce (anteprima), è necessario disporre delle autorizzazioni per creare risorse in una sottoscrizione di Azure. È inoltre necessario disporre delle autorizzazioni per installare i componenti aggiuntivi in LCS. Ecco una panoramica dei passaggi.

1. [Invia il modulo di acquisizione in anteprima per Analisi di Commerce (anteprima)](#joinPreview).
2. [Abilita e configura l'esportazione in Data Lake](#enableExportToDataLake).
3. [Abilita e configura il componente aggiuntivo Analisi di Commerce (anteprima)](#enableCommerceAnalyticsAddin).
4. [Genera un token di firma di accesso condiviso (SAS) per il tuo account di archiviazione](#getSASToken).
5. [Scarica gli script di distribuzione per le visualizzazioni Azure Synapse](#downloadSynapseDeploymentScripts).
6. [Installa e configura Azure Synapse workspace](#configureAzureSynapse).
7. [Installa l'app modello Power BI](#powerbi).

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a>Inviare il modulo di acquisizione in anteprima per Analisi di Commerce (anteprima)

Invia il [modulo di acquisizione in anteprima per Analisi di Commerce (anteprima)](https://forms.office.com/r/vW5VLJGXZ2). Consenti fino a tre giorni lavorativi per l'elaborazione del modulo. Dopo l'elaborazione, verrà inviata un'e-mail di conferma all'indirizzo e-mail fornito nel modulo.

### <a name="enable-and-configure-export-to-data-lake"></a><a name="enableExportToDataLake"></a>Abilitare e configurare l'esportazione in Data Lake

Analisi di Commerce (anteprima) si basa sulla funzionalità Esporta in Data Lake per esportare i dati di Commerce HQ in Data Lake e mantenere i dati aggiornati. Prima di configurare Analisi di Commerce (anteprima), abilita e configura Esporta in Data Lake seguendo i passaggi in [Configurare l'esportazione in Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

Durante la configurazione di Esporta in Data Lake, prendi nota delle seguenti informazioni, perché dovrai inserirle in un secondo momento:

- <a name="keyVault"></a>Il nome DNS (Domain Name System) del key vault e i nomi dei segreti in cui vengono archiviati l'ID e il segreto dell'applicazione. Per ulteriori informazioni, vedi [Aggiungere segreti al Key Vault](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).
- <a name="storageAccount"></a>Il nome dell'account di archiviazione per l'istanza di Data Lake. Per ulteriori informazioni, vedi [Creare un account Data Lake Storage (Gen2) nella sottoscrizione](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription).

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Abilitare e configurare il componente aggiuntivo Analisi di Commerce (anteprima)

Per installare il componente aggiuntivo Analisi di Commerce (anteprima) in LCS, devi essere un amministratore in LCS dell'ambiente che intendi utilizzare.

Per installare e configurare il componente aggiuntivo Analisi di Commerce (anteprima) segui questi passaggi.

1. Accedi a [LCS](https://lcs.dynamics.com/), e vai nel tuo ambiente.
2. Nella pagina **Ambiente**, seleziona **Installa un nuovo componente aggiuntivo** nella scheda **Componenti aggiuntivi dell'ambiente**.
3. Nella finestra di dialogo, seleziona **Analisi di Commerce (anteprima)**.

    Se **Analisi di Commerce (anteprima)** non è elencato, assicurati di aver aderito al Programma Insider.

4. Nella finestra di dialogo **Configura componente aggiuntivo** immetti le seguenti informazioni.

    | Informazioni | Origine | Valore di esempio |
    |---|---|---|
    | ID tenant Azure AD per il tuo ambiente | Accedi al [Portale di Azure](https://portal.azure.com/), e apri il servizio **Azure Active Directory**. Quindi apri la pagina **Proprietà** e copia il valore nel campo **ID directory**. | 72f988bf-0000-0000-00000-2d7cd011db47 |
    | Nome DNS del Key Vault | Specifica il [nome DNS](#keyVault) del Key Vault. Avresti dovuto prendere nota di questo valore nella sezione precedente. | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Segreto che contiene l'ID applicazione | Inserisci il [nome del segreto che memorizza l'ID dell'applicazione](#keyVault). Avresti dovuto prendere nota di questo valore nella sezione precedente. | app-id |
    | Segreto che contiene il segreto applicazione | Inserisci il [nome del segreto che memorizza il segreto dell'applicazione](#keyVault). Avresti dovuto prendere nota di questo valore nella sezione precedente. | app-secret |

5. Accetta le condizioni dell'offerta selezionando la casella di controllo, quindi seleziona **Installa**.

    Il sistema installa e configura il componente aggiuntivo Analisi di Commerce (anteprima) per l'ambiente. Il processo può richiedere alcuni minuti. Dopo che è stato completato, **Analisi di Commerce (anteprima)** dovrebbe essere elencato nella pagina **Ambiente** e lo stato dovrebbe essere **Installato**.

### <a name="generate-a-sas-token-for-your-storage-account"></a><a name="getSASToken"></a>Generare un token SAS per l'account di archiviazione

Un token SAS consente alle entità esterne di accedere al tuo account di archiviazione e di disporre di un set specifico di privilegi per un periodo di tempo limitato. Azure Synapse utilizzerà il token SAS per accedere ai dati sottostanti in Data Lake.

> [!NOTE]
> A causa di una nota limitazione di Analisi di Commerce (anteprima), l'istanza Azure Synapse perderà l'accesso al data lake alla scadenza del token SAS. Pertanto, quando si genera il token SAS, è necessario impostare la data di scadenza massima consentita dai criteri di sicurezza dell'organizzazione.

Per generare un token SAS, segui questi passaggi.

1. Nel portale di Azure, vai all'[account di archiviazione](#storageAccount) che hai creato durante la configurazione di Esporta in Data Lake.
2. Nel riquadro sinistro, sotto l'account di archiviazione, seleziona **Firma ad accesso condiviso**.
3. Nella pagina **Opzioni SAS**, impostare i seguenti campi.

    | Campo | Valore |
    |---|---|
    | Servizi consentiti | Seleziona **BLOB**. |
    | Tipo di risorse consentite | Seleziona **Servizio**, **Contenitore**, e **Oggetto**. |
    | Autorizzazioni consentite | Seleziona **Lettura**, **Scrittura**, **Eliminazione**, **Elenco**, **Aggiunta**, e **Creazione**. |
    | Autorizzazioni per il controllo delle versioni dei BLOB | Seleziona **Abilita eliminazione delle versioni**. |
    | La data e l'ora di inizio e di scadenza | Imposta una data e un'ora di inizio e di fine per il token SAS come appropriato. |
    | Indirizzi IP consentiti | Lascia vuoto il campo. |
    | Protocolli consentiti | Seleziona **Solo HTTPS**. |
    | Livello di routing preferito | Seleziona **Di base (predefinito)**. |
    | Chiave di firma | Seleziona **chiave1** o **chiave2**, a seconda dei casi. |

4. Seleziona **Genera SAS e stringa di connessione**.
5. Copia il valore nel campo **Token SAS** e incollarlo in un editor di testo come Blocco note.

### <a name="download-the-deployment-scripts-for-azure-synapse-views"></a><a name="downloadSynapseDeploymentScripts"></a>Scaricare gli script di distribuzione per le visualizzazioni Azure Synapse

Per creare e pubblicare le viste richieste in Azure Synapse workspace è necessario eseguire una serie di script. Segui i passaggi seguenti per scaricare gli script.

1. Su GitHub, vai nel repository (repo) [Microsoft/Dynamics365Commerce.Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions).
2. Scarica gli script sul tuo computer locale clonando il repository o scaricandolo come file zip.

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Installare e configurare Azure Synapse workspace

Per installare e configurare Azure Synapse workspace segui questi passaggi.

1. Installa Azure Synapse workspace nella tua sottoscrizione di Azure. Per ulteriori informazioni, vedi [Avvio rapido: Creare Synapse workspace](/azure/synapse-analytics/quickstart-create-workspace).
2. Nel Blocco note o in un altro editor di testo, apri il file script **SetupSynapse.sql** dalla cartella sul computer locale in cui hai clonato o scaricato il repository Dynamics365Commerce.Solutions nella sezione precedente. Il file di script si troverà nella cartella /Pipeline/CommerceAnalyticsSynapse/. Nello script, sostituisci il testo segnaposto con i valori come mostrato nella tabella seguente.

    | Testo segnaposto | Valore di sostituzione |
    |---|---|
    | placeholder_storageaccount | Il nome dell'[account di archiviazione](#storageAccount) che hai creato durante la configurazione di Esporta in Data Lake. |
    | <a name="phContainer"></a>placeholder_container | Il nome del contenitore di archiviazione creato nell'istanza di Data Lake dopo aver installato correttamente il componente aggiuntivo Esporta in Data Lake in LCS. Per ottenere il nome del contenitore, è necessario usare Esplora archiviazione nel portale di Azure per esplorare l'account di archiviazione. |
    | placeholder_sastoken | Il [Token SAS](#getSASToken) che hai generato. Assicurati di rimuovere il punto interrogativo (**?**) dall'inizio del valore del token SAS. |
    | <a name="phUserPwd"></a>placeholder_password | Una password sicura a tua scelta. Prendi nota della password. Verrà impostata come password per il nuovo account **reportreadonlyuser** creato dallo script. **Non** immettere la password dell'account **sqladminuser**. |

3. Copia il contenuto aggiornato del file di script.
4. Nel portale di Azure, vai alla nuova Azure Synapse workspace. Nella pagina **Panoramica** seleziona **Apri Synapse Studio**.
5. In Synapse Studio, seleziona **Nuovo \> Script SQL** e incolla il contenuto del file di script nell'editor di script SQL.
6. Assicurati che il campo **Usa database** sia impostato su **master**.
7. Seleziona **Esegui** e attendi che lo script termini l'esecuzione. La corretta esecuzione dello script creerà il database per Analisi di Commerce, le credenziali per l'accesso al data lake e un account utente di sola lettura che Power BI utilizzerà per connettersi all'istanza Azure Synapse.
8. Sul computer locale, apri Windows PowerShell in modalità amministratore e vai alla cartella /Pipeline/CommerceAnalyticsSynapse/ nella cartella in cui hai clonato o scaricato il repository Dynamics365Commerce.Solutions.
9. Configura i criteri di esecuzione di Windows PowerShell eseguendo il comando seguente.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
    ```

10. Se il modulo SQL Server PowerShell non è già installato, installalo eseguendo il comando seguente.

    ```powershell
    Install-Module sqlserver
    ```

    > [!NOTE]
    > Durante l'installazione del modulo, potrebbe essere richiesto di installare il provider NuGet. In questo caso, seleziona **S** per installare il provider NuGet. Potrebbe anche esserti richiesto di confermare che stai reinstallando i moduli da un repository non attendibile. In questo caso, seleziona **S** per continuare l'installazione. È possibile eseguire facoltativamente il cmdlet **Set-PSRepository** rendere attendibile il repository **PSGallery**.

11. Pubblica le visualizzazioni Azure Synapse eseguendo il comando seguente.

    ```powershell
    .\PublishSynapseViews.ps1 -serverName SERVER_NAME -password PASSWORD -storageAccount STORAGE_ACCOUNT -containerName CONTAINER_NAME -datarootpath DATA_ROOT_PATH
    ```

    Quando esegui questo comando, sostituisci il segnaposto con i valori come mostrato nella tabella seguente.

    | Valore segnaposto | Valore di sostituzione |
    |---|---|
    | SERVER_NAME | Nome dell'endpoint di Azure Synapse Serverless SQL. Puoi ottenere questo valore dalla pagina **Panoramica** di  Azure Synapse workspace nel portale di Azure. |
    | PASSWORD | La password per l'account **sqladminuser**. |
    | STORAGE_ACCOUNT | Il nome dell'account di archiviazione per Data Lake. |
    | CONTAINER_NAME | Il nome del contenitore creato dalla funzionalità Esporta in Data Lake. Questo contenitore è lo stesso contenitore che hai specificato come valore di [placeholder_container](#phContainer) al passaggio 2. |
    | DATA_ROOT_PATH | Il nome della cartella sotto il contenitore che contiene tutti i dati. |

    > [!NOTE]
    > È possibile trovare il nome dell'account di archiviazione, il nome del contenitore e il percorso della radice dei dati usando il browser Archiviazione di Azure e l'account di archiviazione di Data Lake nel portale di Azure.

12. Attendi che lo script termini l'esecuzione. La corretta esecuzione dello script creerà viste SQL nell'istanza Azure Synapse Serverless SQL.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Installare l'app modello Power BI

Per installare l'app modello Power BI per Analisi di Commerce (anteprima) segui questi passaggi.

1. Accedi al [portale Power BI](https://powerbi.microsoft.com/) utilizzando l'ID dell'organizzazione.
2. Installa l'app modello Power BI di Analisi di Commerce (anteprima) andando in [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Potresti ricevere un avviso che indica che l'app non è elencata in AppSource. Seleziona **Installa**.
3. Se stai installando l'app per la prima volta, vai al passaggio 5. Se hai già installato questa app, vengono visualizzate le seguenti opzioni per l'aggiornamento dell'app:

    - **Aggiorna l'area di lavoro e l'app** – Aggiorna l'app modello esistente e sovrascrivi le impostazioni dell'app esistenti, come il nome dell'istanza dell'app e le configurazioni delle autorizzazioni.
    - **Aggiorna solo il contenuto dell'area di lavoro senza aggiornare l'app** – Aggiorna l'app modello esistente, ma mantieni le impostazioni dell'app esistente. *Questa opzione è consigliata per gli aggiornamenti delle app.*
    - **Installa un'altra copia dell'app in una nuova area di lavoro** – Crea una nuova area di lavoro, quindi crea una copia dell'app modello esistente al suo interno. L'area di lavoro esistente verrà lasciata intatta.

4. Seleziona una delle opzioni di aggiornamento, quindi seleziona **Installa**.
5. Apri l'app installata selezionando **App** nel riquadro di sinistra e quindi seleziona l'app.
6. Connetti l'app alla tua origine dati selezionando **Connetti**. Se hai già installato l'app, seleziona il collegamento **Connetti i tuoi dati** nella barra dei messaggi gialla.
7. Impostare i seguenti campi.

    | Campo | Valore |
    |---|---|
    | Server | Inserisci il nome dell'endpoint Azure Synapse Serverless SQL creato nella sezione precedente. Puoi ottenere questo valore dalla pagina **Panoramica** di  Azure Synapse workspace nel portale di Azure. |
    | Database | Immetti **CommerceAnalytics**. |
    | Lingua | Seleziona un valore nell'elenco. Questo campo viene utilizzato per i nomi di prodotti e categorie localizzati. Il valore fa distinzione tra maiuscole e minuscole. |
    | Intervallo di date | Seleziona un valore nell'elenco. I dati per il numero di mesi selezionato verranno importati nel set di dati Power BI. Il valore selezionato influisce sulla dimensione del set di dati e sul tempo necessario per la sincronizzazione. |

8. Selezionare **Avanti**. Viene richiesto di inserire le credenziali per la connessione al database SQL Azure Synapse. Imposta i campi come descritto nella tabella seguente.

    | Campo | Valore |
    |---|---|
    | Metodo di autenticazione | Seleziona **Di base**. |
    | Nome utente | Immetti **reportreadonlyuser**. |
    | Password | Inserisci il valore con cui hai sostituito il segnaposto [placeholder_password](#phUserPwd) nello script SetupSynapse.sql. Questa password è la password per l'account **reportreadonlyuser**. |

9. Seleziona **Accedi e connetti**.
10. Attendi fino a quando il set di dati non viene aggiornato correttamente. Quindi seleziona il pulsante **Modifica app** per aprire l'area di lavoro dell'app, dove è possibile visualizzare lo stato di aggiornamento del set di dati. Nell'area di lavoro dell'app, puoi anche configurare facoltativamente pianificazioni di aggiornamento automatico per il tuo set di dati, gestire le autorizzazioni e rinominare l'istanza dell'app.

### <a name="privacy"></a><a name="privacy"></a>Privacy

La privacy è molto importante. Per ulteriori informazioni, leggere l'[Informativa sulla privacy](https://go.microsoft.com/fwlink/?LinkId=521839) di Microsoft.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
