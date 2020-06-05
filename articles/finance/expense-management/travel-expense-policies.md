---
title: Definire i criteri di spesa
description: In Microsoft Dynamics 365 Finance è possibile definire criteri di spesa che devono essere seguiti dai lavoratori per l'inserimento e l'invio di note spese e richieste di viaggio.
author: suvaidya
manager: AnnBe
ms.date: 05/20/2020
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
ms.openlocfilehash: 22504e0e26c025d117f29dee3b59b41d508e7724
ms.sourcegitcommit: 4f90b9ddedf312e75a714e0ec7f7ee5fd43cac6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "3389717"
---
# <a name="define-expense-policies"></a>Definire i criteri di spesa

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
* I criteri di gestione delle spese vengono valutati in base all'entità di origine per impostazione predefinita. Per gli scenari interaziendali, puoi invece impostare i criteri da valutare rispetto all'entità di destinazione (entità mutuataria). Per eseguire i criteri sull'entità di destinazione, attiva la funzione "Valuta i criteri di spesa contro l'entità giuridica richiedente" nell'area di lavoro **Gestione funzionalità**.

## <a name="when-to-evaluate-policies"></a>Quando effettuare la valutazione dei criteri

Nei parametri di Gestione spese, è disponibile un'opzione per effettuare la valutazione basata sui criteri di gestione delle spese quando viene salvata una riga o quando viene inviata una nota spese. Se si sceglie di effettuare la valutazione dei criteri quando viene salvata una riga, ciò garantisce che gli utenti abbiano una visibilità anticipata su ciò che devono fare per completare le note spese contemporaneamente. In alternativa, è possibile ritardare la valutazione basata sui criteri e risparmiare tempo impostando la convalida alla fine, durante l'invio al flusso di lavoro.
