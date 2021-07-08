---
title: L'articolo non può avere una distinta base o una formula
description: Quando tenti di stabilizzare un ordine, ricevi un messaggio di errore durante la convalida dell'articolo. Indica che l'articolo non può avere una distinta base (DBA) o una formula.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294110"
---
# <a name="item-cant-have-a-bom-or-formula"></a>L'articolo non può avere una distinta base o una formula

Codice errore: PRO2614

## <a name="symptoms"></a>Sintomi

Quando tenti di stabilizzare un ordine, ricevi il seguente messaggio di errore durante la convalida dell'articolo:

> L'articolo non può contenere una DBA o una formula

## <a name="resolution"></a>Risoluzione

Gli articoli che hanno una distinta base (DBA) o una formula devono essere di tipo *Elemento di pianificazione*, *DBA*, o *formula*. Per modificare il tipo di un elemento effettua le operazioni indicate di seguito.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Apri il prodotto rilevante.
1. Nella Scheda dettaglio **Progetta**, imposta il campo **Tipo di produzione** su *Elemento di pianificazione*, *DBA*, o *formula*.
