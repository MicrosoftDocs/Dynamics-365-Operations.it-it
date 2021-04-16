---
title: Riclassifica i cespiti
description: Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo.
author: saraschi2
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8935213c4629de408a48df5e54a2122324e1b3e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823934"
---
# <a name="reclassify-fixed-assets"></a>Riclassifica i cespiti

[!include [banner](../../includes/banner.md)]

Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo. 

Quando un cespite viene riclassificato:

* Per il nuovo cespite vengono creati tutti i libri del cespite esistente. Le informazioni impostate per il cespite originario vengono copiate nel nuovo cespite. Lo stato dei libri del cespite originario è Chiuso. 

* Nei nuovi libri del nuovo cespite è contenuta la data di riclassificazione presente nel campo **Data di acquisizione**. La data nel campo **Data esecuzione ammortamento** viene copiata dalle informazioni relative al cespite originario. Se l'ammortamento è già iniziato, nel campo **Data ultimo ammortamento** viene visualizzata la data di riclassificazione. 

* Le transazioni cespiti esistenti per il cespite originario vengono annullate e rigenerate per il nuovo cespite.

Seguire questi passaggi per riclassificare un cespite:

1. Passare a **Cespiti > Attività periodiche > Riclassificazione**.
2. Nel campo **Gruppo cespite** selezionare il gruppo da riclassificare.
3. Nel campo **Numero cespite** selezionare il cespite da riclassificare.
4. Nel campo **Nuovo gruppo cespite**, selezionare un gruppo in cui trasferire il cespite.
    * Se il nuovo gruppo cespite è collegato a una sequenza numerica, il campo **Nuovo numero cespite** verrà aggiornato con il numero della sequenza numerica del nuovo gruppo cespite. In caso contrario, il campo **Nuovo numero cespite** viene aggiornato con il numero della sequenza numerica impostata nella pagina **Parametri cespite**. Se una sequenza numerica non è configurata nella pagina **Parametri cespite**, immettere un numero nel campo **Nuovo numero cespite**.  
5. Immettere una data nel campo **Riclassificazione**.
6. Nel campo **Serie giustificativi** immettere o selezionare un valore.
7. Fare clic su **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]