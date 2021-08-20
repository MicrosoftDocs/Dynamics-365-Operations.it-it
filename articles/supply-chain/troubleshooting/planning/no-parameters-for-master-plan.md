---
title: I parametri per il piano generale non esistono
description: Quando si tenta di stabilizzare un ordine pianificato, viene visualizzato un messaggio di errore che indica che non esistono i parametri per il piano principale.
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
ms.openlocfilehash: d039b79684f87e7791fb9dae7cbdc6ced220bc092d9a0ab624616c1c345986da
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756777"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a>I parametri per il piano generale non esistono

Codice errore: SYS25368

## <a name="symptoms"></a>Sintomi

Quando tenti di stabilizzare un ordine pianificato viene visualizzato il seguente messaggio di errore:

> I parametri per il piano generale %1 non esistono.

## <a name="cause"></a>Causa

A causa di problemi di configurazione, il sistema non riesce a trovare le impostazioni per il piano specificato.

## <a name="resolution"></a>Risoluzione

- Vai a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali** e assicurati che esista un piano con il nome specificato.
