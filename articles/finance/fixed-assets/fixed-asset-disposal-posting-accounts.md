---
title: Conti di registrazione di dismissione cespiti
description: Questo articolo illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1272cdb16396d24b5495f023e7b9fe3dee341507
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871335"
---
# <a name="fixed-asset-disposal-posting-accounts"></a>Conti di registrazione di dismissione cespiti

[!include [banner](../includes/banner.md)]

Questo articolo illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti.

Per impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti, seleziona **Vendita di dismissione** e **Scarto** nella scheda dettaglio **Conti CoGe** nella pagina **Profili registrazione cespiti**.

Per entrambi i tipi di transazione (dismissione di un cespite tramite vendita o scarto), nel conto CoGe verrà accreditato il valore di dismissione del cespite. L'addebito verrà registrato in un conto di contropartita, un conto bancario (ad esempio). Se un cespite viene venduto a un cliente, verrà utilizzato il conto cliente anziché il conto di contropartita. Per ulteriori informazioni, vedi [Dismissione di un cespite come scarto](dispose-of-a-fixed-asset-as-scrap.md).

Fai clic su **Dismissione** e quindi su **Vendita** o **Scarto**, quindi impostare i dettagli dei conti in cui stornare il valore contabile netto del cespite. È inoltre possibile immettere informazioni nei campi **Valore registrato** e **Tipo valore netto di vendita** nella pagina **Parametri di dismissione**. 

La transazione di dismissione per un cespite in un pool a basso valore riduce il valore contabile netto del pool soltanto dell'importo dismesso. Quando tuttavia la vendita di un cespite è superiore al valore contabile netto del pool, il valore contabile netto viene ridotto a zero.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
