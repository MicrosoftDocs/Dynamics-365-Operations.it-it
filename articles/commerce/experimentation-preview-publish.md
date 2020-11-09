---
title: Visualizzare un esperimento in anteprima e pubblicarlo
description: In questo argomento viene descritto come visualizzare in anteprima e pubblicare un esperimento in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: f1a565917ab7a048d4d455bc0a0fbd9316237aeb
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097118"
---
# <a name="preview-and-publish-an-experiment"></a>Visualizzare un esperimento in anteprima e pubblicarlo

Questo argomento descrive come visualizzare in anteprima e pubblicare un esperimento in Dynamics 365 Commerce dopo che hai [collegato l'esperimento e modificato le varianti](experimentation-connect-edit.md). Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in argomenti separati.

[ ![Percorso utente per sperimentazione - Anteprime e pubblicazione](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

## <a name="preview-your-experiment-variations"></a>Visualizzare un'anteprima delle varianti dell'esperimento
Puoi visualizzare in anteprima le varianti e continuare a modificarle finché non hanno l'aspetto desiderato.

Per visualizzare in anteprima le varianti dell'esperimento in Creazione di siti Web di Commerce seguire questi passaggi.

1. Nel menu a discesa delle varianti sotto la barra dei comandi selezionare il contenuto che si desidera visualizzare in anteprima. 
1. Nella barra dei comandi, selezionare **Anteprima**. Viene visualizzata un'anteprima di come apparirà il contenuto una volta pubblicato.
1. Per visualizzare in anteprima una variante diversa, selezionarla dal menu a discesa delle varianti e selezionare di nuovo **Anteprima**.

## <a name="publish-your-experiment"></a>Pubblicare l'esperimento
Se non stai utilizzando un gruppo di pubblicazione per pianificare il momento in cui l'esperimento verrà pubblicato e desideri pubblicarlo immediatamente, seleziona **Pubblica** nella barra dei comandi. Verranno pubblicate tutte le varianti che appartengono all'esperimento.
    
> [!IMPORTANT]
> Se la pagina ha un URL non pubblicato, devi prima pubblicare l'URL o non sarà visibile agli utenti del tuo sito web. Per informazioni dettagliate, vedi [Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md).
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a>Utilizzare gruppi di pubblicazione per pianificare quando l'esperimento verrà pubblicato
Le varianti create in Creazione in siti Web possono essere pianificate per la pubblicazione utilizzando un gruppo di pubblicazione. All'interno di un gruppo di pubblicazione, è possibile collegare una pagina o un frammento all'esperimento selezionando **Esperimenti** nel riquadro di spostamento a sinistra. È possibile eseguire questa operazione anche selezionando **Pagine** o **Frammenti** e seguendo le istruzioni in [Connettere un esperimento e modificare le varianti](experimentation-connect-edit.md). Per informazioni sui gruppi di pubblicazione, vedi [Utilizzare i gruppi di pubblicazione](publish-groups.md).

Quando si utilizzano gruppi di pubblicazione con esperimenti, è necessario tenere presente alcune considerazioni importanti.
- Quando aggiungi una pagina o un frammento per la quale è in esecuzione un esperimento a un gruppo di pubblicazione, l'esperimento verrà rimosso dalla pagina o dal frammento nel gruppo di pubblicazione.
- Gli esperimenti collegati alle pagine di un sito live non sono disponibili per le pagine in gruppi di pubblicazione e viceversa. Allo stesso modo, le pagine per le quali sono in esecuzione esperimenti in un sito live non sono disponibili per altri esperimenti nei gruppi di pubblicazione e viceversa.
- Quando pubblichi o pianifichi un gruppo di pubblicazione, tutto il contenuto nel gruppo di pubblicazione viene pubblicato, indipendentemente dal fatto che esista un esperimento associato al gruppo di pubblicazione.
- Poiché un gruppo di pubblicazione continua a persistere dopo essere stato pubblicato su un sito live, verranno mantenuti anche gli esperimenti nel gruppo di pubblicazione. Pertanto, non potrai associare altri esperimenti alla stessa pagina o frammento. Per evitare questa limitazione, elimina tutti i gruppi di pubblicazione con esperimenti persistenti. Allo stesso modo, se desideri eliminare un esperimento in un sito live che esiste anche in un gruppo di pubblicazione, eliminalo prima dal gruppo di pubblicazione.

## <a name="previous-step"></a>Passaggio precedente
[Collegare e modificare un esperimento](experimentation-connect-edit.md)

## <a name="next-step"></a>Passaggio successivo
[Eseguire e monitorare un esperimento](experimentation-run-monitor.md)
