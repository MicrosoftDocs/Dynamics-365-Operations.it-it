---
title: Conti di registrazione acquisizione cespiti
description: "Questo articolo illustra come impostare i conti di registrazione della contabilità generale per l'acquisizione dei cespiti."
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
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 887616463856875e2382a00b1d56520391ead844
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-acquisition-posting-accounts"></a><span data-ttu-id="294e6-103">Conti di registrazione acquisizione cespiti</span><span class="sxs-lookup"><span data-stu-id="294e6-103">Fixed asset acquisition posting accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="294e6-104">Questo articolo illustra come impostare i conti di registrazione della contabilità generale per l'acquisizione dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="294e6-104">This article explains how to set up general ledger posting accounts for acquiring assets.</span></span>

<span data-ttu-id="294e6-105">I conti utilizzati per registrare le acquisizioni cespiti possono variare in base al metodo utilizzato per l'acquisizione del cespite.</span><span class="sxs-lookup"><span data-stu-id="294e6-105">Accounts used for posting fixed asset acquisitions may vary depending upon the method used to acquire the asset.</span></span> <span data-ttu-id="294e6-106">Nella pagina Profili registrazione cespiti, nella scheda Conti CoGe selezionare Acquisizione e Rettifica acquisizione per impostare i conti cespiti per la registrazione nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="294e6-106">On the Fixed asset posting profiles page, on the Ledger accounts tab, select Acquisition and Acquisition adjustment to set up fixed asset accounts to post to the ledger.</span></span> 

<span data-ttu-id="294e6-107">Nei giornali di registrazione e negli ordini fornitore il conto COGE costituisce in genere il conto dello stato patrimoniale, dove viene addebitato il valore di acquisizione dei nuovi cespiti.</span><span class="sxs-lookup"><span data-stu-id="294e6-107">In journals and on purchase orders, Ledger account is typically the balance sheet account, where the acquisition value of the new fixed asset is debited.</span></span> <span data-ttu-id="294e6-108">Questo conto non viene visualizzato nel giornale di registrazione e non può essere sostituito nelle transazioni.</span><span class="sxs-lookup"><span data-stu-id="294e6-108">This account is not displayed in the journal and cannot be replaced in transactions.</span></span> 

<span data-ttu-id="294e6-109">Anche il conto di contropartita è un conto dello stato patrimoniale.</span><span class="sxs-lookup"><span data-stu-id="294e6-109">Offset account is also a balance sheet account.</span></span> <span data-ttu-id="294e6-110">Nel giornale di registrazione generale e nel giornale cespiti questo conto corrisponde spesso al conto bancario utilizzato per pagare l'acquisizione del cespite.</span><span class="sxs-lookup"><span data-stu-id="294e6-110">In the general journal and in the fixed assets journal, this account often will be the bank account that is used to pay for the acquisition of the asset.</span></span> <span data-ttu-id="294e6-111">Il conto di contropartita è un conto utilizzato come predefinito nei giornali di registrazione,</span><span class="sxs-lookup"><span data-stu-id="294e6-111">The offset account is a default account, which is suggested in the journals.</span></span> <span data-ttu-id="294e6-112">dove può essere sostituito da qualsiasi altro conto del piano dei conti o da un conto fornitore se il cespite è stato acquistato da un fornitore.</span><span class="sxs-lookup"><span data-stu-id="294e6-112">It can be changed in the journal to any other account from the chart of accounts or to a vendor account, if the fixed asset was purchase from a vendor.</span></span> 

<span data-ttu-id="294e6-113">Se per le acquisizioni dei cespiti si utilizza il giornale di registrazione fattura o gli ordini fornitore nella Contabilità fornitori, il conto di contropartita per la transazione cespiti viene sostituito dal conto fornitore selezionato per la transazione.</span><span class="sxs-lookup"><span data-stu-id="294e6-113">When Invoice journal or Purchase orders in Accounts payable are used for fixed asset acquisitions, the offset account for the fixed asset transaction is replaced by the vendor account that is selected for the transaction.</span></span>

<span data-ttu-id="294e6-114">Per le acquisizioni registrate in Contabilità generale utilizzando il giornale di registrazione Scorte a cespiti, il cespite non viene acquistato da origini esterne ma trasferito dalle scorte della società.</span><span class="sxs-lookup"><span data-stu-id="294e6-114">For acquisitions posted using the Inventory to fixed assets journal in General ledger, the fixed asset is not bought from external sources, but transferred from the company's own inventory.</span></span> <span data-ttu-id="294e6-115">Di conseguenza, il conto di contropartita per l'articolo di magazzino presente in Gestione articoli è costituito da un conto uscite da magazzino.</span><span class="sxs-lookup"><span data-stu-id="294e6-115">Therefore, the offset account is an inventory issue account for the inventory item in Inventory management.</span></span>

<span data-ttu-id="294e6-116">Per ulteriori informazioni, vedere [Acquisire cespiti tramite approvvigionamento](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="294e6-116">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md).</span></span>




