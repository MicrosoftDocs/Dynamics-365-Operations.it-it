---
title: Il lavoro non è bloccato
description: Il lavoro non è bloccato
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924206"
---
# <a name="work-isnt-blocked"></a>Il lavoro non è bloccato

Codice di errore: WHSUnblockNotBlockedWorkErrorMessage

## <a name="symptoms"></a>Sintomi

Il sistema mostra il seguente messaggio di errore:

> Lavoro con ID %1 non bloccato.

## <a name="cause"></a>Causa

L'opzione **Ciclo bloccato** nel ciclo è impostata su *No*. Il lavoro non può essere sbloccato perché al momento non è bloccato.

## <a name="resolution"></a>Risoluzione

 Solo il lavoro dove l'opzione **Ciclo bloccato** è impostata su *Sì* può essere sbloccato.
