---
title: Conti di registrazione di dismissione cespiti
description: "Questo argomento illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bfed7657649f938c3d436468891d40d4194b555d
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="fixed-asset-disposal-posting-accounts"></a>Conti di registrazione di dismissione cespiti

[!INCLUDE [banner](../includes/banner.md)]

Questo argomento illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti.

Nella pagina Profilo registrazione cespiti, nella scheda dettaglio Conti CoGe selezionare Dismissione - Vendita e dismissione - Scarto per impostare le registrazioni nella contabilità generale.

Per entrambi i tipi di transazione, nel conto CoGe verrà accreditato il valore di dismissione del cespite. L'addebito verrà registrato in un conto di contropartita, ad esempio un conto bancario. Se un cespite viene venduto a un cliente, verrà utilizzato il conto cliente anziché il conto di contropartita.

Fare clic su Dismissione e quindi su Vendita o Scarto, quindi impostare i dettagli dei conti in cui stornare il valore contabile netto del cespite. È inoltre possibile immettere informazioni nei campi Valore registrato e Tipo valore netto di vendita nella pagina dei parametri di dismissione. 

La transazione di dismissione per un cespite in un pool a basso valore riduce il valore contabile netto del pool soltanto dell'importo dismesso. Quando tuttavia la vendita di un cespite è superiore al valore contabile netto del pool, il valore contabile netto viene ridotto a zero.






