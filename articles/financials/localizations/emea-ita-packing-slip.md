---
title: Registrare e stampare un documento di trasporto con dettagli di consegna di trasporto per l'Italia
description: In questo argomento viene descritto come impostare i dettagli di consegna di trasporto e registrare un documento di trasporto per l'Italia.
author: ShylaThompson
manager: AnnBe
ms.date: 04/06/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: e5000ba29b935bb574e50acbccc3bcfe96d0601e
ms.openlocfilehash: 65d19fc7bc4a00542fa1fdf6c5f4cd44a12f39d8
ms.contentlocale: it-it
ms.lasthandoff: 04/06/2018

---

# <a name="post-and-print-a-packing-slip-with-transportation-delivery-details-for-italy"></a><span data-ttu-id="b3b1e-103">Registrare e stampare un documento di trasporto con dettagli di consegna di trasporto per l'Italia</span><span class="sxs-lookup"><span data-stu-id="b3b1e-103">Post and print a packing slip with transportation delivery details for Italy</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b3b1e-104">Quando si spediscono merci ai clienti, la spedizione deve includere una bolla di accompagnamento e consegna.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-104">When you ship goods to customers, the shipment must contain a transportation delivery document (TDD).</span></span> <span data-ttu-id="b3b1e-105">La bolla di accompagnamento e consegna include informazioni sul cliente e le varie parti coinvolte nella spedizione, ad esempio il terzista della spedizione, il proprietario delle merci e il caricatore della spedizione.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-105">The TDD provides information about the customer and various parties that are involved in the shipment, such as the shipping contractor, the owner of the goods, and the shipment loader.</span></span> <span data-ttu-id="b3b1e-106">Prima di poter stampare un documento di trasporto con i dettagli di consegna di trasporto, è necessario impostare tali dettagli.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-106">Before you can print a packing slip that includes transportation delivery details, you must set up the transportation delivery details.</span></span>

## <a name="set-up-transportation-delivery-details"></a><span data-ttu-id="b3b1e-107">Impostare i dettagli di consegna di trasporto</span><span class="sxs-lookup"><span data-stu-id="b3b1e-107">Set up transportation delivery details</span></span>

<span data-ttu-id="b3b1e-108">Per stampare la bolla di accompagnamento e consegna e le informazioni di consegna nel documento di trasporto, è necessario impostare i dettagli di consegna di trasporto nelle pagine **Parametri contabilità clienti** e **Impostazione moduli**.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-108">To print the TDD and shipping information on a packing slip, you must set up the transportation delivery details on the **Accounts receivable parameters** and **Form setup** pages.</span></span>

1. <span data-ttu-id="b3b1e-109">Nella pagina **Parametri contabilità clienti**, nella scheda **Spedizioni**, nel campo **Nome vettore** selezionare il nome del vettore per la spedizione al cliente.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-109">On the **Accounts receivable parameters** page, on the **Shipments** tab, in the **Carrier name** field, select the name of the carrier for the customer shipment.</span></span>
2. <span data-ttu-id="b3b1e-110">Impostare l'opzione **Utilizza informazioni bolla di accompagnamento su documento di trasporto** su **Sì** per visualizzare i dettagli di consegna di trasporto nel documento di trasporto all'atto della registrazione.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-110">Set the **Use transportation document information on packing slip** option to **Yes** to show the transportation delivery details on the packing slip when it's posted.</span></span>
3. <span data-ttu-id="b3b1e-111">Chiudere la pagina per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-111">Close the page to save your changes.</span></span>
4. <span data-ttu-id="b3b1e-112">Selezionare **Contabilità clienti** &gt; **Impostazione** &gt; **Moduli** &gt; **Impostazione moduli**.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-112">Select **Accounts receivable** &gt; **Setup** &gt; **Forms** &gt; **Form setup**.</span></span>
5. <span data-ttu-id="b3b1e-113">Nella scheda **Documento di trasporto**, selezionare la casella di controllo **Dettagli spedizione** per stampare le informazioni di spedizione nel documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-113">On the **Packing slip** tab, select the **Shipping details** check box to print shipping information on the packing slip.</span></span> <span data-ttu-id="b3b1e-114">Le informazioni di spedizione includono i dettagli del vettore.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-114">The shipping information includes the carrier details.</span></span>
6. <span data-ttu-id="b3b1e-115">Selezionare la casella di controllo **Bolla di accompagnamento** per stampare le informazioni della bolla nel documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-115">Select the **Transportation document** check box to print the transportation document information on the packing slip.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3b1e-116">La casella di controllo **Bolla di accompagnamento** è disponibile solo se l'opzione **Utilizza informazioni bolla di accompagnamento su documento di trasporto** è impostata su **Sì** nella pagina **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-116">The **Transportation document** check box is available only if the **Use transportation document information on packing slip** option is set to **Yes** on the **Accounts receivable parameters** page.</span></span>

7. <span data-ttu-id="b3b1e-117">Chiudere la pagina per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-117">Close the page to save your changes.</span></span>

## <a name="post-and-print-a-packing-slip-that-includes-transportation-delivery-details"></a><span data-ttu-id="b3b1e-118">Registrare e stampare un documento di trasporto con i dettagli di consegna di trasporto</span><span class="sxs-lookup"><span data-stu-id="b3b1e-118">Post and print a packing slip that includes transportation delivery details</span></span>

<span data-ttu-id="b3b1e-119">È possibile registrare e stampare un documento di trasporto con una bolla di accompagnamento e consegna per una spedizione cliente.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-119">You can post and print a packing slip that includes a TDD for a customer shipment.</span></span> <span data-ttu-id="b3b1e-120">La bolla di accompagnamento e consegna contiene le informazioni riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="b3b1e-120">The TDD contains the following details:</span></span>

- <span data-ttu-id="b3b1e-121">Nome e indirizzo principale del terzista della spedizione</span><span class="sxs-lookup"><span data-stu-id="b3b1e-121">The name and primary address of the shipping contractor</span></span>
- <span data-ttu-id="b3b1e-122">Nome e indirizzo principale del caricatore della spedizione</span><span class="sxs-lookup"><span data-stu-id="b3b1e-122">The name and primary address of the shipment loader</span></span>
- <span data-ttu-id="b3b1e-123">Nome e indirizzo principale del proprietario delle merci</span><span class="sxs-lookup"><span data-stu-id="b3b1e-123">The name and primary address of the owner of the goods</span></span>
- <span data-ttu-id="b3b1e-124">Tutte le dichiarazioni, note o istruzioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b3b1e-124">Any additional declarations, notes, or instructions</span></span>
- <span data-ttu-id="b3b1e-125">Nome della persona che ha creato il documento di trasporto (vale a dire il compilatore)</span><span class="sxs-lookup"><span data-stu-id="b3b1e-125">The name of the person who created the packing slip (that is, the compiler)</span></span>

<span data-ttu-id="b3b1e-126">Se nella pagina **Registrazione documento di trasporto** non sono impostati i dettagli relativi a terzista, caricatore, proprietario e compilatore, nel documento di trasporto vengono stampati il nome e l'indirizzo della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-126">If the details of the contractor, loader, owner, and compiler aren't set on the **Packing slip posting** page, the name and address of the legal entity are printed on the packing slip instead.</span></span>

1. <span data-ttu-id="b3b1e-127">Selezionare **Vendite e marketing** &gt; **Comune** &gt; **Ordini cliente** &gt; **Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-127">Select **Sales and marketing** &gt; **Common** &gt; **Sales orders** &gt; **All sales orders**.</span></span>
2. <span data-ttu-id="b3b1e-128">Selezionare un ordine cliente aperto, quindi nel riquadro azioni, nella scheda **Preleva e imballa**, selezionare **Documento di trasporto** per aprire la finestra di dialogo **Registrazione documento di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-128">Select an open sales order, and then, on the Action Pane, on the **Pick and pack** tab, select **Packing slip** to open the **Packing slip posting** dialog box.</span></span>
3. <span data-ttu-id="b3b1e-129">Nella Scheda dettaglio **Parametri**, nel campo **Quantità**, selezionare **Tutto**.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-129">On the **Parameters** FastTab, in the **Quantity** field, select **All**.</span></span>
4. <span data-ttu-id="b3b1e-130">Impostare l'opzione **Registrazione** su **Sì** per registrare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-130">Set the **Posting** option to **Yes** to post the packing slip.</span></span>
5. <span data-ttu-id="b3b1e-131">Impostare l'opzione **Stampa documento di trasporto** su **Sì** per stampare il documento di trasporto una volta registrato.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-131">Set the **Print packing slip** option to **Yes** to print the packing slip when it's posted.</span></span>
6. <span data-ttu-id="b3b1e-132">Nel campo **Nome vettore** selezionare il nome del vettore.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-132">In the **Carrier name** field, select the name of the carrier.</span></span>
7. <span data-ttu-id="b3b1e-133">Nel campo **Compilatore**, applicare il filtro per ordinare i nomi dei compilatori, quindi selezionare il nome della persona che ha creato il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-133">In the **Compiler** field, apply the filter to sort the compiler names, and then select the name of the person who created the packing slip.</span></span>
8. <span data-ttu-id="b3b1e-134">Nei campi **Terzista**, **Caricatore** e **Proprietario**, selezionare il tipo di parte per filtrar la parte del trasporto, quindi selezionare il nome di ogni parte.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-134">In the **Contractor**, **Loader**, and **Owner** fields, select the type of party to filter the transportation party, and then select the name of each party.</span></span>
9. <span data-ttu-id="b3b1e-135">Nei campi **Dichiarazioni aggiuntive**, **Note aggiuntive** e **Istruzioni aggiuntive** immettere tutte le informazioni aggiuntive da stampare nel documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-135">In the **Additional declarations**, **Additional notes**, and **Additional instructions** fields, enter any additional information that should be printed on the packing slip.</span></span>
10. <span data-ttu-id="b3b1e-136">Fare clic su **OK** per registrare e stampare il documento di trasporto con le informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-136">Select **OK** to post and print a packing slip that includes the transportation document information.</span></span>
11. <span data-ttu-id="b3b1e-137">Chiudere la pagina per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b3b1e-137">Close the page to save your changes.</span></span>

