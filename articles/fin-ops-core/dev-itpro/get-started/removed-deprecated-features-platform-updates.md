---
title: Funzionalità della piattaforma rimosse o deprecate
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione dagli aggiornamenti della piattaforma per le app Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 0072ca507301fdb880f0595a06377ff01366ca20
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2020
ms.locfileid: "3260531"
---
# <a name="removed-or-deprecated-platform-features"></a>Funzionalità della piattaforma rimosse o deprecate

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione dagli aggiornamenti della piattaforma per le app Finance and Operations.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione. 

> [!NOTE]
> Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per la versione 10.0.11 delle app Finance and Operations

### <a name="field-groups-containing-invalid-field-references"></a>Gruppi di campi contenenti riferimenti di campo non validi

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | I gruppi di campi nelle definizioni dei metadati della tabella possono contenere riferimenti a campi non validi. Se questi gruppi di campi vengono distribuiti, possono causare errori di runtime in Financial Reporting e in Microsoft SQL Server Reporting Services (SSRS). L'aggiornamento 23 della piattaforma ha introdotto un *avviso* del compilatore che consente di risolvere questo problema relativo ai metadati. Aggiornamenti della piattaforma per la versione 10.0.11 delle app Finance and Operations che classificano questo problema come *errore* del compilatore.<p>Per risolvere questo problema, procedere come segue.</p><ol><li>Rimuovere il riferimento di campo non valido dalla definizione del gruppo di campi di tabella.</li><li>Ricompilare.</li><li>Assicurarsi che eventuali errori vengano risolti.</li></ol> |
| **Sostituita da un'altra funzionalità?**   | Questo errore del compilatore sostituisce in modo permanente l'avviso del compilatore.  |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | **Deprecato:** L'avviso del compilatore è ora un errore del compilatore negli aggiornamenti della piattaforma per la versione 10.0.11 delle app Finance and Operations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licenze ISV create utilizzando l'algoritmo di hashing SHA1

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Il processo per la creazione di licenze ISV (Independent Software Vendor) è cambiato. Per ulteriori informazioni, vedere [Licenze ISV (Independent Software Vendor)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Sostituita da un'altra funzionalità?**   | Sì. Utilizzare Windows PowerShell per creare licenze. |
| **Aree del prodotto interessate**         | Strumenti di sviluppo di Visual Studio |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | <strong>Deprecato:</strong> Licenze ISV create utilizzando l'algoritmo di hashing SHA1. Questo algoritmo dipendeva dai certificati creati utilizzando l'utilità MakeCert e questa utilità è stata deprecata.<p><strong>Deprecato:</strong> L'uso di SHA1 per motivi di sicurezza o di hashing. SHA1 cesserà di funzionare per l'inizio del 2021. Pertanto, non deve più essere utilizzato.<p><strong>Rimosso:</strong> Supporto per richieste in entrata o in uscita Transport Layer Security (TLS) 1.0 e TLS 1.1. |

## <a name="platform-update-32"></a>Update 32 della piattaforma

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La finestra di dialogo per la modifica della richiesta del flusso di lavoro non include più l'elenco a discesa per la selezione dell'utente
|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Questo era un problema di sicurezza perché la richiesta di modifica poteva essere inviata a un utente non intenzionale. Anche questo era un problema di usabilità perché costringeva l'utente a determinare chi era il creatore del flusso di lavoro e selezionarlo manualmente.  |
| **Sostituita da un'altra funzionalità?**   | Nessuno |
| **Aree del prodotto interessate**         | Flusso di lavoro |
| **Opzione di distribuzione**              | Tutte |
| **Stato**                         | L'elenco a discesa di selezione dell'utente è stato rimosso dalla finestra di dialogo di modifica della richiesta nell'aggiornamento 32 della piattaforma. Le richieste di modifica della richiesta verranno inviate automaticamente al mittente come previsto. Per ulteriori informazioni su questa funzionalità, vedere [Azioni nei processi di approvazione del flusso di lavoro](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>I collegamenti drill-through incorporati non sono più supportati nei documenti impaginati visualizzati dal servizio ospitato su cloud 
|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Gli URL di spostamento incorporati nei documenti visualizzati dal servizio possono contenere dati aziendali sensibili. Verrà rimosso il supporto per i collegamenti drill-through incorporati nei documenti come precauzione di sicurezza per proteggere ulteriormente i dati dei clienti. Gli utenti trarranno inoltre vantaggio da prestazioni migliori producendo in modo interattivo documenti a seguito di questo cambiamento.  |
| **Sostituita da un'altra funzionalità?**   | Nessuna |
| **Aree del prodotto interessate**         | Reporting |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Questa funzione è attivamente rimossa dal servizio.<br><br>Il client moderno offre numerose opzioni per la produzione di visualizzazioni che includono collegamenti generati automaticamente per facilitare l'esplorazione dell'applicazione. I documenti impaginati visualizzati dal servizio sono consigliati per le comunicazioni esterne che vengono inviate via e-mail, archiviate e stampate per i destinatari. Abbiamo migliorato l'esperienza per l'anteprima dei documenti direttamente nel browser, che offre accesso diretto alle stampanti locali. Per ulteriori informazioni, vedere [Anteprima dei documenti PDF con un visualizzatore incorporato](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annunci precedenti sulle funzionalità rimosse o deprecate
Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../migration-upgrade/deprecated-features.md).

