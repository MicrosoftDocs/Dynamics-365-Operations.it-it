---
title: Funzionalità della piattaforma rimosse o deprecate
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione dagli aggiornamenti della piattaforma per le app Finance and Operations.
author: sericks007
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 435f7f0090ca16a9e8cfee2d1ceb65bec8457d09
ms.sourcegitcommit: eff3da7ea98758f100d44ff7feec17157afc2e80
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111726"
---
# <a name="removed-or-deprecated-platform-features"></a>Funzionalità della piattaforma rimosse o deprecate

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione dagli aggiornamenti della piattaforma per le app Finance and Operations.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione. 

Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](/dynamics/s-e/global/axtechrefrep_61). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.

## <a name="feature-deprecation-notice-effective-may-2021"></a>Avviso di ritiro delle funzionalità in vigore da maggio 2021

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>Portale di globalizzazione in Lifecycle Services (LCS).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Stiamo deprecando il portale di globalizzazione in LCS poiché questa funzione è stata sostituita da altri servizi basati su LCS. |
| **Sostituita da un'altra funzionalità?**   | Sì, questa funzionalità è stata sostituita da [Ricerca argomento](../lifecycle-services/issue-search-lcs.md) di LCS e il [Servizio di invio di avvisi normativi di Dynamics](../lcs-solutions/submit-localization-alerts.md). |
| **Aree del prodotto interessate**         | Portale di globalizzazione in LCS|
| **Opzione di distribuzione**              | Distribuzione cloud |
| **Stato**                         | Deprecato: data di rimozione pianificata maggio 2022. |


## <a name="feature-removed-effective-january-28-2021"></a>Funzionalità rimossa a partire dal 28 gennaio 2021

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>Processo batch per la gestione della deframmentazione dell'indice SQL

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Per ridurre il sovraccarico di funzionamento, monitoraggio e manutenzione della gestione dell'indice da parte dei clienti, questa funzione è stata rimossa. |
| **Sostituita da un'altra funzionalità?**   | In futuro, la manutenzione dell'indice verrà eseguita dai servizi Microsoft. Ciò avverrà continuamente senza influire sui carichi di lavoro dell'utente. |
| **Aree del prodotto interessate**         | App di Finance and Operations|
| **Opzione di distribuzione**              | Distribuzione nel cloud: interessa gli ambienti di produzione gestiti da Microsoft e gli ambienti sandbox da Livello 2 a Livello 5. |
| **Stato**                         | Questa funzionalità è stata rimossa. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per la versione 10.0.17 delle app Finance and Operations


### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Per supportare le ultime versioni di Visual Studio, è necessario apportare alcune modifiche alle estensioni X++ per Visual Studio. Queste modifiche sono incompatibili con Visual Studio 2015. |
| **Sostituita da un'altra funzionalità?**   | Visual Studio 2017 sostituirà Visual Studio 2015 come versione distribuita e richiesta. |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecata: dopo l'aggiornamento, i precedenti strumenti X ++ verranno rimossi da Visual Studio 2015 e gli strumenti aggiornati non verranno installati su Visual Studio 2015. Non vi è alcun impatto sulle build ospitate. Per la compilazione di macchine virtuali, la pipeline di compilazione (definizione di compilazione) deve essere aggiornata manualmente per modificare la dipendenza da MSBuild 14.0 (Visual Studio 2015) a MSBuild 15.0 (Visual Studio 2017) come descritto in [Aggiornare una pipeline legacy in Azure Pipelines](../dev-tools/pipeline-msbuild-update.md). |

### <a name="user-avatar"></a>Avatar utente 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | L'avatar dell'utente visualizzato sul lato destro della barra di spostamento è stato recuperato utilizzando un'API dal controllo dell'intestazione di Dynamics 365, che è stato deprecato. |
| **Sostituita da un'altra funzionalità?**   | Gli utenti vedranno invece le loro iniziali in un cerchio nella barra di spostamento. Questa è la stessa immagine attualmente utilizzata sulle macchine di sviluppo. |
| **Aree del prodotto interessate**         | Client Web |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Rimosso a partire dalla versione 10.0.17 |

### <a name="enterprise-portal-ep-deprecation"></a>Ritiro di Enterprise Portal (EP)  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Gli artefatti dei metadati associati a Dynamics AX 2012 Enterprise Portal (EP) sono stati deprecati, poiché EP non è mai stato supportato nelle app Finance and Operations. |
| **Sostituita da un'altra funzionalità?**   | Nessuno |
| **Aree del prodotto interessate**         | Client Web |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecata: tutto il codice EP dovrebbe essere rimosso nella versione di ottobre 2021. |

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per la versione 10.0.15 delle app Finance and Operations

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Il supporto di Internet Explorer 11 per Dynamics 365 è deprecato

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | A partire da dicembre 2020, il supporto di Microsoft Internet Explorer 11 per tutti i prodotti Dynamics 365 è deprecato e Internet Explorer 11 non sarà supportato dopo agosto 2021.<br><br>Ciò avrà un impatto sui clienti che utilizzano prodotti Dynamics 365 progettati per essere utilizzati tramite un'interfaccia Internet Explorer 11. Dopo agosto 2021, Internet Explorer 11 non sarà supportato per questi prodotti Dynamics 365. |
| **Sostituita da un'altra funzionalità?**   | Consigliamo ai clienti di passare a Microsoft Edge.|
| **Aree del prodotto interessate**         | Tutti i prodotti Dynamics 365 |
| **Opzione di distribuzione**              | Tutti|
| **Stato**                         | Deprecata: Internet Explorer 11 non sarà supportato dopo agosto 2021.|


### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Componente aggiuntivo di Visual Studio per applicare gli hotfix dei metadati

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Gli hotfix dei metadati non sono più supportati con gli aggiornamenti del servizio [One version](../../fin-ops/get-started/one-version.md) introdotti a luglio 2018 con la versione 8.1. |
| **Sostituita da un'altra funzionalità?**   | I singoli hotfix dei metadati non sono disponibili per le versioni supportate. Al loro posto vengono applicati aggiornamenti di qualità cumulativi. |
| **Aree del prodotto interessate**         | Componenti aggiuntivi di Visual Studio |
| **Opzione di distribuzione**              | Macchine virtuali di sviluppo |
| **Stato**                         | Con la versione 10.0.15, il componente aggiuntivo non è più incluso negli strumenti di Visual Studio. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per la versione 10.0.14 delle app Finance and Operations

### <a name="online-users-page"></a>Pagina Utenti in linea 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questa è una pagina legacy creata per la precedente architettura client/server. Le informazioni in questa pagina non sono sempre accurate, generando confusione e informazioni fuorvianti. |
| **Sostituita da un'altra funzionalità?**   | Verrà fornita una nuova pagina in un futuro aggiornamento.|
| **Aree del prodotto interessate**         | Amministrazione sistema |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Entro ottobre 2021 questo modulo verrà rimosso.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per la versione 10.0.13 delle app Finance and Operations


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Codice personalizzato definito nelle proprietà del report SSRS 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | In generale, il codice personalizzato offre vantaggi limitati e, allo stesso tempo, richiede risorse significative ed elaborazione per il supporto. Il codice personalizzato viene utilizzato principalmente dagli autori di report per chiamare metodi pubblici da un assembly di codice personalizzato. Tuttavia, il servizio ospitato nel cloud non supporta i riferimenti ad assembly personalizzati per i report SSRS. |
| **Sostituita da un'altra funzionalità?**   | Gli autori dei report possono scegliere di continuare a fare riferimento ad API .NET pubbliche per operazioni di matematica, conversione e formattazione da qualsiasi espressione della casella di testo. Per ulteriori informazioni, vedere [Aggiungere codice a un report (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs?view=sql-server-ver15).  |
| **Aree del prodotto interessate**         | Sottoinsieme di progetti di report dell'applicazione definiti in RDL che contengono codice personalizzato. |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Con la versione 10.0.13, il compilatore inizierà a emettere un avviso per le istanze in cui viene rilevato codice personalizzato in una definizione di report SSRS. Per risolvere il problema, aprire la definizione di progettazione del report e rimuovere tutti gli elementi di codice personalizzati. Questo avviso verrà sostituito con un errore del compilatore in un aggiornamento futuro.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Aggiornamento di tre librerie dei componenti jQuery 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Tre librerie dei componenti jQuery sono in fase di aggiornamento per le correzioni di sicurezza e per mantenere la valuta.   
| **Sostituita da un'altra funzionalità?**   | Sono interessate le seguenti librerie: jQuery (alla versione 3.5.0 dalla versione 2.1.4) interfaccia utente jQuery (alla versione 1.12.1 dalla versione 1.11.4) jQuery qTip (alla versione 3.0.3 da 2.2.1). La guida alla migrazione è stata fornita online da jQuery.  |
| **Aree del prodotto interessate**         | Controlli estensibili, in particolare codice JavaScript personalizzato che utilizza API obsolete o rimosse |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Con la versione 10.0.13/Aggiornamento della piattaforma 37, i clienti possono facoltativamente passare alle librerie più recenti abilitando la funzione "Aggiorna tre librerie dei componenti jQuery". Il passaggio alle nuove librerie sarà obbligatorio con la versione di aprile 2021 per consentire il tempo necessario per la migrazione delle API interessate.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>API controllo griglia/forceLegacyGrid() esistente

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il controllo griglia esistente viene sostituito dal nuovo controllo griglia. |
| **Sostituita da un'altra funzionalità?**   | Il [nuovo controllo della griglia](../..//fin-ops/get-started/grid-capabilities.md) |
| **Aree del prodotto interessate**         | Client Web |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Nella versione 10.0.13, il nuovo controllo della griglia è generalmente disponibile e i clienti possono facoltativamente attivare questa funzione. Il nuovo controllo della griglia diventerà obbligatorio nella versione di ottobre 2021. Quando il nuovo controllo della griglia diventa obbligatorio, l'API **forceLegacyGrid()** non sarà più rispettata. |

### <a name="personalization-without-saved-views"></a>Personalizzazione senza visualizzazioni salvate 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il sottosistema di personalizzazione è stato revisionato con la funzione di visualizzazioni salvate, in modo che abbia prestazioni migliori e offra funzionalità aggiuntive. |
| **Sostituita da un'altra funzionalità?**   | Visualizzazioni salvate |
| **Aree del prodotto interessate**         | Client Web |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Nella versione 10.0.13/Platform update 37, la funzione delle visualizzazioni salvate è generalmente disponibile e i clienti possono facoltativamente attivare questa funzione. La funzionalità delle visualizzazioni salvate diventerà obbligatoria nella versione di ottobre 2021. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per la versione 10.0.12 delle app Finance and Operations

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Estensioni di moduli di controllo di griglie o gruppi contenenti riferimenti di campo non validi

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La proprietà del gruppo di dati nei controlli di griglie o gruppi viene utilizzata per mostrare automaticamente tutti i campi di un gruppo di campi. Un controllo di griglie o gruppi aggiunto dall'estensione potrebbe contenere campi che non sono più definiti nel gruppo di campi oppure potrebbe non avere campi definiti nel gruppo di campi. Ciò può causare un comportamento non coerente in fase di esecuzione. Gli aggiornamenti della piattaforma per la versione 10.0.12 delle app Finance and Operations ora classificano questo problema come *avviso* del compilatore. Per risolvere questo problema, aprire l'estensione di moduli e salvarla.
| **Sostituita da un'altra funzionalità?**   | Questo avviso del compilatore verrà sostituito con un errore del compilatore in un aggiornamento futuro. |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Un avviso del compilatore è introdotto negli aggiornamenti della piattaforma per la versione 10.0.12 delle app Finance and Operations. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per la versione 10.0.11 delle app Finance and Operations

### <a name="explicit-safe-lists-for-self-service-environments"></a>Elenchi sicuri espliciti per ambienti self-service

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il processo per spostare l'IP in elenchi sicuri è cambiato. Il self-service non supporta più gli elenchi sicuri IP. |
| **Sostituita da un'altra funzionalità?**   | Per ulteriori informazioni, vedere [Configurazione dell'accesso condizionale di Azure Active Directory](/appcenter/general/configuring-aad-conditional-access).|
| **Aree del prodotto interessate**         | Sicurezza |
| **Opzione di distribuzione**              | Cloud |
| **Stato**                         | Deprecato: questa funzionalità è completamente deprecata per le distribuzioni self-service. |

### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Per supportare le ultime versioni di Visual Studio, è necessario apportare alcune modifiche alle estensioni X++ per Visual Studio. Queste modifiche sono incompatibili con Visual Studio 2015. |
| **Sostituita da un'altra funzionalità?**   | Visual Studio 2017 sostituirà Visual Studio 2015 come versione distribuita e richiesta. |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Le macchine virtuali distribuite sulla versione 10.0.13 (Platform update 37) o successive contengono Visual Studio 2017. La versione 10.0.16 (Platform update 40) è la versione finale con supporto per Visual Studio 2015. Macchine virtuali con solo Visual Studio 2015 non sono in grado di eseguire l'aggiornamento alla versione 10.0.17 (Platform update 41). |

### <a name="field-groups-containing-invalid-field-references"></a>Gruppi di campi contenenti riferimenti di campo non validi

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I gruppi di campi nelle definizioni dei metadati della tabella possono contenere riferimenti a campi non validi. Se questi gruppi di campi vengono distribuiti, possono causare errori di runtime in Financial Reporting e in Microsoft SQL Server Reporting Services (SSRS). L'aggiornamento 23 della piattaforma ha introdotto un *avviso* del compilatore che consente di risolvere questo problema relativo ai metadati. Aggiornamenti della piattaforma per la versione 10.0.11 delle app Finance and Operations che classificano questo problema come *errore* del compilatore.<p>Per risolvere questo problema, procedere come segue.</p><ol><li>Rimuovere il riferimento di campo non valido dalla definizione del gruppo di campi di tabella.</li><li>Ricompilare.</li><li>Assicurarsi che eventuali errori vengano risolti.</li></ol> |
| **Sostituita da un'altra funzionalità?**   | Questo errore del compilatore sostituisce in modo permanente l'avviso del compilatore.  |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: L'avviso del compilatore è un errore del compilatore negli aggiornamenti della piattaforma per la versione 10.0.11 delle app Finance and Operations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licenze ISV create utilizzando l'algoritmo di hashing SHA1

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il processo per la creazione di licenze ISV (Independent Software Vendor) è cambiato. Per ulteriori informazioni, vedere [Licenze ISV (Independent Software Vendor)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Sostituita da un'altra funzionalità?**   | Sì. Utilizzare Windows PowerShell per creare licenze. |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: Licenze ISV create utilizzando l'algoritmo di hashing SHA1. Questo algoritmo dipendeva dai certificati creati utilizzando l'utilità MakeCert e questa utilità è stata deprecata.<br><br>Deprecato: L'uso di SHA1 per motivi di sicurezza o di hashing. SHA1 cesserà di funzionare per l'inizio del 2021. Pertanto, non deve più essere utilizzato.<br><br>Rimosso: Supporto per richieste in entrata o in uscita Transport Layer Security (TLS) 1.0 e TLS 1.1. |

## <a name="platform-update-32"></a>Update 32 della piattaforma

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La finestra di dialogo per la modifica della richiesta del flusso di lavoro non include più l'elenco a discesa per la selezione dell'utente

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questo era un problema di sicurezza perché la richiesta di modifica poteva essere inviata a un utente non intenzionale. Anche questo era un problema di usabilità perché costringeva l'utente a determinare chi era il creatore del flusso di lavoro e selezionarlo manualmente.  |
| **Sostituita da un'altra funzionalità?**   | Nessuno |
| **Aree del prodotto interessate**         | Flusso di lavoro |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | L'elenco a discesa di selezione dell'utente è stato rimosso dalla finestra di dialogo di modifica della richiesta nell'aggiornamento 32 della piattaforma. Le richieste di modifica della richiesta verranno inviate automaticamente al mittente come previsto. Per ulteriori informazioni su questa funzionalità, vedere [Azioni nei processi di approvazione del flusso di lavoro](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>I collegamenti drill-through incorporati non sono più supportati nei documenti impaginati visualizzati dal servizio ospitato su cloud 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Gli URL di spostamento incorporati nei documenti visualizzati dal servizio possono contenere dati aziendali sensibili. Verrà rimosso il supporto per i collegamenti drill-through incorporati nei documenti come precauzione di sicurezza per proteggere ulteriormente i dati dei clienti. Gli utenti trarranno inoltre vantaggio da prestazioni migliori producendo in modo interattivo documenti a seguito di questo cambiamento.  |
| **Sostituita da un'altra funzionalità?**   | Nessuna |
| **Aree del prodotto interessate**         | Reporting |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Questa funzione è attivamente rimossa dal servizio.<br><br>Il client moderno offre numerose opzioni per la produzione di visualizzazioni che includono collegamenti generati automaticamente per facilitare l'esplorazione dell'applicazione. I documenti impaginati visualizzati dal servizio sono consigliati per le comunicazioni esterne che vengono inviate via e-mail, archiviate e stampate per i destinatari. Abbiamo migliorato l'esperienza per l'anteprima dei documenti direttamente nel browser, che offre accesso diretto alle stampanti locali. Per ulteriori informazioni, vedere [Anteprima dei documenti PDF con un visualizzatore incorporato](../analytics/preview-pdf-documents.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annunci precedenti sulle funzionalità rimosse o deprecate
Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
