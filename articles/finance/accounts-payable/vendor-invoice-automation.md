---
title: Automazione delle fatture per i documenti digitalizzati
description: In questo articolo vengono illustrate le funzionalità disponibili per l'automazione completa delle fatture fornitore, anche delle fatture che includono allegati.
author: abruer
ms.date: 03/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0449a13989bad45cf0456a2678e5724036d2af3d
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070696"
---
# <a name="invoice-automation-for-scanned-documents"></a>Automazione delle fatture per i documenti digitalizzati

[!include [banner](../includes/banner.md)]

In questo articolo vengono illustrate le entità di dati disponibili per l'automazione completa delle fatture fornitore, tra cui le fatture che includono allegati.

Le organizzazioni che desiderano semplificare i processi di contabilità fornitori (AP) spesso identificano l'elaborazione delle fatture come una delle principali aree in cui dovrebbero essere più efficienti. In molti casi, queste organizzazioni scaricano l'elaborazione delle fatture cartacee a un provider di servizi OCR di terze parti. Ricevono poi i metadati della fattura leggibile a computer insieme a un'immagine digitalizzata di ogni fattura. Per agevolare l'automazione, viene integrata "una soluzione nella fase finale" per consentire l'utilizzo di questi elementi nel sistema di fatturazione. Ora questa fase finale automatizzata è abilitata come soluzione predefinita, attraverso una soluzione di automazione delle fatture.

## <a name="solution-context"></a>Contesto della soluzione

La soluzione di automazione delle fatture è un'interfaccia standard in grado di accettare i metadati della fattura per l'intestazione e le righe della fattura e anche gli allegati che sono associabili alla fattura. Un sistema esterno che genera gli elementi conformi a questa interfaccia può inviare il feed per l'elaborazione automatica di fatture e allegati.

Nella figura seguente è illustrato uno scenario di integrazione di esempio in cui Contoso è associato a un provider di servizi OCR per l'elaborazione delle fatture fornitore. I fornitori di Contoso inviano le fatture al provider di servizi tramite posta elettronica. Tramite l'elaborazione OCR, il provider di servizi genera i metadati della fattura (intestazione e/o righe) e un'immagine digitalizzata della fattura. Un livello di integrazione trasforma quindi questi elementi in modo che siano utilizzabili.

![Scenario di integrazione di esempio.](media/vendor_invoice_automation_01.png)

Più variazioni dello scenario precedente sono possibili se è richiesta l'integrazione delle fatture. La migrazione dei dati è un altro caso di utilizzo in cui questa interfaccia può essere utilizzata per creare fatture e allegati.

### <a name="solution-components"></a>Componenti della soluzione

L'impronta della soluzione è costituita dai seguenti componenti:

+ Entità di dati per l'intestazione della fattura, le righe di fattura e gli allegati
+ Elaborazione delle eccezione per le fatture
+ Visualizzatore degli allegati parallelo nelle fatture

Il resto di questo articolo fornisce descrizioni dettagliate di questi componenti della soluzione.

## <a name="data-entities"></a>Entità di dati

Un pacchetto dati è l'unità di lavoro che deve essere inviata, in modo che le intestazioni delle fatture, le righe di fattura e gli allegati fatture possono essere creati. Le seguenti entità dati vengono utilizzate per gli elementi che costituiscono il pacchetto dati:

+ Intestazione fattura fornitore
+ Riga fattura fornitore
+ Allegato del documento fattura fornitore

L'allegato documento della fattura fornitore è una nuova entità dati che è introdotta come parte di questa funzionalità. L'entità intestazione della fattura fornitore è stata modificata in modo che supporti gli allegati. L'entità riga fattura fornitore non è stata modificata per questa funzionalità.

Per informazioni dettagliate sui pacchetti di dati, vedi [Panoramica sulla gestione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md). Per informazioni su come creare pacchetti di dati utilizzando l'area di lavoro di gestione dei dati, vedi [Elaborare e consumare pacchetti di dati nella soluzione per le app Dynamics 365 per la finanza e le operazioni](../../fin-ops-core/dev-itpro/lcs-solutions/process-data-packages-lcs-solutions.md).

Per generare rapidamente i dati di test che includono fatture e allegati, effettuare le seguenti operazioni.

1. Accedere all'istanza.
1. Andare a **Contabilità fornitori** > **Fatture** > **Fatture fornitore in sospeso**.
1. Creare fatture con righe e allegati.

    > [!NOTE]
    > Gli allegati devono essere allegati di intestazione. Attualmente, l'entità allegato documento di fattura fornitore non supporta gli allegati alle righe.

1. Aprire l'area di lavoro **Gestione dei dati**.
1. Creare un processo di esportazione che include entità allegati documento di intestazione della fattura fornitore, di una riga fattura fornitore e della fattura fornitore.
1. Esportare i dati.
1. Scaricare i dati esportati come pacchetto. È possibile a questo punto utilizzare il pacchetto per importare i dati nelle istanze di destinazione a scopo di test.

### <a name="determining-the-legal-entity-for-an-invoice"></a>Determinazione della persona giuridica per una fattura

Le fatture che vengono importate tramite il pacchetto dati possono essere associate alla persona giuridica a cui appartengono in due modi:

+ Il processo di importazione che elabora la fattura la importa nella stessa azienda in cui il processo è stato programmato nell'area di lavoro **Gestione dati**. In altre parole, l'azienda del processo determina l'azienda a cui appartiene la fattura.
+ Quando il pacchetto dati che contiene le fatture viene inviato a Finance, il chiamante (vale a dire l'applicazione di integrazione che viene eseguita al di fuori di Finance) può menzionare in modo esplicito l'ID dell'azienda nella richiesta HTTP. In questo caso, il contesto dell'azienda nella quale il processo di elaborazione viene eseguito in Finance viene ignorato e le fatture vengono importate nell'azienda che è stata passata tramite la richiesta HTTP.

> [!NOTE]
> Questo comportamento è un comportamento di gestione dei dati standard. È stato spiegato in questa sede, nel contesto delle fatture, solo a titolo di completezza.

## <a name="exception-processing"></a>Elaborazione delle eccezioni

Negli scenari in cui le fatture fornitore vengono immesse in finanza e operazioni tramite l'integrazione, è necessario fornire al membro del team della contabilità fornitori un modo facile per elaborare le eccezioni o fatture non riuscite e creare fatture in sospeso relative alle fatture non riuscite. Questa elaborazione delle eccezioni per le fatture fornitori è ora parte della soluzione per la finanza e le operazioni.

### <a name="vendor-invoices-that-failed-to-import-list-page"></a>Fatture fornitore che non sono riuscite a importare la pagina elenco

La nuova pagina elenco delle fatture fornitori è disponibile in **Contabilità fornitori** > **Fatture** > **Errori di importazione** > **Fatture fornitore non importate**. Questa pagina visualizza tutti i record di intestazione delle fatture fornitore dalla tabella di gestione temporanea dell'entità dati intestazione della fattura fornitore. Tieni presente che puoi visualizzare gli stessi record dall'area di lavoro **Gestione dati**. Puoi eseguire le stesse azioni che sono fornite nella funzionalità di gestione delle eccezioni dall'area di lavoro **Gestione dati**. La funzionalità di gestione delle eccezioni è stata ottimizzata per un utente funzionale, il che ne semplifica l'utilizzo.

![Pagina elenco delle eccezioni.](media/vendor_invoice_automation_02.png)

Questa pagina elenco include i seguenti campi forniti tramite feed:

+ **Società** - La società a cui appartiene la fattura
+ **Messaggio di errore** - Il messaggio di errore che il framework di gestione dati emette per spiegare perché non è stato possibile creare la fattura
+ **Numero** - Il numero di fattura
+ **Conto fattura**
+ **Nome** - Il nome del fornitore
+ **Conto fornitore**
+ **Ordine fornitore** - Numero di ordine fornitore per la fattura
+ **Data di registrazione**
+ **Data fattura**
+ **Descrizione fattura**
+ **Valuta**
+ **Registro**
+ **Riferimento righe** - L'identificatore che deriva dal sistema esterno

    > [!NOTE]
    > Il riferimento righe non è l'ID fattura.

Questa pagina elenco presenta anche un riquadro di anteprima che è possibile utilizzare nei seguenti modi:

+ Per visualizzare l'intero messaggio di errore, in modo che non sia necessario espandere la colonna **Messaggio di errore** della griglia.

La pagina elenco supporta le seguenti azioni:

+ **Modifica** - Aprire il record di eccezione in modalità di modifica, in modo da poter correggere gli errori.
+ **Opzioni** - Accedere alle opzioni standard disponibili nelle pagine elenco. È possibile utilizzare l'opzione **Aggiungi ad area di lavoro** per appuntare la pagina elenco delle eccezioni sull'area di lavoro come elenco o riquadro.

### <a name="vendor-invoices-that-failed-to-import-details-page"></a>Fatture fornitore che non sono riuscite a importare la pagina dettagli

Quando si avvia la modalità di modifica, viene visualizzata la pagina **Fatture fornitore che non sono riuscite a importare i dettagli** per la fattura con problemi. Se ci sono problemi con una fattura che ha un allegato, l'allegato non verrà visualizzato. L'allegato deve essere riallegato alla fattura.

La pagina **Fatture fornitore che non sono riuscite a importare i dettagli** ti consente di creare una fattura in sospeso. Dopo aver corretto i problemi in una fattura come parte del processo di gestione delle eccezioni, seleziona il pulsante **Crea fattura in sospeso** per creare la fattura in sospeso. La fattura in sospeso verrà creata in background. 

### <a name="shared-service-vs-organization-based-exception-processing"></a>Elaborazione delle eccezioni basata sull'organizzazione rispetto al servizio condiviso

La pagina elenco delle eccezioni supporta i costrutti di sicurezza standard che l'area di lavoro **Gestione dati** supporta per l'elaborazione dei record di gestione temporanea. Il processo di importazione della fattura può essere protetto nei seguenti modi:

+ Per ruolo utente
+ Per utente
+ In base all'entità giuridica

![Importare il processo che viene protetto per ruolo utente e per persona giuridica.](media/vendor_invoice_automation_04.png)

Se viene configurata la sicurezza per il processo di importazione della fattura, la pagina elenco delle eccezioni rispetta queste impostazioni. Gli utenti potranno vedere solo i record delle eccezioni fatture che questa impostazione consente loro di visualizzare.

Ad esempio, Contoso ha deciso di elaborare le eccezioni fatture per persona giuridica. Di conseguenza, la sicurezza è configurata nel processo di importazione delle fatture in modo tale che un utente nella persona giuridica A possa visualizzare solo le eccezioni fatture della persona giuridica A, mentre un utente nella persona giuridica B può visualizzare solo le eccezioni di fattura della persona giuridica B. Questa impostazione consente la separazione dei compiti per la gestione delle eccezioni fatture.

Contoso può inoltre scegliere di non applicare alcuna protezione e in questo caso gli stessi utenti possono elaborare le eccezioni fatture per tutte le persone giuridiche. Questa impostazione consente uno scenario di servizi condiviso per la gestione delle eccezioni fatture.

## <a name="side-by-side-attachment-viewer"></a>Visualizzatore degli allegati parallelo nelle fatture

Per agevolare la visualizzazione degli allegati delle fatture fornitori, le pagine seguenti che vengono utilizzate nel processo di fatturazione includono ora un visualizzatore di allegati:

+ **Gestione delle eccezioni**
+ Pagina **Fatture fornitore in sospeso** (disponibile anche nel processo di revisione della fattura)
+ Pagina di richiesta **Giornale di registrazione fatture** (per le fatture registrate)

Ecco la funzionalità principale del visualizzatore di allegati:

+ Visualizzare tutti i tipi di allegati che Gestione documenti supporta (file, immagini, URL e note).
+ Visualizzare file TIFF a più pagine.
+ Effettuare le seguenti azioni sui file di immagine:
  + Evidenziare parti dell'immagine.
  + Bloccare parti dell'immagine.
  + Aggiungere annotazioni all'immagine.
  + Applicare lo zoom avanti e lo zoom indietro all'immagine.
  + Effettuare una panoramica dell'immagine.
  + Annullare e ripetere le azioni.
  + Adattare le dimensioni dell'immagine.

> [!NOTE]
> Queste azioni sono disponibili solo per i file di immagine (JPEG, TIFF, PNG e così via). Eventuali modifiche apportate a un'immagine utilizzando queste azioni vengono salvate nel file di immagine. Attualmente, il visualizzatore di allegati non include funzionalità di controllo versioni o di controllo.

### <a name="default-attachment"></a>Allegato predefinito

Se una fattura fornitore contiene più di un allegato, è possibile impostare uno dei documenti come allegato predefinito nella pagina **Allegati**. L'opzione **Allegato predefinito** è una nuova opzione che è stata aggiunta come parte di questa funzionalità. Questa opzione è inoltre esposta nell'entità dati allegato del documento della fattura fornitore. Di conseguenza, l'allegato predefinito può essere impostato attraverso le integrazioni.

È possibile impostare come allegato predefinito un solo documento. Una volta impostato un documento come allegato predefinito, questo viene visualizzato automaticamente nel visualizzatore di allegati quando viene aperta la fattura. Se non si imposta un documento come allegato predefinito, il visualizzatore non mostra automaticamente alcun allegato quando viene aperta la fattura.

### <a name="showhide-invoice-attachments"></a>Mostrare/nascondere gli allegati delle fatture

Un nuovo pulsante disponibile nelle pagina di richiesta **Elaborazione delle eccezioni**, **Fattura in sospeso** e **Giornale di registrazione fatture** consente di mostrare o nascondere il visualizzatore di allegati.

## <a name="security"></a>Sicurezza

Le azioni seguenti nel visualizzatore allegati sono controllate tramite la sicurezza basata sui ruoli:

+ Evidenziazione
+ Blocco
+ Annotazione

### <a name="pending-vendor-invoices-page"></a>Pagina Fatture fornitore in sospeso

I privilegi seguenti forniscono l'accesso in sola lettura o l'accesso in lettura/scrittura al visualizzatore di allegati per le azioni di evidenziazione, blocco e annotazione:

+ **Gestisci immagine fattura fornitore** - Questo privilegio consente di accedere in lettura/scrittura.
+ **Visualizza immagine fattura fornitore** - Questo privilegio consente di accedere solo in lettura.

I compiti seguenti forniscono l'accesso in sola lettura o l'accesso in lettura/scrittura al visualizzatore di allegati per le seguenti azioni:

+ **Gestisci fatture fornitore** - Il privilegio Gestisci immagine fattura fornitore viene assegnato a questo compito.
+ **Richiedi informazioni sullo stato delle fatture fornitore** - Il privilegio Visualizza immagine fattura fornitore viene assegnato a questo compito.

I ruoli seguenti forniscono l'accesso in sola lettura o l'accesso in lettura/scrittura al visualizzatore di allegati per le seguenti azioni:

+ **Addetto contabilità fornitori** e **Responsabile contabilità fornitori** - Il compito Gestisci fatture fornitore viene assegnato a questi ruoli.
+ **Addetto contabilità fornitori**, **Responsabile contabilità fornitori**, **Addetto pagamenti centralizzati contabilità fornitori** e **Addetto pagamenti contabilità fornitori** - Il compito Richiedi informazioni sullo stato delle fatture fornitore viene assegnato a questi ruoli.

### <a name="vendor-invoice-attachment"></a>Allegato della fattura fornitore

I privilegi seguenti forniscono l'accesso in sola lettura o l'accesso in lettura/scrittura al visualizzatore di allegati per le azioni di evidenziazione, blocco e annotazione.

> [!NOTE]
> Come predefinito, i ruoli menzionati in questa sezione forniscono l'accesso in sola lettura alle immagini delle fatture nel visualizzatore di allegati. Se un ruolo deve disporre anche dell'accesso di scrittura alle immagini, è possibile concedere l'accesso di scrittura a tale ruolo utilizzando il privilegio e il compito descritti in questa sezione.

+ **Gestisci immagine entità intestazione fattura fornitore** - Questo privilegio fornisce l'accesso in lettura/scrittura alle immagini delle fatture nel visualizzatore di allegati.
+ **Visualizza immagine entità intestazione fattura fornitore** - Questo privilegio fornisce l'accesso solo in lettura all'immagine della fattura nel visualizzatore di allegati.

I compiti seguenti forniscono l'accesso in sola lettura al visualizzatore di allegati per le seguenti azioni:

+ **Gestisci fatture fornitore** - Il privilegio Gestisci immagine entità intestazione fattura fornitore viene assegnato a questo compito.

I ruoli seguenti forniscono l'accesso in sola lettura al visualizzatore di allegati per le seguenti azioni:

+ **Addetto contabilità fornitori** e **Responsabile contabilità fornitori** - Il compito Gestisci fatture fornitore viene assegnato a questi ruoli.

Per impostazione predefinita, se il ruolo utente fornisce i diritti di modifica in una pagina qualsiasi, l'utente avrà diritti di modifica anche nel visualizzatore di allegati per le azioni di evidenziazione, blocco e annotazione. Tuttavia, se vi sono scenari in cui un ruolo specifico deve avere diritti di modifica nella pagina ma non nel visualizzatore di allegati, è possibile utilizzare i privilegi appropriati dall'elenco precedente per soddisfare il caso di utilizzo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

