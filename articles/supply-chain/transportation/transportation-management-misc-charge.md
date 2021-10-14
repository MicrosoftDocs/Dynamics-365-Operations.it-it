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
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 776c73b1a29666e393bed7c40059a578fe86cb0d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576186"
---
# <a name="transportation-management-miscellaneous-charges"></a>Spese varie della gestione dei trasporti

[!include [banner](../includes/banner.md)]

Come per tutte le spese varie, le spese generate dal trasporto devono essere associate a un codice spese. In caso contrario, non verranno aggiunte all'ordine come spesa varia. Il **Codice spese** determina la modalità di contabilizzazione dell'addebito in relazione all'ordine e alla riga ordine in cui viene aggiunto.

Andare a **Gestione trasporti > Impostazione > Valutazione > Spese varie** definire i criteri di qualificazione che determinano quando uno specifico **Codice spese** viene applicato a una spesa.

È necessaria almeno una configurazione per ogni impostazione **Modulo spese** pertinente (*Cliente* e *Fornitore*) dove il **Tipo di spesa varia** è impostato su *Nessuno*. Se questa manca, la spesa varia *non* viene aggiunta all'ordine.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]