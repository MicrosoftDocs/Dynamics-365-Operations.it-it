---
title: Quando reimpostare un data mart
description: Questo argomento elenca le circostanze che potrebbero essere migliorate reimpostando un data mart e le circostanze in cui è improbabile che la reimpostazione del data mart sia di aiuto.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71324d4aa2d20dd6ae4729412a017d130ab0144f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563735"
---
# <a name="when-to-reset-a-data-mart"></a>Quando reimpostare un data mart

La reimpostazione di un data mart può richiedere molto tempo. A seconda delle circostanze, questa azione potrebbe non essere la soluzione necessaria. Questo argomento elenca le circostanze che potrebbero essere migliorate reimpostando un data mart, nonché le circostanze in cui è improbabile che la reimpostazione del data mart sia di aiuto.  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a>Quando è necessario eseguire un ripristino del data mart?
Considera le seguenti domande prima di reimpostare un data mart. La risposta affermativa a una o più domande potrebbe indicare che l'organizzazione può trarre vantaggio dalla reimpostazione del data mart.

- Il database dell'applicazione è stato ripristinato, ma non è stato ripristinato il database data mart.
- Vengono visualizzati dati errati per un periodo contabile, che non sono il risultato di un problema con la progettazione del report.
- Vengono visualizzati dati errati per un periodo contabile e i record sono elencati in Tentativi di integrazione nella pagina **Stato integrazione** in Progettazione report (avvia Progettazione report e seleziona **Strumenti> Stato integrazione**).
- Hai aperto un incidente di supporto e un tecnico del supporto ti ha chiesto di reimpostare il data mart come parte di un passaggio di risoluzione dei problemi.
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a>Quando non è opportuno reimpostare un data mart?
In alcune circostanze non è consigliabile reimpostare un data mart, tra cui le seguenti. 

- Ogni volta che il motivo non è elencato in questo argomento.
- Stai riscontrando problemi di prestazioni associati a una sincronizzazione dei dati. In questa circostanza, la reimpostazione del data mart probabilmente non è di aiuto.
- Se si dispone di uno schema di ripristino ricorrente dovuto a uno dei seguenti motivi: 
  - **Dati mancanti** - In primo luogo, elimina i problemi di progettazione dei report e i problemi di sincronizzazione dei dati, ad esempio, osservi che la mappa dei fatti non è stata eseguita da quando sono stati pubblicati i dati mancanti.
  - **Stato di integrazione bloccato** - Se l'integrazione è lenta o sembra bloccata, è improbabile che il ripristino del data mart risolva il problema.
  - **I tentativi di ripristino non hanno avuto successo** - Se sono stati effettuati diversi tentativi per completare un ripristino e non hanno avuto successo a causa della mancanza di dati, si consiglia di aprire un incidente di supporto e di collaborare con un tecnico dell'assistenza per analizzare la situazione prima di tentare di ripristinare nuovamente il data mart.
  - **Record obsoleti** - I record obsoleti da soli non giustificano necessariamente il ripristino del data mart. Se si dispone di un set di dati di grandi dimensioni, l'esecuzione del processo di ripristino richiederà un po' di tempo, ma è improbabile che si verifichi un miglioramento.
 
## <a name="what-a-data-mart-reset-does-not-do"></a>Cosa non fa un ripristino del data mart  
- Un ripristino inizierà solo al termine delle attività esistenti. Ciò garantisce che i vecchi dati non vengano inseriti. A questo punto potrebbe essere visualizzato un messaggio del tipo "Impossibile elaborare il ripristino del data mart a causa di un'attività attiva. Riprova più tardi."
- Il ripristino disabiliterà le attività di integrazione ed eliminerà tutti i dati del data mart. L'integrazione viene nuovamente abilitata.

> [!NOTE]
> I seguenti punti specificano due cose che il ripristino di un data mart *non* fa. <br>
> - I ripristini non cancellano le progettazioni di report. <br>
> - I ripristini non cancellano i dati della società o dei dati dell'utente a meno che non siano selezionati.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]