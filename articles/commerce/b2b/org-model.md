---
title: Creare gerarchie di modellazione per le organizzazioni B2B
description: Questo argomento descrive come creare gerarchie di modellazione organizzative per le organizzazioni business-to-business (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 450efd595a1cc1b72b2e62afbdd4518bcca59cb0
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035925"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a><span data-ttu-id="63107-103">Creare gerarchie di modellazione per le organizzazioni B2B</span><span class="sxs-lookup"><span data-stu-id="63107-103">Create org modeling hierarchies for B2B organizations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="63107-104">Questo argomento descrive come creare gerarchie di modellazione organizzative per le organizzazioni business-to-business (B2B) in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="63107-104">This topic describes how to create organizational modeling hierarchies for business-to-business (B2B) organizations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="63107-105">In Commerce Headquarters, le organizzazioni dei partner commerciali sono rappresentate da clienti ed entità gerarchiche di clienti.</span><span class="sxs-lookup"><span data-stu-id="63107-105">In Commerce headquarters, business partner organizations are represented by customer and customer hierarchy entities.</span></span> <span data-ttu-id="63107-106">L'organizzazione del partner commerciale e i suoi utenti sono rappresentati come clienti e le gerarchie dei clienti vengono utilizzate per associare questi clienti tra loro.</span><span class="sxs-lookup"><span data-stu-id="63107-106">The business partner organization and its users are represented as customers, and customer hierarchies are used to associate those customers with each other.</span></span>

<span data-ttu-id="63107-107">Quando la richiesta di un partner commerciale di partecipare a un sito di e-commerce B2B viene approvata, vengono eseguite le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="63107-107">When a business partner request to join a B2B e-commerce site is approved, the following actions are performed:</span></span>

- <span data-ttu-id="63107-108">Due nuovi record cliente vengono creati nel sistema: un record cliente **Digita organizzazione** per l'organizzazione del partner commerciale e un record del cliente **Digita persona** per il richiedente (ovvero, l'utente del partner commerciale che ha inoltrato la richiesta).</span><span class="sxs-lookup"><span data-stu-id="63107-108">Two new customer records are created in the system: a **Type Organization** customer record for the business partner organization and a **Type Person** customer record for the requestor (that is, the business partner user who submitted the request).</span></span>
- <span data-ttu-id="63107-109">Un nuovo record della gerarchia del cliente viene creato in **Cliente \> Gerarchia dei clienti**.</span><span class="sxs-lookup"><span data-stu-id="63107-109">A new customer hierarchy record is created under **Customer \> Customer hierarchy**.</span></span> <span data-ttu-id="63107-110">Questo record ha le seguenti proprietà di intestazione:</span><span class="sxs-lookup"><span data-stu-id="63107-110">This record has the following header properties:</span></span>

    - <span data-ttu-id="63107-111">**ID gerarchia cliente**: un ID univoco per la gerarchia del cliente.</span><span class="sxs-lookup"><span data-stu-id="63107-111">**Customer hierarchy ID** – A unique ID for the customer hierarchy.</span></span> <span data-ttu-id="63107-112">Questo ID utilizza la sequenza numerica definita nei parametri condivisi di Commerce in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="63107-112">This ID uses the number sequence that is defined in Commerce shared parameters in Commerce headquarters.</span></span>
    - <span data-ttu-id="63107-113">**Nome**: il nome dell'organizzazione del partner commerciale, come specificato nella richiesta di onboarding.</span><span class="sxs-lookup"><span data-stu-id="63107-113">**Name** – The organization name of the business partner, as specified in the onboarding request.</span></span>
    - <span data-ttu-id="63107-114">**Scopo**: questa proprietà è impostata sul valore predefinito **Organizzazione B2B**.</span><span class="sxs-lookup"><span data-stu-id="63107-114">**Purpose** – This property is set to the predefined value **B2B organization**.</span></span>
    - <span data-ttu-id="63107-115">**Organizzazione**: l'ID cliente del partner commerciale.</span><span class="sxs-lookup"><span data-stu-id="63107-115">**Organization** – The customer ID of the business partner.</span></span>

<span data-ttu-id="63107-116">Di seguito sono riportati i dettagli del record della gerarchia del cliente:</span><span class="sxs-lookup"><span data-stu-id="63107-116">Here are the details of the customer hierarchy record:</span></span>

- <span data-ttu-id="63107-117">Il record del cliente del richiedente è associato alla gerarchia del cliente.</span><span class="sxs-lookup"><span data-stu-id="63107-117">The customer record of the requestor is associated with the customer hierarchy.</span></span>
- <span data-ttu-id="63107-118">Il ruolo di amministratore è associato al richiedente.</span><span class="sxs-lookup"><span data-stu-id="63107-118">The administrator role is associated with the requestor.</span></span>

<span data-ttu-id="63107-119">Quando l'amministratore aggiunge più utenti all'organizzazione del partner commerciale su un sito B2B, viene creato un nuovo record cliente per ogni utente nella sede in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="63107-119">When the administrator adds more users are to the business partner organization on a B2B site, a new customer record for each user is created in Commerce headquarters.</span></span> <span data-ttu-id="63107-120">Questo record del cliente viene inoltre aggiunto anche al record della gerarchia del cliente rilevante per il partner commerciale e ha il ruolo di "utente".</span><span class="sxs-lookup"><span data-stu-id="63107-120">This customer record is also added to the relevant customer hierarchy record for the business partner and has the role of a "user."</span></span>

> [!NOTE]
> <span data-ttu-id="63107-121">Nella maggior parte dei casi, i valori delle proprietà corrispondenti di tutti i record dei clienti in una gerarchia dovrebbero corrispondere.</span><span class="sxs-lookup"><span data-stu-id="63107-121">In most cases, the corresponding property values of all customer records in a hierarchy should match.</span></span> <span data-ttu-id="63107-122">Ad esempio, poiché tutti gli utenti dei partner commerciali dovrebbero ottenere prezzi simili per i prodotti, il loro gruppo di prezzi e le configurazioni associate dovrebbero corrispondere.</span><span class="sxs-lookup"><span data-stu-id="63107-122">For example, because all business partner users should get similar prices for products, their price group and associated configurations should match.</span></span> <span data-ttu-id="63107-123">Tuttavia, il sistema non applica questa coerenza.</span><span class="sxs-lookup"><span data-stu-id="63107-123">However, the system doesn't enforce this consistency.</span></span> <span data-ttu-id="63107-124">Pertanto, gli utenti di Commerce Headquarters pertinenti sono responsabili di garantire che i valori e le configurazioni delle proprietà corrispondano per tutti i clienti in una data gerarchia.</span><span class="sxs-lookup"><span data-stu-id="63107-124">Therefore, the relevant Commerce headquarters users are responsible for ensuring that the property values and configurations match for all customers in a given hierarchy.</span></span>

<span data-ttu-id="63107-125">Gli utenti di Commerce Headquarters possono esaminare i valori delle proprietà per tutti i record dei clienti nella gerarchia in una vista affiancata.</span><span class="sxs-lookup"><span data-stu-id="63107-125">Commerce headquarters users can look at the property values for all customer records in the hierarchy in a side-by-side view.</span></span> <span data-ttu-id="63107-126">Seleziona le proprietà del record del cliente rilevanti selezionando i nomi delle schede nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="63107-126">Select the relevant customer record properties by selecting the tab names on the drop-down menu.</span></span> <span data-ttu-id="63107-127">Gli utenti possono visualizzare e modificare direttamente i valori delle proprietà da questa vista.</span><span class="sxs-lookup"><span data-stu-id="63107-127">Users can directly view and edit the property values from this view.</span></span> <span data-ttu-id="63107-128">In alternativa, se desideri applicare tutti i valori dal record cliente amministratore a tutti i record cliente utente, seleziona **Sovrascrivi** nei dettagli della gerarchia dei clienti.</span><span class="sxs-lookup"><span data-stu-id="63107-128">Alternatively, if you want to apply all the values from the administrator customer record to all the user customer records, select **Override** in the customer hierarchy details.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63107-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="63107-129">Additional resources</span></span>

[<span data-ttu-id="63107-130">Impostare un sito di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="63107-130">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="63107-131">Gestisci gli utenti dei partner commerciali sui siti di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="63107-131">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="63107-132">Configura il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="63107-132">Configure the customer account payment method for B2B e-commerce sites</span></span>](payment-method.md)

[<span data-ttu-id="63107-133">Impostare limiti di quantità di prodotti per i siti di e-commerce B2B</span><span class="sxs-lookup"><span data-stu-id="63107-133">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)
