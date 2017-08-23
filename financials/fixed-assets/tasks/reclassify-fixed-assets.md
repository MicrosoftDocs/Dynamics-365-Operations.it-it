--- 
title: Riclassifica i cespiti
description: "Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo."
author: saraschi2
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: dcad2c2e225a07bf9e9eb7fe7bbec605f668f8f5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="reclassify-fixed-assets"></a>Riclassifica i cespiti

[!include[task guide banner](../../includes/task-guide-banner.md)]

Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo. 

Quando un cespite viene riclassificato:

• Per il nuovo cespite vengono creati tutti i modelli di valore del cespite esistente. Le informazioni impostate per il cespite originario vengono copiate nel nuovo cespite. Lo stato dei modelli di valore del cespite originario è Chiuso. 

• Nei nuovi modelli di valore del nuovo cespite è contenuta la data di riclassificazione presente nel campo Data di acquisizione. La data nel campo Data esecuzione ammortamento viene copiata dalle informazioni relative al cespite originario. Se l'ammortamento è già iniziato, nel campo Data ultimo ammortamento viene visualizzata la data di riclassificazione. 

• Le transazioni cespiti esistenti per il cespite originario vengono annullate e rigenerate per il nuovo cespite.

1. Passare a Cespiti > Attività periodiche > Riclassificazione.
2. Nel campo Gruppo cespite selezionare il gruppo da riclassificare.
3. Nel campo Numero cespite selezionare il cespite da riclassificare.
4. Nel campo Nuovo gruppo cespite, selezionare un gruppo in cui trasferire il cespite.
    * Se il nuovo gruppo cespite è collegato a una sequenza numerica, il campo Nuovo numero cespite verrà aggiornato con il numero della sequenza numerica del nuovo gruppo cespite. In caso contrario, il campo Nuovo numero cespite viene aggiornato con il numero della sequenza numerica impostata nella pagina Parametri cespite. Se una sequenza numerica non è configurata nella pagina Parametri cespite, immettere un numero nel campo Nuovo numero cespite.  
5. Immettere una data nel campo Riclassificazione.
6. Nel campo Serie giustificativi immettere o selezionare un valore.
7. Fare clic su OK.


