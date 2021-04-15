---
title: Creare un cespite
description: In questo argomento viene illustrato come creare un nuovo record di cespite dalla pagina elenco Cespite.
author: moaamer
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 770390092342e2db496dde850a75b2f7736bd4c0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817103"
---
# <a name="create-a-fixed-asset"></a><span data-ttu-id="fc604-103">Creare un cespite</span><span class="sxs-lookup"><span data-stu-id="fc604-103">Create a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fc604-104">In questo argomento viene illustrato come creare un nuovo record di cespite dalla pagina elenco **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="fc604-104">This topic explains how to create a new fixed asset record from the **Fixed asset** list page.</span></span>

<span data-ttu-id="fc604-105">Il sistema assegna il numero di cespite, in base alla sequenza numerica assegnata al gruppo di cespiti.</span><span class="sxs-lookup"><span data-stu-id="fc604-105">The system assigns the asset number, based on the number sequence that is assigned to the fixed asset group.</span></span> <span data-ttu-id="fc604-106">Se si utilizza il modello di cespite per importare cespiti tramite il componente aggiuntivo per Microsoft Excel o se si utilizza un altro processo di importazione, il sistema crea automaticamente record di cespiti e incrementa il numero di cespite.</span><span class="sxs-lookup"><span data-stu-id="fc604-106">If you use the fixed asset template to import assets via the Microsoft Excel add-in, or if you use another import job, the system automatically creates fixed asset records and increments the asset number.</span></span>

<span data-ttu-id="fc604-107">Per creare manualmente un record di cespite, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="fc604-107">To manually create an asset record, follow these steps.</span></span>

1. <span data-ttu-id="fc604-108">Andare a **Pannello di navigazione \> Moduli \> Cespiti \> Cespiti \> Cespiti**.</span><span class="sxs-lookup"><span data-stu-id="fc604-108">Go to **Navigation pane \> Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="fc604-109">Nel **Riquadro azioni** selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fc604-109">On the **Action pane**, select **New**.</span></span>
3. <span data-ttu-id="fc604-110">Nel campo **Gruppo cespite** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc604-110">In **the Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="fc604-111">Il campo **Numero** verrà impostato come predefinito se è stata attivata la funzionalità **Numerazione automatica cespiti** nei parametri **Cespiti** e **Gruppo cespite**.</span><span class="sxs-lookup"><span data-stu-id="fc604-111">The **Number** field will default if you have enabled **Autonumber fixed assets functionality** in the **Fixed assets parameters** and the **Fixed asset group**.</span></span> <span data-ttu-id="fc604-112">In caso contrario, è necessario immettere un numero univoco per identificare il cespite.</span><span class="sxs-lookup"><span data-stu-id="fc604-112">If not, you must enter a unique number to identify the fixed asset.</span></span>
4. <span data-ttu-id="fc604-113">Nel campo **Nome** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="fc604-113">In the **Name** field, enter a value.</span></span> <span data-ttu-id="fc604-114">Immettere le informazioni aggiuntive relative al cespite necessarie per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="fc604-114">Enter the additional information that your business needs for this asset.</span></span>
5. <span data-ttu-id="fc604-115">Nel **riquadro azioni** selezionare **Libri**.</span><span class="sxs-lookup"><span data-stu-id="fc604-115">On the **Action pane**, select **Books**.</span></span>
6. <span data-ttu-id="fc604-116">Immettere una data nel campo **Data di acquisizione**.</span><span class="sxs-lookup"><span data-stu-id="fc604-116">In the **Acquisition date** field, enter a date.</span></span>
7. <span data-ttu-id="fc604-117">Immettere un numero nel campo **Prezzo di acquisizione**.</span><span class="sxs-lookup"><span data-stu-id="fc604-117">In the **Acquisition price** field, enter a number.</span></span>

    - <span data-ttu-id="fc604-118">Immettere le informazioni aggiuntive relative al cespite necessarie per il libro.</span><span class="sxs-lookup"><span data-stu-id="fc604-118">Enter the additional information that your business needs for this book.</span></span>
    - <span data-ttu-id="fc604-119">Immettere le informazioni aggiuntive relative ai libri rimanenti necessarie per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="fc604-119">Enter the additional information that your business needs for the remaining books.</span></span>

8. <span data-ttu-id="fc604-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fc604-120">Close the page.</span></span>

<span data-ttu-id="fc604-121">È inoltre possibile importare i cespiti utilizzando il componente aggiuntivo per Excel o eseguendo un processo di importazione dall'area di lavoro **Gestione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="fc604-121">You can also import fixed assets by using the Excel add-in or by running an import job from the **Data management** workspace.</span></span> <span data-ttu-id="fc604-122">Prima di eseguire l'importazione, immettere i valori nei campi obbligatori del modello.</span><span class="sxs-lookup"><span data-stu-id="fc604-122">Before you run the import, enter the values for required fields in the template.</span></span>

<span data-ttu-id="fc604-123">Se non è stato definito il numero di cespite nel modello del componente aggiuntivo per Excel o in Gestione dei dati, il sistema crea un numero di cespite per ogni cespite importato e incrementa automaticamente la sequenza numerica per ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="fc604-123">If you didn't define the fixed asset number in the template of the Excel add-in, or in Data management, the system creates a fixed asset number for each imported asset and automatically increments the number sequence for each.</span></span> <span data-ttu-id="fc604-124">Tuttavia, se si importano cespiti e si definiscono i numeri di cespite nel modello, il sistema **non** incrementa automaticamente la sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="fc604-124">However, if you import assets and define asset numbers in the template, the system does **not** automatically increment the number sequence.</span></span> <span data-ttu-id="fc604-125">In questo caso, un amministratore potrebbe dover aggiornare manualmente la sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="fc604-125">In this case, an admin might have to manually update the number sequence.</span></span> <span data-ttu-id="fc604-126">Se è stato definito il numero di cespite nel modello del componente aggiuntivo per Excel, il sistema utilizza il numero di cespite definito e incrementa la sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="fc604-126">If you defined the fixed asset number in the template of the Excel add-in, the system uses the defined fixed asset number and increments the number sequence.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="fc604-127">Dopo aver registrato l'ammortamento, i campi **Messa in servizio** e **Data di esecuzione ammortamento** verranno bloccati nella pagina **Libro**.</span><span class="sxs-lookup"><span data-stu-id="fc604-127">After posting the depreciation, the **Placed in service** and **Depreciation run date** fields will be locked on the **Book** page.</span></span> <span data-ttu-id="fc604-128">Inoltre, entrambi i campi non verranno aggiornati dall'entità di dati.</span><span class="sxs-lookup"><span data-stu-id="fc604-128">Also, both neither field will be updated from the data entity.</span></span>

> [!WARNING]
> <span data-ttu-id="fc604-129">Il record del cespite non verrà eliminato se le transazioni sono state registrate nel libro associato o se il cespite appena creato viene immesso in una riga di giornale di registrazione ma non registrato.</span><span class="sxs-lookup"><span data-stu-id="fc604-129">The fixed asset record won't be deleted if transactions were posted to the associated book, or if the newly created fixed asset is entered on a journal line but not posted.</span></span> 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]