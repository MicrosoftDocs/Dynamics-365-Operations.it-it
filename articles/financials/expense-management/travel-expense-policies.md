---
title: Definire i criteri di spesa
description: In Microsoft Dynamics 365 for Finance and Operations è possibile definire criteri di spesa che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26336710b277ce9594c8546f2214e152a3460204
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840891"
---
# <a name="expense-policies"></a>Criteri di spesa

[!include [banner](../includes/banner.md)]

È possibile definire criteri che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.         
L'implementazione di criteri di spesa consente di gestire le spese in modo efficiente.         

È ad esempio possibile impostare un criterio per le spese di albergo a New York, secondo il quale non devono superare USD 250 a notte.       
Se un lavoratore invia una nota spese o una richiesta di viaggio in cui il prezzo della camera supera questo importo, riceverà una notifica        
in cui viene indicato che è stato superato l'importo previsto dal criterio per questo tipo di spesa. È possibile configurare il messaggio che il lavoratore riceverà quando        
si definiscono i criteri.      
        
È possibile definire tre tipi di criteri:         
        
- Avviso: consente al lavoratore di inviare una nota spese o una richiesta di viaggio ma la spesa verrà contrassegnata per tutti gli approvatori e        
  per la dichiarazione successiva.        

- Errore: richiede al lavoratore di rivedere la spesa per conformarsi ai criteri prima di inviare la nota spese o la richiesta di viaggio.       
 
 - Motivazione: richiede al lavoratore o a un responsabile di immettere una motivazione per superare l'importo previsto dai criteri prima di inviare la nota spese o la richiesta di viaggio.        

## <a name="policy-tips"></a>Suggerimenti per i criteri
Di seguito sono riportati alcuni suggerimenti per semplificare la creazione di nuovi criteri per la gestione delle spese. 
* I criteri sono sensibili alla data e non avranno effetto se vengono creati con una data successiva alla data in cui si è verificata la spesa. Ad esempio, se oggi si stanno creando nuovi criteri per applicare una spesa massima per il pasto di 50 EUR, le eventuali spese esistenti inserite ieri non verranno verificate rispetto a questo criterio.
* Durante la creazione dei criteri per una categoria di spesa che può essere dettagliata, è opportuno considerare l'aggiunta di una condizione per il tipo di riga spese. Alcuni criteri come la richiesta di una ricevuta potrebbero non avere senso per le righe dettagliate e dovrebbero essere applicate solo alla riga dell'intestazione o a una riga non dettagliata. 

## <a name="when-to-evaluate-policies"></a>Quando effettuare la valutazione dei criteri

Nei parametri di Gestione spese, è disponibile un'opzione per effettuare la valutazione basata sui criteri di gestione delle spese quando viene salvata una riga o quando viene inviata una nota spese. Se si sceglie di effettuare la valutazione dei criteri quando viene salvata una riga, ciò garantisce che gli utenti abbiano una visibilità anticipata su ciò che devono fare per completare le note spese contemporaneamente. In alternativa, è possibile ritardare la valutazione basata sui criteri e risparmiare tempo impostando la convalida alla fine, durante l'invio al flusso di lavoro.
