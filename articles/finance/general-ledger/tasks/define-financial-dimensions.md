---
title: Definire dimensioni finanziarie
description: Questa guida di attività dimostra l'aggiunta una dimensione finanziaria supportata da un'entità e di una dimensione finanziaria personalizzata.
author: aprilolson
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6fbe739eec0cfa1e7b0276872640bd4f82be3ef7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444614"
---
# <a name="define-financial-dimensions"></a><span data-ttu-id="1e354-103">Definire dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="1e354-103">Define financial dimensions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e354-104">Questa guida di attività dimostra l'aggiunta una dimensione finanziaria supportata da un'entità e di una dimensione finanziaria personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1e354-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="1e354-105">La guida utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="1e354-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="1e354-106">Creare una dimensione finanziaria supportata da un'entità</span><span class="sxs-lookup"><span data-stu-id="1e354-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="1e354-107">Selezionare **Pannello di navigazione > Moduli > Contabilità generale > Piano dei conti > Dimensioni > Dimensioni finanziarie**.</span><span class="sxs-lookup"><span data-stu-id="1e354-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Dimensions > Financial dimensions**.</span></span>
2. <span data-ttu-id="1e354-108">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1e354-108">Click **New**.</span></span>
3. <span data-ttu-id="1e354-109">Nel campo **Usa valori da**, selezionare un'entità definita dal sistema su cui basare la dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="1e354-109">In the **User values form** field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="1e354-110">Nel campo **Nome dimensione**, immettere un valore per descrivere la dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="1e354-110">In the **Dimension name** field, type a value to describe the financial dimension.</span></span> <span data-ttu-id="1e354-111">Il nome può essere diverso da quello dell'entità definita dal sistema ma non può contenere spazi o caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="1e354-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>
5. <span data-ttu-id="1e354-112">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="1e354-112">Click **Activate**.</span></span> <span data-ttu-id="1e354-113">Attivare la dimensione finanziaria aggiorna la tabella con il nome della dimensione finanziaria e rimuove le dimensioni eliminate.</span><span class="sxs-lookup"><span data-stu-id="1e354-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="1e354-114">È possibile immettere i valori delle dimensioni prima di attivare una dimensione finanziaria, ma una dimensione finanziaria non può essere utilizzata fino all'attivazione.</span><span class="sxs-lookup"><span data-stu-id="1e354-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="1e354-115">Fare clic su **Chiudi** nel messaggio di attivazione.</span><span class="sxs-lookup"><span data-stu-id="1e354-115">Click **Close** on the activation message.</span></span>
7. <span data-ttu-id="1e354-116">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="1e354-116">Click **Activate**.</span></span> <span data-ttu-id="1e354-117">L'attivazione della dimensione può essere programmata per l'esecuzione in batch a una data e un'ora specifica.</span><span class="sxs-lookup"><span data-stu-id="1e354-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="1e354-118">Nel **riquadro azioni**, fare clic su **Valori di dimensione**.</span><span class="sxs-lookup"><span data-stu-id="1e354-118">On **Action pane**, click **Dimension values**.</span></span> <span data-ttu-id="1e354-119">Alcuni valori di dimensione sono specifici di società.</span><span class="sxs-lookup"><span data-stu-id="1e354-119">Some dimension values are company specific.</span></span> <span data-ttu-id="1e354-120">È possibile verificare se sono specifici di una società dalla presenza del nome della società nell'elenco di valori di dimensione.</span><span class="sxs-lookup"><span data-stu-id="1e354-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="1e354-121">Creare una dimensione finanziaria personalizzata</span><span class="sxs-lookup"><span data-stu-id="1e354-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="1e354-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1e354-122">Close the page.</span></span>
2. <span data-ttu-id="1e354-123">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1e354-123">Click **New**.</span></span>
3. <span data-ttu-id="1e354-124">Nel campo **Usa valori da**, selezionare **Dimensione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="1e354-124">In the **Use values from** field, select **Custom dimension**.</span></span>
4. <span data-ttu-id="1e354-125">Nel campo **Nome dimensione**, immettere un valore per descrivere la dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="1e354-125">In the **Dimension name** field, type a value to describe the financial dimension.</span></span>
    - <span data-ttu-id="1e354-126">Il nome non può contenere spazi o caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="1e354-126">The name cannot contain spaces or special characters.</span></span>  
    - <span data-ttu-id="1e354-127">È anche possibile specificare una maschera conto per limitare la quantità e il tipo di informazioni che è possibile immettere per i valori di dimensione.</span><span class="sxs-lookup"><span data-stu-id="1e354-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    - <span data-ttu-id="1e354-128">È possibile immettere caratteri rimanenti uguali per ciascun valore di dimensione, ad esempio le lettere o un trattino.</span><span class="sxs-lookup"><span data-stu-id="1e354-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="1e354-129">È inoltre possibile immettere i segni di numero (#) e commerciali (&) come segnaposto per le lettere e i numeri che cambieranno ogni volta che un valore di dimensione viene creato.</span><span class="sxs-lookup"><span data-stu-id="1e354-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="1e354-130">Utilizzare un simbolo di numero (#) come segnaposto per un numero e la e commerciale (&) come segnaposto per una lettera.</span><span class="sxs-lookup"><span data-stu-id="1e354-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="1e354-131">Esempio: per limitare il valore della dimensione alle lettere CC e a tre numeri, immettere CC-### come maschera formato.</span><span class="sxs-lookup"><span data-stu-id="1e354-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="1e354-132">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="1e354-132">Click **Activate**.</span></span> <span data-ttu-id="1e354-133">Attivare la dimensione finanziaria aggiorna la tabella con il nome della dimensione finanziaria e rimuove le dimensioni eliminate.</span><span class="sxs-lookup"><span data-stu-id="1e354-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="1e354-134">È possibile immettere i valori delle dimensioni prima di attivare una dimensione finanziaria, ma una dimensione finanziaria non può essere utilizzata fino all'attivazione.</span><span class="sxs-lookup"><span data-stu-id="1e354-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>     
6. <span data-ttu-id="1e354-135">Fare clic su **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="1e354-135">Click **Activate**.</span></span> <span data-ttu-id="1e354-136">L'attivazione della dimensione può essere programmata per l'esecuzione in batch a una data e un'ora specifica.</span><span class="sxs-lookup"><span data-stu-id="1e354-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>      
7. <span data-ttu-id="1e354-137">Nel **riquadro azioni**, fare clic su **Valori di dimensione**.</span><span class="sxs-lookup"><span data-stu-id="1e354-137">On **Action pane**, click **Dimension values**.</span></span>
8. <span data-ttu-id="1e354-138">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1e354-138">Click **New**.</span></span>
9. <span data-ttu-id="1e354-139">Nel campo **Valore di dimensione**, immettere un nome per descrivere il valore della dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="1e354-139">In the **Dimension value** field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="1e354-140">Nel campo **Descrizione**, immettere una descrizione che descrive il valore di dimensione finanziaria.</span><span class="sxs-lookup"><span data-stu-id="1e354-140">In the **Description** field, type a description that describes your financial dimension value.</span></span>

