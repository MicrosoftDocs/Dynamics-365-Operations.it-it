---
title: Importare e gestire transazioni con carta di credito
description: Questo argomento descrive come importare e gestire le transazioni con carta di credito correlate alle spese. Queste transazioni possono essere impostate per essere incluse automaticamente in una programmazione ricorrente o importate manualmente quando necessarie.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 65501866f0c465f40de842c5f612aae9349db7be
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="import-and-maintain-credit-card-transactions"></a><span data-ttu-id="e3557-104">Importare e gestire transazioni con carta di credito</span><span class="sxs-lookup"><span data-stu-id="e3557-104">Import and maintain credit card transactions</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="e3557-105">Le transazioni con carte di credito correlate alle spese possono essere impostate per essere incluse automaticamente in una programmazione ricorrente.</span><span class="sxs-lookup"><span data-stu-id="e3557-105">Expense-related credit card transactions can be set up so that they are automatically imported on a recurring schedule.</span></span> <span data-ttu-id="e3557-106">In alternativa, le transazioni possono essere importate manualmente secondo le esigenze.</span><span class="sxs-lookup"><span data-stu-id="e3557-106">Alternatively, the transactions can be manually imported as they are required.</span></span> <span data-ttu-id="e3557-107">Le transazioni con carta di credito vengono importate mediante l'entità di dati Transazioni con carta di credito.</span><span class="sxs-lookup"><span data-stu-id="e3557-107">The credit card transactions are imported through the Credit card transactions data entity.</span></span>

<span data-ttu-id="e3557-108">Per ulteriori informazioni sulle entità di dati, vedere [Entità di dati](../../dev-itpro/data-entities/data-entities.md).</span><span class="sxs-lookup"><span data-stu-id="e3557-108">For more information about data entities, see [Data entities](../../dev-itpro/data-entities/data-entities.md).</span></span>

## <a name="import-credit-card-transactions"></a><span data-ttu-id="e3557-109">Importa le transazioni con carta di credito</span><span class="sxs-lookup"><span data-stu-id="e3557-109">Import credit card transactions</span></span>

1. <span data-ttu-id="e3557-110">Nella pagina **Transazioni con carta di credito**, selezionare **Importa transazioni**.</span><span class="sxs-lookup"><span data-stu-id="e3557-110">On the **Credit card transactions** page, select **Import transactions**.</span></span> <span data-ttu-id="e3557-111">Se si apre per la prima volta la gestione dei dati, il sistema deve aggiornare l'elenco delle entità di dati prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e3557-111">If you’re opening data management for the first time, the system must update the list of data entities before you can continue.</span></span>
2. <span data-ttu-id="e3557-112">Nel campo **Nome** immettere una descrizione univoca del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="e3557-112">In the **Name** field, enter a unique description of the import job.</span></span>
3. <span data-ttu-id="e3557-113">Nel campo **Formato dati di origine**, selezionare il formato del file contenente le transazioni con carta di credito da importare.</span><span class="sxs-lookup"><span data-stu-id="e3557-113">In the **Source data format** field, select the format of the file that contains the credit card transactions to import.</span></span>
4. <span data-ttu-id="e3557-114">Selezionare **Carica** e quindi individuare e selezionare il file da importare.</span><span class="sxs-lookup"><span data-stu-id="e3557-114">Select **Upload**, and then find and select the file to import.</span></span>
5. <span data-ttu-id="e3557-115">Dopo che il file è stato caricato, convalidare il mapping del file delle transazioni con carta di credito e le colonne dell'entità di dati Transazioni con carta di credito selezionando il collegamento **Visualizza mapping** nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="e3557-115">After the file has been uploaded, validate the mapping of the credit card transaction file and the columns of the Credit card transactions data entity by selecting the **View map** link on the tile.</span></span> <span data-ttu-id="e3557-116">Se vi sono errori di mapping, o se è necessario modificare il mapping, apportare le modifiche al mapping nella scheda **Visualizzazione mapping** o **Dettagli mapping**.</span><span class="sxs-lookup"><span data-stu-id="e3557-116">If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.</span></span>
6. <span data-ttu-id="e3557-117">Per automatizzare le transazioni con carta di credito, selezionare **Crea processo dati ricorrente**.</span><span class="sxs-lookup"><span data-stu-id="e3557-117">To automate the credit card transactions, select **Create recurring data job**.</span></span> <span data-ttu-id="e3557-118">È quindi possibile impostare la ricorrenza che definisce la frequenza di importazione delle transazioni con carta di credito.</span><span class="sxs-lookup"><span data-stu-id="e3557-118">You can then set the recurrence that defines how often credit card transactions should be imported.</span></span> <span data-ttu-id="e3557-119">Al termine, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3557-119">When you’ve finished, select **OK**.</span></span>
7. <span data-ttu-id="e3557-120">Per importare il file selezionato, selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="e3557-120">To import the selected file now, select **Import**.</span></span>
8. <span data-ttu-id="e3557-121">Se si verificano degli errori durante l'importazione, è possibile visualizzare i dati di gestione temporanea o del registro di esecuzione per visualizzare gli errori che è necessario correggere per garantire una corretta importazione.</span><span class="sxs-lookup"><span data-stu-id="e3557-121">If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help guarantee a successful import.</span></span>

> [!NOTE]
> <span data-ttu-id="e3557-122">Se è necessario importare più formati di file, è necessario creare processi di importazione distinti per ogni tipo di formato.</span><span class="sxs-lookup"><span data-stu-id="e3557-122">If you must import more than one file format, you must create separate import jobs for each format type.</span></span>

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a><span data-ttu-id="e3557-123">Riassegnare le transazioni con carta di credito per dipendenti con rapporto chiuso.</span><span class="sxs-lookup"><span data-stu-id="e3557-123">Reassign the credit card transactions for terminated employees</span></span>

<span data-ttu-id="e3557-124">Dopo che un record dipendente viene terminato, l'account di Servizi di dominio Active Directory del dipendente viene disattivato.</span><span class="sxs-lookup"><span data-stu-id="e3557-124">After an employee record is terminated, the employee’s Active Directory Domain Services (AD DS) account is disabled.</span></span> <span data-ttu-id="e3557-125">È tuttavia possibile che vi siano transazioni con carta di credito attive che devono ancora essere spese e rimborsate.</span><span class="sxs-lookup"><span data-stu-id="e3557-125">However, there might be active credit card transactions that must still be expensed and reimbursed.</span></span> <span data-ttu-id="e3557-126">Nella pagina **Transazioni con carta di credito**, è possibile riassegnare a un altro dipendente qualsiasi transazione con carta di credito del dipendente associato che ha concluso il rapporto di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e3557-126">From the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee has been terminated.</span></span>

<span data-ttu-id="e3557-127">Selezionare una o più transazioni con carta di credito e selezionare **Riassegna transazioni**.</span><span class="sxs-lookup"><span data-stu-id="e3557-127">Select one or more credit card transactions, and then select **Reassign transactions**.</span></span> <span data-ttu-id="e3557-128">È quindi possibile selezionare un altro dipendente a cui assegnare le transazioni con carta di credito.</span><span class="sxs-lookup"><span data-stu-id="e3557-128">You can then select another employee to assign the credit card transactions to.</span></span> <span data-ttu-id="e3557-129">Dopo aver riassegnato le transazioni con carta di credito, possono essere selezionate per una nota spese e pagate tramite il normale processo di rimborso della nota spese.</span><span class="sxs-lookup"><span data-stu-id="e3557-129">After the credit card transactions have been reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.</span></span>

