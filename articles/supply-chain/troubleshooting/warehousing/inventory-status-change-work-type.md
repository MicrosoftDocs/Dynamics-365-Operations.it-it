---
title: Impossibile selezionare Modifica stato inventario come Tipo di lavoro
description: Non è possibile creare una riga del modello di lavoro per Modifica stato inventario perché il tipo di lavoro viene utilizzato solo dai processi di sistema. Selezionare un tipo di lavoro diverso.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ad7f26f3235d15779583f9cdadeb4e6dca16242a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476802"
---
# <a name="cant-select-inventory-status-change-in-the-work-type-column"></a>Impossibile selezionare Modifica stato inventario nella colonna Tipo di lavoro

## <a name="symptoms"></a>Sintomi

Durante la configurazione di Microsoft Dynamics 365 Supply Chain Management, è possibile che venga visualizzato il seguente messaggio di errore:

> Non è possibile creare una riga del modello di lavoro per Modifica stato inventario perché il tipo di lavoro non è valido. Selezionare un tipo di lavoro diverso.

## <a name="resolution"></a>Risoluzione

Questo comportamento è predefinito. Il tipo di lavoro *Modifica stato inventario* viene utilizzato solo dai processi di sistema. Non può essere configurato. Poiché l'elenco dei tipi di lavoro è fisso come un'enumerazione, le voci aggiuntive non possono essere filtrate dal menu a discesa **Tipo di lavoro**.
