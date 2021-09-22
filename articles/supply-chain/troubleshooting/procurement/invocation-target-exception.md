---
title: Si verifica un'eccezione durante la registrazione della fattura fornitore
description: Durante la registrazione della fattura fornitore si verifica un'eccezione "È stata generata un'eccezione dalla destinazione di una chiamata".
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
ms.openlocfilehash: ecc63cb7d0d2392105d8e4290f8e837945ae0781
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476764"
---
# <a name="an-exception-occurs-during-vendor-invoice-posting"></a>Si verifica un'eccezione durante la registrazione della fattura fornitore


## <a name="symptoms"></a>Sintomi

Quando si registra una fattura fornitore, si riceve la seguente eccezione:

> L'eccezione è stata generata dalla destinazione di una chiamata

## <a name="cause"></a>Causa

Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.

## <a name="resolution"></a>Risoluzione

Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**. Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
