---
title: Non è presente alcun valore di data iniziale nella scheda Prezzi attivi della pagina Prezzo articolo
description: Non è presente alcun valore di data iniziale nella scheda Prezzi attivi della pagina Prezzo articolo.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: dc0071bc508fc1b2fcfa5071f0756434641b7e6f872308ed4febb0cb34d37840
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730132"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a>Non è presente alcun valore di data iniziale nella scheda Prezzi attivi della pagina Prezzo articolo

Numero KB: 4613548

## <a name="symptoms"></a>Sintomi

Non è presente alcun valore di **Data iniziale** nella scheda **Prezzi attivi** della pagina **Prezzo articolo**.

## <a name="resolution"></a>Risoluzione

Il valore **Data iniziale** (data di validità) impostato sul prezzo in sospeso non viene trasferito al prezzo attivo.

Quando un record di costo di un articolo viene immesso per la prima volta, ha uno stato *In sospeso* e una data di validità prevista. Quando si attiva il record del costo dell'articolo, lo stato viene aggiornato e diventa *attivo* e la data di validità viene aggiornata alla data di attivazione. Pertanto, la data di attivazione del prezzo attivo è sempre la data effettiva dell'attivazione.

Per ulteriori informazioni, vedi [Panoramica delle versioni di determinazione costi](../../cost-management/costing-versions.md).
