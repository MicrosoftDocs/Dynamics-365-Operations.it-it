---
title: Proporre acquisizioni di cespiti
description: Questa argomento descrive come acquisire un cespite utilizzando la proposta di acquisizione nel giornale di registrazione cespiti.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9259c9bbf52c1c09a7092db6976fc3fabca6601
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990441"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="c3499-103">Proporre acquisizioni di cespiti</span><span class="sxs-lookup"><span data-stu-id="c3499-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c3499-104">Questa argomento descrive come acquisire un cespite utilizzando la proposta di acquisizione nel giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="c3499-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="c3499-105">Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="c3499-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="c3499-106">Per acquisire un cespite tramite un giornale di proposte cespite, è necessario innanzitutto creare il record cespite, quindi definire il prezzo di acquisizione nel libro patrimoniale.</span><span class="sxs-lookup"><span data-stu-id="c3499-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

1. <span data-ttu-id="c3499-107">Nel pannello di navigazione, andare a **Moduli > Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="c3499-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="c3499-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c3499-108">Select **New**.</span></span>
3. <span data-ttu-id="c3499-109">Nel campo **Nome** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c3499-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="c3499-110">Nel riquadro azioni selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="c3499-110">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="c3499-111">Selezione **Proposte**.</span><span class="sxs-lookup"><span data-stu-id="c3499-111">Select **Proposals**.</span></span>
6. <span data-ttu-id="c3499-112">Selezionare **Proposta di acquisizione**.</span><span class="sxs-lookup"><span data-stu-id="c3499-112">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="c3499-113">Selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="c3499-113">Select **Filter**.</span></span> <span data-ttu-id="c3499-114">Fare clic su **Reimposta** per cancellare i valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="c3499-114">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="c3499-115">Selezionare la riga **Numero cespite**.</span><span class="sxs-lookup"><span data-stu-id="c3499-115">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="c3499-116">Nel campo **Criteri** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c3499-116">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="c3499-117">Impostare i criteri rimanenti per i cespiti che si desidera acquisire con la proposta.</span><span class="sxs-lookup"><span data-stu-id="c3499-117">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="c3499-118">Selezionare due volte **OK** per uscire dal riquadro.</span><span class="sxs-lookup"><span data-stu-id="c3499-118">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="c3499-119">Verificare le righe transazione create.</span><span class="sxs-lookup"><span data-stu-id="c3499-119">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="c3499-120">Solo i cespiti con la data di acquisizione e il prezzo di acquisizione impostati sul libro verranno inclusi nella proposta di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="c3499-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="c3499-121">Nella pagina, selezionare la scheda **Libri**.</span><span class="sxs-lookup"><span data-stu-id="c3499-121">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="c3499-122">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="c3499-122">Select **Post**.</span></span>
