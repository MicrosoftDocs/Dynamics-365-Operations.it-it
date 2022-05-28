---
title: Riclassifica i cespiti
description: Questo argomento illustra il processo di riclassificazione dei cespiti. Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo.
author: moaamer
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43ea9e342bf51126aa8857190b91549a364092c7
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726643"
---
# <a name="reclassify-fixed-assets"></a>Riclassifica i cespiti

[!include [banner](../../includes/banner.md)]

Per riclassificare un cespite, è necessario trasferirlo in un nuovo gruppo cespite o assegnare al cespite un nuovo numero nello stesso gruppo. 

Quando un cespite viene riclassificato:

- Per il nuovo cespite vengono creati tutti i libri del cespite esistente. Le informazioni impostate per il cespite originario vengono copiate nel nuovo cespite. Lo stato dei libri del cespite originario è Chiuso. 

- Nei nuovi libri del nuovo cespite è contenuta la data di riclassificazione presente nel campo **Data di acquisizione**. La data nel campo **Data esecuzione ammortamento** viene copiata dalle informazioni relative al cespite originario. Se l'ammortamento è già iniziato, nel campo **Data ultimo ammortamento** viene visualizzata la data di riclassificazione. 

- Le transazioni cespiti esistenti per il cespite originario vengono annullate e rigenerate per il nuovo cespite.

- Quando un cespite che ha una transazione di trasferimento è stato riclassificato, il sistema visualizzerà un messaggio nel **Centro azioni** per indicare che una transazione di trasferimento non è stata completata durante il processo di riclassificazione. È necessario completare una transazione di trasferimento per spostare le transazioni di riclassificazione esistenti nelle dimensioni finanziarie appropriate. 

   Durante il processo di riclassificazione, il sistema esegue le seguenti azioni per riclassificare il saldo cespiti dal cespite originale al nuovo. 
   
   - Il processo di riclassificazione copia i dati dal libro cespiti originale al nuovo libro cespiti.

   - La transazione di riclassificazione utilizza le informazioni dall'acquisizione registrata originale che include le informazioni sulla dimensione finanziaria incluse nella transazione di acquisizione.  
   
   - Allo stesso tempo, il processo di riclassificazione storna le transazioni di acquisizione e trasferimento cespite originali. 

Il diagramma e la procedura seguenti forniscono un esempio del processo di riclassificazione. 

[![Diagramma che mostra il processo di riclassificazione.](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)

Seguire questi passaggi per riclassificare un cespite:

1. Passare a **Cespiti > Attività periodiche > Riclassificazione**.
2. Nel campo **Gruppo cespite** selezionare il gruppo da riclassificare.
3. Nel campo **Numero cespite** selezionare il cespite da riclassificare.
4. Nel campo **Nuovo gruppo cespite**, selezionare un gruppo in cui trasferire il cespite.
    * Se il nuovo gruppo cespite è collegato a una sequenza numerica, il campo **Nuovo numero cespite** verrà aggiornato con il numero della sequenza numerica del nuovo gruppo cespite. In caso contrario, il campo **Nuovo numero cespite** viene aggiornato con il numero della sequenza numerica impostata nella pagina **Parametri cespite**. Se una sequenza numerica non è configurata nella pagina **Parametri cespite**, immettere un numero nel campo **Nuovo numero cespite**.  
5. Immettere una data nel campo **Riclassificazione**.
6. Nel campo **Serie giustificativi** immettere o selezionare un valore.
7. Selezionare **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
