---
title: Funzionalità rimosse o deprecate
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione.
author: sericks007
manager: AnnBe
ms.date: 04/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7201397cd839048465ee0cd8e97c267ab8cbfeb7
ms.sourcegitcommit: 073257c2ec810e3599c1aad5a493bc9f16ffc30d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/12/2019
ms.locfileid: "992885"
---
# <a name="removed-or-deprecated-features"></a>Funzionalità rimosse o deprecate

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità che sono state rimosse o deprecate in Dynamics 365 for Finance and Operations.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione. 

> [!NOTE]
> A partire da Dynamics 365 for Finance and Operations, versione di luglio 2017 con aggiornamento 8 della piattaforma, il tipo di distribuzione viene annotato per ciascuna funzionalità rimossa o deprecata. Tutte le versioni precedenti menzionate in questo argomento supportavano solo le distribuzioni cloud.

> [!NOTE]
> Informazioni dettagliate sugli oggetti in Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione di Finance and Operations.


## <a name="dynamics-365-for-finance-and-operations-1002-with-platform-update-26"></a>Dynamics 365 for Finance and Operations 10.0.2 con aggiornamento 26 della piattaforma

> [!IMPORTANT]
> Dynamics 365 for Finance and Operations 10.0.2 con aggiornamento 26 della piattaforma è disponibile per specifici utenti nell'ambito di una versione di anteprima. Il contenuto e la funzionalità sono soggetti a modifiche. Per ulteriori informazioni sulle versioni di anteprima, vedi [Disponibilità degli aggiornamenti del servizio](../../fin-and-ops/get-started/public-preview-releases.md).

### <a name="legacy-default-action-behavior"></a>Comportamento precedente delle azioni predefinite

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il comportamento precedente delle azioni predefinite nelle griglie determina una colonna inattesa con il collegamento all'azione predefinita dopo il riordinamento delle colonne della griglia tramite la personalizzazione. La nuova funzionalità di azione predefinita permanente corregge questo problema. Per ulteriori informazioni, vedere [Azioni predefinite permanenti nelle griglie](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/sticky-default-action). |
| **Sostituita da un'altra funzionalità?**   | A partire dall'aggiornamento 21 della piattaforma, è stata introdotta una funzionalità per "azioni predefinite permanenti". Questa funzionalità può essere abilitata nella pagina **Opzioni di prestazioni client**. |
| **Aree del prodotto interessate**         | Griglie nel client Web |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Deprecata: a partire da aprile 2020, le azioni predefinite permanenti saranno il comportamento predefinito, senza un meccanismo per tornare al comportamento precedente. |

### <a name="legacy-is-one-of-filtering-experience"></a>Esperienza di filtro "è uno di" precedente

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | L'esperienza di filtro "è uno di" è stata riprogettata nell'aggiornamento 22 della piattaforma, con l'idea di renderla la sola esperienza di filtro "è uno di". |
| **Sostituita da un'altra funzionalità?**   | A partire dall'aggiornamento 22 della piattaforma, un'esperienza di filtro "è uno di" migliorata è diventata disponibile nella pagina **Opzioni di prestazioni client**. Per ulteriori informazioni, vedere [Esperienza di filtro "è uno di" ottimizzata](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering). |
| **Aree del prodotto interessate**         | Client Web |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Deprecata: a partire da aprile 2020, l'esperienza "è uno di" migliorata sarà il comportamento predefinito, senza un meccanismo per tornare al comportamento precedente. |

### <a name="deriving-from-internal-classes-is-deprecated"></a>La derivazione da classi interne è deprecata

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Prima dell'aggiornamento 25 della piattaforma era possibile creare una classe o una tabella che deriva da una classe/tabella interna definita in un altro pacchetto/modulo. Questa non è una procedura di codifica sicura. A partire dall'aggiornamento 25 della piattaforma, il compilatore visualizzerà un avviso. |
| **Sostituita da un'altra funzionalità?**   | L'avviso del compilatore verrà sostituito da un errore nell'aggiornamento 26 della piattaforma. Questa modifica è compatibile con versioni precedenti al runtime, a indicare che è possibile eseguire l'aggiornamento 25 della piattaforma o successivo in qualsiasi ambiente sandbox o di produzione senza la necessità di modificare il codice personalizzato. Questa modifica influisce solo sulla fase di sviluppo e quella di compilazione.|
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Deprecato - L'avviso diventerà un errore di compilazione nell'aggiornamento 26 della piattaforma. |

### <a name="overriding-internal-methods-is-deprecated"></a>La sostituzione dei metodi interni è deprecata

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Prima dell'aggiornamento 25 della piattaforma, era possibile sostituire un metodo interno in una classe derivata definita in un altro pacchetto/modulo. Questa non è una procedura di codifica sicura. A partire dall'aggiornamento 25 della piattaforma, il compilatore visualizzerà un avviso. |
| **Sostituita da un'altra funzionalità?**   | Questo avviso verrà sostituito da un errore di compilazione nell'aggiornamento 26 della piattaforma. Questa modifica è compatibile con versioni precedenti al runtime, a indicare che è possibile eseguire l'aggiornamento 25 della piattaforma o successivo in qualsiasi ambiente sandbox o di produzione senza la necessità di modificare il codice personalizzato. Questa modifica influisce solo sulla fase di sviluppo e quella di compilazione. |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Deprecato - L'avviso diventerà un errore di compilazione nell'aggiornamento 26 della piattaforma. |

### <a name="parameter-to-enable-sales-orders-with-multiple-project-contract-funding-sources"></a>Il parametro per abilitare ordini cliente con molteplici fonti di finanziamento di contratti di progetto
Il supporto per la creazione di ordini cliente basati su progetti in cui il contratto di progetto ha più fonti di finanziamento è abilitato con l'impostazione **Consenti ordini cliente per progetti con più fonti di finanziamento** di **Parametri Gestione progetti e contabilità**. Per impostazione predefinita, questo parametro non è abilitato. 

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La funzionalità sarà sempre abilitata dopo la rimozione del parametro. |
| **Sostituita da un'altra funzionalità?**   | N. La funzionalità per supportare ordini cliente basati su progetti con più fonti di finanziamento sarà sempre attivata.   |
| **Aree del prodotto interessate**         |Il parametro **Consenti ordini cliente per progetti con più fonti di finanziamento** verrà rimosso. I seguenti metodi verranno modificati alla rimozione del parametro: **ctrlSalesOrderTable** nella classe **ProjStatusType**, **validate** nel campo **ProjId** e **run** nel modulo **SalescreateOrder**. I seguenti metodi verranno deprecati alla rimozione del parametro: **IsSalesOrderAllowedForMultipleFundingSources** nel file di tabella **ProjTable**, **IsAllowSalesOrdersForMultipleFundingSourcesParamEnabled** nel file di tabella **ProjTable**, il campo dati **AllowSalesOrdersForMultipleFundingSources** nel modulo **ProjParameters** e nei file **ProjParameterEntity**, il metodo privato **IsAssociatedToMultipleFundingSourcesContract** nel file di tabella **ProjTable**. |
| **Opzione di distribuzione**              | Tutte  |
| **Stato**                         | Il parametro verrà deprecato durante l'ondata di rilascio nell'aprile 2020. |

### <a name="legacy-workflow-reports-for-tracking-and-instance-status"></a>Report di flusso di lavoro precedenti per stato dell'istanza e tracciabilità

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I report di flusso di lavoro precedenti per lo stato dell'istanza e la tracciabilità vengono deprecati in quanto agli stessi non viene più fatto riferimento dalla navigazione. I report sono WorkflowWorkflowInstanceByStatusReport e WorkflowWorkflowTrackingReport. |
| **Sostituita da un'altra funzionalità?**   | In alternativa, è possibile utilizzare il modulo dello storico flusso di lavoro. |
| **Aree del prodotto interessate**         | Client Web |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Deprecato: il calendario di destinazione per la funzionalità verrà rimosso nell'aprile 2020. |

## <a name="dynamics-365-for-finance-and-operations-1001-with-platform-update-25"></a>Dynamics 365 for Finance and Operations 10.0.1 con aggiornamento 25 della piattaforma

> [!IMPORTANT]
> Dynamics 365 for Finance and Operations 10.0.1 con aggiornamento 25 della piattaforma è disponibile per specifici utenti nell'ambito di una versione di anteprima. Il contenuto e la funzionalità sono soggetti a modifiche. Per ulteriori informazioni sulle versioni di anteprima, vedi [Disponibilità degli aggiornamenti del servizio](../../fin-and-ops/get-started/public-preview-releases.md).

### <a name="deprecated-apis-and-potential-breaking-changes"></a>Api deprecate e modifiche significative potenziali


#### <a name="deriving-from-internal-classes-is-deprecated"></a>La derivazione da classi interne è deprecata

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Prima dell'aggiornamento 25 della piattaforma era possibile creare una classe o una tabella che deriva da una classe/tabella interna definita in un altro pacchetto/modulo. Questa non è una procedura di codifica sicura. A partire dall'aggiornamento 25 della piattaforma, il compilatore visualizzerà un avviso. |
| **Sostituita da un'altra funzionalità?**   | L'avviso del compilatore verrà sostituito da un errore nell'aggiornamento 26 della piattaforma. Questa modifica è compatibile con versioni precedenti al runtime, a indicare che è possibile eseguire l'aggiornamento 25 della piattaforma o successivo in qualsiasi ambiente sandbox o di produzione senza la necessità di modificare il codice personalizzato. Questa modifica influisce solo sulla fase di sviluppo e quella di compilazione.|
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Deprecato - L'avviso diventerà un errore di compilazione nell'aggiornamento 26 della piattaforma. |

#### <a name="overriding-internal-methods-is-deprecated"></a>La sostituzione dei metodi interni è deprecata

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Prima dell'aggiornamento 25 della piattaforma, era possibile sostituire un metodo interno in una classe derivata definita in un altro pacchetto/modulo. Questa non è una procedura di codifica sicura. A partire dall'aggiornamento 25 della piattaforma, il compilatore visualizzerà un avviso. |
| **Sostituita da un'altra funzionalità?**   | Questo avviso verrà sostituito da un errore di compilazione nell'aggiornamento 26 della piattaforma. Questa modifica è compatibile con versioni precedenti al runtime, a indicare che è possibile eseguire l'aggiornamento 25 della piattaforma o successivo in qualsiasi ambiente sandbox o di produzione senza la necessità di modificare il codice personalizzato. Questa modifica influisce solo sulla fase di sviluppo e quella di compilazione. |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Deprecato - L'avviso diventerà un errore di compilazione nell'aggiornamento 26 della piattaforma. |


## <a name="dynamics-365-for-finance-and-operations-813-with-platform-update-23"></a>Dynamics 365 for Finance and Operations 8.1.3 con aggiornamento 23 della piattaforma

### <a name="sql-server-reporting-services-reportviewer-control"></a>Controllo ReportViewer di SQL Server Reporting Services
I clienti possono utilizzare l'azione **Esporta** del controllo ReportViewer di SQL Server Reporting Services (SSRS) incorporato per scaricare documenti prodotti dalle applicazioni Finance and Operations. Questa presentazione basata su HTML del report offre agli utenti un'anteprima non impaginata del documento.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La natura non impaginata dell'esperienza di anteprima basata su HTML **non** fornisce un output fedele dei documenti fisici generati mediante Finance and Operations. Utilizzando PDF come formato standard per documenti aziendali, gli utenti possono usufruire di un'esperienza di visualizzazione moderna con prestazioni migliorate nella produzione di report di applicazioni. |
| **Sostituita da un'altra funzionalità?**   | In futuro, il formato PDF sarà quello predefinito per i report il cui rendering viene eseguito mediante Finance and Operations.   |
| **Aree del prodotto interessate**         | Questa modifica **non** interessa gli scenari in cui i report vengono distribuiti elettronicamente o inviati direttamente alle stampanti.    |
| **Opzione di distribuzione**              | Tutte  |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. La funzionalità per visualizzare automaticamente in anteprima i report di applicazioni utilizzando un visualizzatore PDF incorporato è prevista per l'aggiornamento della piattaforma di maggio 2019. |

### <a name="client-kpi-controls"></a>Comandi KPI del client
Gli indicatori di prestazioni chiave (KPI) incorporati potrebbero essere modellati in Visual Studio da uno sviluppatore e essere personalizzati ulteriormente dall'utente finale.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I controlli client nativi utilizzati per definire i KPI sono poco utilizzati dai clienti e necessitano di uno sviluppatore per aggiungere metriche monitorabili. |
| **Sostituita da un'altra funzionalità?**   | Il servizio PowerBI.com fornisce strumenti di prim'ordine per definire e gestire KPI basati sui dati di origini esterne.  In una versione futura, verrà consentita l'integrazione di soluzioni ospitate in PowerBI.com nelle aree di lavoro dell'applicazione.   |
| **Aree del prodotto interessate**         | Questo aggiornamento impedirà agli sviluppatori di introdurre nuovi controlli KPI nella progettazione di Visual Studio.    |
| **Opzione di distribuzione**              | Tutte  |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="deprecated-apis-and-future-breaking-changes"></a>Api deprecate e modifiche significative future

#### <a name="field-groups-containing-invalid-field-references"></a>Gruppi di campi contenenti riferimenti di campo non validi

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Le definizioni di metadati di tabella possono avere gruppi di campi contenenti riferimenti di campo non validi. Questo problema è attualmente categorizzato come *avviso del compilatore* anziché come *errore*, a indicare che è possibile continuare a creare pacchetti distribuibili e a eseguire la distribuzione senza correggere il problema. In caso di distribuzione, è possibile che si verifichino errori di runtime in Financial Reporting e SQL Server Reporting Services (SSRS). Per risolvere il problema:<br><br>1. Rimuovere il riferimento di campo non valido dalla definizione del gruppo di campi di tabella.<br><br>2. Ricompilare.<br><br>3. Verificare che tutti gli errori o avvisi siano stati risolti. |
| **Sostituita da un'altra funzionalità?**   | Questo avviso verrà sostituito da un errore di compilazione in futuro.  |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio. |
| **Opzione di distribuzione**              | Tutto. |
| **Stato**                         | Deprecato - L'avviso diventerà un errore di compilazione in futuro, probabilmente nell'aggiornamento 30 della piattaforma. |

#### <a name="complete-list"></a>Elenco completo
Per accedere all'elenco completo delle API che verranno deprecate, vedere [Deprecazione di metodi e di elementi di metadati](deprecation-deletion-apis.md).

## <a name="dynamics-365-for-finance-and-operations-81-with-platform-update-20"></a>Dynamics 365 for Finance and Operations 8.1 con aggiornamento 20 della piattaforma

### <a name="batch-transfer-rules-for-subledger-journal-account-entries"></a>Regole trasferimento batch per voci contabili del giornale di registrazione secondario
La modalità di trasferimento sincrona viene deprecata nei parametri di contabilità generale.  Questa modalità viene sostituita dalle modalità asincrona e solo batch programmato, che sono già presenti come opzioni per il trasferimento. Per ulteriori informazioni, vedere il blog [Parametri di contabilità generale – Regole di trasferimento batch](https://community.dynamics.com/365/financeandoperations/b/financials/archive/2019/03/15/general-ledger-parameters-batch-transfer-rules) .

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | L'opzione sincrona viene rimossa a causa dell'impatto sulle prestazioni del sistema. |
| **Sostituita da un'altra funzionalità?**   | Batch asincrono e programmato sono opzioni da utilizzare al posto della modalità sincrona.   |
| **Aree del prodotto interessate**         | Contabilità generale, Contabilità fornitori, Contabilità clienti, approvvigionamento, spesa    |
| **Opzione di distribuzione**              | Tutte  |
| **Stato**                         | Deprecato: la rimozione della funzionalità è prevista nella versione 10.0.|

### <a name="electronic-reporting-for-russia"></a>Creazione di report elettronici per la Russia
Funzionalità per la configurazione di formati di file txt e xml per le dichiarazioni. 

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituita con la creazione di report elettronici. |
| **Sostituita da un'altra funzionalità?**   | Sì. |
| **Aree del prodotto interessate**         | Contabilità generale |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Rimossa da Dynamics 365 for Finance and Operations 8.1 con aggiornamento 20 della piattaforma. |

### <a name="financial-reports-generator-for-russia"></a>Generatore di report finanziari per la Russia
Uno strumento per impostare la raccolta dei dati per report fiscali e di contabilità e per esportare i dati in modelli di report XLS e DOC. Parti funzionali: l'esportazione di dati in modelli XLS e DOC, query, requisiti fissi sono stati rimossi. 

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Le parti rimosse sono state sostituite con la creazione di report elettronici. |
| **Sostituita da un'altra funzionalità?**   | Sì. L'interfaccia utente di impostazione dei report finanziari deve essere utilizzata per impostare la raccolta dei dati dai conti di contabilità generale o dai registri delle imposte. Le regole di esportazione dati in vari tipi di file, dei requisiti fissi e della raccolta di dati tipo query devono essere configurate nella creazione di report elettronici. |
| **Aree del prodotto interessate**         | Contabilità generale. |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Rimossa da Dynamics 365 for Finance and Operations 8.1 con aggiornamento 20 della piattaforma. |

### <a name="integration-with-external-providers-for-sending-electronic-reporting-through-communication-channels-for-russia"></a>Integrazione con i fornitore esterni per inviare la dichiarazione elettronica tramite i canali di comunicazione per la Russia
Funzionalità di esportazione dei file elettronici generati delle dichiarazioni nella cartella per l'inoltro ai provider ufficiali di report elettronici, nonché di reimportazione dello stato.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituita con la funzionalità configurabile dei messaggi elettronici. |
| **Sostituita da un'altra funzionalità?**   | Sì.  |
| **Aree del prodotto interessate**         | Contabilità generale, Imposta |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Rimossa da Dynamics 365 for Finance and Operations 8.1 con aggiornamento 20 della piattaforma. |


### <a name="profit-tax-register-wizard"></a>Procedura guidata per registri delle imposte sui profitti
Funzionalità per la creazione di modelli per nuovi registri delle imposte sui profitti. Questa funzionalità consente di creare oggetti X++ per nuovi registri, che vengono quindi generati come modelli con la logica di calcolo appropriata.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La funzionalità non è compatibile con il modello di estendibilità di Dynamics 365 for Finance and Operations. |
| **Sostituita da un'altra funzionalità?**   | Nessuna |
| **Aree del prodotto interessate**         | Imposta sul reddito |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | Rimossa da Dynamics 365 for Finance and Operations 8.1 con aggiornamento 20 della piattaforma. |


## <a name="dynamics-365-for-finance-and-operations-80-with-platform-update-15"></a>Dynamics 365 for Finance and Operations 8.0 con aggiornamento 15 della piattaforma
In questa versione non sono state rimosse o deprecate funzionalità. L'aggiornamento 15 della piattaforma è cumulativo e contiene funzionalità nuove o modificate che derivano dagli aggiornamenti 13, 14 e 15 della piattaforma.

## <a name="dynamics-365-for-finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 con aggiornamento della piattaforma 12

### <a name="personalized-product-recommendations"></a>Suggerimenti sul prodotto personalizzati 
A partire dal 15 febbraio 2018, i rivenditori non potranno più visualizzare consigli personalizzati sui prodotti su dispositivi POS. Per ulteriori informazioni, vedere [Panoramica dei suggerimenti sul prodotto personalizzati](../../retail/personalized-product-recommendations.md).  

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Durante la nuova progettazione della funzionalità del servizio di suggerimenti prodotto con un algoritmo migliore e nuove funzionalità orientate alla vendita al dettaglio, verrà rimossa la versione corrente di tale servizio.  |
| **Sostituita da un'altra funzionalità?**   | N. Tuttavia, dopo la primavera del 2018, è in programma il ripristino di questa funzionalità per un nuovo servizio di suggerimenti   |
| **Aree del prodotto interessate**         | Suggerimenti sul prodotto personalizzati nel POS.                                                    |
| **Opzione di distribuzione**              | Tutti                                                                                      |
| **Stato**                         |Rimosso a partire da 15 febbraio 2018. Questa modifica riguarda i clienti che eseguono Dynamics 365 for Operations, versione 1611 e versioni successive.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Estensione dell'elenco di funzioni di creazione di report elettronici (ER)
La possibilità di introdurre funzioni personalizzate da utilizzare nel generatore di espressioni ER (per ulteriori informazioni, vedere [Estendere l'elenco delle funzioni di creazione di report elettronici](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) non è più supportata. A causa delle modifiche apportate alle API ER, l'API per richiamare funzioni integrate dal generatore di espressioni ER è diventata interna e non può essere più estesa.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Iniziativa di sigillo del codice  |
| **Sostituita da un'altra funzionalità?**   | Nessuna. Ogni volta che è necessaria una nuova funzione incorporata, una nuova richiesta di estensione deve essere indirizzata al team del framework ER.<br><br>Come soluzione alternativa temporanea mentre la funzione richiesta è in fase di sviluppo da parte del team ER, la logica richiesta può essere programmata come metodo di una classe di applicazione personalizzata. È possibile accedere a questo metodo in un'espressione ER come proprietà dell'origine dati ER aggiunta del tipo **Applicazione\Classe** che fa riferimento a tale classe di applicazione personalizzata.  |
| **Aree del prodotto interessate**         | Framework per la creazione di report elettronici                                                      |
| **Opzione di distribuzione**              | Tutte                                                                                      |
| **Stato**                         | Funzionalità rimosse a partire da Dynamics 365 for Finance and Operations, Enterprise Edition 7.3    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>Report di aging delle scorte per gruppo di articoli e delle scorte per dimensione inventariale

I due report più non sono supportati in Finance and Operations. Il report **Aging delle scorte** può essere invece utilizzato per aggiornare le esperienze utente.

|   |  |
|--------------|-----------------------|
| **Motivo del deprecamento**       | Funzionalità duplicata.  |
| **Sostituita da un'altra funzionalità?** | Sì. I due report sono stati sostituiti dal report **Aging delle scorte**.     |
| **Aree del prodotto interessate**       | Gestione inventario, Gestione costi        |
| **Opzione di distribuzione**        | Tutti|
| **Stato**                       | Deprecata: le voci di menu per i due report sono state rimosse nella versione 7.3. Tuttavia, il codice per i report è ancora presente nel prodotto. Il piano è di rimuovere il codice in una versione successiva. |

### <a name="power-bi-content-packs-available-on-appsource"></a>Pacchetti di contenuti Power BI disponibili in AppSource
I pacchetti di contenuti **Gestione costi**, **Prestazioni finanziarie** e **Prestazioni canale di vendita al dettaglio**, disponibili sul sito [Microsoft AppSource](https://appsource.microsoft.com), sono deprecati in conseguenza degli aggiornamenti di prodotto in Microsoft Power BI. Anche i moduli di amministrazione del sistema utilizzati per distribuire questi pacchetti di contenuto in PowerBI.com sono deprecati in Finance and Operations.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Aggiornamenti di prodotto in Microsoft Power BI. |
| **Sostituita da un'altra funzionalità?**   | I pacchetti di contenuti **Gestione costi**, **Prestazioni finanziarie** e **Prestazioni canale di vendita al dettaglio**, disponibili sul sito [AppSource](https://appsource.microsoft.com), vengono sostituiti da applicazioni analitiche che consentono l'integrazione di soluzioni a livello di database. Per ulteriori informazioni sulle applicazioni analitiche, vedere [Power BI nelle aree di lavoro](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Aree del prodotto interessate**         | Cost management, Finance e Retail                                                                                               |
| **Opzione di distribuzione**              | Solo cloud (l'integrazione con PowerBI.com non è supportata nelle distribuzioni locali).                                                                                                            |
| **Stato**                         | Deprecato: il calendario di destinazione per la rimozione della funzionalità è il 2° trimestre 2018.    |

### <a name="standard-ui-in-data-management-workspace"></a>Interfaccia utente standard nell'area di lavoro di gestione dei dati

L'interfaccia utente standard nella gestione dei dati corrisponde all'interfaccia utente legacy, che è l'interfaccia utente predefinita presentata agli utenti quando visitano l'area di lavoro di gestione dei dati.

|   |  |
|------------------|-------------------------|
| **Motivo del deprecamento/rimozione** | stiamo investendo per fornire nuove esperienze utente nella nuova interfaccia utente.             |
| **Sostituita da un'altra funzionalità?**   | La nuova interfaccia utente denominata *Visualizzazione migliorata* sostituisce la vecchia interfaccia utente.            |
| **Aree del prodotto interessate**         | Area di lavoro gestione dati                                                     |
| **Opzione di distribuzione**              | Tutti                                                                           |
| **Stato**                         | Deprecato: il calendario di destinazione per la funzionalità verrà rimosso nel secondo trimestre 2018. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Consumi, IVA, Service Tax (India)

Queste imposte sono state importate nella GST indiana.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo del deprecamento o rimozione**       | Queste imposte sono state importate nella GST indiana.                          |
| **Sostituita da un'altra funzionalità?**            | GST India                                                              |
| **Aree del prodotto interessate**                  | Imposta sul reddito                                                                     |
| **Opzione di distribuzione**                       | Tutti i moduli                                                   |
| **Stato**                                  | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |    

### <a name="file-validation-utility-fvu-for-india"></a>utilità di convalida dei file (FVU) per l'India

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo del deprecamento o rimozione**       | Mancanza di utilizzo del cliente                                                  |
| **Sostituita da un'altra funzionalità?**            | No                                                                      |
| **Aree del prodotto interessate**                  | Ritenuta d'acconto indiana.                                                  |
| **Opzione di distribuzione**                       | Tutti i moduli                                                                    |
| **Stato**                                  | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.   |        

### <a name="tdstcs-certificate-for-india"></a>Certificato di TDS/TCS per l'India

È possibile scaricare questo certificato dal portale governativo.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo del deprecamento o rimozione**       | Mancanza di utilizzo del cliente                                                  |
| **Sostituita da un'altra funzionalità?**            | No                                                                      |
| **Aree del prodotto interessate**                  | Ritenuta d'acconto indiana.                                                  |
| **Opzione di distribuzione**                       | Tutti i moduli                                                                   |
| **Stato**                                  | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Schema di incentivi per EXIM di esportazione/importazione per l'India.


|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo del deprecamento o rimozione**       | Mancanza di utilizzo del cliente                                                  |
| **Sostituita da un'altra funzionalità?**            | No                                                                      |
| **Aree del prodotto interessate**                  | Importazione ed esportazione                                                       |
| **Opzione di distribuzione**                       | Tutti i moduli                                                                    |
| **Stato**                                  | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Suggerimenti sul prodotto personalizzati 
A partire dal 15 febbraio 2018, i rivenditori non potranno più visualizzare consigli personalizzati sui prodotti su dispositivi POS. Per ulteriori informazioni, vedere [Panoramica dei suggerimenti sul prodotto personalizzati](../../retail/personalized-product-recommendations.md).  

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Durante la nuova progettazione della funzionalità del servizio di suggerimenti prodotto con un algoritmo migliore e nuove funzionalità orientate alla vendita al dettaglio, verrà rimossa la versione corrente di tale servizio.  |
| **Sostituita da un'altra funzionalità?**   | N. Tuttavia, dopo la primavera del 2018, è in programma il ripristino di questa funzionalità per un nuovo servizio di suggerimenti   |
| **Aree del prodotto interessate**         | Suggerimenti sul prodotto personalizzati nel POS.                                                    |
| **Opzione di distribuzione**              | Tutti                                                                                      |
| **Stato**                         |Rimosso a partire da 15 febbraio 2018. Questa modifica riguarda i clienti che eseguono Dynamics 365 for Retail, versione 7.2 e versioni successive. |


## <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Dynamics 365 for Finance and Operations, Enterprise Edition luglio 2017 con aggiornamento 8 della piattaforma

### <a name="currency-conversion-for-accounting-and-reporting-currencies"></a>Conversione di valuta per le valute di contabilizzazione e di dichiarazione

La conversione valutaria per le valute di contabilizzazione e di dichiarazione è stata introdotta quando è stato introdotto l'euro.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Utilizzo limitato e aggiunta della funzionalità di copia di persona giuridica come sostituzione.      |
| **Sostituita da un'altra funzionalità?**   | No, ma le funzionalità di copia della persona giuridica e delle configurazioni sono state aggiunte per facilitare lo spostamento di una società i cui requisiti fondamentali cambiano. |
| **Aree del prodotto interessate**         | Gestione finanziaria     |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.   |


### <a name="warehouse-mobile-devices-portal"></a>Portale dei dispositivi mobili del magazzino

Il Portale dei dispositivi mobili del magazzino è un componente autonomo progettato per la distribuzione automatica locale. Il componente non è più supportato in Finance and Operations. Un app nativa che migliora l'esperienza utente ha sostituito la funzionalità Portale dei dispositivi mobili del magazzino.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Funzionalità duplicata.       |
| **Sostituita da un'altra funzionalità?**   | Sì. Questa funzionalità è stata sostituita da Finance and Operations - Magazzino. Per ulteriori informazioni sull'impostazione e sui prerequisiti, vedere [Installare e configurare Microsoft Dynamics 365 for Finance and Operations - Magazzino](../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Aree del prodotto interessate**         | Gestione magazzino, Gestione trasporto     |
| **Opzione di distribuzione**              | Il Portale dei dispositivi mobili del magazzino è un componente autonomo progettato per la distribuzione automatica locale.               |
| **Stato**                         | Deprecato: il calendario di destinazione per la funzionalità verrà rimosso nel quarto trimestre 2019.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Regola avanzata di abbinamento di riconciliazione estratti conto per la corrispondenza manuale

Una regola di abbinamento è stata utilizzata per selezionare e contrassegnare un documento bancario durante la corrispondenza manuale dei documenti nel foglio di lavoro di riconciliazione.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Utilizzo limitato.                                                                         |
| **Sostituita da un'altra funzionalità?**   | N. Le capacità di filtro della colonna devono essere utilizzate per individuare i documenti per la riconciliazione. |
| **Aree del prodotto interessate**         | Gestione cassa e banche                                                               |
| **Opzione di distribuzione**              | Tutte                                                                                    |
| **Stato**                         | Rimosso a partire da luglio 2017.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 con aggiornamento 3 della piattaforma

### <a name="aeb-payment-formats-for-spain"></a>Formati di pagamento AEB per la Spagna

I formati di pagamento Consejo Superior Bancario erano utilizzati per inviare i file di rimessa alla banca per i pagamenti dei clienti e i pagamenti fornitore. Il contenuto di questi formati era determinato dalla Asociación Española de Banca. Copre Cuaderno 19, 32, 58, 34.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.                                  |
| **Sostituita da un'altra funzionalità?**   | Sì, i formati per i pagamenti tramite bonifico ISO20022 e in addebito diretto per la Spagna |
| **Aree del prodotto interessate**         | Contabilità fornitori, contabilità clienti                                    |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Trasferimento di pagamenti bancari per la Lituania

I trasferimenti di pagamento bancario venivano generati e stampati utilizzando il formato di esportazione del trasferimento di pagamento (LT) per la Lituania. Il mercato lituano ha iniziato a utilizzare LITAS, il sistema unificato di E-banking, nel 2005.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.                        |
| **Sostituita da un'altra funzionalità?**   | Sì, formato di pagamento tramite bonifico ISO20022 per la Lituania     |
| **Aree del prodotto interessate**         | Contabilità fornitori                                               |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Formati di pagamento BBS Direkte Remittering per la Norvegia

I formati di pagamento BBS Direkte Remittering includono l'esportazione dei pagamenti recuperati dai clienti (addebito diretto) e l'importazione dei messaggi di reso.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.  |
| **Sostituita da un'altra funzionalità?**   | Il formato di pagamento cliente AvtaleGiro per la Norvegia può essere utilizzato per generare i messaggi di addebito diretto. L'importazione di un messaggio di reso è implementata nelle versioni future. |
| **Aree del prodotto interessate**         | Contabilità fornitori, contabilità clienti   |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Strumento piano dei conti per la Spagna

Lo strumento viene utilizzato quando un piano dei conti in Spagna richiede modifiche importanti. Gli utenti possono importare un nuovo piano dei conti in formato testo o Microsoft Excel, oltre a rendiconti finanziari.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Utilizzo limitato                                                  |
| **Sostituita da un'altra funzionalità?**   | No                                                             |
| **Aree del prodotto interessate**         | Contabilità generale                                                 |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="dom80-payment-format-for-belgium"></a>Formato di pagamento Dom80 per il Belgio

Formato di pagamento precedente per il Belgio per il recupero dei pagamenti (addebito diretto).

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato di pagamento non è più utilizzato.                          |
| **Sostituita da un'altra funzionalità?**   | Sì, formato di pagamento in addebito diretto ISO 20022 per il Belgio         |
| **Aree del prodotto interessate**         | Contabilità clienti                                            |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formati di pagamento DTA/EZAG per la Svizzera

I formati DTA/EZAG sono integrati nel sistema PVR, poiché possono riportare il numero di riferimento. Poiché il numero di riferimento non è obbligatorio, questi formati possono essere utilizzati per elaborare i pagamenti fornitore. Questi formati sono utilizzati dalle società con un conto bancario in un percorso diverso da "Postfinance".

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.                        |
| **Sostituita da un'altra funzionalità?**   | Sì, formato di pagamento tramite bonifico ISO20022 per la Svizzera   |
| **Aree del prodotto interessate**         | Contabilità fornitori                                               |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Formato di pagamento EDIFACT-DIRDEB per l'Austria

Formato di pagamento EDIFACT-DIRDEB per il recupero dei pagamenti (addebito diretto).

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato di pagamento non è più utilizzato.                          |
| **Sostituita da un'altra funzionalità?**   | Sì, formato di pagamento in addebito diretto ISO 20022 per l'Austria         |
| **Aree del prodotto interessate**         | Contabilità clienti                                            |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="edivat-for-belgium"></a>EDIVAT per il Belgio

EDIVAT è uno standard belga obsoleto per la dichiarazione tramite posta elettronica protetta. Microsoft Dynamics AX 2012 mantiene la soluzione di sola lettura per consentire l'accesso ai dati dello storico.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La funzionalità non è più utilizzata.                           |
| **Sostituita da un'altra funzionalità?**   | No                                                             |
| **Aree del prodotto interessate**         | Contabilità generale                                                 |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>Formato di importazione dei pagamenti eGiro EDIFACT CREMUL per la Norvegia

eGiro si basa sullo standard internazionale UN EDIFACT CREMUL, (Multiple Credit Advice Message) utilizzato per la registrazione automatica dei pagamenti cliente. In Microsoft Dynamics AX, eGiro è implementato come formato di importazione di pagamento del cliente.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato di pagamento non è più utilizzato.                                                     |
| **Sostituita da un'altra funzionalità?**   | N. Il formato verrà sostituito dai formati di importazione dei rendiconti ISO 20022 nelle versioni future. |
| **Aree del prodotto interessate**         | Contabilità clienti                                                                       |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                            |

### <a name="external-inventory-for-poland"></a>Inventario esterno per la Polonia

Prova delle merci prese da un fornitore per le vendite senza acquisto. Le merci gestite in inventario esterno non hanno impatto sull'inventario standard e possono essere vendute e acquistate automaticamente. Questo processo crea movimenti di scorte effettive.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituita da un'altra funzionalità                                    |
| **Sostituita da un'altra funzionalità?**   | Sì, la funzionalità core di spedizione in entrata                |
| **Aree del prodotto interessate**         | Contabilità fornitori, Gestione inventario                         |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Generatore di report finanziari nell'Europa dell'Est

Strumento per impostare la raccolta dei dati per i report fiscali e contabili ed esportare i dati nei modelli di report XLS e DOC.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Utilizzo limitato                                                                            |
| **Sostituita da un'altra funzionalità?**   | N. Lo strumento verrà sostituito nelle versioni future dalle configurazioni dei report elettronici. |
| **Aree del prodotto interessate**         | Contabilità generale                                                                           |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Importazione delle transazioni di pagamento dei clienti per la Finlandia

È possibile selezionare un formato di importazione per i pagamenti finlandesi per includere le transazioni di pagamento dei clienti da un file esterno fornito dalla banca.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato di pagamento non è più utilizzato.                                                     |
| **Sostituita da un'altra funzionalità?**   | N. Il formato verrà sostituito dai formati di importazione dei rendiconti ISO 20022 nelle versioni future. |
| **Aree del prodotto interessate**         | Contabilità clienti                                                                       |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Importazione delle transazioni di pagamento in un giornale di registrazione contabile per la Finlandia

Un formato specifico per la Finlandia viene utilizzato per importare le transazioni contabili nella contabilità generale.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato di pagamento non è più utilizzato.                                                     |
| **Sostituita da un'altra funzionalità?**   | N. Il formato verrà sostituito dai formati di importazione dei rendiconti ISO 20022 nelle versioni future. |
| **Aree del prodotto interessate**         | Contabilità clienti                                                                       |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integrazione con CIS (Client Isabel Synchronizer) per il Belgio

Isabel è il framework di E-banking in Europa e uno standard di fatto in Belgio.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | L'integrazione con Client Isabel è stata interrotta.   |
| **Sostituita da un'altra funzionalità?**   | N. I formati di pagamento non più utilizzati verranno sostituiti dal formato di pagamento con bonifico ISO20022 per il Belgio. |
| **Aree del prodotto interessate**         | Contabilità fornitori     |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Modifiche al piano dei conti e alle regole contabili per la Spagna

Questa funzionalità consente delle modifiche al piano dei conti e alle regole contabili in Spagna. Traccia i conti che consentono di trasformare il precedente piano dei conti nel nuovo piano dei conti e confronta l'anno fiscale precedente con il nuovo anno fiscale, anche se sono stati registrati su numeri di conto diversi.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Utilizzo limitato                                                  |
| **Sostituita da un'altra funzionalità?**   | No                                                             |
| **Aree del prodotto interessate**         | Contabilità generale                                                 |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Formato di pagamento fornitori Pagamento Fornitori

Precedente formato di pagamento italiano per i trasferimenti di credito.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato di pagamento non è più utilizzato.                          |
| **Sostituita da un'altra funzionalità?**   | Sì, formato di pagamento tramite bonifico ISO20022 per l'Italia         |
| **Aree del prodotto interessate**         | Contabilità fornitori                                               |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="payment-export-formats-for-estonia"></a>Formati di esportazione dei pagamenti per l'Estonia

I formati Telehansa e Teleservice vengono utilizzati per l'esportazione di pagamenti bancari.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.                        |
| **Sostituita da un'altra funzionalità?**   | Sì, formato di pagamento tramite bonifico ISO20022 per l'Estonia       |
| **Aree del prodotto interessate**         | Contabilità fornitori                                               |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="payment-file-archive-for-norway"></a>Archivio file di pagamento per la Norvegia

Quando i file di pagamento vengono generati, l'archivio dei file archivia automaticamente tutti i file creati, anche i file che in precedenza erano stati scritti o letti.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituita da un'altra funzionalità                                        |
| **Sostituita da un'altra funzionalità?**   | Sì, processi archiviati di creazione report elettronici                            |
| **Aree del prodotto interessate**         | Contabilità fornitori, Contabilità clienti, Amministrazione organizzazione |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.     |

### <a name="payment-import-formats-for-estonia"></a>Formati di importazione dei pagamenti per l'Estonia

I formati Telehansa e TeleTeenus vengono utilizzati per l'importazione di pagamenti bancari.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.                                                    |
| **Sostituita da un'altra funzionalità?**   | N. I formati verranno sostituiti dai formati di importazione dei rendiconti ISO 20022 nelle versioni future. |
| **Aree del prodotto interessate**         | Contabilità clienti                                                                        |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                             |

### <a name="payroll-information-in-human-resources"></a>Informazioni sulle retribuzioni in Risorse umane

Informazioni sulle retribuzioni in Risorse umane

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questa funzionalità è stata sostituita dalle pagine principali sulle risorse umane e sulle retribuzioni.  |
| **Sostituita da un'altra funzionalità?**   | **Benefit**, **Redditi** e altre pagine correlate, incluse in precedenza nelle retribuzioni degli Stati Uniti ora sono state riconfigurate e fanno parte della configurazione principale Risorse umane per supportare l'elaborazione esterna delle retribuzioni. Questa funzionalità è accessibile utilizzando la chiave di configurazione **Risorse umane 1** \> **Retribuzione**. |
| **Aree del prodotto interessate**         | Risorse umane, retribuzioni   |
| **Stato**                         | Rimosso a partire da Dynamics 365 for Operations versione 1611.    |

### <a name="performance-management-goal-workflow"></a>Flusso di lavoro relativo agli obiettivi di gestione delle prestazioni

La gestione delle prestazioni include la gestione e l'integrazione degli obiettivi con le revisioni delle prestazioni.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La gestione delle prestazioni è stata riprogettata e il numero di pagine degli obiettivi è stato ridotto per semplificare il processo.                 |
| **Sostituita da un'altra funzionalità?**   | N. Gli obiettivi sono visibili ai responsabili tramite il portale Responsabile self-service e possono essere modificati e visualizzati dal responsabile. |
| **Aree del prodotto interessate**         | Gestione risorse umane       |
| **Stato**                         | Rimosso a partire da Dynamics 365 for Operations versione 1611.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formati di pagamento Postgirot e Postgirot Utland per la Svezia

Formati di pagamento Postgirot e Postgirot Utland per la Svezia.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.                        |
| **Sostituita da un'altra funzionalità?**   | Sì, formato di pagamento tramite bonifico ISO20022 per la Svezia        |
| **Aree del prodotto interessate**         | Contabilità fornitori                                               |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="radio-frequency-identifier"></a>Identificatore di radiofrequenza

RFID (Radio Frequency Identification) è una tecnologia di raccolta dei dati che consente la memorizzazione dei dati di identificazione all'interno di tag elettronici e l'acquisizione di tali dati mediante un lettore senza requisito di portata ottica.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Basso utilizzo cliente e set di funzionalità limitato.   |
| **Sostituita da un'altra funzionalità?**   | No                                              |
| **Aree del prodotto interessate**         | Gestione inventario                            |
| **Stato**                         | Rimosso a partire da Dynamics 365 for Operations 1611. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Report sulla numerazione delle fatture con stato per la Lettonia

La legislazione lettone fornisce regole specifiche sulla numerazione delle fatture di vendita. La funzionalità consente di assegnare numeri specifici alle fatture di vendita, in base all'utente o al gruppo utenti. È quindi possibile generare un report o un file XML. È inoltre possibile stampare un report relativo ai numeri di fattura utilizzati.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La numerazione di fatture con stato non deve essere più gestito. Il report sui numeri di fattura utilizzati non è più necessario. |
| **Sostituita da un'altra funzionalità?**   | No       |
| **Aree del prodotto interessate**         | Contabilità clienti    |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Impostare i nomi del responsabile e del contabile generale di una società per la Lituania

I nomi del responsabile e del contabile generale di una società possono essere specificati nelle informazioni sulla società e utilizzati negli stampati dei diversi report locali.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituita da un'altra funzionalità                                     |
| **Sostituita da un'altra funzionalità?**   | Sì, l'impostazione dei funzionari può essere utilizzata per lo stesso scopo.   |
| **Aree del prodotto interessate**         | contabilità fornitori, contabilità clienti, gestione contanti e banca |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.  |

### <a name="shipping-carrier-interface"></a>Interfaccia del vettore di spedizione

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Funzionalità duplicata.   |
| **Sostituita da un'altra funzionalità?**   | Parzialmente sostituito da Gestione trasporto |
| **Aree del prodotto interessate**         | Vendite e marketing, gestione inventario  |
| **Stato**                         | Rimosso a partire da Dynamics 365 for Operations versione 1611.  |

### <a name="telepay-payment-formats-for-norway"></a>Formati di pagamento Telepay per la Norvegia

I formati di pagamento Telepay includono l'esportazione dei pagamenti fornitori (bonifico) e il recupero dei pagamenti clienti (addebito diretto).

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.                                                        |
| **Sostituita da un'altra funzionalità?**   | Sì, il formato di pagamento con bonifico ISO20022 e il formato di pagamento cliente AvtaleGiro per la Norvegia |
| **Aree del prodotto interessate**         | Contabilità fornitori, contabilità clienti                                                          |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Formati di esportazione pagamenti fornitori per la Finlandia

Due formati per l'esportazione dei pagamenti disponibili per la Finlandia. LM02 (FI) viene utilizzato per i pagamenti nazionali e LUM2 (FI) viene utilizzato per i pagamenti esteri.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I formati di pagamento non sono più utilizzati.                        |
| **Sostituita da un'altra funzionalità?**   | Sì, formato di pagamento tramite bonifico ISO20022 per la Finlandia       |
| **Aree del prodotto interessate**         | Contabilità fornitori                                               |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="warehouse-management-ii"></a>Gestione magazzino II

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La soluzione di gestione magazzino II (WMS II) che è disponibile nel modulo di **gestione articoli** duplica la funzionalità nel modulo **gestione magazzino** che è stato rilasciato in Microsoft Dynamics AX 2012 R3.                                                                         |
| **Sostituita da un'altra funzionalità?**   | Il modulo **Gestione magazzino** che è stato rilasciato in AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 e Dynamics AX 2012 R3 CU9 sostituisce le funzionalità di gestione magazzino II. Il nuovo modulo dispone di funzionalità più avanzate e di processi di gestione magazzino più flessibili rispetto a quelli offerti nelle funzionalità Gestione magazzino II. |
| **Aree del prodotto interessate**         | Gestione articoli, vendite e marketing, approvvigionamento   |
| **Stato**                         | Rimosso a partire da Dynamics 365 for Operations versione 1611.    |

### <a name="worker-reminders-in-human-resources"></a>Promemoria lavoratore in Risorse umane

Informazioni sulle retribuzioni in Risorse umane

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Basso utilizzo                                                           |
| **Sostituita da un'altra funzionalità?**   | No                                                                  |
| **Aree del prodotto interessate**         | Risorse umane                                                     |
| **Stato**                         | Rimosso a partire da Dynamics 365 for Operations versione 1611 |

### <a name="workflow-for-creating-goals"></a>Flusso di lavoro per creare obiettivi

Un flusso di lavoro per la gestione della creazione degli obiettivi dei dipendenti è uno dei diversi flussi di lavoro che hanno reso possibile il coordinamento del processo di gestione delle prestazioni.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La gestione delle prestazioni è stata completamente riprogettata in Microsoft Dynamics 365 for Finance and Operations.     |
| **Sostituita da un'altra funzionalità?**   | La funzionalità di gestione delle prestazioni riprogettata dà maggiore controllo al contenuto degli obiettivi, alle misurazioni utilizzate per tenere traccia dello stato di avanzamento e all'allegato della documentazione di supporto. I destinatari possono essere archiviati come modelli e quindi riutilizzati. Questa funzionalità consente di impostare più rapidamente gli obiettivi supplementari per i dipendenti. |
| **Aree del prodotto interessate**         | Gestione risorse umane                 |
| **Stato**                         | Rimosso a partire da Dynamics 365 for Operations versione 1611. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Capacità di annullare le modifiche apportate a una fattura fornitore

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Miglioramento delle prestazioni        |
| **Sostituita da un'altra funzionalità?**   | No                             |
| **Aree del prodotto interessate**         | Contabilità fornitori               |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0. |

### <a name="aif-axd-and-axbc-integrations"></a>Integrazioni di AIF, di AxD e di AxBC

In Application Integration Framework (AIF), i dati possono essere scambiati ai sistemi esterni in logica di business che è esposta come servizi. Dynamics AX include i servizi basati su documenti e .NET Business Connector (AxBC). Un documento viene creato utilizzando XML. XML contiene le informazioni di intestazione aggiunte per creare un *messaggio* che è possibile trasferire da o a Dynamics AX. Esempi dei documenti comprendono gli ordini cliente e ordini fornitore. Tuttavia, quasi qualsiasi entità, ad esempio un cliente, può essere rappresentata da un documento. I servizi basati sui documenti usano le classi **Axd \<Documento\>**.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | L'architettura AIF e di AxDs non può essere ridimensionata a un servizio cloud. Si sono verificati problemi di prestazioni nell'importazione di stoccaggio.                                        |
| **Sostituita da un'altra funzionalità?**   | Questa funzionalità è sostituita dal framework esportazione/di importazione dei dati, che supporta l'importazione/esportazione di stoccaggio ricorrente. Per AxBC, si consiglia di utilizzare le tabelle effettive. |
| **Aree del prodotto interessate**         | AxDs, AxBCs e AIF   |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.   |

### <a name="billing-code-rate-scripts"></a>Script di valutazione codice di fatturazione

Gli script di fatturazione erano utilizzati per calcolare le tariffe di fatturazione per i codici di fatturazione. Questi script necessitavano di uno sviluppo personalizzato nel linguaggio di programmazione C Sharp o Visual Basic . Nella versione corrente di Dynamics AX, gli **script di valutazione codice di fatturazione** non sono supportati.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il supporto per gli script in Visual Basic o C Sharp non è stato aggiunto in Dynamics AX 7.0. |
| **Sostituita da un'altra funzionalità?**   | Nessuno                                                                                      |
| **Aree del prodotto interessate**         | Settore pubblico, Contabilità clienti                                    |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.                                                          |

### <a name="boms-without-bom-versions"></a>DBA senza versioni DBA

Se la chiave di configurazione **Versioni DBA** è stata disabilitata, le versioni delle distinte base (DBA) sono state nascoste in tutti i moduli e il sistema forzerebbe una relazione 1:1 tra i prodotti rilasciati e le DBA. La chiave di configurazione **Versioni DBA** non può essere disabilitata nella versione corrente di Dynamics AX.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Utilizzare una chiave di configurazione per controllare le versioni DBA non ridimensiona in un ambiente cloud. |
| **Sostituita da un'altra funzionalità?**   | No                                                                                      |
| **Aree del prodotto interessate**         | Gestione delle informazioni sul prodotto, gestione articoli                                    |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.                                                          |

### <a name="brazilian-bordero"></a>Bordero brasiliano

Metodo di pagamento specifico delle società brasiliane

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il supporto del metodo di pagamento Bordero brasiliano è stato interrotto dalla localizzazione brasiliana |
| **Sostituita da un'altra funzionalità?**   | No   |
| **Aree del prodotto interessate**         | Contabilità fornitori   |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="brazilian-sintegra-statement"></a>Rendiconto brasiliano di Sintegra

Rendiconto delle imposte federali dell'imposta ICMS

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questo rendiconto non è più applicabile in alcuni stati brasiliani. |
| **Sostituita da un'altra funzionalità?**   | N. Gli utenti possono utilizzare lo strumento generico di creazione report elettronici per configurare il rendiconto se richiesto in situazioni specifiche. |
| **Aree del prodotto interessate**         | Libri fiscali    |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Modalità di contingenza SCAN brasiliana per NF-e

L'ambiente di contingenza (SCAN) viene utilizzato per generare, esportare e importare lo stato di una Nota Fiscal eletrônica (NF-e) quando non è disponibile l'ambiente di Secretaria da Fazenda (SEFAZ)

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questo metodo di contingenza non è più applicabile in tutti gli stati brasiliani |
| **Sostituita da un'altra funzionalità?**   | No                                                                          |
| **Aree del prodotto interessate**         | Contabilità clienti                                                         |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.              |

### <a name="business-analyzer"></a>Business Analyzer

Questa applicazione mobile consente agli utenti di esaminare metriche commerciali principali.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questa funzionalità è stata sostituita da un'altra funzionalità.   |
| **Sostituita da un'altra funzionalità?**   | Il pacchetto di contenuto Monitorare le prestazioni finanziarie per Microsoft Power BI includerà metriche finanziarie principali precedentemente disponibili in Business Analyzer. |
| **Aree del prodotto interessate**         | Contabilità generale      |
| **Stato**                         | Deprecato: l'utilizzo di Business Analyzer è stato deprecato.    |

### <a name="business-statistics"></a>Statistiche aziendali

Consente di impostare richieste di informazioni su statistiche aziendali che possono semplificare l'analisi delle prestazioni dell'organizzazione.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Approccio precedente a business intelligence (BI), basso utilizzo del cliente e un set di funzionalità limitato |
| **Sostituita da un'altra funzionalità?**   | Nuove soluzioni BI per la versione corrente di Dynamics AX                                      |
| **Aree del prodotto interessate**         | Aapprovvigionamento, contabilità fornitori, vendite e marketing, contabilità clienti         |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Funzione di modifica della data del documento nel giornale di approvazione fatture

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Basso utilizzo                                                               |
| **Sostituita da un'altra funzionalità?**   | Sì. La data del documento nella transazione fornitore registrazione può essere modificata. |
| **Aree del prodotto interessate**         | Contabilità fornitori                                                        |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Formato pagamento ClieOp03 per i Paesi Bassi

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato non è più applicabile nei Paesi Bassi, poiché è stato sostituito da euro funzionalità di (SEPA) di l di pagamenti Single. |
| **Sostituita da un'altra funzionalità?**   | Esportazione pagamenti SEPA  |
| **Aree del prodotto interessate**         | Tutti i moduli     |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.   |

### <a name="compliance-center"></a>Centro conformità

Il centro conformità è un sito Enterprise Portal per gestire i requisiti della documentazione per le iniziative di conformità correlate alla legge di Sarbanes-Oxley.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Mancanza di utilizzo del cliente. Microsoft SharePoint include la stessa funzione che è disponibile nel centro conformità. |
| **Sostituita da un'altra funzionalità?**   | No   |
| **Aree del prodotto interessate**         | Controlli interni e di conformità  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.    |

### <a name="connector-for-microsoft-dynamics"></a>Connettore per Microsoft Dynamics

Questo strumento è stato utilizzato per integrare i dati di chiave da Microsoft Dynamics CRM alle applicazioni Microsoft Dynamics ERP.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questa funzionalità è stata sostituita da un'altra funzionalità. |
| **Sostituita da un'altra funzionalità?**   | Common Data Service                                      |
| **Aree del prodotto interessate**         | Connettore per Microsoft Dynamics                         |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Unità contenitore e modello multi-dimensionale disponibili

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Funzionalità duplicata. |
| **Sostituita da un'altra funzionalità?**   | Sì. Da AX 2012, questa funzionalità è stata sostituita dal set di funzionalità di ordini batch consolidati. Il set di funzionalità include la visualizzazione della disponibilità consolidata. |
| **Aree del prodotto interessate**         | Gestione delle informazioni sul prodotto, controllo produzione, gestione articoli, vendite e marketing  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0. |

### <a name="cue-group-metadata"></a>Metadati gruppo Cue

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I gruppi Cue sono stati utilizzati per visualizzare uno o più Cue nell'area di Dettaglio informazioni. Vi era un assorbimento è limitato e anche problematiche di prestazioni, poiché registrare la modifica in un modulo padre ha causato una query per Cue nel gruppo Cue. |
| **Sostituita da un'altra funzionalità?**   | No      |
| **Aree del prodotto interessate**         | Tutti i moduli    |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.  |

### <a name="cue-metadata"></a>Metadati Cue

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I metadati Cue sono stati limitati alle informazioni di conteggio o somma.    |
| **Sostituita da un'altra funzionalità?**   | I metadati della sezione sono stato introdotti per dare più flessibilità per la modellizzazione. Ad esempio, è possibile modellare i conteggi correnti, la navigazione e gli indicatori di prestazioni chiave (KPI). I metadati della sezione di conteggio sono la sostituzione diretta dei metadati Cue. |
| **Aree del prodotto interessate**         | Tutti i moduli           |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0      |

### <a name="danish-check-format"></a>Formato assegno italiano

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il supporto al layout di formato dell'assegno danese è stato interrotto e il report è stato rimosso da localizzazione DK. |
| **Sostituita da un'altra funzionalità?**   | No    |
| **Aree del prodotto interessate**         | Tutti i moduli    |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.  |

### <a name="data-partitions"></a>Partizioni di dati

Le partizioni di dati forniscono una separazione logica di dati nel database di Microsoft Dynamics AX.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Le partizioni di dati sono state introdotte in Microsoft Dynamics AX 2012 R2 per abilitare l'isolamento dei dati. In uno scenario comune, una società ha affiliate e i dati di una filiale non devono essere visibili in un'altra filiale, anche se entrambe le filiali sono gestite dallo stesso reparto IT. Tuttavia, un sovraccarico di gestione e script aggiuntivi nel programma erano necessari per creare nuove partizioni e popolarle con i dati e per eseguire il backup dei dati della partizione. Nel cloud, dove si ha accesso ai servizi di database di piattaforma distribuita come servizio (PaaS) (Database SQL di Microsoft Azure), è molto più efficiente utilizzare un database come contenitore di isolamento rispetto all'isolamento nel programma. Indipendentemente dal fatto che il partizionamento dei dati sia necessario per le filiali, per più tenant o semplicemente per esigenze di scalabilità, crediamo che gli scenari possano essere gestiti meglio tramite più istanze di Finance and Operations. |
| **Sostituita da un'altra funzionalità?**   | I clienti che utilizzano partizioni di dati devono utilizzare più istanze di Finance and Operations se la separazione del livello del database è fondamentale.    |
| **Aree del prodotto interessate**         | Tutti i moduli  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Archiviazione nel database e nella condivisione file per gli allegati

Microsoft Dynamics AX 2012 ha consentito l'archiviazione degli allegati nel database e nelle condivisioni file. Entrambe tali opzioni non sono più supportate.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | L'archiviazione nella condivisione dei file non è più supportata in quanto gli ambienti ospitati nel cloud non possono comunicare con le condivisioni file locali. L'archiviazione del database è stata deprecata a favore dell'archivio BLOB di Azure. L'archivio BLOB di Azure equivale all'archiviazione nel database, poiché i documenti sono accessibili solo tramite i moduli del client Dynamics 365 for Finance and Operations. In questo modo si ha il vantaggio aggiuntivo di fornire archiviazione senza influire negativamente sulle prestazioni del database. L'archivio BLOB è il meccanismo di archiviazione predefinito per la gestione di documenti e funziona immediatamente. |
| **Sostituita da un'altra funzionalità?**   | L'archiviazione del database è stata deprecata a favore dell'archivio BLOB di Azure.   |
| **Aree del prodotto interessate**         | Tutti i moduli  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.   |

### <a name="delimitation"></a>Delimitazione

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Non utilizzare la funzione è stato cercato. |
| **Sostituita da un'altra funzionalità?**   | No                                     |
| **Aree del prodotto interessate**         | Orario e presenze                    |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.         |

### <a name="desktop-client"></a>Client desktop

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | L'esperienza client di Dynamics AX è stata riprogettata per migliorare la facilità d'uso tra più piattaforme e dispositivi.                      |
| **Sostituita da un'altra funzionalità?**   | Il nuovo web client è basato sui metadati e il modello di programmazione desktop del modulo modificati per fornire una ricca piattaforma web. |
| **Aree del prodotto interessate**         | Tutti i moduli  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.   |

### <a name="direct-database-connection"></a>Connessione diretta al database

In Dynamics AX 2012 R3, Retail Modern POS poteva connettersi direttamente al database canale in modo simile a Enterprise POS. Questa funzionalità costitutiva un'aggiunta al metodo standard di comunicazione di Retail Modern POS che comunica tramite il server Retail.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La connettività diretta del database richiedeva i protocolli di protezione minimi ed era principalmente utilizzata per ottenere i massimi livelli delle prestazioni. A causa dei miglioramenti di protezione e delle prestazioni di Finance and Operations, questa funzionalità ora comporta più problemi che vantaggi. |
| **Sostituita da un'altra funzionalità?**   | N. È ora supportata solo la comunicazione standard del server Retail.  |
| **Aree del prodotto interessate**         | Database canale/Retail Modern POS   |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.  |

### <a name="dutch-swift-mt940"></a>SWIFT olandese MT940

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La funzionalità generica ora viene utilizzata anziché la funzionalità localizzata.                    |
| **Sostituita da un'altra funzionalità?**   | Sì, questa funzionalità viene sostituita con la funzionalità avanzata di riconciliazione estratti conto. |
| **Aree del prodotto interessate**         | Tutti i moduli                                                                              |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL per la Germania)

Questa funzionalità forniva l'output XBRL (eXtensible Business Reporting Language) in modo specifico per la tassonomia tedesca di eBilanz.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Mancanza di utilizzo del cliente  |
| **Sostituita da un'altra funzionalità?**   | Questa funzionalità non è stata sostituita, ma diversi pacchetti XBRL specializzati che forniscono funzionalità XBRL avanzate sono disponibili per il mercato tedesco. |
| **Aree del prodotto interessate**         | Management Reporter      |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.  |

### <a name="enterprise-portal-client"></a>Client Enterprise Portal

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Una singola piattaforma cliente è stata fornita.  |
| **Sostituita da un'altra funzionalità?**   | Il nuovo web client è basato sui metadati e il modello di programmazione desktop del modulo modificati per fornire una ricca piattaforma web. |
| **Aree del prodotto interessate**         | Tutti i moduli  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.   |

### <a name="environmental-sustainability"></a>Sostenibilità ambientale

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Basso utilizzo cliente e set di funzionalità limitato  |
| **Sostituita da un'altra funzionalità?**   | No              |
| **Aree del prodotto interessate**         | Modulo Controlli interni e di conformità, contabilità fornitori  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0. |

### <a name="form-activex-and-managed-host-controls"></a>Modulo ActiveX e controlli host gestiti

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | ActiveX e i controlli host vengono gestiti in sul client desktop deprecato. |
| **Sostituita da un'altra funzionalità?**   | Il frameword dei controlli estendibili supporta la creazione di nuovi controlli basati su HTML, CSS e JavaScript ed è un controllo di prima classe nell'ambente Microsoft Visual Studio Tooling. |
| **Aree del prodotto interessate**         | Tutti i moduli     |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Generare notifiche anticipate utilizzando un batch

La creazione della notifica anticipata non può essere effettuata operazione utilizzando un batch ma può comunque essere effettuata da un utente.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Non esiste alcun modulo per salvare in modo permanente e visualizzare il file risultante di notifica anticipata quando viene generato utilizzando un batch. |
| **Sostituita da un'altra funzionalità?**   | Le notifiche anticipate possono ancora essere generate e l'utente ha controllo sul percorso di salvataggio del file.   |
| **Aree del prodotto interessate**         | contabilità fornitori, contabilità clienti, gestione contanti e banca  |
| **Stato**                         | Rimosso a partire da AX 7.0.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Esportazione di pagamento di DTAUS e importazione di estratto conto tedesco (totali e transazioni)

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato non è più applicabile in Germania, poiché è stato sostituito dalla funzionalità SEPA.                    |
| **Sostituita da un'altra funzionalità?**   | Sì, questa funzionalità è stata sostituita dall'esportazione di pagamento SEPA e dalla funzionalità avanzata di riconciliazione estratti conto per importare gli estratti conto. |
| **Aree del prodotto interessate**         | Tutti i moduli  |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="german-dtazv-payment-format"></a>Formato di pagamento tedesco di DTAZV

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato non è più applicabile in Germania, poiché è stato sostituito dalla funzionalità SEPA. |
| **Sostituita da un'altra funzionalità?**   | Esportazione pagamenti SEPA    |
| **Aree del prodotto interessate**         | Tutti i moduli   |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.    |

### <a name="german-mt940-import"></a>Importazione tedesca MT940

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La funzionalità generica ora viene utilizzata anziché la funzionalità localizzata.                    |
| **Sostituita da un'altra funzionalità?**   | Sì, questa funzionalità viene sostituita con la funzionalità avanzata di riconciliazione estratti conto. |
| **Aree del prodotto interessate**         | Tutti i moduli                                                                              |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.                           |

### <a name="german-xml-eu-sales-list"></a>Elenco vendite XML tedesco

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il formato XML della dichiarazione Elenco vendite UE per la Germania non è più supportato. Solo il formato del file di testo ELMA5 può essere utilizzato per inviare il report Elenco vendite UE all'ufficio imposte tedesco. |
| **Sostituita da un'altra funzionalità?**   | No         |
| **Aree del prodotto interessate**         | Imposta sul reddito        |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.   |

### <a name="gl-ssrs-reports"></a>Report GL SSRS

Report che includono le seguenti voci di menu sono stati rimossi: **Bilancio di verifica riepilogativo**, **Bilancio di verifica dettagliato**, **Piano dei conti**, **Audit trail**, **Saldi** e **Elenco saldi**.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I report finanziari di Microsoft SQL Server il Reporting Services (SSRS) sono stati sostituiti dalle funzionalità di Management Reporter e i report predefiniti. |
| **Sostituita da un'altra funzionalità?**   | Management Reporter (contrassegnato **Report finanziario** nella versione corrente di Dynamics AX)    |
| **Aree del prodotto interessate**         | Contabilità generale   |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.   |

### <a name="infopart-and-formpart-metadata"></a>I metadati di FormPart e di InfoPart

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I metadati di FormPart e di InfoPart hanno abilitato la creazione dei riquadri dettaglio informazioni per due diversi client. |
| **Sostituita da un'altra funzionalità?**   | I metadati di InfoPart, che erano una definizione semplificata del modulo, vengono convertiti nel modulo di lavorazione con utensili di aggiornamento. I metadati di FormPart, che facevano riferimento un modulo, sono sostituiti da un riferimento più diretto creato mediante tooling di aggiornamento. |
| **Aree del prodotto interessate**         | Tutti i moduli    |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.        |

### <a name="main-account-list-page"></a>Conti principali (pagina elenco)

Un elenco dei conti per la persona giuridica e le informazioni correlate bilanciate

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Le informazioni bilanciate sono disponibili **Bilancio di verifica** nella pagina elenco il conto e la dimensione.  |
| **Sostituita da un'altra funzionalità?**   | **Conti principali** contiene lo stesso elenco dei conti dalla **Conto principale** pagina elenco è contenuto. La visualizzazione griglia in **Conti principali** e viene visualizzato un nuovo più piccola, visualizzare il tipo di griglia. |
| **Aree del prodotto interessate**         | Contabilità generale      |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Report del flusso di cassa bancario di Singapore e Malesia

Questa funzionalità di stampare un report del flusso di cassa bancario contenente le transazioni e i dettagli delle entrate e uscite di cassa relative a un intervallo di date specifico per i conti bancari selezionati.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Le stesse informazioni possono essere ottenute dalla transazione bancaria di indagine. |
| **Sostituita da un'altra funzionalità?**   | Transazione bancaria di indagine                                            |
| **Aree del prodotto interessate**         | Gestione cassa e banche                                                |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità.          |

### <a name="mexican-cfd-electronic-invoice"></a>Fattura elettronica CFD messicana

Questa funzionalità consentiva la generazione di fatture elettroniche messicane utilizzando il metodo CFD (Comprobante Fiscal Digital), in cui la società firma la fattura richiedendo l'autorizzazione correlata al governo. Questa funzionalità include inoltre un report mensile che include tutte le fatture elettroniche emesse nel periodo.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il metodo non viene più applicabile. La generazione di fatture elettroniche utilizzando il metodo di CFD è stata deprecata dagli uffici tributari ed è stata sostituita da Comprobante Digital fiscale un metodo di de Internet (CFDI) di través, in cui la firma è delegata il fornitore di terze parti (PAC). Il report mensile è stato rimosso e un'opzione di richiesta consente agli utenti di richiedere informazioni sulle transazioni dello storico. |
| **Sostituita da un'altra funzionalità?**   | No    |
| **Aree del prodotto interessate**         | Effetti attivi di conto, progetto   |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="mexico-realized-and-unrealized-vat"></a>Messico ha eseguito e L'VAT non realizzata

Microsoft Dynamics AX 2012 gestiva l'imposta sul valore aggiunto non realizzata (IVA) tramite la funzionalità specifica del Messico per l'imposta non realizzata.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Funzionalità duplicata.  |
| **Sostituita da un'altra funzionalità?**   | Sì, sostituita dalla funzionalità IVA condizionata che viene fornita dalle funzioni di base. |
| **Aree del prodotto interessate**         | Imposta sul reddito   |
| **Stato**                         | Deprecato: la data di eliminazione non è stata impostata per questa funzionalità. |

### <a name="microsoft-outlook-integration"></a>Integrazione di Microsoft Outlook


|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questa funzionalità è stata sostituita dall'integrazione di Microsoft Exchange Server. |
| **Sostituita da un'altra funzionalità?**   | Sì                                                                            |
| **Aree del prodotto interessate**         | Vendite e marketing                                                            |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Blocco privato di magazzino e giornali di registrazione di gestione magazzino

Giornali di registrazione magazzino e delle scorte più supporto la capacità di contrassegnare un giornale di registrazione come privato per un utente selezionato. Solo il processo di registrazione di blocco come privato per gruppi di utenti e blocco durante la modifica è supportato.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Non utilizzare la funzione è stato cercato. |
| **Sostituita da un'altra funzionalità?**   | No                                     |
| **Aree del prodotto interessate**         | Gestione inventario                   |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.         |

### <a name="product-builder"></a>Configuratore prodotti

Configuratore prodotti è stato utilizzato per configurare dinamicamente gli articoli da un ordine cliente, un'offerta di vendita, un ordine di produzione, un'offerta di progetto, una richiesta articolo. In base a un modello prodotto che ha effettuato variabili di modellizzazione, l'utente può selezionare i valori per soddisfare i requisiti del cliente e per ottenere una variante prodotto univoco che ha effettuato una DBA e il ciclo di lavorazione.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il Configuratore prodotti ha esposto il codice X++ agli utenti finali e non è supportato la versione corrente di Dynamics AX. È stato rimosso per evitare gli sforzi duplicati in codebase sovrapposti e di grandi dimensioni.  |
| **Sostituita da un'altra funzionalità?**   | Sì. La configurazione basata su vincoli era stata introdotta in Dynamics AX 2012 in cui il deprecamento del Configuratore prodotti in versioni future era già stata annunciata. La tecnologia basata su vincoli di configurazione è selezionata nelle rappresentazioni generali prodotto per consentire la configurazione. Per ulteriori informazioni, vedere [Creare un modello di configurazione prodotto](../../supply-chain/pim/build-product-configuration-model.md). |
| **Aree del prodotto interessate**         | Gestione delle informazioni sul prodotto, vendite e marketing  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.      |

### <a name="production-floor-app"></a>App area di produzione
Si tratta dell'app per tablet con Windows RT 8.1 e Windows 8.1 Pro.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Con la modifica di un client basato sul Web, è possibile fornire una funzionalità simile mediante il client nativo di Dynamics AX 7.0. Il dispositivo schede processo fornisce un'interfaccia utente del piano di produzione ottimizzata per i fattori di modulo e tocco. |
| **Sostituita da un'altra funzionalità?**   | Sì. Il dispositivo schede processo, che è una parte nativa di Dynamics AX 7.0.                                                                           |
| **Aree del prodotto interessate**         | Controllo produzione                                                |
| **Stato**                         | Deprecato: una data di rimozione dal Microsoft Store non è ancora stata definita per questa funzionalità.                                                |


### <a name="rename-product-dimension"></a>Rinomina dimensione prodotto

Questa funzionalità consente di modificare il nome di una delle tre dimensioni prodotto standard (dimensione, colore o stile) con un nome più adatto ai requisiti aziendali. Rinominare è incluso tutte le etichette in cui il nome della dimensione prodotto è stato utilizzato.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La versione corrente di Dynamics AX non supporta le modifiche etichette in fase di esecuzione. |
| **Sostituita da un'altra funzionalità?**   | No                                                                            |
| **Aree del prodotto interessate**         | Gestione informazioni sul prodotto                                                |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.                                                |

### <a name="retail-server-connectivity-using-http"></a>Connettività al server Retail mediante HTTP

In Dynamics AX 2012 R3, il server Retail poteva essere eseguito mediante la comunicazione HTTP (non protetta). Questa funzionalità costituiva un'aggiunta alla comunicazione standard mediante HTTPS.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | A causa dei nuovi requisiti di sicurezza, è ora supportata solo la comunicazioni tramite TLS 1.2 (o superiore, se disponibile). Il programma di installazione self-service configurerà automaticamente il computer per questo tipo di comunicazione. |
| **Sostituita da un'altra funzionalità?**   | N. È ora supportata solo la comunicazione HTTPS standard del server Retail. |
| **Aree del prodotto interessate**         | Server vendita al dettaglio  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0. |

### <a name="role-center-pages"></a>Centri gestione ruolo

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Le pagine Centro gestione ruolo sono state sviluppate sulla piattaforma deprecata Enterprise Portal, che è stata sostituita da nuova piattaforma web client nella versione corrente di Dynamics AX. |
| **Sostituita da un'altra funzionalità?**   | Il nuovo modello di modulo dell'area di lavoro fornisce agli utenti la progettazione processo-centrica che consente l'accesso semplice alle attività usate comunemente all'interno di tale processo.                       |
| **Aree del prodotto interessate**         | Tutti i moduli    |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0   |

### <a name="sales-tax-jurisdictions"></a>Uffici IVA competenti

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Basso utilizzo cliente e set di funzionalità limitato |
| **Sostituita da un'altra funzionalità?**   | No                                           |
| **Aree del prodotto interessate**         | IVA per gli Stati Uniti                                 |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.               |

### <a name="sites-services"></a>Sites Services

La funzionalità Sites Services consente di costruire i siti Web che estendono i processi aziendali in Internet senza supporto IT.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | L'infrastruttura di Microsoft Azure utilizzata da Dynamics AX ha nuove funzionalità che è possibile utilizzare in alternativa, ad esempio siti di Azure. |
| **Sostituita da un'altra funzionalità?**   | No   |
| **Aree del prodotto interessate**         | Selezione del personale, gestione dei casi, richiesta di offerta, registrazione fornitore, aree di lavoro collaborative per opportunità e campagne  |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.    |

### <a name="ssas-demand-forecasting-strategy"></a>Strategia di previsione della domanda SSAS

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | La struttura della funzionalità non può essere supportata nella nuova architettura cloud. |
| **Sostituita da un'altra funzionalità?**   | Strategia di previsione della domanda Azure Machine Learning                           |
| **Aree del prodotto interessate**         | Pianificazione generale                                                              |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Pool di fatture fornitore esclusi i dettagli di registrazione

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Basso utilizzo Questa funzionalità è stata sostituita dal giornale di registrazione fatture che risponde di funzionalità del flusso di lavoro. |
| **Sostituita da un'altra funzionalità?**   | Funzionalità del flusso di lavoro del giornale di registrazione fatture.     |
| **Aree del prodotto interessate**         | Contabilità fornitori |
| **Stato**                         | Rimosso a partire da Dynamics AX 7.0.    |


### <a name="virtual-company-accounts"></a>Account società virtuali

La funzionalità virtuale di più società non è supportata in Dynamics AX. La funzionalità relativa alle società virtuali consente agli utenti di impostare le tabelle da condividere da un insieme di società. Per una descrizione della funzionalità, vedere [Account società e account società virtuali](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). Il funzionamento della funzionalità delle tabelle di raggruppamento le attività assegnate alle società virtuali, ovvero gruppi di società “reali„ esistenti. Le query vengono creati in modo che tutte società nella società virtuale possano accedere ai dati nelle tabelle delle raccolte di tabelle associate.

|   |  | 
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | - Le società virtuali devono essere configurate prima che i dati vengano archiviati nelle tabelle. La modifica delle società virtuali in un'implementazione esistente è molto difficile.<br><br>- Poiché nella versione corrente di Dynamics AX la normalizzazione dei dati è così elevata, è diventato difficile conoscere gli elementi da aggiungere alle raccolte di tabelle. Ad esempio, è difficile conoscere le tabelle da condividere. È necessario inoltre aggiungere tutte le tabelle a cui fanno riferimento le tabelle presenti in una società virtuale. A causa della normalizzazione delle tabelle, anche i semplici dati master distribuiti in più tabelle devono far parte della società virtuale. Tutti gli errori provocheranno problemi funzionali.<br><br>- Quando una tabella fa parte di una società virtuale, perde le informazioni sull'origine dei dati e solo la società virtuale viene registrata.   |
| **Sostituita da un'altra funzionalità?** | Le tabelle globali possono essere utilizzate per rendere accessibili le tabelle da tutte le società. Attualmente, non esiste alcuna sostituzione. |   
| **Aree del prodotto interessate**       | Tutti i moduli |   
| **Stato**                       | Rimosso a partire da Dynamics AX 7.0.   |   

### <a name="windows-8-tablet-app"></a>App tablet di Windows 8

L'app tablet di Windows 8 ha fornito la funzionalità per la voce e l'approvazione di spesa.

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Finance and Operations è compatibile con i tablet. L'app tablet non è più richiesta.    |
| **Sostituita da un'altra funzionalità?**   | N.          |
| **Aree del prodotto interessate**         | Gestione spese   |
| **Stato**                         | Rimosso: questa funzionalità è disponibile solo per Dynamics AX 2012 R3. |

### <a name="workplanner"></a>Pianificazione lavori

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Basso utilizzo |
| **Sostituita da un'altra funzionalità?**   | No, ma la pagina **Relazione profilo**, aperta dalla pagina **Gruppi di profili**, supporta lo stesso scenario aziendale della pagina **Pianificazione lavori** deprecata. |
| **Aree del prodotto interessate**         | Orario e presenze     |
| **Stato**                         | Il codice non è stato rimosso. Tuttavia, per il modulo, JmgWorkPlanner, non è stata eseguita la migrazione.    |

### <a name="x-financial-statements"></a>Rendiconti finanziari X++

|                                                 |                                                                                                          |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>Motivo del deprecamento/rimozione</strong> |                         Questa funzionalità è stata sostituita da un'altra funzionalità.                         |
|  <strong>Sostituita da un'altra funzionalità?</strong>  | Management Reporter (contrassegnato <strong>Report finanziario</strong> nella versione corrente di Dynamics AX) |
|     <strong>Aree del prodotto interessate</strong>     |                                              Contabilità generale                                              |
|             <strong>Stato</strong>             |                                      Rimosso a partire da Dynamics AX 2012                                      |

