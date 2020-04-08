---
title: EUR-00015 Impostare l'ID IVA
description: In questa procedura si descrivono i prerequisiti di registrazione di ID IVA, ad esempio l'impostazione di un tipo di registrazione e la sua assegnazione a una categoria di registrazione.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5bf6fe6926a7cc1aecb1f0a2bb7f3c47cc8828e8
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144323"
---
# <a name="eur-00015-set-up-vat-id"></a><span data-ttu-id="9cc1c-103">EUR-00015 Impostare l'ID IVA</span><span class="sxs-lookup"><span data-stu-id="9cc1c-103">EUR-00015 Set up VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9cc1c-104">In questa procedura si descrivono i prerequisiti di registrazione di ID IVA, ad esempio l'impostazione di un tipo di registrazione e la sua assegnazione a una categoria di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="9cc1c-105">È possibile ottenere ulteriori informazioni sugli ID registrazione e la loro elaborazione, inclusi i prerequisiti necessari, nell'argomento della Guida sugli ID registrazione.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="9cc1c-106">Queste informazioni si applicano a tutti i paesi europei.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="9cc1c-107">Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF con l'indirizzo principale della persona giuridica in Germania.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="9cc1c-108">Quest'attività è destinata agli amministratori di sistema.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-108">This task is intended for system administrators.</span></span> <span data-ttu-id="9cc1c-109">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="9cc1c-110">Scegliere Amministrazione organizzazione > Rubrica globale > Tipi di registrazione > Tipi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="9cc1c-111">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="9cc1c-112">Nel campo Nome digitare 'ID IVA'.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="9cc1c-113">Nel campo Descrizione, numero di partita IVA.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="9cc1c-114">Nel campo Paese immettere o selezionare un valore DEU</span><span class="sxs-lookup"><span data-stu-id="9cc1c-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="9cc1c-115">Selezionare Sì nel campo Univoco.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="9cc1c-116">Selezionare questa casella di controllo per verificare se l'ID IVA è univoco.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="9cc1c-117">Selezionare Sì nel campo Principale per paese.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="9cc1c-118">Selezionare questa casella di controllo se l'ID IVA deve essere valido per tutti gli indirizzi che appartengono al paese specificato.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="9cc1c-119">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-119">Click Create.</span></span>
9. <span data-ttu-id="9cc1c-120">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-120">Click Add.</span></span>
10. <span data-ttu-id="9cc1c-121">Nel campo Paese immettere o selezionare un valore ITA</span><span class="sxs-lookup"><span data-stu-id="9cc1c-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="9cc1c-122">Nel campo Formato digitare '###########'.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="9cc1c-123">Quando si immette un ID registrazione di questo tipo per il paese selezionato, l'ID registrazione verrà verificato rispetto a questo formato.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="9cc1c-124">Selezionare la casella di controllo Univoco.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="9cc1c-125">Selezionare questa casella di controllo per verificare se l'ID IVA è univoco.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="9cc1c-126">Selezionare la casella di controllo Principale per paese.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="9cc1c-127">Selezionare questa casella di controllo se l'ID IVA deve essere valido per tutti gli indirizzi che appartengono al paese specificato.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="9cc1c-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-128">Click Save.</span></span>
15. <span data-ttu-id="9cc1c-129">Scegliere Amministrazione organizzazione > Rubrica globale > Tipi di registrazione > Categorie di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="9cc1c-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-130">Click New.</span></span>
17. <span data-ttu-id="9cc1c-131">Nel campo Paese immettere o selezionare un valore ID IVA, DEU</span><span class="sxs-lookup"><span data-stu-id="9cc1c-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="9cc1c-132">Nel campo Categoria di registrazione selezionare 'ID IVA'</span><span class="sxs-lookup"><span data-stu-id="9cc1c-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="9cc1c-133">Assegnare il tipo di registrazione creato in precedenza a una categoria predefinita di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="9cc1c-134">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-134">Click New.</span></span>
20. <span data-ttu-id="9cc1c-135">Nel campo Paese immettere o selezionare un valore ID IVA, ITA</span><span class="sxs-lookup"><span data-stu-id="9cc1c-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="9cc1c-136">Nel campo Categoria di registrazione selezionare 'ID IVA'</span><span class="sxs-lookup"><span data-stu-id="9cc1c-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="9cc1c-137">Assegnare il tipo di registrazione creato a una categoria predefinita di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="9cc1c-138">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9cc1c-138">Click Save.</span></span>

