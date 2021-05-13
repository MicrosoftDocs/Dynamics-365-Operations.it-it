---
title: Ciclo non è idoneo per la pulizia
description: Ciclo non è idoneo per la pulizia
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924329"
---
# <a name="wave-isnt-eligible-for-cleanup"></a>Ciclo non è idoneo per la pulizia

Codice di errore: WaveNotEligibleForCleanup

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> L'ondata %1 non è idonea per la pulizia.

I dati del ciclo non possono essere puliti.  

## <a name="cause"></a>Causa

Il ciclo è attualmente in fase di elaborazione, come indicato da una delle seguenti condizioni:

- Il campo **Stato ciclo** è impostato su *Esecuzione*.
- Quando selezioni **Processo batch** nel gruppo **Ciclo** della scheda **Ciclo** nel riquadro azioni, il campo **Stato** non è impostato su *Finito*, *Errore*, o *Annullato*. Pertanto, un processo batch è attualmente in esecuzione.

## <a name="resolution"></a>Risoluzione

Nel riquadro azioni, nella scheda **Ciclo**, nel gruppo **Ciclo**, selezionare **Processo batch**, quindi seguire uno di questi passaggi:

- Se il campo **Stato** è impostato su *Esecuzione*: Nel riquadro azioni, nella scheda **Processo batch** nel gruppo **Processo batch**, seleziona **Visualizza attività**. È possibile monitorare lo stato aggiornano la pagina **Attività batch**.
- Se il campo **Stato** non è impostato su *Esecuzione*: Nel riquadro azioni, nella scheda **Processo batch** nel gruppo **Funzioni**, seleziona **Cambia stato**. Nel campo **Seleziona nuovo stato** selezionare *In attesa*. Selezionare **OK**.
