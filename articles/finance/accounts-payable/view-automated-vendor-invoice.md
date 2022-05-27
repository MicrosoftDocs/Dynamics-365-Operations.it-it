---
title: Visualizzare i risultati dell'automazione delle fatture fornitore (anteprima)
description: In questo argomento viene descritto come visualizzare lo stato delle fatture fornitore che si trovano nel processo di invio al flusso di lavoro automatizzato.
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1700f4c4748dc12bf000b25c0d51bc6ed069a97b
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717251"
---
# <a name="view-vendor-invoice-automation-results"></a>Visualizzare i risultati dell'automazione delle fatture dei fornitori

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come visualizzare lo stato delle fatture fornitore che si trovano nel processo di invio al flusso di lavoro automatizzato. I dettagli della cronologia dell'automazione vengono mantenuti per ogni fattura fornitore importata. A seconda dei processi aziendali che hai automatizzato, la pagina **Fatture fornitore in sospeso** mostra i valori **Stato corrispondenza entrate automatizzate** e **Stato Invio a flusso di lavoro automatizzato**. Puoi visualizzare i dettagli e creare un piano per concentrarti sulle fatture che non hanno superato un passaggio automatizzato. Quindi, dopo aver corretto il problema, puoi riprendere il processo automatizzato per la fattura importata.

Prima di poter modificare una fattura inviata, devi sospendere l'elaborazione automatizzata. Se una fattura nel processo di invio al flusso di lavoro automatizzato deve essere sospesa, imposta il campo **Includi in elaborazione automatizzata** su **No** nella pagina **Fatture fornitore**. L'automazione quindi non verrà eseguita fino a quando **Includi in elaborazione automatizzata** non viene impostato su **Sì**. Una fattura può non essere sottoposta a un'ulteriore automazione se non è ancora nel sistema flusso di lavoro e non è utilizzata dal processo automatizzato.

Se una fattura importata è soggetta al processo di invio al flusso di lavoro, è possibile visualizzare il relativo valore **Stato automazione** nella pagina **Fatture fornitore**. Vengono monitorati i seguenti stati:

- **Incluso** - I processi automatizzati definiti nella pagina **Parametri contabilità fornitori** funzionano correttamente ma non sono ancora stati completati.
- **In sospeso** - I processi automatizzati definiti nella pagina **Parametri contabilità fornitori** sono stati eseguiti, ma almeno un passaggio del processo non è riuscito. Lo stato **In sospeso** viene applicato anche se il campo **Includi in elaborazione automatizzata** è impostato su **No**. Puoi visualizzare gli errori selezionando **Visualizza risultati più recenti**.
- **In flusso di lavoro** - La fattura importata è stata inviata al sistema flusso di lavoro, tramite il processo di invio al flusso di lavoro automatizzato o manualmente.
- **Flusso di lavoro completato** - Il processo del flusso di lavoro è stato completato per la fattura importata.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
