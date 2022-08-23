---
title: Reimpostare i numeri di ricevuta
description: Questo articolo descrive come reimpostare i numeri di ricevuta utilizzati per varie azioni a una determinata data (ad esempio, l'anno fiscale o l'anno di calendario).
author: ShalabhjainMSFT
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, Commerce
ms.search.form: ''
ms.openlocfilehash: 3034a1b8f1a9f304b8d8803a7f906418321d81d9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272743"
---
# <a name="reset-receipt-numbers"></a>Reimpostare i numeri di ricevuta 

[!include [banner](includes/banner.md)]

> [!NOTE]
> Ti chiediamo di selezionare la proprietà **Sequenza indipendente** per tutti i tipi di ricevuta nel profilo di funzionalità prima di utilizzare questa funzione. Inoltre, il fuso orario di sistema del dispositivo, in cui viene utilizzato il POS, deve corrispondere al fuso orario del negozio corrispondente. A causa di queste limitazioni, ti consigliamo di non utilizzare questa funzionalità in produzione mentre lavoriamo per risolvere questi problemi in una versione futura. 

I rivenditori generano numeri di ricevuta per varie azioni nel punto vendita, come ad esempio transazioni cash-and-carry, transazioni di reso, ordini cliente, offerte e pagamenti. Sebbene i rivenditori definiscano i propri formati di ricevuta, alcuni paesi o aree geografiche hanno normative che impongono restrizioni a questi formati di ricevute. Ad esempio, queste normative potrebbero limitare il numero di caratteri sulla ricevuta, richiedere numeri di ricevuta consecutivi, limitare alcuni caratteri speciali o richiedere un azzeramento dei numeri di ricevuta all'inizio dell'anno. Microsoft Dynamics 365 Commerce rende estremamente flessibile il processo di gestione dei numeri di ricevuta, per aiutare i rivenditori a soddisfare i requisiti normativi. Questo articolo descrive come utilizzare la funzionalità di reimpostazioni dei numeri di ricevuta.

In Commerce, i formati delle ricevute possono essere alfanumerici. È possibile inserire sia contenuto statico che contenuto dinamico. Il contenuto statico include caratteri alfabetici, numeri e caratteri speciali. Il contenuto dinamico include uno o più caratteri che rappresentano informazioni come il numero di punto vendita, il numero di terminale, la data, il mese, l'anno e le sequenze numeriche che vengono incrementate automaticamente. I formati sono definiti nella sezione **Numerazione ricevute** del profilo della funzionalità. La tabella seguente descrive i caratteri che rappresentano il contenuto dinamico.

| Caratteri | Descrizione |
|------------|-------------|
| S          | Il carattere **S** viene utilizzato per il numero di punto vendita. Ad esempio, se il numero di un punto vendita è HOUSTON1, il formato **SSS** mostra "ON1" sulla ricevuta. Il formato **SSSSS** mostra "STON1" sulla ricevuta. |
| T          | Il carattere **T** viene utilizzato per il numero di terminale. Ad esempio, se il numero di un terminale è 0001, il formato **TTTT** mostra "0001" sulla ricevuta. |
| C          | Il carattere **C** viene utilizzato per il numero di ID personale. Ad esempio, se l'ID di un membro del personale è 000160, il formato **CCCC** mostra "0160" sulla ricevuta. |
| ggg        | I caratteri **ggg** corrispondono al giorno dell'anno, dall'1 al 366. Ad esempio, il 15 gennaio, il formato **ggg** mostra "015" sulla ricevuta. |
| MM         | I caratteri **MM** vengono utilizzati per il mese a due cifre. Ad esempio, in gennaio, il formato **MM** mostra "01" sulla ricevuta. |
| GG         | I caratteri **GG** vengono utilizzati per il giorno del mese a due cifre. Ad esempio, il 15 gennaio, il formato **GG** mostra "15" sulla ricevuta. |
| AA         | I caratteri **AA** vengono utilizzati per l'anno a due cifre. Ad esempio, in qualsiasi mese dell'anno 2020, il formato **AA** mostra "20" sulla ricevuta. |
| \#         | Un segno numerico ( **\#**) viene utilizzato per la numerazione sequenziale. Ad esempio, il formato **####** mostra "0001", "0002", "0003" e così via sulla ricevuta. |

È possibile reimpostare la numerazione sequenziale della ricevuta a una data specifica. Quindi, per la prima transazione che si verifica dopo le 00:00 alla data di azzeramento selezionata, il sistema reimposta la sequenza numerica della ricevuta su 1. È inoltre possibile specificare se la reimpostazione si verifica una sola volta o se si ripete ogni anno. Se viene specificata la ricorrenza annuale, la reimpostazione si verifica automaticamente ogni anno fino a quando il rivenditore non decide di interromperla. 

Per attivare la reimpostazione, effettuare le seguenti operazioni.

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**.
1. Nella Scheda dettaglio **Numerazione ricevute**, selezionare **Reimposta data di azzeramento numero**.
1. Nella finestra di dialogo a discesa, in **Data di azzeramento**, selezionare la data futura alla quale dovrebbe avvenire la reimpostazione.
1. Nel campo **Reimposta tipo di ricevuta**, selezionare **Una sola volta** o **Ogni anno**.
1. Selezionare **OK**.

![Selezionare la data di azzeramento delle ricevute.](media/Enable_receipt_reset.png "Selezionare la data di azzeramento delle ricevute")

Dopo aver selezionato una data, questa appare nella colonna **Data di azzeramento numero di ricevuta successiva**. La data di azzeramento è applicabile a tutti i tipi di transazioni di ricevuta. Pertanto, la sequenza del numero di ricevuta verrà reimpostata per tutti i tipi di ricevuta.

Alla data di azzeramento, il numero di ricevuta viene reimpostato per la prima transazione di ogni tipo. Inoltre, nel profilo delle funzionalità, la data di azzeramento viene spostata dalla colonna **Data di azzeramento numero di ricevuta successiva** alla colonna **Data di azzeramento numero di ricevuta corrente**. Questa modifica indica che se un registro non viene utilizzato alla data di azzeramento, il numero di ricevuta verrà reimpostato la volta successiva che il registro *è* utilizzato. Ad esempio, il 3 dicembre 2019, si seleziona **1 gennaio 2020**, come data di azzeramento. Il 1° gennaio, quando i registri effettuano la prima transazione, il numero di ricevuta viene reimpostato. Tuttavia, un registro non viene utilizzato affatto a dicembre e gennaio, ma inizia a essere utilizzato a febbraio. In questo caso, poiché è stata definita un'azione di reimpostazione, il numero di ricevuta per quel registro verrà reimpostato quando il registro effettua la prima transazione a febbraio.

È possibile utilizzare la funzionalità **Annulla data di azzeramento** per annullare le date di azzeramento future. Tuttavia, se la data di azzeramento si è verificata in passato, non può essere annullata. Pertanto, la reimpostazione verrà comunque eseguita per tutti i registri in cui la reimpostazione non è ancora stata eseguita.

> [!NOTE]
> A seconda della data di azzeramento selezionata e del formato della ricevuta, è possibile che si abbiano numeri di ricevuta duplicati. Sebbene il sistema POS sia in grado di gestire queste situazioni, queste aumentano la quantità di tempo necessaria per elaborare i resi poiché gli addetti alle vendite devono scegliere tra le ricevute duplicate. Altre complicazioni legate alla pulizia dei dati possono verificarsi se le ricevute duplicate non erano una conseguenza pianificata. Pertanto, si consiglia di utilizzare caratteri di data dinamici (ad esempio, **ggg**, **MM**, **DD** e **AA**) per evitare numeri di ricevuta duplicati dopo una reimpostazione.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
