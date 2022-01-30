---
title: Applica automaticamente i pagamenti anticipati per le fatture fornitore
description: Questo argomento descrive la capacità di applicare automaticamente i pagamenti anticipati alle fatture fornitore.
author: sunfzam
ms.date: 10/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5b07c1d4c2189184b2ad29d46ec2aef0ee03c1c0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985364"
---
# <a name="automatically-apply-to-vendor-invoices"></a>Applica automaticamente alle fatture fornitore

[!include [banner](../includes/banner.md)]

Questo argomento descrive la capacità di applicare automaticamente i pagamenti anticipati alle fatture fornitore. È possibile creare un pagamento anticipato per un ordine fornitore come parte di un contratto di acquisto. Dopo aver ricevuto una fattura fornitore, il pagamento anticipato può essere utilizzato per liquidare la contabilità fornitori dalla fattura fornitore. La nuova funzionalità consente al sistema di utilizzare automaticamente i numeri dell'ordine fornitore su una fattura fornitore per cercare i pagamenti anticipati corrispondenti quando viene importata la fattura fornitore.

Se i pagamenti anticipati vengono trovati e possono essere applicati, le righe vengono aggiunte alle righe fattura esistenti per applicare i pagamenti anticipati. Le righe di pagamento anticipato non vengono mai considerate durante il processo di abbinamento fatture.

I seguenti punti descrivono come vengono applicati i pagamenti anticipati quando vengono seguiti diversi processi di acquisto:

- **Una fattura fornitore per ordine fornitore**: il pagamento anticipato sull'ordine fornitore verrà applicato alla fattura fornitore.
- **Una fattura fornitore per più ordini fornitore**: i pagamenti anticipati su tutti gli ordini fornitore verranno applicati alla fattura fornitore.
- **Più fatture fornitore per ordine fornitore**: il pagamento anticipato sull'ordine fornitore verrà applicato alla fattura fornitore importata per prima. Se l'importo del pagamento anticipato supera l'importo della fattura, l'applicazione del pagamento anticipato non riesce ed è necessario applicare manualmente il pagamento anticipato.
- **Più fatture fornitore per più ordini fornitore**: i pagamenti anticipati sugli ordini fornitore verrà applicato alla prima fattura fornitore rilevante. Se l'importo del pagamento anticipato supera l'importo della fattura, l'applicazione del pagamento anticipato non riesce ed è necessario applicare manualmente i pagamenti anticipati. Se eventuali pagamenti anticipati che rimangono dopo i pagamenti anticipati vengono applicati alla prima fattura, possono essere applicati alle fatture successive.

Se il sistema tenta di applicare un pagamento anticipato, ma l'applicazione non riesce, il comportamento dipende dall'impostazione dell'opzione **Blocca il processo di automazione del follow-up in caso di esito negativo della richiesta di pagamento anticipato**:

- **Sì**: il messaggio di errore "Applicazione automatica del pagamento anticipato: non riuscita" viene aggiunto nella cronologia dell'automazione e la fattura rimane nell'elenco delle fatture fornitore in sospeso. La fattura rimarrà bloccata fino a quando non applicherai manualmente il pagamento anticipato.

    Per applicare manualmente i pagamenti anticipati, vai alla fattura fornitore in sospeso. Nella pagina **Dettagli della fattura**, imposta l'opzione **Includi in elaborazione automatizzata** per la fattura bloccata su **No**. Ora puoi applicare manualmente il pagamento anticipato. Dopo aver applicato il pagamento anticipato, imposta l'opzione **Includi in elaborazione automatizzata** di nuovo su **Sì** in modo che la fattura possa essere elaborata automaticamente.

    Puoi anche ignorare l'applicazione automatica del pagamento anticipato impostando l'opzione **Includi in elaborazione automatizzata** su **No** e poi reimpostandola su **Sì**. Riceverai il seguente messaggio: "Esiste già un pagamento anticipato per l'ordine fornitore. Vuoi ignorarlo per la fattura fornitore selezionata?" Selezionare **Sì**. Il messaggio "Applicazione di pagamento anticipato ignorata manualmente" viene aggiunto nella cronologia dell'automazione e la fattura fornitore non verrà bloccata quando il processo automatizzato verrà nuovamente eseguito.

- **No**: i successivi processi di automazione continueranno. Puoi comunque applicare il pagamento anticipato durante il regolamento.
