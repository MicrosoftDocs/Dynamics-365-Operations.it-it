---
title: Riclassifica i cespiti
description: Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd108f2e778b31749c66b2787d9f59467cae97dd
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977217"
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
