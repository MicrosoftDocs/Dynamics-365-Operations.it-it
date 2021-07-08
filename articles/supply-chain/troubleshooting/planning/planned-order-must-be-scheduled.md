---
title: L'ordine di produzione pianificato deve essere programmato prima di poter essere stabilizzato
description: Quando si tenta di stabilizzare un ordine pianificato, viene visualizzato un messaggio di errore che indica che l'ordine deve essere pianificato prima di poter essere stabilizzato.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294114"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a>L'ordine di produzione pianificato deve essere programmato prima di poter essere stabilizzato

Codice errore: SYS309802

## <a name="symptoms"></a>Sintomi

Quando tenti di stabilizzare un ordine pianificato viene visualizzato il seguente messaggio di errore:

> Per stabilizzare un ordine di produzione pianificato, è innanzitutto necessario programmarlo.

## <a name="cause"></a>Causa

Le date di inizio e fine pianificate non possono essere vuote.

## <a name="resolution"></a>Risoluzione

Per specificare le date di inizio e di fine per l'ordine pianificato, segui questi passaggi.

1. Andare a **Pianificazione generale \> Pianificazione generale \> Ordini pianificati**.
1. Apri l'ordine pianificato rilevante.
1. Nella scheda dettaglio **Generale** nella sezione **Programmato** specifica le date nei campi **Data di inizio** e **Data di fine**.
