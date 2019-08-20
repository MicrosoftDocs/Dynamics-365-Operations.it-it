---
title: Modificare la proprietà dell'inventario spedizione in base alla domanda di produzione
description: In questa procedura viene illustrato come modificare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica quando c'è domanda di inventario nella produzione.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9587d39801ad39649aa5fa3ff682cdeab411516e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838801"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="91687-103">Modificare la proprietà dell'inventario spedizione in base alla domanda di produzione</span><span class="sxs-lookup"><span data-stu-id="91687-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91687-104">In questa procedura viene illustrato come modificare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica quando c'è domanda di inventario nella produzione.</span><span class="sxs-lookup"><span data-stu-id="91687-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="91687-105">Questo cambio di proprietà viene eseguito creando e registrando un giornale di registrazione modifiche proprietà inventario.</span><span class="sxs-lookup"><span data-stu-id="91687-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="91687-106">Le righe del giornale di registrazione modifiche proprietà possono essere create manualmente oppure, come illustrato nella registrazione corrente, in base alla domanda di produzione esistente.</span><span class="sxs-lookup"><span data-stu-id="91687-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="91687-107">In genere, un supervisore dello shop floor esegue questa attività.</span><span class="sxs-lookup"><span data-stu-id="91687-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="91687-108">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure sui propri dati.</span><span class="sxs-lookup"><span data-stu-id="91687-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="91687-109">Se si utilizzano i propri dati, verificare che siano presenti i seguenti prerequisiti: un nome di giornale di registrazione inventario impostato per la modifica di proprietà di inventario, gli articoli registrati di proprietà del fornitore fisicamente disponibili e una o più righe di ordine di produzione per il materiale.</span><span class="sxs-lookup"><span data-stu-id="91687-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="91687-110">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="91687-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="91687-111">Creare un giornale di registrazione proprietà inventario</span><span class="sxs-lookup"><span data-stu-id="91687-111">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="91687-112">Passare a Gestione inventario > Inserimenti nel giornale di registrazione > Articoli > Modifica proprietà inventario.</span><span class="sxs-lookup"><span data-stu-id="91687-112">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="91687-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="91687-113">Click New.</span></span>
    * <span data-ttu-id="91687-114">Il giornale di registrazione modifiche proprietà inventario viene utilizzato per cambiare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica corrente.</span><span class="sxs-lookup"><span data-stu-id="91687-114">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="91687-115">Questo cambio di proprietà viene effettuato mediante il rilascio delle scorte disponibili di proprietà del fornitore e la ricezione di inventario nella persona giuridica corrente.</span><span class="sxs-lookup"><span data-stu-id="91687-115">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="91687-116">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="91687-116">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="91687-117">È possibile selezionare soltanto i nomi di giornale di registrazione inventario con un tipo di giornale di registrazione Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="91687-117">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="91687-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="91687-118">Click OK.</span></span>
5. <span data-ttu-id="91687-119">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="91687-119">Click Functions.</span></span>
6. <span data-ttu-id="91687-120">Fare clic su Creare righe del giornale di registrazione dagli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="91687-120">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="91687-121">È possibile avviare il processo di cambio di proprietà eseguendo una query su tutte le righe di produzione con domanda di consumo di materie prime.</span><span class="sxs-lookup"><span data-stu-id="91687-121">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="91687-122">Nel campo Stati uscita inventario da includere, selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="91687-122">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="91687-123">Questa opzione consente di filtrare in base allo stato dell'uscita delle transazioni di inventario.</span><span class="sxs-lookup"><span data-stu-id="91687-123">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="91687-124">Ad esempio, è possibile creare righe del giornale di registrazione per l'inventario con gli stati Prelevato e Fisico prenotato.</span><span class="sxs-lookup"><span data-stu-id="91687-124">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="91687-125">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="91687-125">Expand the Records to include section.</span></span>
    * <span data-ttu-id="91687-126">Questa sezione consente di applicare filtri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="91687-126">This section lets you apply additional filtering.</span></span> <span data-ttu-id="91687-127">Ad esempio, è possibile selezionare una data specifica per le materie prime.</span><span class="sxs-lookup"><span data-stu-id="91687-127">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="91687-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="91687-128">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="91687-129">Registrare il giornale di registrazione modifiche proprietà inventario</span><span class="sxs-lookup"><span data-stu-id="91687-129">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="91687-130">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="91687-130">Click Post.</span></span>
    * <span data-ttu-id="91687-131">Quando il giornale viene registrato, l'inventario di proprietà del fornitore viene rilasciato mediante un riferimento "Modifica proprietà".</span><span class="sxs-lookup"><span data-stu-id="91687-131">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="91687-132">L'inventario verrà ricevuto come scorte disponibili utilizzando una transazione di inventario che viene aggiornata con un'entrata prodotti ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="91687-132">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="91687-133">Tenere presente che solo le transazioni relative al giornale registrato vengono create.</span><span class="sxs-lookup"><span data-stu-id="91687-133">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="91687-134">Non vengono create transazioni di inventario previste.</span><span class="sxs-lookup"><span data-stu-id="91687-134">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="91687-135">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="91687-135">Click OK.</span></span>
3. <span data-ttu-id="91687-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="91687-136">Close the page.</span></span>

