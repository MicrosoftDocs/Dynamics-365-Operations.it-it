---
title: Il nome della consegna non viene sincronizzato dopo aver modificato un indirizzo di consegna nell'intestazione di un ordine fornitore
description: Dopo aver modificato l'indirizzo di consegna nell'intestazione di un ordine fornitore, il nome della consegna non viene sincronizzato
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 588d1ef6250d249aa4fc9da4f5125e9a34c0255f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476736"
---
# <a name="the-delivery-name-isnt-synced-after-changing-a-purchase-order-delivery-address"></a>Il nome della consegna non viene sincronizzato dopo aver modificato un indirizzo di consegna nell'intestazione di un ordine fornitore

## <a name="symptoms"></a>Sintomi

L'indirizzo nell'intestazione di un ordine fornitore viene aggiornato su un indirizzo che non è un indirizzo di consegna. Sebbene l'indirizzo sia aggiornato nell'ordine fornitore, il nome della consegna non viene aggiornato in base all'indirizzo aggiornato.

## <a name="resolution"></a>Risoluzione

Questo comportamento è predefinito. L'indirizzo selezionato deve essere classificato come indirizzo di consegna. In caso contrario, il nome della consegna non viene aggiornato in base all'indirizzo selezionato.
