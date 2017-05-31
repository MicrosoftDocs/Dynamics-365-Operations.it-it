---
title: Importazione pagamenti cliente PVR
description: In questo argomento vengono fornite informazioni sull&quot;importazione dei pagamenti cliente in formato PVR.
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymMode, LedgerJournalTransCustPaym
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264584
ms.assetid: 60c429b5-1d88-4fef-be6b-b8585e0e9ee7
ms.search.region: Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f573885a71fdf449197ecea438e83d747c20a391
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="esr-customer-payments-import"></a>Importazione pagamenti cliente PVR

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sull'importazione dei pagamenti cliente in formato PVR.

PVR è un servizio di addebito elettronico che utilizza distinte di pagamento per raccogliere denaro. Si tratta del sistema di pagamento elettronico standard creato dalla Posta svizzera. È possibile ricevere i file di pagamento clienti in formato PVR, il quale può includere le transazioni e le commissioni bancarie. Questa funzionalità è progettata per le transazioni clienti importate in base ai riferimenti di pagamento originariamente generati in Microsoft Dynamics 365 for Operations e stampati nella distinta di pagamento.

## <a name="generate-payment-references"></a>Generare i riferimenti di pagamento
I riferimenti di pagamento devono essere stampati nella distinta di pagamento dopo la registrazione. È inoltre possibile verificare i riferimenti di pagamento nella pagina **Giornale di registrazione fatture** per ordine cliente selezionato. Per generare i riferimenti di pagamento, è necessario specificare le impostazioni seguenti.

1.  Configurare le impostazioni del conto bancario in **PVR**, **ID PVRB** e **Numero di registrazione**.
2.  Impostare il campo **Numero di caratteri per il conto ordini di accredito** nella pagina dei **parametri contabilità clienti** nella scheda **Contabilità generale e IVA**. In questo modo viene definito quanti simboli del conto cliente devono essere inclusi nel riferimento di pagamento.
3.  La sequenza numerica della fattura di vendita deve essere nel formato corretto (non deve includere simboli diversi dalle cifre e non deve contenere zeri iniziali).
4.  È necessario specificare il formato **Orange** per il conto cliente nel campo **Su fattura cliente** nella scheda **Fattura e consegna**.

Per ulteriori informazioni, vedere [Report distinta di pagamento (Giro)](emea-eur-payment-slip-report-giro.md).

## <a name="import-a-payment-file"></a>Importare un file di pagamento
1.  Passare alla pagina **Giornale di registrazione pagamenti**
2.  Fare clic su **Righe**.
3.  Fare clic su **Funzioni** &gt; **Importa pagamenti**.
4.  Nella finestra di dialogo selezionare il metodo di pagamento e quindi selezionare il percorso del file da importare. 
  > [!NOTE]
  >  Prima di completare questo passaggio, è necessario aver già importato le configurazioni **PVR (CH)** da Lifecycle Services (LCS) e aver impostato il metodo di pagamento PVR. Per ulteriori informazioni, vedere [Formati di file per metodi di pagamento](emea-select-file-formats-for-the-method-of-payments.md).

Dopo aver importato il file di pagamento, le righe del giornale di registrazione pagamenti vengono create e contrassegnate per la liquidazione con le fatture cliente in base al riferimento di pagamento. Se nel file sono presenti delle spese specificate per il conto bancario, ad esempio le transazioni tra il conto principale e il conto di addebito commissioni, queste spese verranno aggiunte al giornale di registrazione.




