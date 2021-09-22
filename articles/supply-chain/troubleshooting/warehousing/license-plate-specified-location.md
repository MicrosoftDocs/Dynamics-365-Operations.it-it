---
title: È necessario specificare la targa per questa ubicazione
description: Se si riceve questo errore dopo aver creato un ordine di trasferimento per un magazzino abilitato WMS, il campo Ubicazione predefinita entrata è vuoto per un magazzino di transito.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2e562ad2b41dd149f215adc83bd2d54e55dccc05
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476735"
---
# <a name="license-plate-specification-error-when-confirming-shipment-for-a-transfer-order"></a>Errore di specifica della targa durante la conferma della spedizione per un ordine di trasferimento

## <a name="symptoms"></a>Sintomi

Se si crea un ordine di trasferimento utilizzando un magazzino abilitato per la gestione avanzata del magazzino (WMS) e quindi si tenta di confermare la spedizione dopo il completamento del lavoro, è possibile che venga visualizzato il seguente messaggio di errore:

> È necessario specificare la targa per questa ubicazione.

## <a name="cause"></a>Causa

Ciò si verifica perché il campo **Ubicazione predefinita entrata** è vuoto per un magazzino di transito del magazzino di provenienza.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, specificare un'ubicazione di ricevimento predefinita nel magazzino di transito. Assicurarsi che questa ubicazione sia controllata dalla targa.
