---
title: Configurazioni richiesta fornitore
description: In questo argomento vengono descritti i campi obbligatori in una richiesta nuovo fornitore.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d238e0dbb754e88dcffa171456aa0a2336238cab
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="vendor-request-configurations"></a><span data-ttu-id="9dd45-103">Configurazioni richiesta fornitore</span><span class="sxs-lookup"><span data-stu-id="9dd45-103">Vendor request configurations</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="9dd45-104">Per completare una richiesta fornitore, un contatto del fornitore deve completare la procedura guidata di registrazione del fornitore potenziale.</span><span class="sxs-lookup"><span data-stu-id="9dd45-104">To complete a vendor request, a vendor contact person must complete the prospective vendor registration wizard.</span></span>

<span data-ttu-id="9dd45-105">Nel modulo **Configurazioni richiesta fornitore**, è possibile creare profili che specificano i campi obbligatori e i campi visibili nella procedura guidata di registrazione del fornitore potenziale.</span><span class="sxs-lookup"><span data-stu-id="9dd45-105">In the **Vendor request configurations** form, you can create profiles that specify required fields and visible fields in the prospective vendor registration wizard.</span></span>

<span data-ttu-id="9dd45-106">La procedura guidata per la registrazione del fornitore inizierà chiedendo al fornitore potenziale in quale paese opera il fornitore.</span><span class="sxs-lookup"><span data-stu-id="9dd45-106">The vendor registration wizard will start out by asking the prospective vendor user which country/region the vendor is doing business in.</span></span> <span data-ttu-id="9dd45-107">Queste informazioni consentono di determinare la configurazione applicabile.</span><span class="sxs-lookup"><span data-stu-id="9dd45-107">This information determines the applicable configuration.</span></span> <span data-ttu-id="9dd45-108">Se nessuna specifica configurazione è definita per un paese, verrà utilizzata una configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9dd45-108">If no specific configuration is defined for a country/region, a default configuration will be used.</span></span>

### <a name="set-up-a-vendor-request-configuration"></a><span data-ttu-id="9dd45-109">Impostare una configurazione delle richieste fornitore</span><span class="sxs-lookup"><span data-stu-id="9dd45-109">Set up a vendor request configuration</span></span>

<span data-ttu-id="9dd45-110">Per impostazione predefinita, è disponibile una configurazione fornitore nel modulo di configurazione delle richieste del fornitore.</span><span class="sxs-lookup"><span data-stu-id="9dd45-110">By default, there is a vendor configuration available in the Vendor request configurations form.</span></span>

<span data-ttu-id="9dd45-111">Non è possibile selezionare paesi per la configurazione predefinita, quindi la sezione **Paesi** non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="9dd45-111">It is not possible to select country/regions for the default configuration, so the **Countries/regions** section cannot be changed.</span></span>

1. <span data-ttu-id="9dd45-112">Fare clic su **Approvvigionamento** > **Impostazione** > **Fornitori** e **Configurazioni richiesta fornitore**.</span><span class="sxs-lookup"><span data-stu-id="9dd45-112">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2. <span data-ttu-id="9dd45-113">Fare clic sulla scheda **Campi** per impostare lo stato dei campi elencati.</span><span class="sxs-lookup"><span data-stu-id="9dd45-113">Click the **Fields** tab to set the status of the listed fields.</span></span>
3. <span data-ttu-id="9dd45-114">Nascosto (non visibile)</span><span class="sxs-lookup"><span data-stu-id="9dd45-114">Hidden (Not visible)</span></span>
4. <span data-ttu-id="9dd45-115">Visualizzato (visibile ma non obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="9dd45-115">Displayed (Visible but not mandatory)</span></span>
5. <span data-ttu-id="9dd45-116">Obbligatorio (visibile e obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="9dd45-116">Required (Visible and mandatory)</span></span>
6. <span data-ttu-id="9dd45-117">Fare clic sulla scheda **Contenuto** per specificare se il testo verrà visualizzato nella procedura guidata e se è necessario confermare che l'utente del fornitore potenziale deve accettarlo prima di continuare al passaggio successivo della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9dd45-117">Click the **Content** tab to specify if text is going to be shown on the wizard and if there should be an acknowledgement that the prospective vendor user must accept this before moving to the next step in the wizard.</span></span> <span data-ttu-id="9dd45-118">L'accettazione verrà richiesta per tutti i termini e le condizioni che l'utente deve accettare per continuare.</span><span class="sxs-lookup"><span data-stu-id="9dd45-118">The acknowledgement will be requested for any terms and conditions that the user must accept to continue.</span></span>

<span data-ttu-id="9dd45-119">È inoltre possibile immettere un messaggio di conferma che viene visualizzato quando la procedura guidata è finalizzata e aggiungere uno o più questionari.</span><span class="sxs-lookup"><span data-stu-id="9dd45-119">You can also enter a confirmation message that will be displayed when the wizard is finalized, and you can add one or more questionnaires.</span></span>

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a><span data-ttu-id="9dd45-120">Creare una configurazione del fornitore per un paese specifico</span><span class="sxs-lookup"><span data-stu-id="9dd45-120">Create a vendor configuration for a specific country/region</span></span>
1.  <span data-ttu-id="9dd45-121">Fare clic su **Approvvigionamento** > **Impostazione** > **Fornitori** e **Configurazioni richiesta fornitore**.</span><span class="sxs-lookup"><span data-stu-id="9dd45-121">Click **Procurement and sourcing** > **Setup** > **Vendors**, and then click **Vendor request configurations**.</span></span>
2.  <span data-ttu-id="9dd45-122">Fare clic su **Nuovo** per creare una nuova configurazione e immettere un nome per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="9dd45-122">Click **New** to create a new configuration, and provide a name for the configuration.</span></span>
3.  <span data-ttu-id="9dd45-123">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9dd45-123">Click **Save**.</span></span>
4.  <span data-ttu-id="9dd45-124">Aprire la scheda **Paesi** per selezionare il paese per cui la configurazione deve essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="9dd45-124">Open the **Country/regions** tab to select the country/region that the configuration should be used for.</span></span>
5.  <span data-ttu-id="9dd45-125">Completare la configurazione seguendo le indicazioni per la configurazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9dd45-125">Complete the configuration by following the guidelines for the default configuration.</span></span>


