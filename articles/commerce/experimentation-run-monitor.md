---
title: Eseguire e monitorare un esperimento
description: In questo argomento viene descritto come eseguire e monitorare un esperimento in un servizio di terze parti. Descrive inoltre come apportare modifiche alle varianti dopo l'inizio dell'esperimento.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ba6fb94033e227790e01676819308bb4f0cd6868
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965219"
---
# <a name="run-and-monitor-an-experiment"></a>Eseguire e monitorare un esperimento

In questo argomento viene descritto come eseguire e monitorare un esperimento in un app di terze parti e modificare le variazioni se necessario. Prima di completare i passaggi in questo argomento, è necessario [pubblicare](experimentation-preview-publish.md) l'esperimento in Commerce. 

Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in argomenti separati.

[ ![Percorso utente per sperimentazione - Esecuzione e monitoraggio](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)

Dopo aver pubblicato le varianti, vengono eseguiti tutti i passaggi necessari in Commerce per completare l'esperimento. Il passaggio successivo consiste nel determinare quale variante mostrare agli utenti quando richiedono una pagina. Il servizio di terze parti prende questa decisione, ma prima devi attivare l'esperimento nel servizio. Poiché i passaggi per l'attivazione di un esperimento variano da servizio a servizio, dovrai seguire le istruzioni fornite dal servizio o dal fornitore. Se l'esperimento non viene attivato, gli utenti vedranno solo la versione predefinita della pagina e non verranno visualizzate le varianti.

Dovrai continuare a eseguire l'esperimento per un periodo sufficiente per raccogliere dati per risultati statisticamente validi. Utilizza il servizio di terze parti per monitorare i dati e le analisi relativi all'esperimento mentre l'esperimento è in esecuzione.

## <a name="adjust-your-variations"></a>Regolare le varianti
Se per un qualsiasi motivo devi modificare le varianti, segui i passaggi seguenti.

> [!IMPORTANT]
> Se apporti modifiche a un esperimento live in Commerce o nel servizio di terze parti, i risultati potrebbero essere modificati in modo significativo. Valuta la possibilità di completare l'esperimento e quindi di creare un nuovo esperimento per le modifiche più importanti.

1. In Creazione di siti Web di Commerce selezionare **Esperimenti** nel riquadro di spostamento a sinistra e selezionare l'esperimento. 
1. Seleziona la variante che desideri aggiornare dal menu a discesa.
1. Apportare le modifiche necessarie e visualizzare l'anteprima delle varianti e pubblicarle. Per ulteriori informazioni, vedi [Visualizzare un esperimento in anteprima e pubblicarlo](experimentation-preview-publish.md).
1. Vai al servizio di terze parti per apportare eventuali modifiche relative alla configurazione dell'esperimento.
    
## <a name="previous-step"></a>Passaggio precedente
[Visualizzare un esperimento in anteprima e pubblicarlo](experimentation-preview-publish.md)

## <a name="next-step"></a>Passaggio successivo
[Promuovere una variante e completare un esperimento](experimentation-review-complete.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]