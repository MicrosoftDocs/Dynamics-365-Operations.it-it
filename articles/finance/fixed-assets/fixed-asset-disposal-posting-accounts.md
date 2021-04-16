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
ms.openlocfilehash: 5d1d6a3dc6348e64bcf247544bc7b56c5314db4c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826860"
---
# <a name="fixed-asset-disposal-posting-accounts"></a><span data-ttu-id="02916-103">Conti di registrazione di dismissione cespiti</span><span class="sxs-lookup"><span data-stu-id="02916-103">Fixed asset disposal posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02916-104">Questo argomento illustra come impostare i conti di registrazione della contabilità generale per la dismissione dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="02916-104">This topic explains how to set up general ledger posting accounts for disposing of assets.</span></span>

<span data-ttu-id="02916-105">Nella pagina Profilo registrazione cespiti, nella scheda dettaglio Conti CoGe selezionare Dismissione - Vendita e dismissione - Scarto per impostare le registrazioni nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="02916-105">In the Fixed asset posting profiles page, on the Ledger accounts FastTab, select Disposal - sale and Disposal - scrap to set up postings to the ledger.</span></span>

<span data-ttu-id="02916-106">Per entrambi i tipi di transazione, nel conto CoGe verrà accreditato il valore di dismissione del cespite.</span><span class="sxs-lookup"><span data-stu-id="02916-106">For both transaction types, the ledger account is credited for the disposal value of the fixed asset.</span></span> <span data-ttu-id="02916-107">L'addebito verrà registrato in un conto di contropartita, ad esempio un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="02916-107">The debit is posted to an offset account, which might be, for example, a bank account.</span></span> <span data-ttu-id="02916-108">Se un cespite viene venduto a un cliente, verrà utilizzato il conto cliente anziché il conto di contropartita.</span><span class="sxs-lookup"><span data-stu-id="02916-108">If a fixed asset is sold to a customer, the customer account is used instead of the offset account.</span></span>

<span data-ttu-id="02916-109">Fare clic su Dismissione e quindi su Vendita o Scarto, quindi impostare i dettagli dei conti in cui stornare il valore contabile netto del cespite.</span><span class="sxs-lookup"><span data-stu-id="02916-109">Click Disposal and then click Sale or Scrap, and then set up detailed accounts to reverse the net book value of the fixed asset.</span></span> <span data-ttu-id="02916-110">È inoltre possibile immettere informazioni nei campi Valore registrato e Tipo valore netto di vendita nella pagina dei parametri di dismissione.</span><span class="sxs-lookup"><span data-stu-id="02916-110">You can also enter information in the Post value and Sales value type fields in the Disposal parameters page.</span></span> 

<span data-ttu-id="02916-111">La transazione di dismissione per un cespite in un pool a basso valore riduce il valore contabile netto del pool soltanto dell'importo dismesso.</span><span class="sxs-lookup"><span data-stu-id="02916-111">The disposal transaction for an asset in a low-value pool reduces the net book value of the low-value pool by the disposed amount only.</span></span> <span data-ttu-id="02916-112">Quando tuttavia la vendita di un cespite è superiore al valore contabile netto del pool, il valore contabile netto viene ridotto a zero.</span><span class="sxs-lookup"><span data-stu-id="02916-112">However, when the sale of an asset exceeds the net book value of the low-value pool, the net book value is reduced to zero.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]