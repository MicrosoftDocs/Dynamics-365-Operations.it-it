---
title: Domande frequenti sul ripristino dei data mart
description: In questo articolo vengono fornite risposte ad alcune domande frequenti sul ripristino dei data mart.
author: jinniew
ms.date: 03/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.search.form: ''
ms.openlocfilehash: 6cb418c331f0ad260f0c370b87404028e5a953f1
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9205828"
---
# <a name="data-mart-resets-faq"></a>Domande frequenti sul ripristino dei data mart

In questo articolo vengono fornite risposte ad alcune domande frequenti sul ripristino dei data mart. Un ripristino del data mart può richiedere molto tempo e, a seconda delle circostanze, potrebbe non essere la soluzione necessaria. Pertanto, questo articolo include informazioni sulle circostanze in cui un ripristino del data mart potrebbe essere d'aiuto e anche sulle circostanze in cui è improbabile che sia d'aiuto.

## <a name="what-is-a-data-mart-reset"></a>Cos'è una reimpostazione di un data mart?

Un ripristino del data mart disabiliterà le attività di integrazione, eliminerà tutti i dati del data mart e quindi riattiverà l'integrazione.

Per garantire che i vecchi dati non vengano inseriti, è possibile avviare un ripristino del data mart solo dopo che le attività esistenti sono state completate. Se tenti di reimpostare il data mart prima del completamento di tutte le attività, è possibile che venga visualizzato un messaggio del tipo "Impossibile elaborare il ripristino del data mart a causa di un'attività attiva. Riprova più tardi."

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Quando si esegue il ripristino del data mart?

Se una o più delle seguenti affermazioni si applicano alla tua situazione, la tua organizzazione può trarre vantaggio da un ripristino del data mart:

- **Il database dell'applicazione è stato ripristinato**
- **Hai aperto un ticket di supporto** - Un tecnico del supporto ti ha chiesto di ripristinare il data mart come parte di un passaggio di risoluzione dei problemi.
- **Grande percentuale di record obsoleti** - I record obsoleti da soli non giustificano necessariamente il ripristino del data mart. Percentuali elevate di dati obsoleti possono ridurre la generazione di report e le prestazioni di integrazione complessive e comportare un utilizzo aggiuntivo dello spazio del database. Si consiglia di completare un ripristino del datamart per rimuovere i dati obsoleti quando nel datamart sono presenti più dell'80% di dati non aggiornati.
 
> [!NOTE]
> Il processo di reimpostazione di un data mart è influenzato dal numero di transazioni di contabilità generale e budget nel database. A seconda del numero di transazioni nel sistema, un ripristino del data mart può essere completato in appena 15 minuti o possono essere necessarie fino a quattro ore. Tuttavia, se il ripristino richiede più di quattro ore, ti consigliamo di contattare l'assistenza.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Quando non è appropriato ripristinare un data mart?

Ecco alcune circostanze in cui non è consigliabile reimpostare un data mart:

- Stai riscontrando problemi di prestazioni di integrazione dei dati.
- L'integrazione di Financial Reporter non è abilitata. 

    - Ciò significa che i dati di contabilità generale non vengono più sincronizzati con il datamart di Financial Reporting. Il tuo Financial Reporter potrebbe non ricevere numeri aggiornati per i tuoi report finanziari. Ciò si verifica in genere se non si utilizza Financial Reporter per molto tempo.
    - Verrà richiesto di abilitare l'integrazione reimpostando il data mart. Puoi procedere selezionando **sì**. Puoi anche scegliere di ripristinare il data mart in un secondo momento. Dopo aver abilitato l'integrazione, i dati della contabilità generale vengono nuovamente sincronizzati in Financial Reporter. 
- Se hai uno schema di ripristino ricorrente per uno dei seguenti motivi:

    - **Dati mancanti o imprevisti nel report** – Se noti che mancano dei dati, apri un ticket di supporto con Microsoft per rivedere il formato del report e i possibili problemi di sincronizzazione dei dati.
    - **Stato di integrazione bloccato** - Se noti che lo stato di integrazione è bloccato in esecuzione, ciò potrebbe essere dovuto a un volume elevato di transazioni nel sistema. Questo stato si risolverà da solo. Tuttavia, se noti che lo stato di integrazione è bloccato per più di quattro ore, apri un ticket di supporto con Microsoft. 
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Se reimposto il data mart, perderò i report che ho già progettato?

N. I report vengono archiviati in tabelle SQL che non sono influenzate da un ripristino del data mart. Se sei preoccupato di perdere i report che hai progettato, puoi eseguire il backup dei dati che non vuoi rischiare di perdere. Per eseguire il backup dei progetti, apri Progettazione report e vai a **Società \> Società \> Blocchi predefiniti \> Esporta**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Tutti gli utenti devono uscire dal sistema prima di poter ripristinare il data mart?

N. Gli utenti possono continuare a lavorare nel sistema durante il ripristino del data mart. Tuttavia, non potranno accedere ai report creati con Financial Reporter fino al termine del ripristino.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
