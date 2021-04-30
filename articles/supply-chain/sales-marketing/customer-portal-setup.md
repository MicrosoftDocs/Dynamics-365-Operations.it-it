---
title: Installare, configurare e aggiornare il portale clienti
description: Questo argomento fornisce dettagli sulle licenze e istruzioni per la configurazione del portale clienti.
author: dasani-madipalli
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 5c4cad305e3d130b3283ca3424c84f60e2d13307
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907817"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="257ce-103">Installare, configurare e aggiornare il portale clienti</span><span class="sxs-lookup"><span data-stu-id="257ce-103">Install, set up, and update the Customer portal</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a><span data-ttu-id="257ce-104">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="257ce-104">Licensing requirements</span></span>

<span data-ttu-id="257ce-105">Per implementare il portale clienti, è necessario disporre delle seguenti licenze:</span><span class="sxs-lookup"><span data-stu-id="257ce-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="257ce-106">**Portali Power Apps** - Questa licenza è richiesta per ospitare il portale clienti.</span><span class="sxs-lookup"><span data-stu-id="257ce-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="257ce-107">I portali sono concessi in licenza in base all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="257ce-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="257ce-108">Per ulteriori informazioni, consultare [Requisiti di licenza per portali Power Apps](/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="257ce-108">For more information, see the [Power Apps portals licensing requirements](/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="257ce-109">**Doppia scrittura** - È necessario disporre delle licenze necessarie per abilitare la doppia scrittura per le tabelle Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="257ce-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management tables.</span></span> <span data-ttu-id="257ce-110">Per ulteriori informazioni, vedere i [Requisiti di sistema per la doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="257ce-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="257ce-111">Dipendenze da doppia scrittura e portali Power Apps</span><span class="sxs-lookup"><span data-stu-id="257ce-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="257ce-112">Il portale clienti dipende dai portali Power Apps e dalla doppia scrittura, come mostrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="257ce-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

<span data-ttu-id="257ce-113">![Dipendenze del portale clienti](media/customer-portal-elements.png "Dipendenze del portale clienti")</span><span class="sxs-lookup"><span data-stu-id="257ce-113">![Customer portal dependencies](media/customer-portal-elements.png "Customer portal dependencies")</span></span>

<span data-ttu-id="257ce-114">A differenza di altre funzionalità di Supply Chain Management, il modello di portale clienti risiede nei portali Power Apps.</span><span class="sxs-lookup"><span data-stu-id="257ce-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="257ce-115">Pertanto, il portale clienti è limitato dalle funzionalità fornite dai portali  Power Apps e dalle tabelle in doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="257ce-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the tables in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="257ce-116">Configurazione richiesta per abilitare il portale clienti</span><span class="sxs-lookup"><span data-stu-id="257ce-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="257ce-117">Dopo aver verificato di disporre delle licenze necessarie, è possibile configurare la doppia scrittura come descritto in [Istruzioni di sincronizzazione iniziale con doppia scrittura](/dynamics365/supply-chain/sales-marketing/enable-entity-map).</span><span class="sxs-lookup"><span data-stu-id="257ce-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](/dynamics365/supply-chain/sales-marketing/enable-entity-map).</span></span>

<span data-ttu-id="257ce-118">Assicurarsi di abilitare i seguenti mapping di tabelle in doppia scrittura:</span><span class="sxs-lookup"><span data-stu-id="257ce-118">Be sure to enable the following table mappings in dual-write:</span></span>

- <span data-ttu-id="257ce-119">Intestazione ordine cliente</span><span class="sxs-lookup"><span data-stu-id="257ce-119">Sales Order Header</span></span>
- <span data-ttu-id="257ce-120">Dettagli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="257ce-120">Sales Order Details</span></span>
- <span data-ttu-id="257ce-121">Conti</span><span class="sxs-lookup"><span data-stu-id="257ce-121">Accounts</span></span>
- <span data-ttu-id="257ce-122">Contatti</span><span class="sxs-lookup"><span data-stu-id="257ce-122">Contacts</span></span>
- <span data-ttu-id="257ce-123">Prodotti</span><span class="sxs-lookup"><span data-stu-id="257ce-123">Products</span></span>

<span data-ttu-id="257ce-124">Al termine della configurazione, è possibile eseguire il provisioning del modello di portale clienti.</span><span class="sxs-lookup"><span data-stu-id="257ce-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="257ce-125">Provisioning del portale clienti</span><span class="sxs-lookup"><span data-stu-id="257ce-125">Provision the Customer portal</span></span>

<span data-ttu-id="257ce-126">Prima di iniziare, assicurarsi di aver già completato la [configurazione richiesta](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="257ce-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="257ce-127">Quindi seguire questi passaggi per eseguire il provisioning del portale clienti.</span><span class="sxs-lookup"><span data-stu-id="257ce-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="257ce-128">Andare a [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="257ce-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="257ce-129">Assicurarsi di utilizzare l'ambiente in cui la doppia scrittura è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="257ce-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="257ce-130">Nella scheda **Crea**, scorrere verso il basso fino alla sezione **Inizia da modello** e selezionare il modello denominato **Portale clienti**.</span><span class="sxs-lookup"><span data-stu-id="257ce-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Customer Portal**.</span></span>
4. <span data-ttu-id="257ce-131">Seguire le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="257ce-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="257ce-132">Una volta completato il provisioning, è possibile accedere al portale clienti nella sezione **App personali** della **Home page**.</span><span class="sxs-lookup"><span data-stu-id="257ce-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="257ce-133">Se la soluzione di doppia scrittura non è installata nell'ambiente in cui si sta lavorando, verrà visualizzato un messaggio di errore e il provisioning del portale clienti non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="257ce-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="257ce-134">Aggiornare il portale clienti</span><span class="sxs-lookup"><span data-stu-id="257ce-134">Update the Customer portal</span></span>

<span data-ttu-id="257ce-135">Ulteriori funzionalità potrebbero essere aggiunte al portale clienti in seguito.</span><span class="sxs-lookup"><span data-stu-id="257ce-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="257ce-136">Qualsiasi modifica apportata da Microsoft ai componenti della soluzione sottostante apparirà automaticamente nell'ambiente corrente.</span><span class="sxs-lookup"><span data-stu-id="257ce-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="257ce-137">Tuttavia, il sito Web di cui viene eseguito il provisioning nell'ambiente non rifletterà automaticamente le modifiche apportate ai dati di configurazione.</span><span class="sxs-lookup"><span data-stu-id="257ce-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="257ce-138">Sarà necessario applicare manualmente tali modifiche ottenendo il codice dal nuovo modello ed eseguendone il merging con il sito Web di cui è stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="257ce-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="257ce-139">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="257ce-139">Additional resources</span></span>

<span data-ttu-id="257ce-140">Per informazioni su come configurare e personalizzare il portale clienti, è necessario consultare la seguente documentazione per le tecnologie sottostanti:</span><span class="sxs-lookup"><span data-stu-id="257ce-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="257ce-141">Documentazione sui portali Power Apps</span><span class="sxs-lookup"><span data-stu-id="257ce-141">Power Apps portals documentation</span></span>](/powerapps/maker/portals/overview)
- [<span data-ttu-id="257ce-142">Documentazione sulla doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="257ce-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="257ce-143">Per gestire efficacemente i portali, è necessario acquisire familiarità con i portali Power Apps e il ciclo di vita di Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="257ce-143">To effectively manage your portals, you must understand the Power Apps portals and Microsoft Dataverse lifecycle.</span></span> <span data-ttu-id="257ce-144">Per ulteriori informazioni, vedi le seguenti risorse:</span><span class="sxs-lookup"><span data-stu-id="257ce-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="257ce-145">Informazioni sul ciclo di vita dei portali</span><span class="sxs-lookup"><span data-stu-id="257ce-145">About portal lifecycle</span></span>](/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="257ce-146">Aggiornare un portale</span><span class="sxs-lookup"><span data-stu-id="257ce-146">Upgrade a portal</span></span>](/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="257ce-147">Migrare la configurazione del portale</span><span class="sxs-lookup"><span data-stu-id="257ce-147">Migrate portal configuration</span></span>](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="257ce-148">Gestione del ciclo di vita delle soluzioni: app Dynamics 365 for Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="257ce-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]