---
title: Importazione di importare i pagamenti PVR
description: In questo argomento vengono fornite informazioni sull&quot;importazione dei pagamenti cliente in formato PVR.
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: f7fd20ef0c78bc781f0ef9f17fc612723906ac78
ms.openlocfilehash: 87643da8ef213f72740370a52d500d9f6fb2fcf2
ms.lasthandoff: 03/31/2017


---

# <a name="esr-customer-payments-import"></a>Importazione di importare i pagamenti PVR

In questo argomento vengono fornite informazioni sull'importazione dei pagamenti cliente in formato PVR.

In ESR è un servizio del contribuente che utilizza le distinte di pagamento per raccogliere il denaro. Si tratta del sistema di pagamento elettronico standard creato dalla posta svizzera. È possibile ricevere i file di pagamento del cliente in formato PVR, che possono includere le transazioni e le commissioni bancarie. Questa funzionalità è progettata per le transazioni incluse del cliente in base ai riferimenti di pagamento da consegnare sono stati generati in Microsoft Dynamics 365 per le operazioni e sono state stampati nella distinta di pagamento.

## <a name="generate-payment-references"></a>Generare i riferimenti di pagamento
I riferimenti di pagamento devono essere stampati nella distinta di pagamento dopo la registrazione. È inoltre possibile verificare i riferimenti di pagamento ** giornale di registrazione fatture ** nella pagina per l'ordine cliente selezionato. Per generare i riferimenti di pagamento, le seguenti impostazioni devono essere specificate.

1.  Impostare le impostazioni di conto bancario a ** ESR **, ** ID BESR, ** e ** numero di registrazione **.
2.  Impostare ** numero di caratteri per il conto ordini di accredito ** il campo ** parametri di effetti attivi del conto ** nella pagina ** contabilità generale e VAT ** nella scheda. Si definisce il numero di simboli del cliente devono essere inclusi nel riferimento di pagamento.
3.  La sequenza numerica della fattura di vendita deve essere nel formato corretto (non deve essere simboli diversi dalle cifre e non deve contenere zeri iniziali).
4.  ** Arancia ** il formato deve essere specificata per il conto cliente in ** in una fattura cliente ** sistema ** fattura e consegna ** nella scheda.

Per ulteriori informazioni, vedere [report della distinta di pagamento (ordine di accredito)](emea-eur-payment-slip-report-giro.md).

## <a name="import-a-payment-file"></a>Importare un file di pagamento
1.  Passare ** giornale di registrazione pagamenti nella pagina **
2.  Fare clic su **Righe**.
3.  Fare clic su Funzioni ** ** &gt; ** pagamenti di importazione **.
4.  Nella finestra di dialogo, selezionare il metodo di pagamento e quindi selezionare il percorso del file da importare. 
  > [!NOTE]
  >  Prima di completare questo passaggio, è necessario che siano già includere ** (ESR) CH ** le configurazioni da Servizi (LCS) del ciclo di vita e impostare il metodo PVR di pagamento. Per ulteriori informazioni, vedere [formati di file per il metodo di pagamento emea-select-file-formats-for-the-method-of-payments.md] ().

Dopo aver importare il file di pagamento, le righe del giornale di registrazione pagamenti vengono create e contrassegnate per la liquidazione con le fatture cliente in base al riferimento di pagamento. Se esistono delle spese specificate per il conto bancario che sono rappresentate nel file, ad esempio le transazioni tra il conto principale e il conto di addebito commissioni, queste verranno aggiunti al giornale di registrazione.


