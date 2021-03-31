---
title: Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione
description: In questo argomento viene descritto come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0fee32d9fd1ab89b1a8cedb2e1965674586d4e7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227186"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="75a66-103">Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione</span><span class="sxs-lookup"><span data-stu-id="75a66-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="75a66-104">In questo argomento viene descritto come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese.</span><span class="sxs-lookup"><span data-stu-id="75a66-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="75a66-105">Creare e registrare una fattura</span><span class="sxs-lookup"><span data-stu-id="75a66-105">Create and post and invoice</span></span>
1. <span data-ttu-id="75a66-106">Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Registro fatture**.</span><span class="sxs-lookup"><span data-stu-id="75a66-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="75a66-107">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="75a66-107">Select **New**.</span></span>
3. <span data-ttu-id="75a66-108">Selezionare il nome del registro fatture che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="75a66-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="75a66-109">Selezionare **Righe** per aprire il registro e immettere le righe di spesa.</span><span class="sxs-lookup"><span data-stu-id="75a66-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="75a66-110">Selezionare un fornitore.</span><span class="sxs-lookup"><span data-stu-id="75a66-110">Select a vendor.</span></span> <span data-ttu-id="75a66-111">Ad esempio, immettere o selezionare `US-104`.</span><span class="sxs-lookup"><span data-stu-id="75a66-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="75a66-112">Digitare un valore nel campo **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="75a66-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="75a66-113">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="75a66-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="75a66-114">Nel campo **Credito** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="75a66-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="75a66-115">Nel campo **Approvato da**, selezionare un approvatore dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="75a66-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="75a66-116">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="75a66-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="75a66-117">Approvare una fattura</span><span class="sxs-lookup"><span data-stu-id="75a66-117">Approve an invoice</span></span>
1. <span data-ttu-id="75a66-118">Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Approvazione fattura**.</span><span class="sxs-lookup"><span data-stu-id="75a66-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="75a66-119">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="75a66-119">Select **New**.</span></span>
3. <span data-ttu-id="75a66-120">Selezionare il nome del giornale di approvazione fatture che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="75a66-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="75a66-121">Selezionare **Righe** per visualizzare una pagina in cui sarà possibile selezionare le fatture che si desidera approvare.</span><span class="sxs-lookup"><span data-stu-id="75a66-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="75a66-122">Selezionare **Trova giustificativi** per visualizzare tutte le fatture pronte per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="75a66-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="75a66-123">Contrassegnare la fattura creata, quindi fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="75a66-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="75a66-124">I giustificativi selezionati in precedenza vengono spostati in questo elenco dopo che sono stati selezionati.</span><span class="sxs-lookup"><span data-stu-id="75a66-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="75a66-125">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="75a66-125">Select **OK**.</span></span>
8. <span data-ttu-id="75a66-126">Selezionare il campo **Numero di conto** per aggiungere un conto spese alla fattura.</span><span class="sxs-lookup"><span data-stu-id="75a66-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="75a66-127">Immettere un numero di conto e uscire dal campo.</span><span class="sxs-lookup"><span data-stu-id="75a66-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="75a66-128">Ad esempio, immettere `600120`.</span><span class="sxs-lookup"><span data-stu-id="75a66-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="75a66-129">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="75a66-129">Select **Post**.</span></span>
11. <span data-ttu-id="75a66-130">Selezionare **Giustificativo** per visualizzare le voci registrate.</span><span class="sxs-lookup"><span data-stu-id="75a66-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="75a66-131">Il conto di approvazione fatture in sospeso viene stornato e sostituito con il conto spese effettivo.</span><span class="sxs-lookup"><span data-stu-id="75a66-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]