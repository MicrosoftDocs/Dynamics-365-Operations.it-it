---
title: Impostare i modelli di valore
description: In questa procedura viene illustrato come creare un nuovo libro cespiti e associarlo a un gruppo cespite.
author: moaamer
ms.date: 08/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46c26e5fad3c5c60d87c2fea2b29043c69b82b5d
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344660"
---
# <a name="set-up-value-models"></a>Impostare i modelli di valore

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]


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

  - I periodi di ammortamento sono calcolati dopo aver inserito la vita utile del bene.  
  - La convenzione di ammortamento può essere impostata come richiesto a fini fiscali.
  - Per le attività fisse che sono associate a leasing, il valore nel campo **Vita utile** sarà sovrascritto dal minore tra la durata del leasing nel libro delle attività e la vita utile dell'attività. Se il campo **Trasferimento di proprietà** è impostato a **Sì** per il libro delle locazioni, il valore nel campo **Vita** utile sarà sempre la vita utile del bene.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
