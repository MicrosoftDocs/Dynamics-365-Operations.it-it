---
title: "Funzionalità deprecate"
description: "In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione."
author: sericks007
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 6
ms.translationtype: HT
ms.sourcegitcommit: 9ee81bbdd22fed4ef6ea97080fe1f6b3d82bcaf5
ms.openlocfilehash: ee051bbf50a6124fe1700a244b36b5f9c599e714
ms.contentlocale: it-it
ms.lasthandoff: 11/06/2017

---

# <a name="deprecated-features"></a>Funzionalità deprecate

[!include[banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità che sono state o che verranno rimosse da Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

## <a name="features-that-have-been-deprecated-in-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Funzionalità che sono state deprecate in Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017) con l'aggiornamento piattaforma 8

### <a name="warehouse-mobile-devices-portal"></a>Portale dei dispositivi mobili del magazzino

Il Portale dei dispositivi mobili del magazzino è un componente autonomo progettato per la distribuzione automatica locale. Questo componente non è più supportato in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Un app nativa che migliora l'esperienza utente ha sostituito la funzionalità Portale dei dispositivi mobili del magazzino. 

|                                  |                                                 |
|----------------------------------|-------------------------------------------------|
| **Motivo del deprecamento**       | Funzionalità duplicata.                        |
| **Sostituita da un'altra funzionalità?** | Sì. Questa funzionalità è stata sostituita da Finance and Operations - Magazzino. Per ulteriori informazioni sull'impostazione e sui prerequisiti, vedere [Installare e configurare Microsoft Dynamics 365 for Finance and Operations - Magazzino](../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Moduli interessati**             | Gestione magazzino, Gestione trasporto |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Regola avanzata di abbinamento di riconciliazione estratti conto per la corrispondenza manuale

Una regola di abbinamento è stata utilizzata per selezionare e contrassegnare un documento bancario durante la corrispondenza manuale dei documenti nel foglio di lavoro di riconciliazione.

|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Utilizzo limitato.                                                                         |
| **Sostituita da un'altra funzionalità?** | N. Le capacità di filtro della colonna devono essere utilizzate per individuare i documenti per la riconciliazione. |
| **Moduli interessati**             | Gestione cassa e banche                                                               |

### <a name="windows-8-tablet-app"></a>App tablet di Windows 8

L'app tablet di Windows 8 ha fornito la funzionalità per la voce e l'approvazione di spesa.

|                                  |                                                                                          |
|----------------------------------|------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Finance and Operations è compatibile con i tablet. L'app tablet non è più richiesta. |
| **Sostituita da un'altra funzionalità?** | N.                                                                                      |
| **Moduli interessati**             | Gestione spese                                                                       |


## <a name="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3"></a>Le funzionalità che sono state deprecate in Dynamics 365 per le operazioni 1611 con l'aggiornamento piattaforma 3

### <a name="aeb-payment-formats-for-spain"></a>Formati di pagamento AEB per la Spagna

I formati di pagamento Consejo Superior Bancario vengono utilizzati per inviare i file di rimessa alla banca per i pagamenti dei clienti e i pagamenti fornitore. Il contenuto di questi formati è determinato dalla Asociación Española de Banca. Copre Cuaderno 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| **Motivo del deprecamento**       | I formati di pagamento non sono più utilizzati.                                  |
| **Sostituita da un'altra funzionalità?** | Sì, i formati per i pagamenti tramite bonifico ISO20022 e in addebito diretto per la Spagna |
| **Moduli interessati**             | Contabilità fornitori, contabilità clienti                                    |

### <a name="bank-payments-transfer-for-lithuania"></a>Trasferimento di pagamenti bancari per la Lituania

I trasferimenti di pagamento bancario vengono generati e stampati utilizzando il formato di esportazione del trasferimento di pagamento (LT) per la Lituania. Il mercato lituano ha iniziato a utilizzare LITAS, il sistema unificato di E-banking, nel 2005.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| **Motivo del deprecamento**       | I formati di pagamento non sono più utilizzati.                    |
| **Sostituita da un'altra funzionalità?** | Sì, formato di pagamento tramite bonifico ISO20022 per la Lituania |
| **Moduli interessati**             | Contabilità fornitori                                           |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Formati di pagamento BBS Direkte Remittering per la Norvegia

I formati di pagamento BBS Direkte Remittering includono l'esportazione dei pagamenti recuperati dai clienti (addebito diretto) e l'importazione dei messaggi di reso.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | I formati di pagamento non sono più utilizzati.                                                                                                                        |
| **Sostituita da un'altra funzionalità?** | Il formato di pagamento cliente AvtaleGiro per la Norvegia può essere utilizzato per generare i messaggi di addebito diretto. L'importazione di un messaggio di reso è implementata nelle versioni future. |
| **Moduli interessati**             | Contabilità fornitori, contabilità clienti                                                                                                                          |

### <a name="chart-of-accounts-tool-for-spain"></a>Strumento piano dei conti per la Spagna

Lo strumento viene utilizzato quando un piano dei conti in Spagna richiede modifiche importanti. Gli utenti possono importare un nuovo piano dei conti in formato testo o Microsoft Excel, oltre a rendiconti finanziari.

|                              |                |
|------------------------------|----------------|
| **Motivo del deprecamento**       | Utilizzo limitato  |
| **Sostituita da un'altra funzionalità?** | Nessuna             |
| **Moduli interessati**             | Contabilità generale |

### <a name="dom80-payment-format-for-belgium"></a>Formato di pagamento Dom80 per il Belgio

Formato di pagamento precedente per il Belgio per il recupero dei pagamenti (addebito diretto).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo del deprecamento**      | Il formato di pagamento non è più utilizzato.                  |
| **Sostituita da un'altra funzionalità?** | Sì, formato di pagamento in addebito diretto ISO 20022 per il Belgio |
| **Moduli interessati**            | Contabilità clienti                                    |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formati di pagamento DTA/EZAG per la Svizzera

I formati DTA/EZAG sono integrati nel sistema PVR, poiché possono riportare il numero di riferimento. Poiché il numero di riferimento non è obbligatorio, questi formati possono essere utilizzati per elaborare i pagamenti fornitore. Questi formati sono utilizzati dalle società con un conto bancario in un percorso diverso da "Postfinance".

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| **Motivo del deprecamento**       | I formati di pagamento non sono più utilizzati.                      |
| **Sostituita da un'altra funzionalità?** | Sì, formato di pagamento tramite bonifico ISO20022 per la Svizzera |
| **Moduli interessati**             | Contabilità fornitori                                             |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Formato di pagamento EDIFACT-DIRDEB per l'Austria

Formato di pagamento EDIFACT-DIRDEB per il recupero dei pagamenti (addebito diretto).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato di pagamento non è più utilizzato.                  |
| **Sostituita da un'altra funzionalità?** | Sì, formato di pagamento in addebito diretto ISO 20022 per l'Austria |
| **Moduli interessati**             | Contabilità clienti                                    |

### <a name="edivat-for-belgium"></a>EDIVAT per il Belgio

EDIVAT è uno standard belga obsoleto per la dichiarazione tramite posta elettronica protetta. Microsoft Dynamics AX 2012 mantiene la soluzione di sola lettura per consentire l'accesso ai dati dello storico.

|                              |                                      |
|------------------------------|--------------------------------------|
| **Motivo del deprecamento**       | La funzionalità non è più utilizzata. |
| **Sostituita da un'altra funzionalità?** | Nessuna                                   |
| **Moduli interessati**             | Contabilità generale                       |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>Formato di importazione dei pagamenti eGiro EDIFACT CREMUL per la Norvegia

eGiro si basa sullo standard internazionale UN EDIFACT CREMUL, (Multiple Credit Advice Message) utilizzato per la registrazione automatica dei pagamenti cliente. In Microsoft Dynamics AX eGiro è implementato come formato di importazione dei pagamenti cliente.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato di pagamento non è più utilizzato.                                                     |
| **Sostituita da un'altra funzionalità?** | N. Il formato verrà sostituito dai formati di importazione dei rendiconti ISO 20022 nelle versioni future. |
| **Moduli interessati**             | Contabilità clienti                                                                       |

### <a name="external-inventory-for-poland"></a>Inventario esterno per la Polonia

Prova delle merci prese da un fornitore per le vendite senza acquisto. Le merci gestite in inventario esterno non hanno impatto sull'inventario standard e possono essere vendute e acquistate automaticamente. Questo processo crea movimenti di scorte effettive.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| **Motivo del deprecamento**       | Sostituita da un'altra funzionalità                     |
| **Sostituita da un'altra funzionalità?** | Sì, la funzionalità core di spedizione in entrata |
| **Moduli interessati**             | Contabilità fornitori, Gestione inventario          |

### <a name="financial-reports-generator-for-eastern-europe"></a>Generatore di report finanziari nell'Europa dell'Est

Strumento per impostare la raccolta dei dati per i report fiscali e contabili ed esportare i dati nei modelli di report XLS e DOC.

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Utilizzo limitato                                                                            |
| **Sostituita da un'altra funzionalità?** | N. Lo strumento verrà sostituito nelle versioni future dalle configurazioni dei report elettronici. |
| **Moduli interessati**             | Contabilità generale                                                                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Importazione delle transazioni di pagamento dei clienti per la Finlandia

È possibile selezionare un formato di importazione per i pagamenti finlandesi per includere le transazioni di pagamento dei clienti da un file esterno fornito dalla banca.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato di pagamento non è più utilizzato.                                                     |
| **Sostituita da un'altra funzionalità?** | N. Il formato verrà sostituito dai formati di importazione dei rendiconti ISO 20022 nelle versioni future. |
| **Moduli interessati**             | Contabilità clienti                                                                       |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Importazione delle transazioni di pagamento in un giornale di registrazione contabile per la Finlandia

Un formato specifico per la Finlandia viene utilizzato per importare le transazioni contabili nella contabilità generale.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato di pagamento non è più utilizzato.                                                     |
| **Sostituita da un'altra funzionalità?** | N. Il formato verrà sostituito dai formati di importazione dei rendiconti ISO 20022 nelle versioni future. |
| **Moduli interessati**             | Contabilità clienti                                                                       |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integrazione con CIS (Client Isabel Synchronizer) per il Belgio

Isabel è il framework di E-banking in Europa e uno standard di fatto in Belgio.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | L'integrazione con Client Isabel è stata interrotta.                                                                |
| **Sostituita da un'altra funzionalità?** | N. I formati di pagamento non più utilizzati verranno sostituiti dal formato di pagamento con bonifico ISO20022 per il Belgio. |
| **Moduli interessati**             | Contabilità fornitori                                                                                                     |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Modifiche al piano dei conti e alle regole contabili per la Spagna

Questa funzionalità consente delle modifiche al piano dei conti e alle regole contabili in Spagna. Traccia i conti che consentono di trasformare il precedente piano dei conti nel nuovo piano dei conti e confronta l'anno fiscale precedente con il nuovo anno fiscale, anche se sono stati registrati su numeri di conto diversi.

|                              |                |
|------------------------------|----------------|
| **Motivo del deprecamento**       | Utilizzo limitato  |
| **Sostituita da un'altra funzionalità?** | Nessuna             |
| **Moduli interessati**             | Contabilità generale |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Formato di pagamento fornitori Pagamento Fornitori

Precedente formato di pagamento italiano per i trasferimenti di credito.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato di pagamento non è più utilizzato.                  |
| **Sostituita da un'altra funzionalità?** | Sì, formato di pagamento tramite bonifico ISO20022 per l'Italia |
| **Moduli interessati**             | Contabilità fornitori                                       |

### <a name="payment-export-formats-for-estonia"></a>Formati di esportazione dei pagamenti per l'Estonia

I formati Telehansa e Teleservice vengono utilizzati per l'esportazione di pagamenti bancari.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo del deprecamento**      | I formati di pagamento non sono più utilizzati.                  |
| **Sostituita da un'altra funzionalità?** | Sì, formato di pagamento tramite bonifico ISO20022 per l'Estonia |
| **Moduli interessati**             | Contabilità fornitori                                         |

### <a name="payment-file-archive-for-norway"></a>Archivio file di pagamento per la Norvegia

Quando i file di pagamento vengono generati, l'archivio dei file archivia automaticamente tutti i file creati, anche i file che in precedenza erano stati scritti o letti.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| **Motivo del deprecamento**       | Sostituita da un'altra funzionalità                                        |
| **Sostituita da un'altra funzionalità?** | Sì, processi archiviati di creazione report elettronici                            |
| **Moduli interessati**             | Contabilità fornitori, Contabilità clienti, Amministrazione organizzazione |

### <a name="payment-import-formats-for-estonia"></a>Formati di importazione dei pagamenti per l'Estonia

I formati Telehansa e TeleTeenus vengono utilizzati per l'importazione di pagamenti bancari.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | I formati di pagamento non sono più utilizzati.                                                    |
| **Sostituita da un'altra funzionalità?** | N. I formati verranno sostituiti dai formati di importazione dei rendiconti ISO 20022 nelle versioni future. |
| **Moduli interessati**             | Contabilità clienti                                                                        |

### <a name="performance-management-goal-workflow"></a>Flusso di lavoro relativo agli obiettivi di gestione delle prestazioni

La gestione delle prestazioni include la gestione e l'integrazione degli obiettivi con le revisioni delle prestazioni.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La gestione delle prestazioni è stata riprogettata e il numero di pagine degli obiettivi è stato ridotto per semplificare il processo.                 |
| **Sostituita da un'altra funzionalità?** | N. Gli obiettivi sono visibili ai responsabili tramite il portale Responsabile self-service e possono essere modificati e visualizzati dal responsabile. |
| **Moduli interessati**             | Gestione risorse umane                                                                                                 |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formati di pagamento Postgirot e Postgirot Utland per la Svezia

Formati di pagamento Postgirot e Postgirot Utland per la Svezia.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| **Motivo del deprecamento**       | I formati di pagamento non sono più utilizzati.                 |
| **Sostituita da un'altra funzionalità?** | Sì, formato di pagamento tramite bonifico ISO20022 per la Svezia |
| **Moduli interessati**             | Contabilità fornitori                                        |

### <a name="radio-frequency-identifier"></a>Identificatore di radiofrequenza

RFID (Radio Frequency Identification) è una tecnologia di raccolta dei dati che consente la memorizzazione dei dati di identificazione all'interno di tag elettronici e l'acquisizione di tali dati mediante un lettore senza requisito di portata ottica.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| **Motivo del deprecamento**       | Basso utilizzo cliente e set di funzionalità limitato. |
| **Sostituita da un'altra funzionalità?** | No                                            |
| **Moduli interessati**             | Gestione inventario                          |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Report sulla numerazione delle fatture con stato per la Lettonia

La legislazione lettone fornisce regole specifiche sulla numerazione delle fatture di vendita. La funzionalità consente di assegnare numeri specifici alle fatture di vendita, in base all'utente o al gruppo utenti. È quindi possibile generare un report o un file XML. È inoltre possibile stampare un report relativo ai numeri di fattura utilizzati.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La numerazione di fatture con stato non deve essere più gestito. Il report sui numeri di fattura utilizzati non è più necessario. |
| **Sostituita da un'altra funzionalità?** | Nessuna                                                                                                                       |
| **Moduli interessati**             | Contabilità clienti                                                                                                      |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Impostare i nomi del responsabile e del contabile generale di una società per la Lituania

I nomi del responsabile e del contabile generale di una società possono essere specificati nelle informazioni sulla società e utilizzati negli stampati dei diversi report locali.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| **Motivo del deprecamento**       | Sostituita da un'altra funzionalità                                     |
| **Sostituita da un'altra funzionalità?** | Sì, l'impostazione dei funzionari può essere utilizzata per lo stesso scopo.   |
| **Moduli interessati**             | contabilità fornitori, contabilità clienti, gestione contanti e banca |

### <a name="telepay-payment-formats-for-norway"></a>Formati di pagamento Telepay per la Norvegia

I formati di pagamento Telepay includono l'esportazione dei pagamenti fornitori (bonifico) e il recupero dei pagamenti clienti (addebito diretto).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | I formati di pagamento non sono più utilizzati.                                                        |
| **Sostituita da un'altra funzionalità?** | Sì, il formato di pagamento con bonifico ISO20022 e il formato di pagamento cliente AvtaleGiro per la Norvegia |
| **Moduli interessati**            | Contabilità fornitori, contabilità clienti                                                          |

### <a name="vendor-payment-export-formats-for-finland"></a>Formati di esportazione pagamenti fornitori per la Finlandia

Due formati per l'esportazione dei pagamenti disponibili per la Finlandia. LM02 (FI) viene utilizzato per i pagamenti nazionali e LUM2 (FI) viene utilizzato per i pagamenti esteri.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo del deprecamento**       | I formati di pagamento non sono più utilizzati.                  |
| **Sostituita da un'altra funzionalità?** | Sì, formato di pagamento tramite bonifico ISO20022 per la Finlandia |
| **Moduli interessati**            | Contabilità fornitori                                         |

### <a name="workflow-for-creating-goals"></a>Flusso di lavoro per creare obiettivi

Un flusso di lavoro per la gestione della creazione degli obiettivi dei dipendenti è uno dei diversi flussi di lavoro che hanno reso possibile il coordinamento del processo di gestione delle prestazioni.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La gestione delle prestazioni è stata completamente riprogettata in Microsoft Dynamics 365 for Finance and Operations.                                                                                                                                                                                                                                        |
| **Sostituita da un'altra funzionalità?** | La funzionalità di gestione delle prestazioni riprogettata dà maggiore controllo al contenuto degli obiettivi, alle misurazioni utilizzate per tenere traccia dello stato di avanzamento e all'allegato della documentazione di supporto. I destinatari possono essere archiviati come modelli e quindi riutilizzati. Questa funzionalità consente di impostare più rapidamente gli obiettivi supplementari per i dipendenti. |
| **Moduli interessati**            | Gestione risorse umane                                                                                                                                                                                                                                                                                                               |

## <a name="features-that-have-been-deprecated-in-dynamics-ax-70-releases"></a>Funzionalità che sono state deprecate nelle versioni di Dynamics AX 7.0

### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Capacità di annullare le modifiche apportate a una fattura fornitore

|                              |                         |
|------------------------------|-------------------------|
| **Motivo del deprecamento**       | Miglioramento delle prestazioni |
| **Sostituita da un'altra funzionalità?** | No                      |
| **Moduli interessati**            | Contabilità fornitori        |

### <a name="aif-axd-and-axbc-integrations"></a>Integrazioni di AIF, di AxD e di AxBC

In Application Integration Framework (AIF), i dati possono essere scambiati ai sistemi esterni in logica di business che è esposta come servizi. Dynamics AX include i servizi basati su documenti e .NET Business Connector (AxBC). Un documento viene creato utilizzando XML. XML contiene le informazioni di intestazione aggiunte per creare un *messaggio* che è possibile trasferire da o a Microsoft Dynamics AX. Esempi dei documenti comprendono gli ordini cliente e ordini fornitore. Tuttavia, quasi qualsiasi entità, ad esempio un cliente, può essere rappresentata da un documento. I servizi basati sui documenti usano le classi **Axd &lt;*Document*&gt;**.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | L'architettura AIF e di AxDs non può essere ridimensionata a un servizio cloud. Si sono verificati problemi di prestazioni nell'importazione di stoccaggio.                                                                               |
| **Sostituita da un'altra funzionalità?** | Nella versione corrente di Dynamics AX, questa funzionalità è sostituito dal framework di esportazione e importazione dei dati, che supporta l'importazione/esportazione in blocco ricorrente. Per AxBC, si consiglia di utilizzare le tabelle effettive. |
| **Moduli interessati**             | AxDs, AxBCs e AIF                                                                                                                                                                                     |

### <a name="boms-without-bom-versions"></a>DBA senza versioni DBA

Se la chiave di configurazione **Versioni DBA** è stata disabilitata, le versioni delle distinte base (DBA) sono state nascoste in tutti i moduli e il sistema forzerebbe una relazione 1:1 tra i prodotti rilasciati e le DBA. La chiave di configurazione **Versioni DBA** non può essere disabilitata nella versione corrente di Dynamics AX.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| **Motivo del deprecamento**      | Utilizzare una chiave di configurazione per controllare le versioni DBA non ridimensiona in un ambiente cloud. |
| **Sostituita da un'altra funzionalità?** | No                                                                                      |
| **Moduli interessati**            | Gestione delle informazioni sul prodotto, gestione articoli                                    |

### <a name="brazilian-bordero"></a>Bordero brasiliano

Metodo di pagamento specifico delle società brasiliane

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il supporto del metodo di pagamento Bordero brasiliano è stato interrotto dalla localizzazione brasiliana |
| **Sostituita da un'altra funzionalità?** | Nessuna                                                                                                    |
| **Moduli interessati**             | Contabilità fornitori                                                                                      |

### <a name="brazilian-sintegra-statement"></a>Rendiconto brasiliano di Sintegra

Rendiconto delle imposte federali dell'imposta ICMS

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Questo rendiconto non è più applicabile in alcuni stati brasiliani.                                                     |
| **Sostituita da un'altra funzionalità?** | N. Gli utenti possono utilizzare lo strumento generico di creazione report elettronici per configurare il rendiconto se richiesto in situazioni specifiche. |
| **Moduli interessati**             | Libri fiscali                                                                                                          |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Modalità di contingenza SCAN brasiliana per NF-e

L'ambiente di contingenza (SCAN) viene utilizzato per generare, esportare e importare lo stato di una Nota Fiscal eletrônica (NF-e) quando non è disponibile l'ambiente di Secretaria da Fazenda (SEFAZ)

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Questo metodo di contingenza non è più applicabile in tutti gli stati brasiliani |
| **Sostituita da un'altra funzionalità?** | Nessuna                                                                          |
| **Moduli interessati**             | Contabilità clienti                                                         |

### <a name="business-analyzer"></a>Business Analyzer

Questa applicazione mobile consente agli utenti di esaminare metriche commerciali principali.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Questa funzionalità è stata sostituita da un'altra funzionalità.                                                                                                      |
| **Sostituita da un'altra funzionalità?** | Il pacchetto di contenuto Monitorare le prestazioni finanziarie per Microsoft Power BI includerà metriche finanziarie principali precedentemente disponibili in Business Analyzer. |
| **Moduli interessati**             | Contabilità generale                                                                                                                                                |

### <a name="business-statistics"></a>Statistiche aziendali

Consente di impostare richieste di informazioni su statistiche aziendali che possono semplificare l'analisi delle prestazioni dell'organizzazione.

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Approccio precedente a business intelligence (BI), basso utilizzo del cliente e un set di funzionalità limitato |
| **Sostituita da un'altra funzionalità?** | Nuove soluzioni BI per la versione corrente di Dynamics AX                                      |
| **Moduli interessati**             | Aapprovvigionamento, contabilità fornitori, vendite e marketing, contabilità clienti         |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Funzione di modifica della data del documento nel giornale di approvazione fatture

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Basso utilizzo                                                               |
| **Sostituita da un'altra funzionalità?** | Sì. La data del documento nella transazione fornitore registrazione può essere modificata. |
| **Moduli interessati**             | Contabilità fornitori                                                        |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Formato pagamento ClieOp03 per i Paesi Bassi

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato non è più applicabile nei Paesi Bassi, poiché è stato sostituito da euro funzionalità di (SEPA) di l di pagamenti Single. |
| **Sostituita da un'altra funzionalità?** | Esportazione pagamenti SEPA                                                                                       |
| **Moduli interessati**             | Tutti                                                                                                        |

### <a name="compliance-center"></a>Centro conformità

Il centro conformità è un sito Enterprise Portal per gestire i requisiti della documentazione per le iniziative di conformità correlate alla legge di Sarbanes-Oxley.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Mancanza di utilizzo del cliente. Microsoft SharePoint include la stessa funzione che è disponibile nel centro conformità. |
| **Sostituita da un'altra funzionalità?** | No                                                                                                                     |
| **Moduli interessati**             | Controlli interni e di conformità                                                                                       |

### <a name="connector-for-microsoft-dynamics"></a>Connettore per Microsoft Dynamics

Questo strumento è stato utilizzato per integrare i dati di chiave da Microsoft Dynamics CRM alle applicazioni Microsoft Dynamics ERP.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo del deprecamento**       | Questa funzionalità è stata sostituita da un'altra funzionalità. |
| **Sostituita da un'altra funzionalità?** | Integratore di Dynamics                                      |
| **Moduli interessati**             | Connettore per Microsoft Dynamics                         |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Unità contenitore e modello multi-dimensionale disponibili

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Funzionalità duplicata.                                                                                                                                         |
| **Sostituita da un'altra funzionalità?** | Sì. Da AX 2012, questa funzionalità è stata sostituita dal set di funzionalità di ordini batch consolidati. Il set di funzionalità include la visualizzazione della disponibilità consolidata. |
| **Moduli interessati**             | Gestione delle informazioni sul prodotto, controllo produzione, gestione articoli, vendite e marketing                                                                   |

### <a name="cue-group-metadata"></a>Metadati gruppo Cue

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | I gruppi Cue sono stati utilizzati per visualizzare uno o più Cue nell'area di Dettaglio informazioni. Vi era un assorbimento è limitato e anche problematiche di prestazioni, poiché registrare la modifica in un modulo padre ha causato una query per Cue nel gruppo Cue. |
| **Sostituita da un'altra funzionalità?** | No                                                                                                                                                                                                                            |
| **Moduli interessati**             | Tutti                                                                                                                                                                                                                           |

### <a name="cue-metadata"></a>Metadati Cue

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | I metadati Cue sono stati limitati alle informazioni di conteggio o somma.                                                                                                                                                                                   |
| **Sostituita da un'altra funzionalità?** | I metadati della sezione sono stato introdotti per dare più flessibilità per la modellizzazione. Ad esempio, è possibile modellare i conteggi correnti, la navigazione e gli indicatori di prestazioni chiave (KPI). I metadati della sezione di conteggio sono la sostituzione diretta dei metadati Cue. |
| **Moduli interessati**             | Tutti                                                                                                                                                                                                                                     |

### <a name="danish-check-format"></a>Formato assegno italiano

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il supporto al layout di formato dell'assegno danese è stato interrotto e il report è stato rimosso da localizzazione DK. |
| **Sostituita da un'altra funzionalità?** | No                                                                                                                      |
| **Moduli interessati**             | Tutti                                                                                                                     |

### <a name="data-partitions"></a>Partizioni di dati

Le partizioni di dati forniscono una separazione logica di dati nel database di Microsoft Dynamics AX.

|   |   |
|---|---|
| **Motivo del deprecamento**       | Le partizioni di dati sono state introdotte in Microsoft Dynamics AX 2012 R2 per abilitare l'isolamento dei dati. In uno scenario comune, una società ha affiliate e i dati di una filiale non devono essere visibili in un'altra filiale, anche se entrambe le filiali sono gestite dallo stesso reparto IT. Tuttavia, un sovraccarico di gestione e script aggiuntivi nel programma erano necessari per creare nuove partizioni e popolarle con i dati e per eseguire il backup dei dati della partizione. Nel cloud, dove si ha accesso ai servizi di database di piattaforma distribuita come servizio (PaaS) (Database SQL di Microsoft Azure), è molto più efficiente utilizzare un database come contenitore di isolamento rispetto all'isolamento nel programma. Indipendentemente dal fatto che il partizionamento dei dati sia necessario per le filiali, per più tenant o semplicemente per esigenze di scalabilità, crediamo che gli scenari possono essere gestiti meglio tramite più database o più istanze di Dynamics AX. |
| **Sostituita da un'altra funzionalità?** | Verranno sostituite le partizioni di dati tramite il supporto per più database o istanze di Dynamics AX in una versione futura.    |
| **Moduli interessati**             | Tutti  |

### <a name="database-and-file-share-storage-for-attachments"></a>Archiviazione nel database e nella condivisione file per gli allegati
Microsoft Dynamics AX 2012 ha consentito l'archiviazione degli allegati nel database e nelle condivisioni file. Entrambe tali opzioni non sono più supportate.

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo del deprecamento**       | L'archiviazione nella condivisione dei file non è più supportata in quanto gli ambienti ospitati nel cloud non possono comunicare con le condivisioni file locali. L'archiviazione del database è stata deprecata a favore dell'archivio BLOB di Azure. L'archivio BLOB di Azure equivale all'archiviazione nel database, poiché i documenti sono accessibili solo tramite i moduli del client Dynamics 365 for Finance and Operations. In questo modo si ha il vantaggio aggiuntivo di fornire archiviazione senza influire negativamente sulle prestazioni del database. L'archivio BLOB è il meccanismo di archiviazione predefinito per la gestione di documenti e funziona immediatamente. |
| **Sostituita da un'altra funzionalità?** | L'archiviazione del database è stata deprecata a favore dell'archivio BLOB di Azure.       |
| **Moduli interessati**             | Tutti                   |

### <a name="delimitation"></a>Delimitazione

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo del deprecamento**       | Non utilizzare la funzione è stato cercato. |
| **Sostituita da un'altra funzionalità?** | No                                     |
| **Moduli interessati**             | Orario e presenze                    |

### <a name="desktop-client"></a>Client desktop

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | L'esperienza client di Dynamics AX è stata riprogettata per migliorare la facilità d'uso tra più piattaforme e dispositivi.                      |
| **Sostituita da un'altra funzionalità?** | Il nuovo web client è basato sui metadati e il modello di programmazione desktop del modulo modificati per fornire una ricca piattaforma web. |
| **Moduli interessati**             | Tutti                                                                                                                                    |

### <a name="direct-database-connection"></a>Connessione diretta al database

In Dynamics AX 2012 R3, Retail Modern POS poteva connettersi direttamente al database canale in modo simile a Enterprise POS. Questa funzionalità costitutiva un'aggiunta al metodo standard di comunicazione di Retail Modern POS che comunica tramite il server Retail.  

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La connettività diretta del database richiedeva i protocolli di protezione minimi ed era principalmente utilizzata per ottenere i massimi livelli delle prestazioni. A causa dei miglioramenti di protezione e delle prestazioni di Finance and Operations, questa funzionalità ora comporta più problemi che vantaggi. |
| **Sostituita da un'altra funzionalità?** | N. È ora supportata solo la comunicazione standard del server Retail.    |
| **Moduli interessati**             | Database canale/Retail Modern POS                                    |

### <a name="dutch-swift-mt940"></a>SWIFT olandese MT940

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La funzionalità generica ora viene utilizzata anziché la funzionalità localizzata.                                                                                                                                                                 |
| **Sostituita da un'altra funzionalità?** | Sì, questa funzionalità viene sostituita con la funzionalità avanzata di riconciliazione estratti conto. |
| **Moduli interessati**             | Tutti                                                                                                                                                                                                                                   |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL per la Germania)

Questa funzionalità forniva l'output XBRL (eXtensible Business Reporting Language) in modo specifico per la tassonomia tedesca di eBilanz.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Mancanza di utilizzo del cliente                                                                                                                                                 |
| **Sostituita da un'altra funzionalità?** | Questa funzionalità non è stata sostituita, ma diversi pacchetti XBRL specializzati che forniscono funzionalità XBRL avanzate sono disponibili per il mercato tedesco. |
| **Moduli interessati**             | Management Reporter                                                                                                                                                    |

### <a name="enterprise-portal-client"></a>Client Enterprise Portal

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Una singola piattaforma cliente è stata fornita.                                                                                            |
| **Sostituita da un'altra funzionalità?** | Il nuovo web client è basato sui metadati e il modello di programmazione desktop del modulo modificati per fornire una ricca piattaforma web. |
| **Moduli interessati**             | Tutti                                                                                                                                    |

### <a name="environmental-sustainability"></a>Sostenibilità ambientale

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| **Motivo del deprecamento**       | Basso utilizzo cliente e set di funzionalità limitato       |
| **Sostituita da un'altra funzionalità?** | No                                                 |
| **Moduli interessati**             | Modulo Controlli interni e di conformità, contabilità fornitori |

### <a name="form-activex-and-managed-host-controls"></a>Modulo ActiveX e controlli host gestiti

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | ActiveX e i controlli host vengono gestiti in sul client desktop deprecato.                                                                                                             |
| **Sostituita da un'altra funzionalità?** | Il frameword dei controlli estendibili supporta la creazione di nuovi controlli basati su HTML, CSS e JavaScript ed è un controllo di prima classe nell'ambente Microsoft Visual Studio Tooling. |
| **Moduli interessati**             | Tutti                                                                                                                                                                                           |

### <a name="generate-prenotes-by-using-a-batch"></a>Generare notifiche anticipate utilizzando un batch

La creazione della notifica anticipata non può essere effettuata operazione utilizzando un batch ma può comunque essere effettuata da un utente.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Non esiste alcun modulo per salvare in modo permanente e visualizzare il file risultante di notifica anticipata quando viene generato utilizzando un batch. |
| **Sostituita da un'altra funzionalità?** | Le notifiche anticipate possono ancora essere generate e l'utente ha controllo sul percorso di salvataggio del file.   |
| **Moduli interessati**             | contabilità fornitori, contabilità clienti, gestione contanti e banca                                        |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Esportazione di pagamento di DTAUS e importazione di estratto conto tedesco (totali e transazioni)

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato non è più applicabile in Germania, poiché è stato sostituito dalla funzionalità SEPA.                                                                                                                                                                 |
| **Sostituita da un'altra funzionalità?** | Sì, questa funzionalità è stata sostituita dall'esportazione di pagamento SEPA e dalla funzionalità avanzata di riconciliazione estratti conto per importare gli estratti conto. |
| **Moduli interessati**             | Tutti                                                                                                                                                                                                                                                                                            |

### <a name="german-dtazv-payment-format"></a>Formato di pagamento tedesco di DTAZV

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato non è più applicabile in Germania, poiché è stato sostituito dalla funzionalità SEPA. |
| **Sostituita da un'altra funzionalità?** | Esportazione pagamenti SEPA                                                                               |
| **Moduli interessati**             | Tutti                                                                                                |

### <a name="german-mt940-import"></a>Importazione tedesca MT940

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La funzionalità generica ora viene utilizzata anziché la funzionalità localizzata.                                                                                                                                                                 |
| **Sostituita da un'altra funzionalità?** | Sì, questa funzionalità viene sostituita con la funzionalità avanzata di riconciliazione estratti conto. |
| **Moduli interessati**             | Tutti                                                                                                                                                                                                                                   |

### <a name="german-xml-eu-sales-list"></a>Elenco vendite XML tedesco

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il formato XML della dichiarazione Elenco vendite UE per la Germania non è più supportato. Solo il formato del file di testo ELMA5 può essere utilizzato per inviare il report Elenco vendite UE all'ufficio imposte tedesco. |
| **Sostituita da un'altra funzionalità?** | No                                                                                                                                                                                 |
| **Moduli interessati**             | Imposta                                                                                                                                                                                |

### <a name="gl-ssrs-reports"></a>Report GL SSRS

Report che includono le seguenti voci di menu sono stati rimossi: **Bilancio di verifica riepilogativo****Bilancio di verifica dettagliato****Piano dei conti****Audit trail**, **Saldi** e **Elenco saldi**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | I report finanziari di Microsoft SQL Server il Reporting Services (SSRS) sono stati sostituiti dalle funzionalità di Management Reporter e i report predefiniti. |
| **Sostituita da un'altra funzionalità?** | Management Reporter (contrassegnato **Report finanziario** nella versione corrente di Dynamics AX)                                                  |
| **Moduli interessati**            | Contabilità generale                                                                                                                               |

### <a name="infopart-and-formpart-metadata"></a>I metadati di FormPart e di InfoPart

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | I metadati di FormPart e di InfoPart hanno abilitato la creazione dei riquadri dettaglio informazioni per due diversi client.                                                                                                                                    |
| **Sostituita da un'altra funzionalità?** | I metadati di InfoPart, che erano una definizione semplificata del modulo, vengono convertiti nel modulo di lavorazione con utensili di aggiornamento. I metadati di FormPart, che facevano riferimento un modulo, sono sostituiti da un riferimento più diretto creato mediante tooling di aggiornamento. |
| **Moduli interessati**             | Tutti                                                                                                                                                                                                                            |

### <a name="main-account-list-page"></a>Conti principali (pagina elenco)

Un elenco dei conti per la persona giuridica e le informazioni correlate bilanciate

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Le informazioni bilanciate sono disponibili **Bilancio di verifica** nella pagina elenco il conto e la dimensione.                                                                                      |
| **Sostituita da un'altra funzionalità?** | **Conti principali** contiene lo stesso elenco dei conti dalla **Conto principale** pagina elenco è contenuto. La visualizzazione griglia in **Conti principali** e viene visualizzato un nuovo più piccola, visualizzare il tipo di griglia. |
| **Moduli interessati**             | Contabilità generale                                                                                                                                                                     |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Report del flusso di cassa bancario di Singapore e Malesia

Questa funzionalità di stampare un report del flusso di cassa bancario contenente le transazioni e i dettagli delle entrate e uscite di cassa relative a un intervallo di date specifico per i conti bancari selezionati.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Le stesse informazioni possono essere ottenute dalla transazione bancaria di indagine. |
| **Sostituita da un'altra funzionalità?** | Transazione bancaria di indagine                                            |
| **Moduli interessati**             | Gestione cassa e banche                                                |

### <a name="mexican-cfd-electronic-invoice"></a>Fattura elettronica CFD messicana

Questa funzionalità consentiva la generazione di fatture elettroniche messicane utilizzando il metodo CFD (Comprobante Fiscal Digital), in cui la società firma la fattura richiedendo l'autorizzazione correlata al governo. Questa funzionalità include inoltre un report mensile che include tutte le fatture elettroniche emesse nel periodo.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il metodo non viene più applicabile. La generazione di fatture elettroniche utilizzando il metodo di CFD è stata deprecata dagli uffici tributari ed è stata sostituita da Comprobante Digital fiscale un metodo di de Internet (CFDI) di través, in cui la firma è delegata il fornitore di terze parti (PAC). Il report mensile è stato rimosso e un'opzione di richiesta consente agli utenti di richiedere informazioni sulle transazioni dello storico. |
| **Sostituita da un'altra funzionalità?** | No                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Moduli interessati**             | Effetti attivi di conto, progetto                                                                                                                                                                                                                                                                                                                                                                              |

### <a name="mexico-realized-and-unrealized-vat"></a>Messico ha eseguito e L'VAT non realizzata

Microsoft Dynamics AX 2012 ha gestito l'imposta sul valore aggiunto non (VAT) la funzionalità Messico- specifica “per l'vat non realizzata„.

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Funzionalità duplicata.                                                                                             |
| **Sostituita da un'altra funzionalità?** | Sì, sostituita dalla funzionalità IVA condizionata che viene fornita dalle funzioni di base. |
| **Moduli interessati**             | Imposta                                                                                                                 |

### <a name="microsoft-outlook-integration"></a>Integrazione con Microsoft Outlook

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Questa funzionalità è stata sostituita dall'integrazione di Microsoft Exchange Server. |
| **Sostituita da un'altra funzionalità?** | Sì                                                                            |
| **Moduli interessati**             | Vendite e marketing                                                            |

### <a name="payroll-information-in-human-resources"></a>Informazioni sulle retribuzioni in Risorse umane

Informazioni sulle retribuzioni in Risorse umane

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Questa funzionalità è stata sostituita dalle pagine principali sulle risorse umane e sulle retribuzioni.                                                                                                                                                                                                                                              |
| **Sostituita da un'altra funzionalità?** | **Benefit**, **Redditi** e altre pagine correlate, incluse in precedenza nelle retribuzioni degli Stati Uniti ora sono state riconfigurate e fanno parte della configurazione principale Risorse umane per supportare l'elaborazione esterna delle retribuzioni. Questa funzionalità è accessibile utilizzando la chiave di configurazione **Risorse umane 1** &gt; **Retribuzione**. |
| **Moduli interessati**             | Risorse umane, retribuzioni                                                                                                                                                                                                                                                                                                     |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Blocco privato di magazzino e giornali di registrazione di gestione magazzino

Giornali di registrazione magazzino e delle scorte più supporto la capacità di contrassegnare un giornale di registrazione come privato per un utente selezionato. Solo il processo di registrazione di blocco come privato per gruppi di utenti e blocco durante la modifica è supportato.

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo del deprecamento**       | Non utilizzare la funzione è stato cercato. |
| **Sostituita da un'altra funzionalità?** | No                                     |
| **Moduli interessati**             | Gestione inventario                   |

### <a name="product-builder"></a>Configuratore prodotti

Configuratore prodotti è stato utilizzato per configurare dinamicamente gli articoli da un ordine cliente, un'offerta di vendita, un ordine di produzione, un'offerta di progetto, una richiesta articolo. In base a un modello prodotto che ha effettuato variabili di modellizzazione, l'utente può selezionare i valori per soddisfare i requisiti del cliente e per ottenere una variante prodotto univoco che ha effettuato una DBA e il ciclo di lavorazione.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Il Configuratore prodotti ha esposto il codice X++ agli utenti finali e non è supportato la versione corrente di Dynamics AX. È stato rimosso per evitare gli sforzi duplicati in codebase sovrapposti e di grandi dimensioni. |
| **Sostituita da un'altra funzionalità?** | Configurazione prodotto                                                                                                                                                                                   |
| **Moduli interessati**             | Gestione delle informazioni sul prodotto, vendite e marketing                                                                                                                                                     |

### <a name="rename-product-dimension"></a>Rinomina dimensione prodotto

Questa funzionalità consente di modificare il nome di una delle tre dimensioni prodotto standard (dimensione, colore o stile) con un nome più adatto ai requisiti aziendali. Rinominare è incluso tutte le etichette in cui il nome della dimensione prodotto è stato utilizzato.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La versione corrente di Dynamics AX non supporta le modifiche etichette in fase di esecuzione. |
| **Sostituita da un'altra funzionalità?** | No                                                                            |
| **Moduli interessati**             | Gestione informazioni sul prodotto                                                |

### <a name="retail-server-connectivity-using-http"></a>Connettività al server Retail mediante HTTP

In Dynamics AX 2012 R3, il server Retail poteva essere eseguito mediante la comunicazione HTTP (non protetta). Questa funzionalità costituiva un'aggiunta alla comunicazione standard mediante HTTPS.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | A causa dei nuovi requisiti di sicurezza, è ora supportata solo la comunicazioni tramite TLS 1.2 (o superiore, se disponibile). Il programma di installazione self-service configurerà automaticamente il computer per questo tipo di comunicazione. |
| **Sostituita da un'altra funzionalità?** | N. È ora supportata solo la comunicazione HTTPS standard del server Retail.                                                                           |
| **Moduli interessati**             | Server Retail                                                |

### <a name="role-center-pages"></a>Centri gestione ruolo

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Le pagine Centro gestione ruolo sono state sviluppate sulla piattaforma deprecata Enterprise Portal, che è stata sostituita da nuova piattaforma web client nella versione corrente di Dynamics AX. |
| **Sostituita da un'altra funzionalità?** | Il nuovo modello di modulo dell'area di lavoro fornisce agli utenti la progettazione processo-centrica che consente l'accesso semplice alle attività usate comunemente all'interno di tale processo.                       |
| **Moduli interessati**             | Tutti                                                                                                                                                                      |

### <a name="sales-tax-jurisdictions"></a>Uffici IVA competenti

|                              |                                              |
|------------------------------|----------------------------------------------|
| **Motivo del deprecamento**       | Basso utilizzo cliente e set di funzionalità limitato |
| **Sostituita da un'altra funzionalità?** | No                                           |
| **Moduli interessati**             | IVA per gli Stati Uniti                                 |

### <a name="shipping-carrier-interface"></a>Interfaccia del vettore di spedizione

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Funzionalità duplicata.                                                                                                                         |
| **Sostituita da un'altra funzionalità?** | Sì, parzialmente sostituita dalla gestione di trasporto, ma non ancora sostituita dalla Gestione magazzino di base (WMS I). |
| **Moduli interessati**             | Vendite e marketing, gestione inventario                                                                                                       |

### <a name="sites-services"></a>Sites Services

La funzionalità Sites Services consente di costruire i siti Web che estendono i processi aziendali in Internet senza supporto IT.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | L'infrastruttura di Microsoft Azure utilizzata da Dynamics AX ha nuove funzionalità che è possibile utilizzare in alternativa, ad esempio siti di Azure. |
| **Sostituita da un'altra funzionalità?** | No                                                                                                                                       |
| **Moduli interessati**             | Selezione del personale, gestione dei casi, richiesta di offerta, registrazione fornitore                                                                  |

### <a name="ssas-demand-forecasting-strategy"></a>Strategia di previsione della domanda SSAS

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La struttura della funzionalità non può essere supportata nella nuova architettura cloud. |
| **Sostituita da un'altra funzionalità?** | Strategia di previsione della domanda Azure Machine Learning                           |
| **Moduli interessati**             | Pianificazione                                                                     |

### <a name="travel-requisitions"></a>Richieste di viaggio

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| **Motivo del deprecamento**       | L'utilizzo basso e la maggior parte delle funzionalità vengono esistito in Enterprise Portal. |
| **Sostituita da un'altra funzionalità?** | No                                                              |
| **Moduli interessati**             | Gestione spese                                              |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Pool di fatture fornitore esclusi i dettagli di registrazione

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Basso utilizzo Questa funzionalità è stata sostituita dal giornale di registrazione fatture che risponde di funzionalità del flusso di lavoro. |
| **Sostituita da un'altra funzionalità?** | Funzionalità del flusso di lavoro del giornale di registrazione fatture.                                                           |
| **Moduli interessati**             | Contabilità fornitori                                                                                        |

### <a name="virtual-company-accounts"></a>Account società virtuali

La funzionalità virtuale di più società non è supportata in Dynamics AX. La funzionalità relativa alle società virtuali consente agli utenti di impostare le tabelle da condividere da un insieme di società. Per una descrizione della funzionalità, vedere [Account società e account società virtuali](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). Il funzionamento della funzionalità delle tabelle di raggruppamento le attività assegnate alle società virtuali, ovvero gruppi di società “reali„ esistenti. Le query vengono creati in modo che tutte società nella società virtuale possano accedere ai dati nelle tabelle delle raccolte di tabelle associate.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><b>Motivo del deprecamento</b></td>
<td><ul>
<li>Le società virtuali è necessario impostare prima che i dati sono archiviati nelle tabelle. La modifica delle società virtuali in un'implementazione esistente è molto difficile.</li>
<li>Poiché nella versione corrente di Dynamics AX la normalizzazione dei dati è così elevata, è diventato difficile conoscere gli elementi da aggiungere alle raccolte di tabelle. Ad esempio, è difficile conoscere le tabelle da condividere. È necessario inoltre aggiungere tutte le tabelle a cui fanno riferimento le tabelle presenti in una società virtuale. A causa della normalizzazione delle tabelle, anche i semplici dati master distribuiti in più tabelle devono far parte della società virtuale. Tutti gli errori provocheranno problemi funzionali.</li>
<li>Quando una tabella fa parte di una società virtuale, perde le informazioni sull'origine dei dati e solo la società virtuale viene registrata.</li>
</ul></td>
</tr>
<tr class="even">
<td><b>Sostituita da un'altra funzionalità?</b></td>
<td>Le tabelle globali possono essere utilizzate per rendere accessibili le tabelle da tutte le società. Attualmente, non esiste alcuna sostituzione.</td>
</tr>
<tr class="odd">
<td><b>Moduli interessati</b></td>
<td>Non applicabile</td>
</tr>
</tbody>
</table>

### <a name="warehouse-management-ii"></a>Gestione magazzino II

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | La soluzione di gestione magazzino II (WMS II) che è disponibile nel modulo **Gestione articoli** duplica la funzionalità nel modulo **Gestione magazzino** che è stato rilasciato in Microsoft Dynamics AX 2012 R3.                                                                         |
| **Sostituita da un'altra funzionalità?** | Il modulo **Gestione magazzino** che è stato rilasciato in AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 e Microsoft Dynamics AX 2012 R3 CU9 sostituisce le funzionalità di gestione magazzino II. Il nuovo modulo dispone di funzionalità più avanzate e di processi di gestione magazzino più flessibili rispetto a quelli offerti nelle funzionalità Gestione magazzino II. |
| **Moduli interessati**             | Gestione articoli, vendite e marketing, approvvigionamento                                                                                                                                                                                                                                         |

### <a name="worker-reminders-in-human-resources"></a>Promemoria lavoratore in Risorse umane

Informazioni sulle retribuzioni in Risorse umane

|                              |                 |
|------------------------------|-----------------|
| **Motivo del deprecamento**       | Basso utilizzo       |
| **Sostituita da un'altra funzionalità?** | No              |
| **Moduli interessati**             | Risorse umane |

### <a name="workplanner"></a>Pianificazione lavori

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Basso utilizzo                                                                                                                                                            |
| **Sostituita da un'altra funzionalità?** | No, ma la pagina **Relazione profilo**, aperta dalla pagina **Gruppi di profili**, supporta lo stesso scenario aziendale della pagina **Pianificazione lavori** deprecata. |
| **Moduli interessati**             | Orario e presenze                                                                                                                                                  |

### <a name="x-financial-statements"></a>Rendiconti finanziari X++

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| **Motivo del deprecamento**       | Questa funzionalità è stata sostituita da un'altra funzionalità.                                    |
| **Sostituita da un'altra funzionalità?** | Management Reporter (contrassegnato **Report finanziario** nella versione corrente di Dynamics AX) |
| **Moduli interessati**             | Contabilità generale                                                                              |


