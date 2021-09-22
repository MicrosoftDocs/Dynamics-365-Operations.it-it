---
title: Informazioni fiscali non aggiornate se viene modificata l'ubicazione dell'ordine cliente
description: Se il sito, il magazzino o l'indirizzo di consegna viene modificato nell'intestazione di un ordine cliente, le informazioni sull'imposta del caso non vengono aggiornate nelle righe. Devi farlo manualmente.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 77a73a787ff8a174c575f3b4f75694ded45d5712
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476772"
---
# <a name="tax-information-isnt-updated-if-location-on-a-sales-order-header-is-changed"></a>I dati fiscali non vengono aggiornati se viene modificata l'ubicazione nell'intestazione di un ordine cliente

## <a name="symptoms"></a>Sintomi

Se il sito, il magazzino o l'indirizzo di consegna viene modificato nell'intestazione di un ordine cliente, le informazioni sull'imposta del caso non vengono aggiornate nelle righe.

## <a name="resolution"></a>Risoluzione

Questo comportamento è predefinito. Il problema si verifica perché l'indirizzo di consegna, il sito e il magazzino non vengono modificati automaticamente a livello di riga. È necessario aggiornarli manualmente.
