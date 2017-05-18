---
title: Conti di registrazione per dismissione cespiti
description: "Questo articolo illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 111ff7ec677b699b8455b3a46a2866bd98970527
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="fixed-asset-disposal-posting-accounts"></a>Conti di registrazione per dismissione cespiti

[!include[banner](../includes/banner.md)]


Questo articolo illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti.

Nella pagina Profilo registrazione cespiti, nella scheda dettaglio Conti CoGe selezionare Dismissione - Vendita e dismissione - Scarto per impostare le registrazioni nella contabilità generale.

Per entrambi i tipi di transazione, nel conto CoGe verrà accreditato il valore di dismissione del cespite. L'addebito verrà registrato in un conto di contropartita, ad esempio un conto bancario. Se un cespite viene venduto a un cliente, verrà utilizzato il conto cliente anziché il conto di contropartita.

Fare clic su Dismissione e quindi su Vendita o Scarto, quindi impostare i dettagli dei conti in cui stornare il valore contabile netto del cespite. È inoltre possibile immettere informazioni nei campi Valore registrato e Tipo valore netto di vendita nella pagina dei parametri di dismissione. 

La transazione di dismissione per un cespite in un pool a basso valore riduce il valore contabile netto del pool soltanto dell'importo dismesso. Quando tuttavia la vendita di un cespite è superiore al valore contabile netto del pool, il valore contabile netto viene ridotto a zero.






