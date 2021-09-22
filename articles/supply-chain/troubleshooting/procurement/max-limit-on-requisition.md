---
title: Il limite massimo di un contratto di acquisto non è valido per una richiesta di acquisto.
description: Il limite massimo di un contratto di acquisto non è valido per una richiesta di acquisto.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c19d40dce65acbe80d4572bfc4e925aa87ea4f02
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476746"
---
# <a name="the-purchase-agreement-maximum-limit-isnt-effective-on-a-purchase-requisition"></a>Il limite massimo di un contratto di acquisto non è valido per una richiesta di acquisto.

## <a name="symptoms"></a>Sintomi

Quando una richiesta di acquisto è collegata a un contratto di acquisto, il limite massimo del contratto di acquisto non è valido per la richiesta di acquisto. Le informazioni sul prezzo predefinito sono inserite correttamente, ma nella richiesta di acquisto è possibile ordinare più del limite massimo del contratto di acquisto.

## <a name="resolution"></a>Risoluzione

Questo comportamento è previsto. Poiché le richieste non sono sempre approvate, una quantità o un importo non deve essere riservato nel contratto di acquisto. Pertanto, non raggiungerai il limite massimo del contratto di acquisto.
