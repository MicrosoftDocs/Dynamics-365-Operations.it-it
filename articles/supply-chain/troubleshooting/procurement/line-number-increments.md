---
title: Gli ordini fornitore importati mostrano numeri di riga errati
description: Quando gli ordini fornitore vengono importati tramite la gestione dei dati, i numeri di riga dell'ordine fornitore non seguono l'incremento definito nei parametri di sistema
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
ms.openlocfilehash: e1cf5cf1d04824213f495ac3ebf556796c96611a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476723"
---
# <a name="imported-purchase-orders-show-incorrect-line-numbers"></a>Gli ordini fornitore importati mostrano numeri di riga errati

## <a name="symptoms"></a>Sintomi

Per impostazione predefinita, i numeri di riga generati automaticamente per le righe ordine fornitore importate tramite l'entità di dati *Righe ordine fornitore V2* non utilizza l'incremento del numero di riga di sistema specificato nei parametri di sistema. Se crei manualmente un ordine fornitore e aggiungi righe tramite l'interfaccia utente (UI), i numeri di riga vengono incrementati correttamente. Tuttavia, se si utilizza Data Management Framework (DMF), non vengono incrementati correttamente.

Questo problema si verifica perché, quando si importano righe tramite DMF, se i numeri di riga non sono già assegnati nell'entità importata, il sistema utilizza il metodo DMF per assegnarli. Questo metodo incrementa sempre i numeri di riga di uno.

## <a name="workaround"></a>Soluzione alternativa

Accertarsi che i numeri di riga desiderati siano già specificati nei campi del numero di riga dell'entità di dati quando si importano le righe dell'ordine fornitore. In questo caso, DMF non sovrascriverà i numeri di riga.
