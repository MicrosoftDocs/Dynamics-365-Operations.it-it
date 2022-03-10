---
title: Impossibile creare la riga di carico a causa di dimensioni di inventario non valide
description: Quando si tenta di rilasciare un ordine di reso cliente al magazzino, è possibile che venga visualizzato un errore relativo a dimensioni inventariali non valide. Rimuovili dalla riga dell'ordine.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b02408b61b07b272a7e7d52004dc2492d60ef28c
ms.sourcegitcommit: 0d14c4a1e6cf533dd20463f1a84eae8f6d88f71b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119214"
---
# <a name="cant-create-load-line-for-return-sales-order-due-to-invalid-inventory-dimensions"></a>Impossibile creare la riga di carico per l'ordine di reso cliente a causa di dimensioni inventariali non valide

## <a name="symptoms"></a>Sintomi

Quando si tenta di rilasciare un ordine di reso cliente al magazzino, è possibile che venga visualizzato il seguente messaggio di errore:

> Impossibile creare una riga di carico per questa riga ordine perché contiene dimensioni di inventario non valide. Non è possibile fare riferimento a dimensioni di inventario che si trovano sotto la dimensione di ubicazione nella gerarchia di prenotazione. Rimuovere le dimensioni non valide dalla riga ordine.

## <a name="resolution"></a>Risoluzione

Il prodotto non supporta l'elaborazione del carico per un processo di reso cliente. Pertanto, non è possibile rilasciare l'ordine di reso cliente al magazzino.

Nelle transazioni di ordini cliente, non è possibile fare riferimento a dimensioni di inventario che si trovano sotto la dimensione di **ubicazione** nella gerarchia di prenotazione. La risoluzione consiste nel rimuovere le dimensioni non valide dalla riga ordine.
