---
title: Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio
description: In questo argomento viene descritto come modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: ff16d8e2e75a877e5ca7de604c7915e908473da6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792707"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a><span data-ttu-id="fdde2-103">Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="fdde2-103">Edit financial dimensions for retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fdde2-104">In questo argomento viene descritto come modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fdde2-104">This topic describes how to edit financial dimensions for retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="edit-financial-dimensions"></a><span data-ttu-id="fdde2-105">Modificare le dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="fdde2-105">Edit financial dimensions</span></span>

<span data-ttu-id="fdde2-106">Per modificare le dimensioni finanziare per le transazioni di vendita al dettaglio in Commerce Headquarters, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="fdde2-106">To edit financial dimensions for retail transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="fdde2-107">Aprire la pagina **Configurazione dimensione finanziaria per integrazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="fdde2-107">Open the **Financial dimensions configuration for integrating applications** page.</span></span>
1. <span data-ttu-id="fdde2-108">Selezionare il record **Integrazione dimensioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="fdde2-108">Select the active **Default dimensions integration** record.</span></span>
1. <span data-ttu-id="fdde2-109">Nella Scheda dettaglio **Dimensioni finanziarie**, assicurarsi che tutte le dimensioni che si desidera modificare nel foglio di lavoro Excel siano presenti nell'elenco **Selezionata**.</span><span class="sxs-lookup"><span data-stu-id="fdde2-109">On the **Financial dimensions** FastTab, make sure that all the dimensions that you want to edit in the Excel worksheet are present in the **Selected** list.</span></span> <span data-ttu-id="fdde2-110">Per ulteriori informazioni, vedere [Entità di dati](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).</span><span class="sxs-lookup"><span data-stu-id="fdde2-110">For more information, see [Data entities](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).</span></span>
1. <span data-ttu-id="fdde2-111">Scaricare e aprire il file Excel dalla pagina **Rendiconti**, la pagina **Transazioni vendita al dettaglio** o il riquadro **Errori di convalida transazioni** nell'area di lavoro **Dati finanziari punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="fdde2-111">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="fdde2-112">Per modificare la dimensione finanziaria della transazione, selezionare **Progettazione**, quindi selezionare il simbolo della matita accanto alla riga **Transazione (verificabile)**.</span><span class="sxs-lookup"><span data-stu-id="fdde2-112">To change the transaction financial dimension, select **Design**, and then select the pencil symbol next to the **Transaction (auditable)** row.</span></span>
1. <span data-ttu-id="fdde2-113">Trovare e selezionare il campo **FinancialDimensionDisplayValue**, selezionare una cella nella parte dell'intestazione del foglio di lavoro di Excel, quindi selezionare **Aggiungi etichetta**.</span><span class="sxs-lookup"><span data-stu-id="fdde2-113">Find and select the **FinancialDimensionDisplayValue** field, select a cell in the header part of the Excel worksheet, and then select **Add label**.</span></span>
1. <span data-ttu-id="fdde2-114">Selezionare una cella sotto la cella selezionata nel passaggio precedente, selezionare **Aggiungi valore** e quindi selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="fdde2-114">Select a cell below the cell that you selected in the previous step, select **Add Value**, and then select **Refresh**.</span></span> <span data-ttu-id="fdde2-115">Le dimensioni finanziarie vengono aggiunte al foglio di lavoro di Excel e possono quindi essere modificate e pubblicate.</span><span class="sxs-lookup"><span data-stu-id="fdde2-115">The financial dimensions are added to the Excel worksheet, and they can then be edited and published.</span></span>
1. <span data-ttu-id="fdde2-116">Per modificare le dimensioni nelle righe di transazione, selezionare la riga **Transazioni di vendita (verificabili)**, selezionare il simbolo della matita, quindi ripetere i passaggi 6 e 7.</span><span class="sxs-lookup"><span data-stu-id="fdde2-116">To change the dimensions on the transaction lines, select the **Sales transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>
1. <span data-ttu-id="fdde2-117">Per modificare le dimensioni nelle righe di pagamento, selezionare la riga **Transazioni di pagamento (verificabili)**, selezionare il simbolo della matita, quindi ripetere i passaggi 6 e 7.</span><span class="sxs-lookup"><span data-stu-id="fdde2-117">To change the dimensions on the payment lines, select the **Payment transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fdde2-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fdde2-118">Additional resources</span></span>

[<span data-ttu-id="fdde2-119">Modificare e controllare le transazioni di cash-and-carry e di gestione di cassa</span><span class="sxs-lookup"><span data-stu-id="fdde2-119">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="fdde2-120">Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni</span><span class="sxs-lookup"><span data-stu-id="fdde2-120">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="fdde2-121">Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="fdde2-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="fdde2-122">Aggiungere campi a una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="fdde2-122">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]