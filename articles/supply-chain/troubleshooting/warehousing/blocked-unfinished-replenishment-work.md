---
title: Lavoro di prelievo bloccato a causa di un lavoro di rifornimento incompiuto
description: Il lavoro di prelievo potrebbe essere bloccato a causa del lavoro di rifornimento dipendente. Completare il lavoro di rifornimento, quindi elaborare il lavoro di prelievo.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 53b50d1e3e2d7bb64e78514affe80076ddcb9052
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476814"
---
# <a name="picking-work-cant-be-unblocked-because-of-unfinished-replenishment-work"></a>Il lavoro di prelievo non può essere sbloccato a causa del lavoro di rifornimento incompiuto

## <a name="symptoms"></a>Sintomi

Quando si utilizza il rifornimento della domanda ciclo, il lavoro di prelievo può essere bloccato a causa del lavoro di rifornimento dipendente. Se un'ubicazione di prelievo deve essere rifornita per soddisfare la domanda dell'ordine di origine, il sistema crea sia il lavoro di rifornimento che il lavoro di prelievo. Tuttavia, il sistema blocca il lavoro di prelievo fino al completamento del lavoro di rifornimento e viene visualizzato il seguente messaggio di errore:

> Impossibile sbloccare il lavoro %1 perché sono presenti azioni di rifornimento non terminate.

## <a name="resolution"></a>Risoluzione

Questo comportamento è intenzionale perché l'ubicazione di prelievo non avrà inventario sufficiente a meno che il lavoro di rifornimento non sia completato. Completare il lavoro di rifornimento, quindi elaborare il lavoro di prelievo.
