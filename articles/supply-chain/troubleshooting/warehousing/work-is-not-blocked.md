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
ms.openlocfilehash: 6b4361682246397732e8326b98b1b86ff878664e54c8c352296b0d7eaff6bbbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719553"
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
