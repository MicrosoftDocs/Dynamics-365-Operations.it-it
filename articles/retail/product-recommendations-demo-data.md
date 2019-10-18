---
title: Dati dimostrativi dei consigli sui prodotti omnicanale
description: Questo documento ha lo scopo di fornire una guida su come sfruttare i consigli sui prodotti omnicanale in ambienti one-box di livello 1 utilizzando dati dimostrativi precompilati e personalizzabili.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 81af4c1bb7828c9b346a3ef514d8657e853dcefb
ms.sourcegitcommit: c526cfd1f823df1ff33ded95e599a72f0a15cc5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2226093"
---
# <a name="omni-channel-product-recommendations-demo-data"></a><span data-ttu-id="95b8c-103">Dati dimostrativi dei consigli sui prodotti omnicanale</span><span class="sxs-lookup"><span data-stu-id="95b8c-103">Omni-channel product recommendations demo data</span></span>

<span data-ttu-id="95b8c-104">Questo documento ha lo scopo di fornire una guida su come sfruttare i consigli sui prodotti omnicanale in ambienti one-box di livello 1 utilizzando dati dimostrativi precompilati e personalizzabili.</span><span class="sxs-lookup"><span data-stu-id="95b8c-104">This document aims to provide guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="95b8c-105">I suggerimenti sul prodotto omnicanale forniscono un set di elenchi di prodotti ordinati curati in modo editoriale o generati a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="95b8c-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated ordered list of products.</span></span> <span data-ttu-id="95b8c-106">Gli elenchi possono essere utilizzati in vari scenari, in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="95b8c-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="95b8c-107">Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto.](product-recommendaitons-overview.md)</span><span class="sxs-lookup"><span data-stu-id="95b8c-107">For more information about product recommendation lists, see [Product recommendations overview.](product-recommendaitons-overview.md)</span></span>

<span data-ttu-id="95b8c-108">Per gli ambienti Dynamics di livello 2 e superiore, i suggerimenti sui prodotti vengono calcolati automaticamente in base ai dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="95b8c-108">For Tier-2 and higher Dynamics Environments product recommendations are automatically computed based on customer data.</span></span>
<span data-ttu-id="95b8c-109">L'uso dei dati dimostrativi dei suggerimenti sui prodotti non disabilita alcuna soluzione di suggerimenti sui prodotti già predisposta nell'ambiente e i costi associati al suo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="95b8c-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="95b8c-110">I suggerimenti sui prodotti degli ambienti di livello 1 si basano solo sui dati dimostrativi statici memorizzati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="95b8c-110">For Tier-1 environments product recommendations are based only off the static demo data stored in a csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="95b8c-111">Abilitazione dei dati dimostrativi dei suggerimenti sui prodotti in un ambiente</span><span class="sxs-lookup"><span data-stu-id="95b8c-111">Enabling product recommendations demo data in an environment</span></span>

<span data-ttu-id="95b8c-112">I clienti devono distribuire l'**Estensione dimostrativa dell'anteprima di Dynamics 365 Commerce** al rispettivo ambiente, che abilita automaticamente i dati dimostrativi dei suggerimenti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="95b8c-112">Customers need to deploy the **Dynamics 365 Commerce Preview Demo Extension** to the respective environment, which automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="95b8c-113">Dati dimostrativi predefiniti</span><span class="sxs-lookup"><span data-stu-id="95b8c-113">Default demo data</span></span>
<span data-ttu-id="95b8c-114">Ogni ambiente di tipo Onebox viene fornito con un set precaricato di dati dimostrativi di suggerimenti sui prodotti memorizzati nel file **‘reco_demo_data.csv’**, situato nella stessa cartella di questo documento su Retail Server.</span><span class="sxs-lookup"><span data-stu-id="95b8c-114">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated **‘reco_demo_data.csv’** file, located in the same folder as this document on Retail Server.</span></span>

<span data-ttu-id="95b8c-115">Questi dati sono strutturati nelle seguenti colonne</span><span class="sxs-lookup"><span data-stu-id="95b8c-115">This data is structured along the following columns</span></span>

| <span data-ttu-id="95b8c-116">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="95b8c-116">Column name</span></span>         | <span data-ttu-id="95b8c-117">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="95b8c-117">Mandatory</span></span>          | <span data-ttu-id="95b8c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95b8c-118">Description</span></span>                                                                                                                                 | <span data-ttu-id="95b8c-119">Valori possibili</span><span class="sxs-lookup"><span data-stu-id="95b8c-119">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="95b8c-120">RecoList</span><span class="sxs-lookup"><span data-stu-id="95b8c-120">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="95b8c-122">Il tipo di elenco di suggerimenti sul prodotto specifico che deve essere generato dal punto dei dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="95b8c-122">The specific product   recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="95b8c-123">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="95b8c-123">RecoBestSelling</span></span></li><li><span data-ttu-id="95b8c-124">RecoNew</span><span class="sxs-lookup"><span data-stu-id="95b8c-124">RecoNew</span></span></li><li><span data-ttu-id="95b8c-125">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="95b8c-125">RecoTrending</span></span></li><li><span data-ttu-id="95b8c-126">RecoCart</span><span class="sxs-lookup"><span data-stu-id="95b8c-126">RecoCart</span></span></li><li><span data-ttu-id="95b8c-127">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="95b8c-127">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="95b8c-128">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="95b8c-128">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="95b8c-130">Il numero specifico dell'unità operativa in cui sono previsti i suggerimenti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="95b8c-130">The specific   operating unit number where product recommendations are expected to be   surfaced in.</span></span>                                        |                                                                              |
| <span data-ttu-id="95b8c-131">Categoria</span><span class="sxs-lookup"><span data-stu-id="95b8c-131">Category</span></span>            |                    |    <span data-ttu-id="95b8c-132">La categoria per cui deve essere restituito l'elenco specifico.</span><span class="sxs-lookup"><span data-stu-id="95b8c-132">The category the   specific list should be returned for.</span></span> <span data-ttu-id="95b8c-133">Se non viene specificata alcuna categoria, l'elenco è solo per la parte superiore della gerarchia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="95b8c-133">If no category is specified, list is   for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="95b8c-134">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="95b8c-134">SeedItemId</span></span>          |                    |    <span data-ttu-id="95b8c-135">Per gli elenchi che richiedono seed (RecoPeopleAlsoBuy e RecoCart) il prodotto per cui tali elenchi devono mostrare prodotti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="95b8c-135">For lists that   require seed (RecoPeopleAlsoBuy and RecoCart) the product those lists should   show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="95b8c-136">ItemIds</span><span class="sxs-lookup"><span data-stu-id="95b8c-136">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="95b8c-138">Uno o più prodotti da restituire come risultato, separati da **‘;’**.</span><span class="sxs-lookup"><span data-stu-id="95b8c-138">One or more products   to be returned as the result, separated by **‘;’**.</span></span>                                                                  |                                                                              |


## <a name="customize-demo-data"></a><span data-ttu-id="95b8c-139">Personalizzare i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="95b8c-139">Customize demo data</span></span>
<span data-ttu-id="95b8c-140">I clienti possono modificare i dati dimostrativi predefiniti con qualsiasi informazione su prodotto e categoria configurata nella sede centrale.</span><span class="sxs-lookup"><span data-stu-id="95b8c-140">Customers can edit the default demo data with any product and category information that is configured in HQ.</span></span> <span data-ttu-id="95b8c-141">Una volta aggiornato il CSV, i suggerimenti sul prodotto restituiti ai clienti rifletteranno immediatamente le modifiche.</span><span class="sxs-lookup"><span data-stu-id="95b8c-141">Once the CSV is updated, the Product Recommendations returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="95b8c-142">L'estensione contiene un file di dati chiamato RecoMockDataset.csv che consente al cliente di controllare il set di dati utilizzato per potenziare i risultati dei suggerimenti simulati.</span><span class="sxs-lookup"><span data-stu-id="95b8c-142">The extension contains a datafile called RecoMockDataset.csv which allows the customer to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="95b8c-143">Il nome del file può essere controllato tramite la configurazione dell'estensione usando l'impostazione **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="95b8c-143">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="95b8c-144">I clienti in tal modo posso disporre di più set di dati che possono essere commutati facilmente attraverso la configurazione.</span><span class="sxs-lookup"><span data-stu-id="95b8c-144">This enables the customers to have multiple datasets available that can be switched between easily through configuration.</span></span>

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="95b8c-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="95b8c-145">Additional resources</span></span>

[<span data-ttu-id="95b8c-146">Panoramica dei suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="95b8c-146">Product recommendations overview</span></span>](product-recommendations-overview.md)

[<span data-ttu-id="95b8c-147">Pianificazione ambiente</span><span class="sxs-lookup"><span data-stu-id="95b8c-147">Environment planning</span></span>](environment-planning.md)
