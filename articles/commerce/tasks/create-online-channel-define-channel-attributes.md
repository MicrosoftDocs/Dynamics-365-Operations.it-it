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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f85a74e44be28452f5d892f1875d74261f9dbe3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215438"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="7c0ec-103">Creare il canale online e definire gli attributi del canale</span><span class="sxs-lookup"><span data-stu-id="7c0ec-103">Create online channel and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c0ec-104">In questa procedura vengono descritti i passaggi per creare un nuovo canale online e aggiungerlo alla gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="7c0ec-105">Prima di creare un nuovo canale online è necessario creare la gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="7c0ec-106">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="7c0ec-107">Creare un nuovo canale online</span><span class="sxs-lookup"><span data-stu-id="7c0ec-107">Create a new online channel</span></span>
1. <span data-ttu-id="7c0ec-108">Passare a Retail e Commerce > Canali > Punti vendita online.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-108">Go to Retail and Commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="7c0ec-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-109">Click New.</span></span>
3. <span data-ttu-id="7c0ec-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7c0ec-111">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="7c0ec-112">Selezionare un'opzione nel campo Fuso orario punto vendita.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="7c0ec-113">Nel campo Cliente predefinito, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="7c0ec-114">Nel campo Rubrica clienti, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="7c0ec-115">Nel campo Termini di pagamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="7c0ec-116">Nel campo Metodo di pagamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="7c0ec-117">Nel campo Profilo di notifica tramite posta elettronica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="7c0ec-118">Espandere la sezione Dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="7c0ec-119">Nel campo Business Unit immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="7c0ec-120">In modo analogo, impostare il valore per tutte le altre dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="7c0ec-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="7c0ec-122">Aggiungere il canale online alla gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="7c0ec-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="7c0ec-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-123">Close the page.</span></span>
2. <span data-ttu-id="7c0ec-124">Andare ad Amministrazione organizzazione > Organizzazioni > Gerarchie organizzative.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="7c0ec-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="7c0ec-126">Fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-126">Click View.</span></span>
5. <span data-ttu-id="7c0ec-127">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-127">Click Edit.</span></span>
    * <span data-ttu-id="7c0ec-128">È possibile selezionare qualsiasi nodo di gerarchia in cui si desidera inserire il nuovo canale.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="7c0ec-129">Fare clic su Inserisci.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-129">Click Insert.</span></span>
7. <span data-ttu-id="7c0ec-130">Fai clic sul canale di Commerce.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-130">Click Commerce channel.</span></span>
8. <span data-ttu-id="7c0ec-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-131">Click OK.</span></span>
9. <span data-ttu-id="7c0ec-132">Fare clic su Pubblica per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="7c0ec-133">Nel campo Data di validità immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="7c0ec-134">Fare clic su Pubblica.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-real-time-notification"></a><span data-ttu-id="7c0ec-135">Configurare ordini per la notifica quasi in tempo reale</span><span class="sxs-lookup"><span data-stu-id="7c0ec-135">Configure orders for near real-time notification</span></span>
1. <span data-ttu-id="7c0ec-136">Andare a Retail e Commerce > Impostazione sedi centrali > Parametri > Parametri di commercio.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-136">Go to Retail and Commerce  > Headquarters setup > Parameters > Commerce parameters.</span></span>
2. <span data-ttu-id="7c0ec-137">Impostare Utilizza servizio in tempo reale per creazione di ordini di e-commerce su "Sì".</span><span class="sxs-lookup"><span data-stu-id="7c0ec-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="7c0ec-138">Eseguire la programmazione di distribuzione 1070 per sincronizzare le modifiche nel database del canale.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]