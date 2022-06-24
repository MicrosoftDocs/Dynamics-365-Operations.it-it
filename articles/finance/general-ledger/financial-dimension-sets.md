---
title: Set di dimensioni finanziarie
description: In questo articolo vengono descritti set di dimensioni finanziarie e vengono forniti alcuni suggerimenti per ottimizzarne l'utilizzo.
author: yukonpeegs
ms.date: 03/07/2022
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 3d4c15504b2ad128493e1bafa36aed271c2ab6dc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864283"
---
# <a name="financial-dimension-sets"></a>Set di dimensioni finanziarie

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritti set di dimensioni finanziarie e vengono forniti alcuni suggerimenti per ottimizzarne l'utilizzo.

Un set di dimensioni è un elenco ordinato di dimensioni finanziarie che possono essere utilizzate per riepilogare i dati di contabilità generale in un modo definito dall'utente. Un utilizzo principale dei set di dimensioni è definire un bilancio di verifica.

L'unico set di dimensioni standard è il set di dimensioni che contiene solo il conto principale.

La pagina **Set di dimensioni finanziarie** viene utilizzata per creare e gestire set di dimensioni finanziarie.

## <a name="dimension-set-balances"></a>Saldi di set di dimensioni

Un set di dimensioni può avere saldi basati sulle relative dimensioni finanziarie. I saldi esistono nella contabilità generale e si basano sulla definizione del set di dimensioni. I saldi vengono riepilogati dai dati di contabilità generale per migliorare le prestazioni quando vengono recuperati (ad esempio, quando viene generato un bilancio di verifica).

## <a name="create-balances"></a>Crea saldi

Usare il pulsante **Crea saldi** per inizializzare i saldi per un set di dimensioni che attualmente non dispone di saldi.

> [!NOTE]
> Si consiglia di limitare il numero di set di dimensioni con saldi, poiché gli aggiornamenti dei saldi influiscono su tutte le attività di registrazione della contabilità generale.

## <a name="update-balances"></a>Aggiorna saldi

Usare il pulsante **Aggiorna saldi** per includere l'ultima attività di registrazione di contabilità generale nei saldi. Gli aggiornamenti dei saldi sono operazioni semplici. Devono elaborare solo l'attività di registrazione della contabilità generale che si è verificata dall'ultimo aggiornamento.

> [!NOTE]
> La visualizzazione del bilancio di verifica forza un aggiornamento, per garantire che i saldi visualizzati siano correnti. Considerare l'utilizzo di un processo batch ricorrente in modo che gli aggiornamenti dei set di dimensioni utilizzati più di frequente siano rapidi. In questo modo, è possibile ridurre al minimo il tempo di attesa degli utenti del bilancio di verifica.

## <a name="rebuild-balances"></a>Ricostruisci saldi

Usare il pulsante **Ricostruisci saldi** per ricreare i saldi da zero. In questo modo, se ne assicura la corrispondenza ai dati nella contabilità generale. Una ricostruzione dei saldi richiede molte elaborazioni e di solito non dovrebbe essere necessaria.

> [!NOTE]
> Se è presente uno scenario che richiede regolarmente una ricostruzione dei saldi, si consiglia di contattare l'assistenza clienti. L'assistenza clienti può aiutare a determinare il motivo per cui i saldi non corrispondono ai dati nella contabilità generale.

## <a name="clear-balances"></a>Cancella saldi

Usare il pulsante **Cancella saldi** per rimuovere i saldi e interrompere eventuali ulteriori aggiornamenti. Il set di dimensioni non avrà più alcun impatto sulle attività di registrazione della contabilità generale.

## <a name="delete-a-dimension-set"></a>Eliminare un set di dimensioni

Non **eliminare e ricreare** la quota impostata come qualsiasi forma di soluzione per risolvere potenziali problemi con i dati di bilancio per un set di quote specifiche. Ricreare un set di quote è costoso. Per ulteriore assistenza con questi problemi, contatta il supporto clienti. 


Per ulteriori informazioni, vedere [Dimensioni finanzarie](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
