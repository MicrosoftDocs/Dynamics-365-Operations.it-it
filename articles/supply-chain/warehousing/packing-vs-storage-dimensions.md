---
title: Impostare dimensioni diverse per l'imballaggio e l'immagazzinamento
description: In questo argomento viene illustrato come specificare il processo (imballaggio, immagazzinamento o imballaggio nidificato) per cui viene utilizzata ciascuna dimensione specificata.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: aa5cbf807e809238489c539d3ad8c0bc34421774
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501296"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a><span data-ttu-id="df585-103">Impostare dimensioni diverse per l'imballaggio e l'immagazzinamento</span><span class="sxs-lookup"><span data-stu-id="df585-103">Set different dimensions for packing and storage</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="df585-104">Alcuni articoli sono imballati o sotccati in modo tale che potrebbe essere necessario tener traccia delle dimensioni fisiche in modo diverso per ciascuno dei diversi processi.</span><span class="sxs-lookup"><span data-stu-id="df585-104">Some items are packed or stored in such a way that you may need to track physical dimensions differently for each of several different processes.</span></span> <span data-ttu-id="df585-105">La funzionalità *Dimensioni prodotto di imballaggio* consente di configurare uno o più tipi di dimensioni per ogni prodotto.</span><span class="sxs-lookup"><span data-stu-id="df585-105">The *Packaging product dimensions* feature lets you set up one or several types of dimensions for each product.</span></span> <span data-ttu-id="df585-106">Ogni tipo di dimensione fornisce una serie di misure fisiche (peso, larghezza, profondità e altezza) e stabilisce il processo in cui si applicano tali valori di misura fisica.</span><span class="sxs-lookup"><span data-stu-id="df585-106">Each dimension type provides a set of physical measurements (weight, width, depth, and height), and establishes the process where those physical measurement values apply.</span></span> <span data-ttu-id="df585-107">Quando questa fnzionalità è abilitata, il sistema supporterà i seguenti tipi di dimensioni:</span><span class="sxs-lookup"><span data-stu-id="df585-107">When this feature is enabled, your system will support the following types of dimensions:</span></span>

- <span data-ttu-id="df585-108">*Immagazzinamento*: le dimensione di immagazzinamento vengono utilizzate insieme ai valori volumetrici di ubicazione per determinare il numero di articoli che possono essere immagazzinati in varie ubicazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="df585-108">*Storage* - Storage dimensions are used along with location volumetrics to determine how many of each item can be stored in various warehouse locations.</span></span>
- <span data-ttu-id="df585-109">*Imballaggio*: le dimensioni dell'imballaggio vengono utilizzate durante la containerizzazione e il processo di imballaggio manuale per determinare quanti di ciascun articolo si adatteranno ai vari tipi di contenitore.</span><span class="sxs-lookup"><span data-stu-id="df585-109">*Packing* - Packing dimensions are used during containerization and the manual packing process to determine how many of each item will fit in various container types.</span></span>
- <span data-ttu-id="df585-110">*Imballaggio annidato*: le dimensioni di imballaggio nidificate vengono utilizzate quando il processo di imballaggio contiene più livelli.</span><span class="sxs-lookup"><span data-stu-id="df585-110">*Nested packing* - Nested packing dimensions are used when the packing process contains multiple levels.</span></span>

<span data-ttu-id="df585-111">Le dimensioni *Immagazzinamento* sono supportate anche quando la funzionalità *Dimensioni prodotto di immagazzinamento* non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="df585-111">*Storage* dimensions are supported even when the *Packaging product dimensions* feature isn't enabled.</span></span> <span data-ttu-id="df585-112">Puoi configurarle utilizzando la pagina **Dimensione fisica** in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="df585-112">You set these up using the **Physical dimension** page in Supply Chain Management.</span></span> <span data-ttu-id="df585-113">Queste dimensioni vengono utilizzate da tutti i processi in cui le dimensioni di imballaggio e imballaggio nidificato non sono specificate.</span><span class="sxs-lookup"><span data-stu-id="df585-113">These dimensions are used by all processes where the packing and nested packing dimensions aren't specified.</span></span>

<span data-ttu-id="df585-114">Le dimensioni di *imballaggio* e *imballaggio annidato* vengono configurate utilizzando la pagina **Dimensioni fisiche del prodotto**, che viene aggiunta quando abiliti la funzionalità *Dimensioni prodotto di immagazzinamento*.</span><span class="sxs-lookup"><span data-stu-id="df585-114">*Packing* and *nested packing* dimensions are set up using the **Physical product dimensions** page, which is added when you enable the *Packaging product dimensions* feature.</span></span>
<span data-ttu-id="df585-115">Questo argomento fornisce uno scenario che illustra come utilizzare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="df585-115">This topic provides a scenario that illustrates how to use this feature.</span></span>

## <a name="turn-on-the-packaging-product-dimensions-feature"></a><span data-ttu-id="df585-116">Attivare la funzionalità delle dimensioni del prodotto di imballaggio</span><span class="sxs-lookup"><span data-stu-id="df585-116">Turn on the packaging product dimensions feature</span></span>

<span data-ttu-id="df585-117">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="df585-117">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="df585-118">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="df585-118">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="df585-119">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="df585-119">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="df585-120">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="df585-120">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="df585-121">**Nome funzionalità:** *Dimensioni prodotto di imballaggio*</span><span class="sxs-lookup"><span data-stu-id="df585-121">**Feature name:** *Packaging product dimensions*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="df585-122">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="df585-122">Example scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="df585-123">Impostare lo scenario</span><span class="sxs-lookup"><span data-stu-id="df585-123">Set up the scenario</span></span>

<span data-ttu-id="df585-124">Prima di poter eseguire lo scenario di esempio, è necessario preparare il sistema come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="df585-124">Before you can run the example scenario, you must prepare your system as described in this section.</span></span>

#### <a name="enable-demo-data"></a><span data-ttu-id="df585-125">Abilitare i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="df585-125">Enable demo data</span></span>

<span data-ttu-id="df585-126">Per elaborare lo scenario utilizzando i record e i valori demo specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard.</span><span class="sxs-lookup"><span data-stu-id="df585-126">To work through this scenario using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="df585-127">È inoltre necessario selezionare la persona giuridica *USMF* prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="df585-127">Additionally, you must select the *USMF* legal entity before you begin.</span></span>

#### <a name="add-a-new-physical-dimension-to-a-product"></a><span data-ttu-id="df585-128">Aggiungere una nuova dimensione fisica a un prodotto</span><span class="sxs-lookup"><span data-stu-id="df585-128">Add a new physical dimension to a product</span></span>

<span data-ttu-id="df585-129">Aggiungi una nuova dimensione fisica per un prodotto procedendo come segue:</span><span class="sxs-lookup"><span data-stu-id="df585-129">Add a new physical dimension for a product by doing the following:</span></span>

1. <span data-ttu-id="df585-130">Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="df585-130">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="df585-131">Seleziona il prodotto con **Numero articolo** *A0001*.</span><span class="sxs-lookup"><span data-stu-id="df585-131">Select the product with **Item number** *A0001*.</span></span>
1. <span data-ttu-id="df585-132">Nel riquadro azioni, aprire **Gestione articoli** e, dal gruppo **Magazzino**, selezionare **Dimensioni fisiche del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="df585-132">On the Action Pane, open the **Manage inventory** tab and, from the **Warehouse** group, select **Physical product dimensions**.</span></span>
1. <span data-ttu-id="df585-133">Si apre la pagina **Dimensioni fisiche del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="df585-133">The **Physical product dimensions** page opens.</span></span> <span data-ttu-id="df585-134">Nel riquadro azioni selezionare **Nuovo** per aggiungere una nuova dimensione alla griglia con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="df585-134">On the Action Pane, select **New** to add a new dimension to the grid with the following settings:</span></span>
    - <span data-ttu-id="df585-135">**Tipo di dimensione fisica** - *Imballaggio*</span><span class="sxs-lookup"><span data-stu-id="df585-135">**Physical dimension type** - *Packing*</span></span>
    - <span data-ttu-id="df585-136">**Unità fisica** - *pz*</span><span class="sxs-lookup"><span data-stu-id="df585-136">**Physical unit** - *pcs*</span></span>
    - <span data-ttu-id="df585-137">**Peso** - *4*</span><span class="sxs-lookup"><span data-stu-id="df585-137">**Weight** - *4*</span></span>
    - <span data-ttu-id="df585-138">**Unità peso** - *kg*</span><span class="sxs-lookup"><span data-stu-id="df585-138">**Weight unit** - *kg*</span></span>
    - <span data-ttu-id="df585-139">**Profondità** - *3*</span><span class="sxs-lookup"><span data-stu-id="df585-139">**Depth** - *3*</span></span>
    - <span data-ttu-id="df585-140">**Altezza** - *4*</span><span class="sxs-lookup"><span data-stu-id="df585-140">**Height** - *4*</span></span>
    - <span data-ttu-id="df585-141">**Larghezza** - *3*</span><span class="sxs-lookup"><span data-stu-id="df585-141">**Width** - *3*</span></span>
    - <span data-ttu-id="df585-142">**Lunghezza** - *cm*</span><span class="sxs-lookup"><span data-stu-id="df585-142">**Length** - *cm*</span></span>
    - <span data-ttu-id="df585-143">**Unità di volume** - *cm3*</span><span class="sxs-lookup"><span data-stu-id="df585-143">**Volume unit** - *cm3*</span></span>

<span data-ttu-id="df585-144">Il campo **Volume** viene calcolato automaticamente in base alle impostazioni **Profondità**, **Altezza** e **Larghezza**.</span><span class="sxs-lookup"><span data-stu-id="df585-144">The **Volume** field is automatically calculated based on your **Depth**, **Height**, and **Width** settings.</span></span>

#### <a name="create-a-new-container-type"></a><span data-ttu-id="df585-145">Creare un nuovo tipo di contenitore</span><span class="sxs-lookup"><span data-stu-id="df585-145">Create a new container type</span></span>

<span data-ttu-id="df585-146">Vai a **Gestione magazzino \> Imposta \> Contenitori \> Tipi di contenitori** e crea un nuovo record con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="df585-146">Go to **Warehouse management \> Setup \> Containers \> Container types** and create a new record with the following settings:</span></span>

- <span data-ttu-id="df585-147">**Codice tipo di contenitore** - *Scatola piccola*</span><span class="sxs-lookup"><span data-stu-id="df585-147">**Container type code** - *Short Box*</span></span>
- <span data-ttu-id="df585-148">**Descrizione** - *Scatola piccola*</span><span class="sxs-lookup"><span data-stu-id="df585-148">**Description** - *Short Box*</span></span>
- <span data-ttu-id="df585-149">**Peso netto massimo** - *50*</span><span class="sxs-lookup"><span data-stu-id="df585-149">**Maximum net weight** - *50*</span></span>
- <span data-ttu-id="df585-150">**Volume** - *144*</span><span class="sxs-lookup"><span data-stu-id="df585-150">**Volume** - *144*</span></span>
- <span data-ttu-id="df585-151">**Lunghezza** - *6*</span><span class="sxs-lookup"><span data-stu-id="df585-151">**Length** - *6*</span></span>
- <span data-ttu-id="df585-152">**Larghezza** - *6*</span><span class="sxs-lookup"><span data-stu-id="df585-152">**Width** - *6*</span></span>
- <span data-ttu-id="df585-153">**Altezza** - *4*</span><span class="sxs-lookup"><span data-stu-id="df585-153">**Height** - *4*</span></span>

#### <a name="create-a-container-group"></a><span data-ttu-id="df585-154">Creare un gruppo di contenitori</span><span class="sxs-lookup"><span data-stu-id="df585-154">Create a container group</span></span>

<span data-ttu-id="df585-155">Vai a **Gestione magazzino \> Imposta \> Contenitori \> Gruppi di contenitori** e crea un nuovo record con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="df585-155">Go to **Warehouse management \> Setup \> Containers \> Container groups** and create a new record with the following settings:</span></span>

- <span data-ttu-id="df585-156">**ID gruppo di contenitori** - *Scatola piccola*</span><span class="sxs-lookup"><span data-stu-id="df585-156">**Container group ID** - *Short Box*</span></span>
- <span data-ttu-id="df585-157">**Descrizione** - *Scatola piccola*</span><span class="sxs-lookup"><span data-stu-id="df585-157">**Description** - *Short Box*</span></span>

<span data-ttu-id="df585-158">Aggiungere una nuova riga alla sezione **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="df585-158">Add a new line to the **Details** section.</span></span> <span data-ttu-id="df585-159">Impostare **Tipo di contenitore** su *Scatola piccola*.</span><span class="sxs-lookup"><span data-stu-id="df585-159">Set the **Container type** to *Short Box*.</span></span>

#### <a name="set-up-a-container-build-template"></a><span data-ttu-id="df585-160">Impostare un modello di versione del contenitore</span><span class="sxs-lookup"><span data-stu-id="df585-160">Set up a container build template</span></span>

<span data-ttu-id="df585-161">Andare a **Gestione magazzino \> Imposta \> Contenitori \> Modelli di build contenitore** se selezionare **Scatole**.</span><span class="sxs-lookup"><span data-stu-id="df585-161">Go to **Warehouse management \> Setup \> Containers \> Container build templates** and select **Boxes**.</span></span> <span data-ttu-id="df585-162">Modificare **ID gruppo di contenitori** su *Scatola piccola*.</span><span class="sxs-lookup"><span data-stu-id="df585-162">Change the **Container group ID** to *Short Box*.</span></span>

### <a name="run-the-scenario"></a><span data-ttu-id="df585-163">Eseguire lo scenario</span><span class="sxs-lookup"><span data-stu-id="df585-163">Run the scenario</span></span>

<span data-ttu-id="df585-164">Dopo aver preparato il sistema come descritto nella sezione precedente, sei pronto per eseguire lo scenario come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="df585-164">After you have prepared your system as described in the previous section, you are ready to run the scenario as described in the next section.</span></span>

#### <a name="create-a-sales-order-and-create-a-shipment"></a><span data-ttu-id="df585-165">Creare un ordine cliente e una spedizione</span><span class="sxs-lookup"><span data-stu-id="df585-165">Create a sales order and create a shipment</span></span>

<span data-ttu-id="df585-166">In questo processo creerai una spedizione basata sulle dimensioni di *imballaggio* dell'articolo, per le quali l'altezza è inferiore a 3.</span><span class="sxs-lookup"><span data-stu-id="df585-166">In this process you will create a shipment based on the item *packing* dimensions, for which the height is less than 3.</span></span>

1. <span data-ttu-id="df585-167">Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="df585-167">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="df585-168">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="df585-168">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="df585-169">Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="df585-169">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="df585-170">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="df585-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="df585-171">**Magazzino:** *63*</span><span class="sxs-lookup"><span data-stu-id="df585-171">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="df585-172">Scegli **OK** per creare l'ordine cliente e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="df585-172">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="df585-173">Viene aperto il nuovo ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="df585-173">The new sales order is opened.</span></span> <span data-ttu-id="df585-174">Dovrebbe includere una nuova riga vuota nella griglia della Scheda dettaglio **Righe ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="df585-174">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="df585-175">Su questa riga, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="df585-175">On this line, set the following values:</span></span>

    - <span data-ttu-id="df585-176">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="df585-176">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="df585-177">**Quantità:** *5*</span><span class="sxs-lookup"><span data-stu-id="df585-177">**Quantity:** *5*</span></span>

1. <span data-ttu-id="df585-178">Nella scheda dettaglio **Righe ordine cliente**, selezionare **Scorte \> Prenotazione**.</span><span class="sxs-lookup"><span data-stu-id="df585-178">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="df585-179">Nella pagina **Prenotazione**, quindi nel riquadro azioni, selezionare **Prenota lotto** per prenotare le scorte.</span><span class="sxs-lookup"><span data-stu-id="df585-179">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="df585-180">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="df585-180">Close the page.</span></span>
1. <span data-ttu-id="df585-181">Nel riquadro azioni, aprire la scheda **Magazzino** e selezionare **Rilascia in magazzino** per creare lavoro per il magazzino.</span><span class="sxs-lookup"><span data-stu-id="df585-181">On the Action Pane, open the **Warehouse** tab and select **Release to warehouse** to create work for the warehouse.</span></span>
1. <span data-ttu-id="df585-182">Nella Scheda dettaglio **Righe ordine cliente**, selezionare **Magazzino \> Dettagli spedizione**.</span><span class="sxs-lookup"><span data-stu-id="df585-182">On the **Sales order lines** FastTab, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="df585-183">Nel riquadro azioni, aprire la scheda **Trasporto** e selezionare **Visualizza contenitori**.</span><span class="sxs-lookup"><span data-stu-id="df585-183">On the Action Pane, open the **Transportation** tab and select **View containers**.</span></span> <span data-ttu-id="df585-184">Confermare che l'articolo è stato containerizzato nei due contenitori *Scatola piccola*.</span><span class="sxs-lookup"><span data-stu-id="df585-184">Confirm that the item was containerized into the two *Short Box* containers.</span></span>

#### <a name="place-an-item-into-storage"></a><span data-ttu-id="df585-185">Posizionare un articolo in magazzino</span><span class="sxs-lookup"><span data-stu-id="df585-185">Place an item into storage</span></span>

1. <span data-ttu-id="df585-186">Aprire il dispositivo mobile, accedere al magazzino 63 e passare a **Inventario \> Rettifica in entrata**.</span><span class="sxs-lookup"><span data-stu-id="df585-186">Open the mobile device, sign in to warehouse 63 and go to **Inventory \> Adjust In**.</span></span>
1. <span data-ttu-id="df585-187">Immettere **Ubicazione** = *SHORT-01*.</span><span class="sxs-lookup"><span data-stu-id="df585-187">Enter **Loc** = *SHORT-01*.</span></span> <span data-ttu-id="df585-188">Creare una nuova targa con **Articolo** = *A0001* e **Quantità** = *1 pz*.</span><span class="sxs-lookup"><span data-stu-id="df585-188">Make a new license plate with **Item** = *A0001* and **Quantity** = *1 pcs*.</span></span>
1. <span data-ttu-id="df585-189">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="df585-189">Select **OK**.</span></span> <span data-ttu-id="df585-190">Riceverai l'errore "Ubicazione SHORT-01 non riuscita perché l'articolo A0001 non si adatta alle dimensioni specificate dell'ubicazione."</span><span class="sxs-lookup"><span data-stu-id="df585-190">You will receive the error "Location SHORT-01 failed because item A0001 does not fit in location's specified dimensions."</span></span> <span data-ttu-id="df585-191">Questo perché le dimensioni del tipo di *Immagazzinamento* del prodotto sono maggiori delle dimensioni specificate nel profilo di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="df585-191">This is because the *Storage* type dimensions of the product are larger than the dimensions specified on the location profile.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]