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
ms.openlocfilehash: a89f5f98895be5b934dbdc1194fa58b9af34f9cbc7f5e2092f6f47791dd52400
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777745"
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
