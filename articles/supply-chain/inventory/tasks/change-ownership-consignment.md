---
title: Modificare la proprietà dell'inventario spedizione in base alla domanda di produzione
description: In questa procedura viene illustrato come modificare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica quando c'è domanda di inventario nella produzione.
author: perlynne
manager: tfehr
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a4130670d2291fef16c9ff5482995a709b03cd3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000186"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="63d40-103">Modificare la proprietà dell'inventario spedizione in base alla domanda di produzione</span><span class="sxs-lookup"><span data-stu-id="63d40-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="63d40-104">In questa procedura viene illustrato come modificare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica quando c'è domanda di inventario nella produzione.</span><span class="sxs-lookup"><span data-stu-id="63d40-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="63d40-105">Questo cambio di proprietà viene eseguito creando e registrando un giornale di registrazione modifiche proprietà inventario.</span><span class="sxs-lookup"><span data-stu-id="63d40-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="63d40-106">Le righe del giornale di registrazione modifiche proprietà possono essere create manualmente oppure, come illustrato nella registrazione corrente, in base alla domanda di produzione esistente.</span><span class="sxs-lookup"><span data-stu-id="63d40-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="63d40-107">In genere, un supervisore dello shop floor esegue questa attività.</span><span class="sxs-lookup"><span data-stu-id="63d40-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="63d40-108">È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure sui propri dati.</span><span class="sxs-lookup"><span data-stu-id="63d40-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="63d40-109">Se si utilizzano i propri dati, verificare che siano presenti i seguenti prerequisiti: un nome di giornale di registrazione inventario impostato per la modifica di proprietà di inventario, gli articoli registrati di proprietà del fornitore fisicamente disponibili e una o più righe di ordine di produzione per il materiale.</span><span class="sxs-lookup"><span data-stu-id="63d40-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="63d40-110">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="63d40-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

> [!NOTE]
> <span data-ttu-id="63d40-111">I processi di spedizione in uscita non sono predefiniti e il giornale di registrazione proprietà automatico non è supportato.</span><span class="sxs-lookup"><span data-stu-id="63d40-111">Outbound consignment processes are not supported out-of-the-box and automatic ownership journal processing is not supported.</span></span>

## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="63d40-112">Creare un giornale di registrazione proprietà inventario</span><span class="sxs-lookup"><span data-stu-id="63d40-112">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="63d40-113">Passare a Gestione inventario > Inserimenti nel giornale di registrazione > Articoli > Modifica proprietà inventario.</span><span class="sxs-lookup"><span data-stu-id="63d40-113">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="63d40-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="63d40-114">Click New.</span></span>
    * <span data-ttu-id="63d40-115">Il giornale di registrazione modifiche proprietà inventario viene utilizzato per cambiare il proprietario dell'inventario di spedizione dal fornitore alla persona giuridica corrente.</span><span class="sxs-lookup"><span data-stu-id="63d40-115">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="63d40-116">Questo cambio di proprietà viene effettuato mediante il rilascio delle scorte disponibili di proprietà del fornitore e la ricezione di inventario nella persona giuridica corrente.</span><span class="sxs-lookup"><span data-stu-id="63d40-116">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="63d40-117">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="63d40-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="63d40-118">È possibile selezionare soltanto i nomi di giornale di registrazione inventario con un tipo di giornale di registrazione Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="63d40-118">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="63d40-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="63d40-119">Click OK.</span></span>
5. <span data-ttu-id="63d40-120">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="63d40-120">Click Functions.</span></span>
6. <span data-ttu-id="63d40-121">Fare clic su Creare righe del giornale di registrazione dagli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="63d40-121">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="63d40-122">È possibile avviare il processo di cambio di proprietà eseguendo una query su tutte le righe di produzione con domanda di consumo di materie prime.</span><span class="sxs-lookup"><span data-stu-id="63d40-122">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="63d40-123">Nel campo Stati uscita inventario da includere, selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="63d40-123">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="63d40-124">Questa opzione consente di filtrare in base allo stato dell'uscita delle transazioni di inventario.</span><span class="sxs-lookup"><span data-stu-id="63d40-124">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="63d40-125">Ad esempio, è possibile creare righe del giornale di registrazione per l'inventario con gli stati Prelevato e Fisico prenotato.</span><span class="sxs-lookup"><span data-stu-id="63d40-125">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="63d40-126">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="63d40-126">Expand the Records to include section.</span></span>
    * <span data-ttu-id="63d40-127">Questa sezione consente di applicare filtri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="63d40-127">This section lets you apply additional filtering.</span></span> <span data-ttu-id="63d40-128">Ad esempio, è possibile selezionare una data specifica per le materie prime.</span><span class="sxs-lookup"><span data-stu-id="63d40-128">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="63d40-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="63d40-129">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="63d40-130">Registrare il giornale di registrazione modifiche proprietà inventario</span><span class="sxs-lookup"><span data-stu-id="63d40-130">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="63d40-131">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="63d40-131">Click Post.</span></span>
    * <span data-ttu-id="63d40-132">Quando il giornale viene registrato, l'inventario di proprietà del fornitore viene rilasciato mediante un riferimento "Modifica proprietà".</span><span class="sxs-lookup"><span data-stu-id="63d40-132">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="63d40-133">L'inventario verrà ricevuto come scorte disponibili utilizzando una transazione di inventario che viene aggiornata con un'entrata prodotti ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="63d40-133">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="63d40-134">Tenere presente che solo le transazioni relative al giornale registrato vengono create.</span><span class="sxs-lookup"><span data-stu-id="63d40-134">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="63d40-135">Non vengono create transazioni di inventario previste.</span><span class="sxs-lookup"><span data-stu-id="63d40-135">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="63d40-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="63d40-136">Click OK.</span></span>
3. <span data-ttu-id="63d40-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="63d40-137">Close the page.</span></span>

