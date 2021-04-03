---
title: Funzionalità rimosse o deprecate in Dynamics 365 Finance
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 02/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 14428491383883c1fc2a8cdcd1975e1f1cb71b40
ms.sourcegitcommit: e9d19f25e64cf4d1c1d07c8031a7081454a6f79e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5474065"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Funzionalità rimosse o deprecate in Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Finance.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione. 

> [!NOTE]
> Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://docs.microsoft.com/dynamics/s-e/global/axtechrefrep_61). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.17

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>Repository LCS come opzione di archiviazione per configurazioni di report elettronici

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituito con il nuovo repository globale di Regulatory Configuration Service (RCS) |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Prodotti Dynamics 365 Finance, Supply Chain Management e Project Operations|
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1° aprile 2022, prevediamo di non supportare più il repository Microsoft Dynamics Lifecycle Services (LCS) come opzione di archiviazione per le configurazioni per la creazione di report elettronici (ER). Le nuove configurazioni di Microsoft ER verranno pubblicate per il download esclusivamente dal repository globale. È possibile accedere al repository globale dai prodotti Dynamics 365 e da RCS. Per ulteriori informazioni, vedere [Importare configurazioni ER da RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.16

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Formati di dichiarazione elettronica "Dichiarazione IVA (CZ)" e "Esportazione dichiarazione di controllo (CZ)" per la Repubblica ceca

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituito con nuovi formati |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 22 gennaio 2022, prevediamo che non verranno più supportati i formati per report elettronici (ER) "Dichiarazione IVA (CZ)" ed "Esportazione dichiarazione di controllo (CZ)". I nuovi formati XML (CZ) di dichiarazione IVA, Excel di dichiarazione IVA (CZ), XML di dichiarazione di controllo IVA (CZ) sono stati invece introdotti nel modello "Dichiarazione fiscale". |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>Formato di creazione di report elettronici "Ledger transaction export format (BE)" e rispettivo modello "Ledger transaction export (BE)" per il Belgio

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituito con il nuovo formato di creazione report elettronici "Standard Audit File (SAF-T)".  |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1 ° dicembre 2021, prevediamo di non supportare più il formato di creazione di report elettronici "Ledger transaction export format (BE)" e rispettivo modello "Ledger transaction export (BE)" per il Belgio. Un nuovo formato "General ledger data export (BE)" insieme a "General ledger data model mapping" sono invece introdotti nel modello "Standard Audit File (SAF-T)". |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>Report "VAT 100" per il Regno Unito nel formato SSRS

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Sostituito con il nuovo formato per la creazione di report elettronici: formato "Excel di dichiarazione IVA (UK)" in "Modello di dichiarazione fiscale".  |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1° dicembre 2021, prevediamo di non supportare più il "report VAT 100" nel formato SSRS. Un nuovo formato "Excel di dichiarazione IVA (UK)" in "Modello di dichiarazione fiscale" è stato introdotto nella [funzionalità IVA MTD](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Il supporto di Internet Explorer 11 per Dynamics 365 è deprecato

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | A partire da dicembre 2020, il supporto di Microsoft Internet Explorer 11 per tutti i prodotti Dynamics 365 è deprecato e Internet Explorer 11 non sarà supportato dopo agosto 2021.<br><br>Ciò avrà un impatto sui clienti che utilizzano prodotti Dynamics 365 progettati per essere utilizzati tramite un'interfaccia Internet Explorer 11. Dopo agosto 2021, Internet Explorer 11 non sarà supportato per questi prodotti Dynamics 365. |
| **Sostituita da un'altra funzionalità?**   | Consigliamo ai clienti di passare a Microsoft Edge.|
| **Aree del prodotto interessate**         | Tutti i prodotti Dynamics 365 |
| **Opzione di distribuzione**              | Tutti|
| **Stato**                         | Deprecato. Internet Explorer 11 non sarà supportato dopo agosto 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.12

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Report SSRS polacchi: registro IVA vendite, registro IVA acquisti, registro IVA riepilogativo UE - Riferimento funzione PL-00014

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Non obbligatorio per legge.  |
| **Sostituita da un'altra funzionalità?**   | Sì (formato Excel per file di controllo standard con dichiarazione IVA - JPK_VDEK) |
| **Aree del prodotto interessate**         | Richiesta |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1° luglio 2021 non verranno più supportati i report SSRS: **Registro IVA vendite, Registro IVA acquisti, Registro IVA riepilogativo UE - Riferimento funzione PL-00014**. Verrà introdotto un esempio di formato Excel per il file di audit standard con dichiarazione IVA (JPK_VDEK). |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.11

### <a name="norwegian-standard-main-accounts"></a>Conti principali standard per la Norvegia

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Riprogettazione  |
| **Sostituita da un'altra funzionalità?**   | Sì (sostituito con parametri specifici dell'applicazione in formato ER) |
| **Aree del prodotto interessate**         | Richiesta |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1° aprile 2021, prevediamo di non supportare più la funzionalità relativa ai conti principali standard: campo di riferimento, tabella correlata, entità dei dati. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Funzionalità rimosse o deprecate nella versione Finance and Operations 10.0.7

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La finestra di dialogo per la modifica della richiesta del flusso di lavoro non include più l'elenco a discesa per la selezione dell'utente
|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Modificato nella funzionalità con selezione di gruppi di conti.  |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Flusso di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: Dal 1° dicembre 2020, prevediamo di non supportare più l'impostazione dei tipi di giustificativi cinesi senza la selezione dei gruppi di conti. Ulteriori dettagli relativi alla nuova progettazione della funzionalità sono disponibili in [Novità di 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annunci precedenti sulle funzionalità rimosse o deprecate
Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
