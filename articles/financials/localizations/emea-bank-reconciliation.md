---
title: Rendiconto bancario e riconciliazione dei pagamenti dell'UE
description: "In questo argomento viene fornita una panoramica delle funzionalità che è possibile utilizzare per riconciliare le informazioni sul pagamento dalle banche dei formati utilizzati dai paesi europei."
author: neserovleo
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 267994
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 3dc0b968fdf217554b350a152195a4b3d235fdf0
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="bank-statement-and-payment-reconciliation-for-the-eu"></a>Rendiconto bancario e riconciliazione dei pagamenti dell'UE

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica delle funzionalità che è possibile utilizzare per riconciliare le informazioni sul pagamento dalle banche dei formati utilizzati dai paesi europei.

In Microsoft Dynamics 365 for Finance and Operations, è possibile importare transazioni da banche e liquidare queste transazioni a fronte di transazioni esistenti. In Europa, è possibile effettuare questa operazione per gli scenari seguenti:

-   Importazione rendiconti bancari
-   Importazione pagamenti
-   Importazione di file di risposta

## <a name="bank-statements"></a>Rendiconti bancari
Un *rendiconto bancario* o *estratto conto* è un riepilogo delle transazioni finanziarie effettuate in un dato periodo su un conto bancario gestito da una società presso un istituto finanziario. In Finance and Operations è possibile importare un rendiconto bancario. È importante liquidare le transazioni importate con le transazioni esistenti nonché verificare il saldo iniziale e finale dei conti bancari. Nel seguente elenco sono riportati i formati europei supportati.

-   Formati di file europei per la riconciliazione estratti conto avanzata. Per ulteriori informazioni, vedere [Panoramica sulla riconciliazione degli estratti conto avanzata](../cash-bank-management/advanced-bank-reconciliation-overview.md).
-   Formato di file del messaggio di rendiconto bancario ISO 20022 camt.053.
-   Formato di file di rendiconto bancario CODA. Per ulteriori informazioni, vedere [Rendiconto bancario CODA](emea-bel-coda-bank-statement-import.md).

## <a name="customer-and-vendor-payments-import-and-return-messages"></a>Messaggi di importazione e risposta di pagamenti clienti e fornitori
Oltre a un rendiconto bancario, le banche possono generare messaggi specifici, contenenti informazioni sui pagamenti clienti/fornitori, che possono essere importati in Finance and Operations ed essere riconciliati con le transazioni dei clienti e dei fornitori. Quando una società necessita di ricevere dalla banca informazioni sulle transazioni dei pagamenti clienti in entrata, è possibile utilizzare i formati di importazione. Le società che utilizzano l'addebito diretto e il bonifico possono ricevere messaggi di risposta per aggiornare lo stato dei pagamenti precedentemente esportati. La differenza tra i formati di importazione e i formati di risposta consiste nel fatto che le risposte servono principalmente ad aggiornare le righe del giornale di registrazione pagamenti già create (possono essere create con l'addebito diretto o il bonifico) anziché crearne di nuove. Alcuni formati di importazione complessi possono includere gli scenari di risposta. Nel seguente esempio viene illustrato come implementare questa divisione.

### <a name="import-formats"></a>Formato di importazione

-   Messaggio di notifica della banca ISO 20022 [camt.054](emea-ISO20022-file-formats.md)
-   [Formato di importazione Nets](emea-nor-nets-import-format.md) - Complessa funzionalità per i formati di pagamento norvegesi
-   [Importazione pagamenti clienti ESR](emea-che-esr-customer-payments-import.md)
-   formati di importazione pagamenti per la Svezia - formati BankGirot Max e BankGirot OCR

### <a name="return-formats"></a>Formati di risposta

-   Report sullo stato dei pagamenti ISO 20022 [pain.002](emea-ISO20022-file-formats.md)
-   (DNK) BetalingsserviceBasis-returformat - Formato di risposta per il formato di esportazione clienti Betalingsservice
-   [Formati di importazione pagamenti per la Svezia](emea-swe-payment-formats-import.md) - Risposte Bankgirot Autogiro
-   Risposta (SWE) BankGirot - Formato di risposta pagamenti fornitori che corrisponde al formato di esportazione Bankgirot



