---
title: Impossibile rilasciare il carico per la quantità parziale con una gerarchia batch-above
description: Quando si utilizza un articolo con la gerarchia di prenotazione batch-above, le righe di carico devono specificare le dimensioni sopra l'ubicazione affinché le scorte possano essere allocate.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eb7e71cc271903cb689c33777b72862246f2dd42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476743"
---
# <a name="cant-release-a-load-for-partial-quantity-with-batch-above-reservation-hierarchy"></a>Impossibile rilasciare il carico per la quantità parziale con una gerarchia di prenotazione batch-above

## <a name="symptoms"></a>Sintomi

Quando si utilizza un articolo che ha una gerarchia di prenotazione *batch-above*, il comando **Rilascia in magazzino** nella pagina **Workbench di pianificazione** non funziona se provi a rilasciare un carico per una quantità parziale. Potrebbe essere visualizzato il seguente messaggio:

> Per essere assegnate al ciclo, le righe di carico devono specificare le dimensioni sopra l'ubicazione. Per assegnare queste dimensioni, prenotare e ricreare la riga di carico.

Tuttavia quando utilizzi un articolo che ha una gerarchia di prenotazione *batch-below*, è possibile rilasciare un carico per una quantità parziale dalla pagina **Workbench di pianificazione del carico**.

## <a name="cause"></a>Causa

Quando una dimensione è sopra la dimensione **Ubicazione** nella gerarchia di prenotazione, deve essere specificata prima del rilascio al magazzino. L'inventario può essere allocato correttamente solo se non ci sono spazi vuoti nelle dimensioni sopra l'ubicazione.

## <a name="resolution"></a>Risoluzione

Assicurarsi che tutte le dimensioni sopra **Ubicazione** sono state assegnate prenotando e ricreando la riga di carico.
