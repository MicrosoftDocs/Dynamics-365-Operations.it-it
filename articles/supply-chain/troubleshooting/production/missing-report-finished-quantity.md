---
title: L'aggiornamento di dichiarazione di finito non riesce con errore di quantità mancante
description: Se si tenta di terminare un ordine di produzione mentre si segnala la quantità errata ma non la quantità di tempo o materiale, l'aggiornamento della dichiarazione di finito avrà esito negativo.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7785549c47063727f2749749940c1a96a351e70f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476739"
---
# <a name="report-as-finished-update-fails-with-a-missing-quantity-error"></a>L'aggiornamento della dichiarazione di finito non riesce con un errore di quantità mancante

## <a name="symptoms"></a>Sintomi

Si tenta di dichiarare un ordine di produzione come finito durante la segnalazione della quantità errata, ma non durante la segnalazione della quantità di tempo o di materiale. L'aggiornamento della dichiarazione di finito non riesce quando si tenta di terminare l'ordine di produzione. Verrà visualizzato il seguente messaggio di errore:

> Manca quantità dichiarata finita.

## <a name="resolution"></a>Risoluzione

Se si segnala la quantità errata in un ordine di produzione, è necessario segnalare anche la quantità corretta.
