---
title: Panoramica di riconciliazione di pagamento e di rendiconto bancario dell&quot;UE
description: "In questo argomento viene fornita una panoramica delle funzionalità che è possibile utilizzare per riconciliare le informazioni sul pagamento dalle banche dei formati utilizzati per i paesi europei."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267994
ms.assetid: 2bfb8ecc-e850-43cb-9a96-deb11716a391
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 22d93d7b3618d4f5931c6a7e39d681173734b0b9
ms.lasthandoff: 03/31/2017


---

# <a name="bank-statement-and-payment-reconciliation-overview-for-the-eu"></a>Panoramica di riconciliazione di pagamento e di rendiconto bancario dell'UE

In questo argomento viene fornita una panoramica delle funzionalità che è possibile utilizzare per riconciliare le informazioni sul pagamento dalle banche dei formati utilizzati per i paesi europei.

In Microsoft Dynamics 365 per le operazioni, è possibile importare transazioni dalle banche e liquidare le transazioni a fronte delle transazioni esistenti. In Europa, è possibile effettuare questa operazione per gli scenari seguenti:

-   Importazione dei rendiconti bancari
-   Importazione dei pagamenti.
-   Importazione di file di ritorno.

## <a name="bank-statements"></a>Rendiconti bancari
Uno statement* di *bank o lo statement* di *account è un riepilogo delle transazioni finanziarie che si verificano in un determinato periodo su un conto bancario utilizzato da una società con un istituto finanziario. In Dynamics 365 per le operazioni è possibile includere un rendiconto bancario. È importante liquidare le transazioni importate con le transazioni esistenti nonché verificare l'esito dell'apertura e il saldo finale dei conti bancari. Nel seguente elenco sono riportati i formati europei supportati.

-   Formati di file anticipati di europeo di riconciliazione estratti conto. Per ulteriori informazioni, vedere [panoramica avanzata di riconciliazione estratti conto (]. /cash-bank-management/advanced-bank-reconciliation-overview.md).
-   Formato di file del messaggio di rendiconto bancario camt.053 ISO 20022
-   Formato file di rendiconto bancario CODA. Per ulteriori informazioni, vedere [] rendiconto bancario CODA (emea-bel-coda-bank-statement-import.md).

## <a name="customer-and-vendor-payments-import-and-return-messages"></a>I pagamenti clienti/fornitori sono e rende i messaggi
Oltre a un rendiconto bancario, le banche possono generare messaggi specifici, contenendo le informazioni sui pagamenti clienti/fornitori, che possono essere importati in Dynamics 365 per le operazioni e essere eseguita la riconciliazione tra con il cliente e le transazioni fornitore. Una società deve ricevere informazioni sulle operazioni di pagamento entrate del cliente dalla banca, i formati di importazione possono essere utilizzati. Per le società che utilizzano addebito diretto e il bonifico, i messaggi di reso possono essere ricevuti per aggiornare lo stato del pagamento che sono stati precedentemente esportati. Differenza tra i formati di importazione e i formati di reso consente dei resi sono mirati a principalmente per aggiornare le righe esistenti del giornale di registrazione pagamenti (possono essere creati in addebito diretto o il bonifico è ancora iniziata) anziché creare nuove righe. Alcuni formati di importazione complessi possono includere gli scenari di reso. Nel seguente esempio viene illustrato come questa suddivisione deve essere implementate.

##### <a name="import-formats"></a>Formati di importazione

-   Messaggio di notifica della banca camt.054 ISO 20022
-   [Formato di importazione delle reti] () - emea-nor-nets-import-format.md funzionalità complessa per il pagamento norvegese formattazione
-   Importazione di importare i pagamenti PVR
-   Importare i formati di pagamento per la Svezia - Bankgirot formati Bankgirot e massimo OCR

##### <a name="return-formats"></a>Ripristina i formati

-   Relazione di pagamento pain.002 ISO 20022
-   (DNK) BetalingsserviceBasis-returformat - formato resi per il formato di esportazione Betalingsservice cliente
-   [Il pagamento di importazione formattare per la Svezia] () - emea-swe-payment-formats-import.md Bankgirot Autogiro viene reimpostato su
-   (SWE) Bankgirot reso dei pagamenti fornitore vengono rese il formato, che corrisponda al formato di esportazione Bankgirot

