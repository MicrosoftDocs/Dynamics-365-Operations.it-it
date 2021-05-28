---
title: Quando reimpostare un data mart
description: Questo argomento elenca le circostanze che potrebbero essere migliorate reimpostando un data mart e le circostanze in cui è improbabile che la reimpostazione del data mart sia di aiuto.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988994"
---
# <a name="when-to-reset-a-data-mart"></a>Quando reimpostare un data mart

La reimpostazione di un data mart può richiedere molto tempo. A seconda delle circostanze, questa azione potrebbe non essere la soluzione necessaria. Questo argomento elenca le circostanze che potrebbero essere migliorate reimpostando un data mart, nonché le circostanze in cui è improbabile che la reimpostazione del data mart sia di aiuto.  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a>Quando devo eseguire la reimpostazione del data mart?
Considera le seguenti domande prima di reimpostare un data mart. La risposta affermativa a una o più domande potrebbe indicare che l'organizzazione può trarre vantaggio dalla reimpostazione del data mart.

- Il database dell'applicazione è stato ripristinato?
- Se hai aperto un incidente di supporto e un tecnico del supporto ti ha chiesto di reimpostare il data mart come parte di un passaggio di risoluzione dei problemi.
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a>Quando non è opportuno reimpostare un data mart?
In alcune circostanze non è consigliabile reimpostare un data mart, tra cui le seguenti. 

- Stai riscontrando problemi di prestazioni associati a una sincronizzazione dei dati. 
- Se si dispone di uno schema di ripristino ricorrente dovuto a uno dei seguenti motivi: 
  - **Dati mancanti** 
  - **Stato di integrazione bloccato** 
  - **Record obsoleti** - I record obsoleti da soli non giustificano necessariamente la reimpostazione del data mart. Se si dispone di un set di dati di grandi dimensioni, l'esecuzione del processo di reimpostazione richiederà un po' di tempo, ma è improbabile che si verifichi un miglioramento.
 
## <a name="what-is-a-data-mart-reset"></a>Cos'è una reimpostazione di un data mart?
- Una reimpostazione inizierà solo al termine delle attività esistenti. Ciò garantisce che i vecchi dati non vengano inseriti. A questo punto potrebbe essere visualizzato un messaggio del tipo "Impossibile elaborare la reimpostazione del data mart a causa di un'attività attiva. Riprova più tardi."
- La reimpostazione disabiliterà le attività di integrazione ed eliminerà tutti i dati del data mart. L'integrazione viene nuovamente abilitata.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Se reimposto il data mart, perderò i report che ho già progettato? 
No, i report vengono archiviati in tabelle SQL che non sono influenzate da una reimpostazione del data mart. Se sei preoccupato di perdere i report che hai progettato, puoi eseguire il backup dei dati che non vuoi rischiare di perdere. Per eseguire il backup, apri Report Designer e vai a **Società > Società > Blocchi predefinit > Esporta**.
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a>È necessario che tutti gli utenti escano dal sistema per reimpostare il data mart?
No, gli utenti possono continuare a lavorare nel sistema durante la reimpostazione del data mart. Tuttavia, non potranno accedere ai report creati con Financial Reporter fino al termine della reimpostazione. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
