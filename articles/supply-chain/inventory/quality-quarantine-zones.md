---
title: Aree di quarantena per non conformità
description: Questo argomento descrive come creare e utilizzare aree di quarantena per le non conformità.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93ca74ec4586fffa3b9156aadab887629283b98a
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956718"
---
# <a name="quarantine-zones-for-nonconformances"></a>Aree di quarantena per non conformità

[!include [banner](../includes/banner.md)]

Questo argomento descrive come creare e utilizzare aree di quarantena per le non conformità.

Utilizzare la pagina **Aree quarantena** per definire le zone che possono essere assegnate alle non conformità. Quando crei una non conformità, puoi impostare i campi **Area quarantena** e **Tipo di quarantena** della scheda **Generale** della pagina **Non conformità**. Il capo **Area quarantena** indica in genere l'area o la ubicazione in cui si trova l'articolo. Il campo **Tipo di quarantena** definisce l'articolo come *Utilizzo limitato* o *Inutilizzabile*.

Quando si stampa un report di non conformità o di correzioni per una non conformità, è possibile visualizzare l'area di quarantena in cui si trova l'articolo.

È inoltre possibile stampare un tag di non conformità per una non conformità. Questo report mostra l'area di quarantena assegnata e le informazioni sull'utilizzo per fornire istruzioni sulla modalità di gestione del materiale difettoso. Le aree di quarantena possono corrispondere alle ubicazioni di magazzino o alle risorse operative.

## <a name="examples-of-quarantine-zones"></a>Esempi di aree di quarantena

### <a name="example-1"></a>Esempio 1

Lavori in un'azienda di produzione di elettronica che produce e distribuisce televisori, altoparlanti e lettori multimediali. In questo caso, puoi configurare una area di quarantena per rappresentare ogni tipo di prodotto.

### <a name="example-2"></a>Esempio 2

Tre contenitori e due scaffali vengono utilizzati per conservare gli articoli non conformi. In questo caso, è possibile configurare cinque aree di quarantena, una per ogni contenitore e ogni rack.

## <a name="create-a-quarantine-zone"></a>Creare un'area di quarantena

1. Andare a **Gestione articoli \> Impostazioni \> Gestione qualità \> Aree quarantena**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Area quarantena** - Immettere un ID o un nome univoco per la area di quarantena.
    - **Descrizione** - Immettere una descrizione dettagliata della area di quarantena.

1. Chiudere la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica gestione qualità](quality-management-processes.md)
- [Abilitare la gestione della qualità e della non conformità](enable-quality-management.md)
- [Lavoratori responsabili dell'approvazione delle non conformità](quality-responsible-workers.md)
- [Tipi di problemi per non conformità](quality-quarantine-zones.md)
- [Tipi di diagnostica per non conformità](quality-diagnostic-types.md)
- [Spese di gestione qualità per non conformità](quality-charges.md)
- [Operazioni per non conformità](quality-operations.md)
- [Gestione qualità per i processi di magazzino](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
