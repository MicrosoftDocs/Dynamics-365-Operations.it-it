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
ms.openlocfilehash: 1e946adc3a04db60bf15ac7bb44163085e1c19802872964877d3929b1f79bf7d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730108"
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
