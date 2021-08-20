---
title: Spese varie della gestione dei trasporti
description: Questo argomento spiega come le spese generate dal trasporto devono essere associate a un codice spese.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6d334a1ac290ab258964df2f146d9cbe30eb766f4002c8bae856cbe5499181b3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769517"
---
# <a name="transportation-management-miscellaneous-charges"></a>Spese varie della gestione dei trasporti

[!include [banner](../includes/banner.md)]

Come per tutte le spese varie, le spese generate dal trasporto devono essere associate a un codice spese. In caso contrario, non verranno aggiunte all'ordine come spesa varia. Il **Codice spese** determina la modalità di contabilizzazione dell'addebito in relazione all'ordine e alla riga ordine in cui viene aggiunto.

Andare a **Gestione trasporti > Impostazione > Valutazione > Spese varie** definire i criteri di qualificazione che determinano quando uno specifico **Codice spese** viene applicato a una spesa.

È necessaria almeno una configurazione per ogni impostazione **Modulo spese** pertinente (*Cliente* e *Fornitore*) dove il **Tipo di spesa varia** è impostato su *Nessuno*. Se questa manca, la spesa varia *non* viene aggiunta all'ordine.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]