---
title: Conti di registrazione di dismissione cespiti
description: Questo argomento illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4313cb2029fc94d292abcf36eb01becb00869fa41dbda794b91d6c8f4bc5b9da
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778292"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Conti di registrazione di dismissione cespiti

[!include [banner](../includes/banner.md)]

Questo argomento illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti.

Nella pagina Profilo registrazione cespiti, nella scheda dettaglio Conti CoGe selezionare Dismissione - Vendita e dismissione - Scarto per impostare le registrazioni nella contabilità generale.

Per entrambi i tipi di transazione, nel conto CoGe verrà accreditato il valore di dismissione del cespite. L'addebito verrà registrato in un conto di contropartita, ad esempio un conto bancario. Se un cespite viene venduto a un cliente, verrà utilizzato il conto cliente anziché il conto di contropartita.

Fare clic su Dismissione e quindi su Vendita o Scarto, quindi impostare i dettagli dei conti in cui stornare il valore contabile netto del cespite. È inoltre possibile immettere informazioni nei campi Valore registrato e Tipo valore netto di vendita nella pagina dei parametri di dismissione. 

La transazione di dismissione per un cespite in un pool a basso valore riduce il valore contabile netto del pool soltanto dell'importo dismesso. Quando tuttavia la vendita di un cespite è superiore al valore contabile netto del pool, il valore contabile netto viene ridotto a zero.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]