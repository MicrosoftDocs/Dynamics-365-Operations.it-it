---
title: Workbench di allestimento del carico
description: Questo argomento descrive come lavorare con il workbench allestimento del carico.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7b8633adbab43c95366d42cf409f5e508771c906
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809040"
---
# <a name="load-building-workbench"></a>Workbench di allestimento del carico

Il workbench allestimento del carico consente di applicare strategie di allestimento del carico durante la creazione dei carichi.

## <a name="create-a-load-building-strategy"></a>Creare una strategia di allestimento del carico

Si utilizzano le strategie di allestimento del carico per allestire automaticamente i carichi. Questa capacità può essere utile nelle seguenti situazioni:

- Se si spedisce regolarmente un set specifico di prodotti, le strategie di carico aiutano a risparmiare tempo, perché non si deve creare lo stesso carico ogni volta.
- Se si desidera evitare carichi mezzi pieni per massimizzare l'efficienza, le strategie di carico possono aiutare a riempire ogni carico il più possibile.

Una classe di strategia di allestimento del carico denominata `TMSLoadBuildingVolumeStrategy` fornisce una strategia di allestimento del carico denominata *Strategia di allestimento del carico basata sul volume*. Questa strategia consente di utilizzare i valori massimi specificati per l'altezza e il peso nel modello di carico o di sostituire le impostazioni con nuovi valori. Questa strategia è l'unica strategia inclusa per impostazione predefinita. Tuttavia, è possibile avere strategie personalizzate.

Per utilizzare la *Strategia di allestimento del carico basata sul volume* predefinita selezionarla nel campo **Strategia di allestimento del carico** della pagina **Workbench di allestimento del carico** (**Gestione trasporto &gt; Pianificazione &gt; Workbench di allestimento del carico**).

Per creare una strategia di allestimento del carico, attenersi alla procedura seguente.

1. Andare a **Gestione trasporti &gt; Impostazione &gt; Allestimento del carico &gt; Strategie di allestimento del carico**.
1. Nel riquadro azioni selezionare **Genera elenco di classi** per assicurarsi di avere le ultime versioni di tutte le classi disponibili.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Immettere un nome univoco per la strategia, selezionare la classe della strategia di generazione del carico e immettere una descrizione.
1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro azioni, seleziona **Parametri**.
1. Nella pagina **Parametri strategia di allestimento del carico** selezionare **Capacità volume** nell'elenco e quindi nel campo **Valore** immettere la percentuale della capacità di volume totale del carico da applicare per la nuova strategia di allestimento del carico.
1. Selezionare **Capacità peso** nell'elenco e quindi nel campo **Valore** immettere la percentuale della capacità di peso totale del carico da applicare per la nuova strategia di allestimento del carico.
1. Chiudere la pagina **Parametri strategia di allestimento del carico**.
1. Chiudere la pagina **Strategie di allestimento del carico**.

È ora possibile assegnare la strategia di allestimento del carico a un modello di allestimento del carico. In alternativa, è possibile utilizzarla direttamente nel workbench di allestimento del carico.

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a>Utilizzare una strategia di allestimento del carico nel workbench di allestimento del carico

1. Andare a **Gestione trasporto &gt; Pianificazione &gt; Workbench allestimento carico**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Selezionare una strategia nel campo **Strategia di allestimento del carico**.
    - Se è stato definito un modello di allestimento del carico e gli è stata assegnata la strategia di allestimento del carico, nel riquadro azioni, nella scheda **Gestisci modelli** selezionare **Applica modello**. Quindi, nella finestra di dialogo a discesa **Applica modello di allestimento del carico** selezionare un modello nel campo **Nome modello di allestimento del carico**.

1. Nella scheda dettaglio **Sequenza modelli di carico** selezionare uno o più [modelli di carico](load-template.md). Il workbench cercherà di adattare il carico a questi tipi di contenitori, nella sequenza qui specificata. In genere, è necessario inserire i contenitori più piccoli all'inizio dell'elenco per assicurarsi che venga selezionato per primo il contenitore più piccolo possibile.
1. Nel riquadro azioni selezionare **Proponi carichi**.
1. Rivedere i carichi proposti e le righe di carico proposte.
1. Nel riquadro azioni selezionare **Crea carichi** per creare carichi basati sulle righe del documento di origine nella scheda dettaglio **Righe carico proposte**.
1. Chiudere la pagina **Workbench di allestimento del carico**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]