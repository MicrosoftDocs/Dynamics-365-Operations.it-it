---
title: Creare il canale online e definire gli attributi del canale
description: In questa procedura vengono descritti i passaggi per creare un nuovo canale online e aggiungerlo alla gerarchia organizzativa.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4547731d7e3bc56b1ba5e0a35ff4746c6c0e9863
ms.sourcegitcommit: 901ec3b360303bb8b4d9a9dcfecc6d75d7f844a0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "1618298"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="f955e-103">Creare il canale online e definire gli attributi del canale</span><span class="sxs-lookup"><span data-stu-id="f955e-103">Create online channel and define channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f955e-104">In questa procedura vengono descritti i passaggi per creare un nuovo canale online e aggiungerlo alla gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="f955e-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="f955e-105">Prima di creare un nuovo canale online è necessario creare la gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="f955e-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="f955e-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="f955e-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="f955e-107">Creare un nuovo canale online</span><span class="sxs-lookup"><span data-stu-id="f955e-107">Create a new online channel</span></span>
1. <span data-ttu-id="f955e-108">Passare a Vendita al dettaglio e commercio > Canali > Punti vendita online.</span><span class="sxs-lookup"><span data-stu-id="f955e-108">Go to Retail and commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="f955e-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f955e-109">Click New.</span></span>
3. <span data-ttu-id="f955e-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f955e-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="f955e-111">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f955e-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="f955e-112">Selezionare un'opzione nel campo Fuso orario punto vendita.</span><span class="sxs-lookup"><span data-stu-id="f955e-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="f955e-113">Nel campo Cliente predefinito, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f955e-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="f955e-114">Nel campo Rubrica clienti, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f955e-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="f955e-115">Nel campo Termini di pagamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f955e-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="f955e-116">Nel campo Metodo di pagamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f955e-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="f955e-117">Nel campo Profilo di notifica tramite posta elettronica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f955e-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="f955e-118">Espandere la sezione Dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="f955e-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="f955e-119">Nel campo Business Unit immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f955e-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="f955e-120">In modo analogo, impostare il valore per tutte le altre dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="f955e-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="f955e-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f955e-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="f955e-122">Aggiungere il canale online alla gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="f955e-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="f955e-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f955e-123">Close the page.</span></span>
2. <span data-ttu-id="f955e-124">Andare ad Amministrazione organizzazione > Organizzazioni > Gerarchie organizzative.</span><span class="sxs-lookup"><span data-stu-id="f955e-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="f955e-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f955e-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f955e-126">Fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="f955e-126">Click View.</span></span>
5. <span data-ttu-id="f955e-127">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="f955e-127">Click Edit.</span></span>
    * <span data-ttu-id="f955e-128">È possibile selezionare qualsiasi nodo di gerarchia in cui si desidera inserire il nuovo canale.</span><span class="sxs-lookup"><span data-stu-id="f955e-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="f955e-129">Fare clic su Inserisci.</span><span class="sxs-lookup"><span data-stu-id="f955e-129">Click Insert.</span></span>
7. <span data-ttu-id="f955e-130">Fare clic su Canale di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f955e-130">Click Retail channel.</span></span>
8. <span data-ttu-id="f955e-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f955e-131">Click OK.</span></span>
9. <span data-ttu-id="f955e-132">Fare clic su Pubblica per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f955e-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="f955e-133">Nel campo Data di validità immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="f955e-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="f955e-134">Fare clic su Pubblica.</span><span class="sxs-lookup"><span data-stu-id="f955e-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-realtime-notification"></a><span data-ttu-id="f955e-135">Configurare ordini per la notifica quasi in tempo reale</span><span class="sxs-lookup"><span data-stu-id="f955e-135">Configure orders for near realtime notification</span></span>
1. <span data-ttu-id="f955e-136">Accedere a Vendita al dettaglio > Impostazione sedi centrali > Parametri > Parametri di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="f955e-136">Go to Retail  > Headquarters setup > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="f955e-137">Impostare Utilizza servizio in tempo reale per creazione di ordini di e-commerce su "Sì".</span><span class="sxs-lookup"><span data-stu-id="f955e-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="f955e-138">Eseguire la programmazione di distribuzione 1070 per sincronizzare le modifiche nel database del canale.</span><span class="sxs-lookup"><span data-stu-id="f955e-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 


