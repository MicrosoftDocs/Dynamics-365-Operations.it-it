--- 
title: Impostare libri
description: In questa procedura viene illustrato come creare un nuovo libro cespiti e associarlo a un gruppo cespite.
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 668fea64810524e8ce0c3833d25656c026f2780a
ms.openlocfilehash: 7e57b26c17d3bf773a719f9725d5f47dce2af6f7
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2017

---
# <a name="set-up-books"></a>Impostare libri

[!include[task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come creare un nuovo libro cespiti e associarlo a un gruppo cespite. Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.


## <a name="create-a-book"></a>Creare un libro
1. Passare a Cespiti > Impostazione > Libri.
2. Fare clic su Nuovo.
3. Nel campo Libro digitare un valore.
4. Nel campo Descrizione digitare un valore.
    * Se Calcola ammortamento è selezionato, il libro cespiti associato verrà incluso nelle proposte di ammortamento. Se non è selezionato, il libro cespiti non verrà ammortizzato automaticamente.  
5. Selezionare Sì nel campo Calcola ammortamento.
6. Nel campo Profilo di ammortamento immettere o selezionare un valore.
    * Un profilo di ammortamento alternativo è anche noto come metodo di ammortamento alternativo. La proposta di ammortamento passerà a questo profilo quando il profilo alternativo calcolerà un importo di ammortamento uguale o maggiore del profilo di ammortamento predefinito.  
    * Parametri di ammortamento straordinario viene utilizzato per l'ammortamento aggiuntivo di un cespite in circostanze insolite. È ad esempio possibile utilizzare questi parametri per registrare l'ammortamento causato da un disastro naturale.  
    * Se Crea rettifiche all'ammortamento con rettifiche di base è selezionato, le rettifiche di ammortamento verranno automaticamente create quando il valore del cespite viene aggiornato. Se non è selezionato, il valore del cespite aggiornato influirà solo sui calcoli di ammortamento successivi.  
7. Selezionare Sì nel campo Crea rettifiche all'ammortamento con rettifiche di base.
    * Per impostazione predefinita, Ogni transazione libro cespiti verrà registrata nella contabilità generale. È possibile disabilitare la registrazione nella contabilità generale per il libro impostando il campo Registra nella contabilità generale su No. I libri che non vengono registrate nella contabilità generale viene in genere utilizzato a fini di reporting fiscale. Ciò offre flessibilità aggiuntiva per eliminare le transazioni storiche del libro cespiti perché non sono state impegnate nella contabilità generale.  
    * Il livello di registrazione assume il valore predefinito Livello corrente se il libro viene registrato nella contabilità generale e Nessuno se non viene registrato nella contabilità generale. Aggiornare il livello di registrazione se sono necessarie delle transazioni perché tale libro venga registrato in un altro livello.  
8. Nel campo Calendario immettere o selezionare un valore.
    * I libri derivati registreranno transazioni in libri diversi contemporaneamente. Le transazioni si creano con il libro principale e durante la registrazione, una copia esatta della transazione viene registrata nel libro derivato. Non esiste un ricalcolo con le transazioni nei libri derivati, quindi non devono essere utilizzati per le transazioni di ammortamento.  

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Associare il libro a un gruppo cespite
1. Fare clic su Gruppi cespiti.
2. Nel campo Cespiti immettere o selezionare un valore.
3. Immettere un numero nel campo Vita utile.
    * Si noti che il valore del campo Periodi di ammortamento viene calcolato dopo aver impostato Vita utile.  
    * È possibile impostare la convenzione di ammortamento come richiesto per scopi fiscali.  


