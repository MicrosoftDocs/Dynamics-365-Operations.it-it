---
title: L'errore "Riferimento oggetto non impostato" si verifica durante la conferma dell'ordine fornitore
description: L'errore "Riferimento oggetto non impostato" si verifica durante la conferma dell'ordine fornitore
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 78e5e365f7197c1a0c25bf6eb63bcd5bd0f482ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476789"
---
# <a name="error-object-reference-not-set-occurs-during-purchase-order-confirmation"></a>L'errore "Riferimento oggetto non impostato" si verifica durante la conferma dell'ordine fornitore

## <a name="symptoms"></a>Sintomi

Si riceve la seguente eccezione quando si conferma un ordine fornitore:

> Riferimento oggetto non impostato

## <a name="cause"></a>Causa

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

## <a name="resolution"></a>Risoluzione

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
