---
title: Creare un conto fornitore
description: Questa procedura mostra come creare un conto fornitore e come aggiungere un indirizzo e informazioni di contatto.
author: RichardLuan
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7f5723fc2aa50fc66c825eb09a01e45833b817e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022133"
---
# <a name="create-a-vendor-account"></a><span data-ttu-id="b2ce8-103">Creare un conto fornitore</span><span class="sxs-lookup"><span data-stu-id="b2ce8-103">Create a vendor account</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b2ce8-104">Questa procedura mostra come creare un conto fornitore e come aggiungere un indirizzo e informazioni di contatto.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="b2ce8-105">La procedura non illustra come popolare tutti i campi per scopi finanziari e di acquisto.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="b2ce8-106">Per ulteriori informazioni su questi campi, leggere le descrizioni dei campi.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="b2ce8-107">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="b2ce8-108">I conti fornitore in genere vengono creati da un responsabile degli approvvigionamenti o dal personale addetto alla contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="b2ce8-109">Creare un conto fornitore</span><span class="sxs-lookup"><span data-stu-id="b2ce8-109">Create a vendor account</span></span>
1. <span data-ttu-id="b2ce8-110">Andare a **Pannello di navigazione > Moduli > Approvvigionamento > Fornitori > Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-110">Go to **Navigation pane > Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="b2ce8-111">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-111">Click **New**.</span></span>
3. <span data-ttu-id="b2ce8-112">Nel campo **Conto fornitore**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-112">In the **Vendor account** field, type a value.</span></span>
    - <span data-ttu-id="b2ce8-113">Il valore può essere immesso automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-113">The value may be populated automatically.</span></span> <span data-ttu-id="b2ce8-114">In tal caso, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-114">If so, you can skip this step.</span></span>  
    - <span data-ttu-id="b2ce8-115">È possibile creare conti fornitore per una persona o un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="b2ce8-116">Ciò interesserà i campi disponibili.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-116">This will affect which fields are available.</span></span> <span data-ttu-id="b2ce8-117">In questo esempio verrà creato un conto fornitore per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-117">In this example, we'll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="b2ce8-118">Nel campo **Nome** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-118">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="b2ce8-119">Se il fornitore è già una parte registrata nel sistema, è possibile utilizzare il menu a discesa e selezionarlo in questo campo. Il nuovo conto fornitore erediterà l'indirizzo e le informazioni di contatto già registrate.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that's already registered.</span></span>
5. <span data-ttu-id="b2ce8-120">Nel campo **Gruppo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-120">In the **Group** field, enter or select a value.</span></span> <span data-ttu-id="b2ce8-121">Il gruppo di fornitori viene utilizzato per raggruppare i fornitori con uno dei seguenti parametri in comune: termini di pagamento, periodo di liquidazione, conti CoGe di registrazione magazzino, inclusi fascia IVA, conti CoGe predefiniti, codici di filtro prodotti o configurazione di previsione dell'offerta.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment, settle period, inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>
6. <span data-ttu-id="b2ce8-122">Nel campo **Numero di dipendenti** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-122">In the **Number of employees** field, enter a number.</span></span>
7. <span data-ttu-id="b2ce8-123">Digitare un valore nel campo **Numero organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-123">In the **Organization number** field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="b2ce8-124">Aggiungere un indirizzo</span><span class="sxs-lookup"><span data-stu-id="b2ce8-124">Add an address</span></span>
1. <span data-ttu-id="b2ce8-125">Espandere la sezione **Indirizzi**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-125">Expand the **Addresses** section.</span></span>
2. <span data-ttu-id="b2ce8-126">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-126">Click **Add**.</span></span>
3. <span data-ttu-id="b2ce8-127">Nel campo **Scopo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-127">In the **Purpose** field, enter or select a value.</span></span> <span data-ttu-id="b2ce8-128">È possibile selezionare uno o più scopi.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-128">You can select one or more purposes.</span></span> <span data-ttu-id="b2ce8-129">Questi vengono utilizzati per selezionare l'indirizzo corretto per uno scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="b2ce8-130">Ad esempio, se lo scopo è "Fattura", tale indirizzo verrà utilizzato per l'invio di fatture.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-130">For example, if the purpose is "Invoice" that address will be used when you send invoices.</span></span>
4. <span data-ttu-id="b2ce8-131">Digitare un valore nel campo **Nome o descrizione**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-131">In the **Name or description** field, type a value.</span></span>
5. <span data-ttu-id="b2ce8-132">Nel campo **Paese**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-132">In the **Country/region** field, enter or select a value.</span></span> <span data-ttu-id="b2ce8-133">Immettere i dettagli dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-133">Enter the address details.</span></span> <span data-ttu-id="b2ce8-134">Il paese selezionato determinerà i campi visualizzati, corrispondenti al formato di indirizzo per il paese.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span> 
6. <span data-ttu-id="b2ce8-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-135">Click **OK**.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="b2ce8-136">Aggiungere informazioni contatto</span><span class="sxs-lookup"><span data-stu-id="b2ce8-136">Add contact information</span></span>
1. <span data-ttu-id="b2ce8-137">Espandere la sezione **Informazioni sul contatto**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-137">Expand the **Contact information** section.</span></span>
2. <span data-ttu-id="b2ce8-138">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-138">Click **Add**.</span></span>
3. <span data-ttu-id="b2ce8-139">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b2ce8-139">In the **Description** field, type a value.</span></span>
4. <span data-ttu-id="b2ce8-140">Selezionare un'opzione nel campo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-140">In the **Type** field, select an option.</span></span>
5. <span data-ttu-id="b2ce8-141">Digitare un valore nel campo **Numero/indirizzo contatto**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-141">In the **Contact number/address** field, type a value.</span></span> <span data-ttu-id="b2ce8-142">È possibile selezionare la casella di controllo Primario se è il contatto principale.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-142">You can select the Primary check box if this is the primary contact.</span></span>  
6. <span data-ttu-id="b2ce8-143">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-143">Click **Save**.</span></span>
7. <span data-ttu-id="b2ce8-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-144">Close the page.</span></span>
8. <span data-ttu-id="b2ce8-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b2ce8-145">Close the page.</span></span>

