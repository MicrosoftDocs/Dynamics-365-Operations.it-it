---
title: Estensibilità dell'ottimizzazione della pianificazione
description: Questo articolo descrive gli scenari di estensibilità supportati in Ottimizzazione pianificazione.
author: t-benebo
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 7d649110959e6bcfdaeb32dd53c55dbc446ed1be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857546"
---
# <a name="planning-optimization-extensibility"></a>Estensibilità dell'ottimizzazione della pianificazione

[!include [banner](../../includes/banner.md)]

Questo articolo descrive gli scenari di estensibilità relativi alla pianificazione generale e supportati in Ottimizzazione pianificazione. Queste funzionalità sono disponibili a partire da Microsoft Dynamics 365 Supply Chain Management versione 10.0.13.

## <a name="custom-processing-when-master-planning-is-completed"></a>Elaborazione personalizzata al completamento della pianificazione generale

Nello scenario di estensibilità più comune in Ottimizzazione pianificazione, l'elaborazione personalizzata viene eseguita dopo l'aggiornamento del piano. Ad esempio, potresti aggiungere una colonna alla tabella degli ordini pianificati (`ReqPO`) oppure potresti voler ricavare alcune informazioni statistiche dal piano generato. Il principale punto di estensibilità che consente questi scenari è il metodo `jobCompletedSuccessfully` nella classe `MpsMasterPlanningEvents`.

```X++
public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
```

Ecco un esempio di un'estensione che imposta un campo `CstmOrderPriority` personalizzato sull'ordine pianificato.

```X++
[ExtensionOf(classStr(MpsMasterPlanningEvents))]
public static final class MpsMasterPlanningEvents_Cstm_Extension
{
    public static void jobCompletedSuccessfully(MpsMasterPlanningJobCompletedSuccessfullyEventArgs _args)
    {
        ttsbegin;

        var affectedPlannedOrdersQuery = _args.parmPostProcessingQueryBuilder().buildAffectedPlannedOrdersQuery();
        var affectedPlannedOrdersQueryRun = new QueryRun(affectedPlannedOrdersQuery);

        while (affectedPlannedOrdersQueryRun.next())
        {
            ReqPO reqPO = affectedPlannedOrdersQueryRun.get(tableNum(ReqPO));
            reqPO.selectForUpdate(true);
            reqPO.CstmOrderPriority = reqPO.ReqDate - systemDateGet() < 7 ? CstmPlannedOrderPriority::Urgent : CstmPlannedOrderPriority::Regular;
            reqPO.doUpdate();
        }

        ttscommit;

        next jobCompletedSuccessfully(_args);
    }

}
```

Quando aggiungi la logica personalizzata, considera i seguenti vincoli e procedure consigliate:

- Il metodo `jobCompletedSuccessfully` viene chiamato al di fuori dell'ambito della transazione. Pertanto, il piano è già visibile all'utente quando inizia l'esecuzione della logica personalizzata. Se la personalizzazione imposta campi aggiuntivi sugli ordini pianificati, è importante informare gli utenti che i valori di tali campi alla fine saranno coerenti (in altre parole, potrebbero essere obsoleti subito dopo il completamento di un processo di pianificazione).
- Un altro lavoro di pianificazione generale può iniziare quando viene chiamato il metodo `jobCompletedSuccessfully`. Il nuovo lavoro potrebbe influire sull'intero piano o su parte del piano. Il nuovo processo potrebbe aggiornare o eliminare gli stessi ordini pianificati o transazioni di richiesta che sono stati creati o aggiornati come parte del processo di pianificazione gestito in `jobCompletedSuccessfully`. Le eccezioni di conflitto di aggiornamento devono essere gestite quando questo evento viene esteso.
- Evita di utilizzare l'ambito della singola transazione quando estendi questo metodo. Una singola esecuzione della pianificazione generale può produrre milioni di transazioni di fabbisogno e centinaia di migliaia di ordini pianificati. Se tutte queste transazioni e ordini pianificati vengono elaborati nell'ambito di una singola transazione, si verificheranno molti blocchi SQL e bloccheranno altri processi di pianificazione. Inoltre, se la transazione viene trattenuta per lungo tempo, verranno creati "record fantasma" nel database SQL. I record fantasma influenzeranno negativamente ogni processo nel sistema.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]