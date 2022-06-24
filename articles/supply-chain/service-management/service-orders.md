---
title: Ordini di assistenza
description: In questo articolo viene fornita una panoramica di come utilizzare gli ordini di assistenza.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 606a1e3df72f8a76dab477bb1dd961b6df16f3cf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882375"
---
# <a name="service-orders"></a>Ordini di assistenza

[!include [banner](../includes/banner.md)]

L'ordine di assistenza rappresenta l'intervento eseguito da un tecnico presso la sede di un cliente in una data specifica. Ogni ordine di assistenza consiste in una o più righe di ordine di assistenza, che rappresentano le ore di lavoro che il tecnico dovrà effettuare, nonché gli articoli, le spese e gli addebiti.

È possibile collegare le attività e gli oggetti a una riga di ordine di assistenza e raggruppare quindi le righe di ordine di assistenza in base a un'attività o a un oggetto. È inoltre possibile allegare articoli a magazzino alle righe dell'ordine di assistenza.

## <a name="create-service-orders"></a>Creare ordini di assistenza

Gli ordini di assistenza vengono creati in base al contratto di assistenza e alle relative righe. Tuttavia, è possibile creare ordini di assistenza associati a un contratto di assistenza solo nel periodo specificato nel contratto. Ad esempio, per il contratto di assistenza valido per l'anno 2011, era possibile creare ordini di assistenza nel periodo che andava dal 1 gennaio 2011 al 31 dicembre 2011.

Gli ordini di assistenza possono essere anche individuali, ovvero non devono necessariamente essere associati a un contratto di assistenza. Tali ordini di assistenza possono essere utilizzati per gestire interventi singoli o non programmati. Nel mese di marzo il cliente decide, ad esempio, di richiedere un intervento di assistenza su due macchine oltre a quelle specificate nel contratto di assistenza. Per questa attività, vengono creati gli ordini di assistenza, ma senza associarli a un contratto di assistenza.


> [!NOTE]
> Per creare degli ordini di assistenza non associati a un contratto di assistenza, è necessario selezionare la casella di controllo **Consenti senza contratto di assistenza** nella pagina **Parametri di gestione assistenza**.

### <a name="scenario"></a>Scenario

Nel seguente scenario viene descritta un'altra situazione in cui è utile creare un ordine di assistenza non associato a un contratto di assistenza.

Il responsabile interventi della società riceve una chiamata in cui si richiede un intervento di assistenza urgente per un ascensore. Non c'è tempo per impostare un contratto di assistenza e un progetto per l'assistenza. Di conseguenza, il responsabile intervento crea un ordine di assistenza direttamente nella pagina **Ordini di assistenza**, allega l'ordine di assistenza a un progetto esistente e crea le righe di ordine di assistenza. Per registrare il lavoro non correlato al contratto di assistenza, il responsabile intervento crea inoltre una relazione di attività o oggetto per un ordine di assistenza esistente. Per ulteriori informazioni, vedere [Creare ordini di assistenza manualmente](create-service-orders-manually.md) e [Creare relazioni di attività di assistenza tecnica](create-service-task-relations.md).

## <a name="monitor-the-progress-of-service-orders"></a>Monitoraggio dello stato di avanzamento degli ordini di assistenza

Per monitorare lo stato di avanzamento di un ordine cliente attraverso i diversi team e processi di lavoro, è possibile impostare un sistema di fasi e di codici causale per gli ordini di assistenza. Per ogni fase, è possibile specificare le azioni che sono consentite. Per ulteriori informazioni sui codici motivo, vedere [Creare codici motivo](create-reason-codes.md).

### <a name="example"></a>Esempio

Un ordine di assistenza è approvato dal responsabile intervento. Il responsabile aggiorna la fase dell'ordine di assistenza e specifica un codice causale che indichi che l'ordine di assistenza è stato rilasciato al tecnico. Il tecnico si reca presso la sede del cliente ed effettua l'assistenza.

## <a name="specify-item-requirements-for-service-orders"></a>Specificare richieste articoli per gli ordini di assistenza

È possibile specificare gli articoli di magazzino necessari per gli ordini di assistenza. Tuttavia, l'ordine di assistenza deve essere associato a un progetto. Le richieste articoli per gli ordini di assistenza vengono elaborati nel corso di un progetto. 

### <a name="example"></a>Esempio

Gli ordini di assistenza creati in base al contratto di assistenza vengono quindi elaborati dal responsabile intervento. Al primo ordine di assistenza, il responsabile intervento si rende conto che il tecnico ha bisogno di un pezzo di ricambio importante che non è disponibile in magazzino, di conseguenza crea una richiesta per il pezzo di ricambio direttamente dall'ordine di assistenza.

## <a name="move-and-post-lines"></a>Spostare e registrare le righe

Il tecnico torna da un intervento di assistenza e modifica e aggiorna le righe di ordine di assistenza. Durante l'assistenza, ha eseguito un lavoro di manutenzione che era programmato per l'intervento di assistenza successivo. Di conseguenza, il tecnico sposta le righe dall'intervento di assistenza successivo nell'intervento di assistenza corrente. Il tecnico quindi registra l'ordine di assistenza. Per ulteriori informazioni, vedere [Spostare righe ordine di assistenza](move-service-order-lines.md).

## <a name="cancel-service-orders"></a>Annulla ordini di assistenza

Uno degli altri ordini di assistenza generati per il mese di gennaio è diventato obsoleto, perché l'intervento è stato annullato. Il responsabile intervento annulla pertanto l'ordine di assistenza. Per ulteriori informazioni, vedere [Annullare ordini di assistenza](cancel-service-orders.md).

## <a name="post-from-projects"></a>Effettuare una registrazione da progetti

Al termine di ciascuna settimana, il responsabile intervento desidera registrare tutti gli ordini di assistenza collegati a un progetto specifico. Di conseguenza, individua il progetto pertinente nella pagina **Progetti** e registra gli ordini di assistenza che sono stati completati. Per ulteriori informazioni, vedere [Registra ordini di assistenza (modulo di classe)](https://technet.microsoft.com/library/aa574685\(v=ax.60\)).

## <a name="delete-service-orders"></a>Elimina ordini di assistenza

Durante il secondo semestre il cliente decide che gli interventi di assistenza non sono sufficientemente frequenti. È necessario creare una nuova serie di interventi più frequenti per la durata rimanente del contratto di assistenza. Gli ordini di assistenza già creati devono quindi essere eliminati ed è necessario crearne di nuovi. Per ulteriori informazioni, vedere [Eliminare ordini di assistenza](delete-service-orders.md).

## <a name="see-also"></a>Vedere anche

[Ordini di assistenza (modulo)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]