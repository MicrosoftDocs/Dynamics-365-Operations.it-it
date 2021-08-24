---
title: Domande frequenti sul ripristino dei data mart
description: In questo argomento vengono fornite risposte ad alcune domande frequenti sul ripristino dei data mart.
author: jinniew
ms.date: 07/16/2021
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
ms.openlocfilehash: e5a40342306eb9888b456a865ab2220dccfe65f8ccecc67bf8fc16f907e06977
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767757"
---
# <a name="data-mart-resets-faq"></a>Domande frequenti sul ripristino dei data mart

In questo argomento vengono fornite risposte ad alcune domande frequenti sul ripristino dei data mart. Un ripristino del data mart può richiedere molto tempo e, a seconda delle circostanze, potrebbe non essere la soluzione necessaria. Pertanto, questo argomento include informazioni sulle circostanze in cui un ripristino del data mart potrebbe essere d'aiuto e anche sulle circostanze in cui è improbabile che sia d'aiuto.

## <a name="what-is-a-data-mart-reset"></a>Cos'è una reimpostazione di un data mart?

Un ripristino del data mart disabiliterà le attività di integrazione, eliminerà tutti i dati del data mart e quindi riattiverà l'integrazione.

Per garantire che i vecchi dati non vengano inseriti, è possibile avviare un ripristino del data mart solo dopo che le attività esistenti sono state completate. Se tenti di reimpostare il data mart prima del completamento di tutte le attività, è possibile che venga visualizzato un messaggio del tipo "Impossibile elaborare il ripristino del data mart a causa di un'attività attiva. Riprova più tardi."

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Quando si esegue il ripristino del data mart?

Se una o più delle seguenti affermazioni si applicano alla tua situazione, la tua organizzazione può trarre vantaggio da un ripristino del data mart:

- Il database dell'applicazione è stato ripristinato.
- Hai aperto un ticket di supporto e un tecnico del supporto ti ha chiesto di ripristinare il data mart come parte di un passaggio di risoluzione dei problemi.
 
> [!NOTE]
> Il processo di reimpostazione di un data mart è influenzato dal numero di transazioni di contabilità generale e budget nel database. A seconda del numero di transazioni nel sistema, un ripristino del data mart può essere completato in appena 15 minuti o possono essere necessarie fino a quattro ore. Tuttavia, se il ripristino richiede più di quattro ore, ti consigliamo di contattare l'assistenza.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Quando non è appropriato ripristinare un data mart?

Ecco alcune circostanze in cui non è consigliabile reimpostare un data mart:

- Stai riscontrando problemi di prestazioni associati a una sincronizzazione dei dati.
- Se hai uno schema di ripristino ricorrente per uno dei seguenti motivi:

    - **Dati mancanti** – Se noti che mancano dei dati, apri un ticket di supporto con Microsoft per rivedere il formato del report e i possibili problemi di sincronizzazione dei dati.
    - **Stato di integrazione bloccato**
    - **Record obsoleti** - I record obsoleti da soli non giustificano necessariamente il ripristino del data mart. Se hai un set di dati di grandi dimensioni, l'esecuzione del processo di reimpostazione richiederà un po' di tempo, ma è improbabile che si verifichi un miglioramento.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Se reimposto il data mart, perderò i report che ho già progettato?

N. I report vengono archiviati in tabelle SQL che non sono influenzate da un ripristino del data mart. Se sei preoccupato di perdere i report che hai progettato, puoi eseguire il backup dei dati che non vuoi rischiare di perdere. Per eseguire il backup dei progetti, apri Progettazione report e vai a **Società \> Società \> Blocchi predefiniti \> Esporta**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Tutti gli utenti devono uscire dal sistema prima di poter ripristinare il data mart?

N. Gli utenti possono continuare a lavorare nel sistema durante il ripristino del data mart. Tuttavia, non potranno accedere ai report creati con Financial Reporter fino al termine del ripristino.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
