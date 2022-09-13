---
title: Funzionalità rimosse o deprecate in Dynamics 365 Finance
description: In questo articolo vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Finance.
author: kfend
ms.date: 06/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 83fa9d0a08d4d9ec171aeee685d39bba46e5687d
ms.sourcegitcommit: 6fd44fc6e9a7bad197cab58c36ec25a555724cf1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2022
ms.locfileid: "9410452"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Funzionalità rimosse o deprecate in Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Finance.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione. 

> [!NOTE]
> Informazioni dettagliate sugli oggetti nelle app per la finanza e le operazioni sono disponibili nei [Report tecnici di riferimento](/dynamics/s-e/global/axtechrefrep_61). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app per la finanza e le operazioni.

## <a name="features-removed-or-deprecated-in-the-finance-10030-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.30

### <a name="revenue-recognition"></a>Riconoscimento ricavi

[Riconoscimento ricavi](../../finance/accounts-receivable/revenue-recognition-overview.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo della deprecazione/rimozione** |Sostituito da una funzionalità migliorata, [Fatturazione abbonamento](../../finance/accounts-receivable/subscription-billing-summary.md)
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate** | Domanda di lavoro |
| **Opzione di distribuzione** | Tutti |
| **Status** | Deprecata: dopo aprile 2023, la funzionalità di riconoscimento delle entrate in Dynamics 365 Finance non riceverà più supporto con correzioni di bug. Ai clienti verrà chiesto di utilizzare la funzionalità migliorata, [Fatturazione abbonamento](../../finance/accounts-receivable/subscription-billing-summary.md). A ottobre 2023 la funzione di riconoscimento delle entrate non sarà più disponibile. Ai clienti verrà chiesto di passare alla funzionalità migliorata, Fatturazione abbonamento.|

## <a name="features-removed-or-deprecated-in-the-finance-10029-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.29

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Ordini di trasferimento scorte con imposta sul prezzo di trasferimento

[Ordini di trasferimento scorte con imposta sul prezzo di trasferimento](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo della deprecazione/rimozione** | Sostituita da una funzionalità migliorata, [Ordini di trasferimento stock per l'India](../../finance/localizations/apac-ind-stock-transfer.md)|
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate** | Domanda di lavoro |
| **Opzione di distribuzione** | Tutti |
| **Status** | Deprecata: dopo aprile 2023, la funzionalità **Ordini di trasferimento scorte con imposta sul prezzo di trasferimento** non riceverà più supporto per correzioni di bug e correzioni di sicurezza. Ai clienti verrà chiesto di utilizzare la funzionalità migliorata, [Ordini di trasferimento stock per l'India](../../finance/localizations/apac-ind-stock-transfer.md). Dopo ottobre 2023, la funzionalità **Ordini di trasferimento scorte con imposta sul prezzo di trasferimento** non sarà più disponibile e ai clienti verrà chiesto di passare alla funzionalità migliorata. |

### <a name="bank-statement-import-and-export-of-positive-pay-file"></a>Importazione ed esportazione dei rendiconti bancari del file pagamenti sicuri

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo della deprecazione/rimozione** |Sostituito da funzionalità migliorate, importa rendiconti bancari ed esporta il file pagamenti positivi.| 
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Status**                         | Deprecato: la funzionalità XSLT per l'importazione e l'esportazione di file non riceverà più supporto con correzioni di bug e correzioni di sicurezza. Ai clienti verrà chiesto di utilizzare la funzionalità migliorata: [Impostare file di pagamento sicuri utilizzando la creazione di report elettronici](../../finance/accounts-payable/set-up-positive-pay-er.md) e [Impostare il processo di importazione della riconciliazione estratti conto avanzata mediante la creazione di report elettronici](../../finance/accounts-payable/import-bai2-er.md). Dopo settembre 2022, la funzionalità XSLT non sarà più disponibile e ai clienti verrà chiesto di passare alla funzionalità migliorata.|


## <a name="features-removed-or-deprecated-in-the-finance-10026-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.26

### <a name="sales-tax-report-for-finland-design-based-on-reporting-codes"></a>Report IVA per la Finlandia (progettazione basata sui codici di reporting)

[Report IVA per la Finlandia](../localizations/emea-fin-sales-tax-payment-report-finland.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con un nuovo modello di dichiarazione IVA, [Dichiarazione IVA per la Finlandia](../localizations/emea-fin-vat-declaration.md). |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Status**                         | Deprecato: entro il 1° marzo 2023, prevediamo di non supportare più il report IVA per la Finlandia (layout report finlandese). I nuovi formati di report elettronici **XML di dichiarazione IVA (FI**) e **Excel di dichiarazione IVA (FI)** sono stati invece introdotti nel modello **Dichiarazione fiscale**. |

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.24

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>Report IVA per la Svezia (progettazione basata sui codici di reporting)

[Report IVA per la Svezia](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con un nuovo modello di dichiarazione IVA, [Dichiarazione IVA per la Svezia](../localizations/emea-swe-vat-declaration-sweden.md) |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Applicazione |
| **Opzione di distribuzione**              | Tutte |
| **Status**                         | Deprecato: entro il 1° dicembre 2022, prevediamo di non supportare più il report IVA per la Svezia (layout report svedese). I nuovi formati di report elettronici **XML di dichiarazione IVA (SE**) e **Excel di dichiarazione IVA (SE)** sono stati invece introdotti nel modello **Dichiarazione fiscale**. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>Dichiarazione IVA per l'Austria (progettazione basata su codici di reporting)

[Dettagli dichiarazione IVA per l'Austria](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con un nuovo modello di dichiarazione IVA, [Dichiarazione IVA per l'Austria](../localizations/emea-aut-vat-declaration-austria.md) |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Applicazione |
| **Opzione di distribuzione**              | Tutte |
| **Status**                         | Deprecato: entro il 1 dicembre 2022, prevediamo di non supportare più il formato di report elettronici **Dichiarazione IVA (AT)** sotto **Modello di dichiarazione IVA**. I nuovi formati **XML di dichiarazione IVA (AT)** e **Excel di dichiarazione IVA (AT)** sono stati invece introdotti nel modello **Dichiarazione fiscale**. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes"></a>Dichiarazione ELSTER per la Germania (progettazione basata su codici di reporting)

[Dichiarazione IVA](../localizations/emea-de-vat-declaration.md)</br>
[Impostare la dichiarazione fiscale elettronica per la Germania](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>
[Trasmissione elettronica della dichiarazione IVA (ELSTER)](../localizations/tasks/de-00003-electronic-transmission-elster.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con un nuovo modello di dichiarazione IVA, [Dichiarazione IVA per la Germania](../localizations/emea-deu-vat-declaration-germany.md) |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Applicazione |
| **Opzione di distribuzione**              | Tutte |
| **Status**                         | Deprecato: entro il 1 dicembre 2022, prevediamo di non supportare più i formati di report elettronici **Elster (DE)** e **Modello Elster**. I nuovi formati **XML di dichiarazione IVA (DE)** e **Excel di dichiarazione IVA (DE)** sono stati invece introdotti nel modello **Dichiarazione fiscale**. |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes"></a>Dichiarazione OB per i Paesi Bassi (progettazione basata su codici di reporting)

[Dichiarazione OB](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con un nuovo modello di dichiarazione IVA, [Dichiarazione IVA per i Paesi Bassi](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Applicazione |
| **Opzione di distribuzione**              | Tutte |
| **Status**                         | Deprecato: entro il 1 dicembre 2022, prevediamo di non supportare più i formati di report elettronici **Dichiarazione OB (NL)** e **Modello di dichiarazione OB**. I nuovi formati **XML di dichiarazione IVA (NL)** e **Excel di dichiarazione IVA (NL)** sono stati invece introdotti nel modello **Dichiarazione fiscale**. |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.20

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>Configurazione di formato "RTIR Query Invoice Data Request (HU)" per la creazione di report elettronici

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Escluso dall'elaborazione della messaggistica elettronica dell'interoperabilità con il sistema di fatturazione online ungherese |
| **Sostituita da un'altra funzionalità?**   | No |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Obsoleto: entro il 15 aprile 2022, prevediamo di non supportare più la configurazione del formato "RTIR Query Invoice Data Request (HU)". |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>Formato per la creazione di report elettronici "File di controllo FEC in francese" per la Francia in "Output file di controllo in tedesco"

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con il nuovo formato "File di controllo FEC (FR)" |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: a partire dal 1 maggio 2022, prevediamo di non supportare più il formato "File di controllo FEC in francese" per la creazione di report elettronici per la Francia in "Output file di controllo in tedesco". Il nuovo formato di file di controllo FEC (FR) viene invece introdotto in "Modello di esportazione dati". |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.17

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>Repository LCS come opzione di archiviazione per configurazioni di report elettronici

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con il nuovo repository globale di Regulatory Configuration Service (RCS) |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Prodotti Dynamics 365 Finance, Supply Chain Management e Project Operations|
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1° aprile 2022, prevediamo di non supportare più il repository Microsoft Dynamics Lifecycle Services (LCS) come opzione di archiviazione per le configurazioni per la creazione di report elettronici (ER). Le nuove configurazioni di Microsoft ER verranno pubblicate per il download esclusivamente dal repository globale. È possibile accedere al repository globale dai prodotti Dynamics 365 e da RCS. Per ulteriori informazioni, vedere [Importazione di configurazioni ER da RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) e [Regulatory Configuration Service - Deprecazione dell'archiviazione di Lifecycle Services](../localizations/rcs-lcs-repo-dep-faq.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.16

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Formati di dichiarazione elettronica "Dichiarazione IVA (CZ)" e "Esportazione dichiarazione di controllo (CZ)" per la Repubblica ceca

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con nuovi formati |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 22 gennaio 2022, prevediamo che non verranno più supportati i formati per report elettronici (ER) "Dichiarazione IVA (CZ)" ed "Esportazione dichiarazione di controllo (CZ)". I nuovi formati XML (CZ) di dichiarazione IVA, Excel di dichiarazione IVA (CZ), XML di dichiarazione di controllo IVA (CZ) sono stati invece introdotti nel modello "Dichiarazione fiscale". |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>Formato di creazione di report elettronici "Ledger transaction export format (BE)" e rispettivo modello "Ledger transaction export (BE)" per il Belgio

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con il nuovo formato di creazione report elettronici "Standard Audit File (SAF-T)".  |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1 ° dicembre 2021, prevediamo di non supportare più il formato di creazione di report elettronici "Ledger transaction export format (BE)" e rispettivo modello "Ledger transaction export (BE)" per il Belgio. Un nuovo formato "General ledger data export (BE)" insieme a "General ledger data model mapping" sono invece introdotti nel modello "Standard Audit File (SAF-T)". |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>Report "VAT 100" per il Regno Unito nel formato SSRS

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Sostituito con il nuovo formato per la creazione di report elettronici: formato "Excel di dichiarazione IVA (UK)" in "Modello di dichiarazione fiscale".  |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1° dicembre 2021, prevediamo di non supportare più il "report VAT 100" nel formato SSRS. Un nuovo formato "Excel di dichiarazione IVA (UK)" in "Modello di dichiarazione fiscale" è stato introdotto nella [funzionalità IVA MTD](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Il supporto di Internet Explorer 11 per Dynamics 365 è deprecato

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | A partire da dicembre 2020, il supporto di Microsoft Internet Explorer 11 per tutti i prodotti Dynamics 365 è deprecato e Internet Explorer 11 non sarà supportato dopo agosto 2021.<br><br>Ciò avrà un impatto sui clienti che utilizzano prodotti Dynamics 365 progettati per essere utilizzati tramite un'interfaccia Internet Explorer 11. Dopo agosto 2021, Internet Explorer 11 non sarà supportato per questi prodotti Dynamics 365. |
| **Sostituita da un'altra funzionalità?**   | Consigliamo ai clienti di passare a Microsoft Edge.|
| **Aree del prodotto interessate**         | Tutti i prodotti Dynamics 365 |
| **Opzione di distribuzione**              | Tutti|
| **Stato**                         | Deprecato. Internet Explorer 11 non sarà supportato dopo agosto 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.12

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Non deprecato: Report SSRS polacchi: registro IVA vendite, registro IVA acquisti, registro IVA riepilogativo UE - Riferimento funzione PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Non obbligatorio per legge.  |
| **Sostituita da un'altra funzionalità?**   | Sì (formato Excel per file di controllo standard con dichiarazione IVA - JPK_VDEK) |
| **Aree del prodotto interessate**         | Domanda di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Non deprecato: da 27 aprile 2021 continueremo a supportare i report SSRS: **Registro IVA vendite, Registro IVA acquisti, Registro IVA riepilogativo UE - Riferimento funzione PL-00014**. È stato anche introdotto un esempio di formato Excel per il file di audit standard con dichiarazione IVA (JPK_VDEK). |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.11

### <a name="norwegian-standard-main-accounts"></a>Conti principali standard per la Norvegia

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Riprogettazione  |
| **Sostituita da un'altra funzionalità?**   | Sì (sostituito con parametri specifici dell'applicazione in formato ER) |
| **Aree del prodotto interessate**         | Richiesta |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: entro il 1° aprile 2021, prevediamo di non supportare più la funzionalità relativa ai conti principali standard: campo di riferimento, tabella correlata, entità dei dati. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Funzionalità rimosse o deprecate nella versione Finance 10.0.7

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>La finestra di dialogo per la modifica della richiesta del flusso di lavoro non include più l'elenco a discesa per la selezione dell'utente

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Modificato nella funzionalità con selezione di gruppi di conti.  |
| **Sostituita da un'altra funzionalità?**   | Sì |
| **Aree del prodotto interessate**         | Flusso di lavoro |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: Dal 1° dicembre 2020, prevediamo di non supportare più l'impostazione dei tipi di giustificativi cinesi senza la selezione dei gruppi di conti. Ulteriori dettagli relativi alla nuova progettazione della funzionalità sono disponibili in [Novità di 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annunci precedenti sulle funzionalità rimosse o deprecate
Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

