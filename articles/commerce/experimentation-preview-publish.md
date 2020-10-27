---
title: Visualizzare un esperimento in anteprima e pubblicarlo
description: In questo argomento viene descritto come visualizzare in anteprima e pubblicare un esperimento in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
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
ms.openlocfilehash: 91e2e4840a2d53f195d881279050b6415d48b070
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930229"
---
# <a name="preview-and-publish-an-experiment"></a>Visualizzare un esperimento in anteprima e pubblicarlo

Questo argomento descrive come visualizzare in anteprima e pubblicare un esperimento in Dynamics 365 Commerce dopo che hai [collegato l'esperimento e modificato le varianti](experimentation-connect-edit.md). Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in argomenti separati.

[ ![Percorso utente per sperimentazione - Anteprime e pubblicazione](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

## <a name="preview-your-experiment-variations"></a>Visualizzare un'anteprima delle varianti dell'esperimento
Puoi visualizzare in anteprima le varianti e continuare a modificarle finché non hanno l'aspetto desiderato.

1. In Creazione di siti Web, utilizza il menu a discesa delle varianti sotto la barra dei comandi per selezionare il contenuto che desideri visualizzare in anteprima. 
1. Seleziona **Anteprima** nella barra in alto. Viene visualizzata un'anteprima di come apparirà il contenuto una volta pubblicato.
1. Per visualizzare in anteprima una variante diversa, selezionala dal menu a discesa delle varianti e seleziona di nuovo **Anteprima**.

## <a name="publish-your-experiment"></a>Pubblicare l'esperimento
Se non stai utilizzando un gruppo di pubblicazione per pianificare il momento in cui l'esperimento verrà pubblicato e desideri pubblicarlo immediatamente, seleziona**Pubblica** nella barra dei comandi. Verranno pubblicate tutte le varianti che appartengono all'esperimento.
    
> [!IMPORTANT]
> Se la pagina ha un URL non pubblicato, devi prima pubblicare l'URL o non sarà visibile agli utenti del tuo sito web. Per informazioni dettagliate, vedi [Salvare, visualizzare in anteprima e pubblicare una pagina](save-preview-publish-page.md).
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a>Utilizzare gruppi di pubblicazione per pianificare quando l'esperimento verrà pubblicato
Le varianti create in Creazione in siti Web possono essere pianificate per la pubblicazione utilizzando un gruppo di pubblicazione. In un gruppo di pubblicazione, puoi collegare una pagina o un frammento all'esperimento nella scheda **Esperimenti** o **Pagine** o **Frammenti**. Per ulteriori informazioni, vedi l'argomento [Collegare un esperimento e modificare le varianti](experimentation-connect-edit.md). Per informazioni sui gruppi di pubblicazione, vedi [Utilizzare i gruppi di pubblicazione](publish-groups.md).

Quando si utilizzano gruppi di pubblicazione con esperimenti, è necessario tenere presente alcune considerazioni importanti.
- Quando aggiungi una pagina o un frammento per la quale è in esecuzione un esperimento a un gruppo di pubblicazione, l'esperimento verrà rimosso dalla pagina o dal frammento nel gruppo di pubblicazione.
- Gli esperimenti collegati alle pagine di un sito live non sono disponibili per le pagine in gruppi di pubblicazione e viceversa. Allo stesso modo, le pagine per le quali sono in esecuzione esperimenti in un sito live non sono disponibili per altri esperimenti nei gruppi di pubblicazione e viceversa.
- Quando pubblichi o pianifichi un gruppo di pubblicazione, tutto il contenuto nel gruppo di pubblicazione viene pubblicato, indipendentemente dal fatto che esista un esperimento associato al gruppo di pubblicazione.
- Poiché un gruppo di pubblicazione continua a persistere dopo essere stato pubblicato su un sito live, verranno mantenuti anche gli esperimenti nel gruppo di pubblicazione. Pertanto, non potrai associare altri esperimenti alla stessa pagina o frammento. Per evitare questa limitazione, elimina tutti i gruppi di pubblicazione con esperimenti persistenti. Allo stesso modo, se desideri eliminare un esperimento in un sito live che esiste anche in un gruppo di pubblicazione, eliminalo prima dal gruppo di pubblicazione.

## <a name="previous-step"></a>Passaggio precedente
[Collegare e modificare un esperimento](experimentation-connect-edit.md)

## <a name="next-step"></a>Passaggio successivo
[Eseguire e monitorare un esperimento](experimentation-run-monitor.md)
