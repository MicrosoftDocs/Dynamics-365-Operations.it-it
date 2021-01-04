---
title: Creare un contratto di acquisto
description: In questo argomento viene descritta la creazione di un contratto di acquisto
author: mkirknel
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1edfd4e56910376d0596eec5eff2af888f7dc98d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431091"
---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="eba0e-103">Creare un contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="eba0e-103">Create a purchase agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eba0e-104">In questo argomento viene descritta la creazione di un contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="eba0e-104">This topic guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="eba0e-105">e viene in genere effettuata da un responsabile acquisti.</span><span class="sxs-lookup"><span data-stu-id="eba0e-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="eba0e-106">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="eba0e-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="eba0e-107">È necessario impostare le classificazioni del contratto di acquisto prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="eba0e-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="eba0e-108">Una volta creato un contratto, è possibile utilizzarlo quando si crea un ordine fornitore. In questo modo le condizioni del contratto di acquisto verranno copiate nell'intestazione e in tutte le righe nell'ordine in cui sono interessate dal contratto.</span><span class="sxs-lookup"><span data-stu-id="eba0e-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="eba0e-109">Creare un nuovo contratto di acquisto</span><span class="sxs-lookup"><span data-stu-id="eba0e-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="eba0e-110">Andare a **Pannello di navigazione > Moduli > Approvvigionamento > Contratti di acquisto > Contratti di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-110">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase agreements > Purchase agreements**.</span></span>
2. <span data-ttu-id="eba0e-111">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-111">Click **New**.</span></span>
3. <span data-ttu-id="eba0e-112">Nel campo **Conto fornitore**, selezionare il menu a discesa e selezionare la riga del record desiderato.</span><span class="sxs-lookup"><span data-stu-id="eba0e-112">In the **Vendor account** field, select the drop-down menu and select the row of the desired record.</span></span>
4. <span data-ttu-id="eba0e-113">Nel campo **Classificazione contratto di acquisto**, selezionare il menu a discesa e selezionare la riga del record desiderato.</span><span class="sxs-lookup"><span data-stu-id="eba0e-113">In the **Purchase agreement classification** field, select the drop-down menu and select the row of the desired record.</span></span>
5. <span data-ttu-id="eba0e-114">Espandere la Scheda dettaglio **Generale**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-114">Expand the **General** FastTab.</span></span>
6. <span data-ttu-id="eba0e-115">Nel campo **Data di scadenza** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="eba0e-115">In the **Expiration date** field, enter a date.</span></span>

    - <span data-ttu-id="eba0e-116">La data di scadenza verrà impostata per tutti le righe di impegno e determinerà il periodo di validità di ogni impegno specifico.</span><span class="sxs-lookup"><span data-stu-id="eba0e-116">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  

7. <span data-ttu-id="eba0e-117">Nel campo **Titolo documento** digitare un nome per il contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="eba0e-117">In the **Document title** field, type a name for your purchase agreement.</span></span>

    - <span data-ttu-id="eba0e-118">Lasciare il campo **Impegno predefinito** impostato su **Impegno quantità prodotto** o modificarlo se non è impostato su tale valore.</span><span class="sxs-lookup"><span data-stu-id="eba0e-118">Leave the **Default commitment** field set to **Product quantity commitment** (or change it if it's not set to this).</span></span>  
    - <span data-ttu-id="eba0e-119">Il valore di impegno predefinito determina le opzioni nelle righe del contratto.</span><span class="sxs-lookup"><span data-stu-id="eba0e-119">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="eba0e-120">Se è necessarie un nuovo tipo di impegno durante la creazione delle righe del contratto, è necessario modificare l'impegno predefinito nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="eba0e-120">If you need a new commitment type when you're creating the agreement lines, you need to change the default commitment on the header.</span></span> <span data-ttu-id="eba0e-121">Sono presenti i 4 tipi di impegni seguenti. **Impegno quantità prodotto** - per una specifica quantità di prodotto, **Impegno valore prodotto** - per un importo in valuta specifico del prodotto, **Impegno valore categoria prodotto** - per un importo in valuta specifico in una categoria di approvvigionamento in cui l'importo può essere correlato a un articolo del catalogo oppure a un articolo fuori catalogo, **Impegno valore** - per un importo in valuta specifico che può essere soddisfatto da qualsiasi prodotto o da qualsiasi categoria di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="eba0e-121">There are 4 types of commitments: **Product quantity commitment** - for a specific quantity of a product; **Product value commitment** - for a specific currency amount of a product; **Product category value commitment** - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; **Value commitment** - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  

8. <span data-ttu-id="eba0e-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-122">Select **OK**.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="eba0e-123">Aggiungere un impegno</span><span class="sxs-lookup"><span data-stu-id="eba0e-123">Add a commitment</span></span>
1. <span data-ttu-id="eba0e-124">Selezionare **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-124">Select **Add line**.</span></span>
2. <span data-ttu-id="eba0e-125">Nel campo **Numero articolo** fare clic sul record desiderato del menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="eba0e-125">In the **Item number** field, select the desired record from the drop-down menu.</span></span>
3. <span data-ttu-id="eba0e-126">Nel campo **Quantità** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="eba0e-126">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="eba0e-127">Si tratta della quantità totale accettata per l'acquisto dal fornitore.</span><span class="sxs-lookup"><span data-stu-id="eba0e-127">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
4. <span data-ttu-id="eba0e-128">Immettere un numero nel campo **Prezzo unitario**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-128">In the **Unit price** field, enter a number.</span></span>
5. <span data-ttu-id="eba0e-129">Espandere la sezione **Dettagli riga**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-129">Expand the **Line details** section.</span></span>
6. <span data-ttu-id="eba0e-130">Impostare l'opzione **Valore massimo applicato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-130">Set the **Max is enforced** option to **Yes**.</span></span> <span data-ttu-id="eba0e-131">L'opzione **Valore massimo applicato** limita l'utilizzo dell'impegno.</span><span class="sxs-lookup"><span data-stu-id="eba0e-131">The **Max is enforced** option limits the use of the commitment.</span></span> <span data-ttu-id="eba0e-132">È possibile acquistare una quantità pari al massimo al valore specificato nel campo **Quantità** per la riga.</span><span class="sxs-lookup"><span data-stu-id="eba0e-132">You can only purchase up to the quantity that's specified in the **Quantity** field for the line.</span></span>  

## <a name="add-header-conditions"></a><span data-ttu-id="eba0e-133">Aggiungere condizioni di intestazione</span><span class="sxs-lookup"><span data-stu-id="eba0e-133">Add header conditions</span></span>
1. <span data-ttu-id="eba0e-134">Nel riquadro azioni selezionare **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-134">On the Action Pane, select **Options**.</span></span>
2. <span data-ttu-id="eba0e-135">Selezionare **Cambia visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-135">Select **Change view**.</span></span>
3. <span data-ttu-id="eba0e-136">Selezionare **Visualizzazione intestazione**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-136">Select **Header view**.</span></span>
4. <span data-ttu-id="eba0e-137">Espandere la sezione **Termini**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-137">Expand the **Terms** section.</span></span>
5. <span data-ttu-id="eba0e-138">Nel campo **Metodo di pagamento** fare clic sul record desiderato del menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="eba0e-138">In the **Method of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="eba0e-139">I termini di pagamento del conto fornitore vengono visualizzati in questo punto per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="eba0e-139">The payment terms from the vendor account are shown here by default.</span></span>  
6. <span data-ttu-id="eba0e-140">Nel campo **Modalità di consegna** fare clic sul record desiderato del menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="eba0e-140">In the **Mode of delivery** field, select the desired record in the drop-down menu.</span></span>
7. <span data-ttu-id="eba0e-141">Nel campo **Termini di consegna** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="eba0e-141">In the **Delivery terms** field, select the drop-down button to open the lookup.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="eba0e-142">Confermare e attivare il contratto</span><span class="sxs-lookup"><span data-stu-id="eba0e-142">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="eba0e-143">Nel riquadro azioni fare clic su **Contratto di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-143">On the Action Pane, select **Purchase agreement**.</span></span>
2. <span data-ttu-id="eba0e-144">Selezionare **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-144">Select **Confirmation**.</span></span> <span data-ttu-id="eba0e-145">Impostare l'opzione **Contrassegna contratto come valido** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-145">Set the **Mark agreement as effective** option to **Yes**.</span></span>  
3. <span data-ttu-id="eba0e-146">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-146">Select **OK**.</span></span>
4. <span data-ttu-id="eba0e-147">Nel riquadro azioni fare clic su **Contratto di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-147">On the Action Pane, select **Purchase agreement**.</span></span>
5. <span data-ttu-id="eba0e-148">Selezionare **Conferme contratto di acquisto**.</span><span class="sxs-lookup"><span data-stu-id="eba0e-148">Select **Purchase agreement confirmations**.</span></span> <span data-ttu-id="eba0e-149">L'opzione **Anteprima/Stampa** consente di generare un documento per il contratto di acquisto che successivamente è possibile stampare o inviare al fornitore.</span><span class="sxs-lookup"><span data-stu-id="eba0e-149">The **Preview/Print** option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="eba0e-150">Se in seguito si aggiorna il contratto e lo si riconferma, entrambe le versioni verranno visualizzate in questo punto.</span><span class="sxs-lookup"><span data-stu-id="eba0e-150">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="eba0e-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="eba0e-151">Close the page.</span></span>

