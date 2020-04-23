---
title: Crea suggerimenti con dati dimostrativi
description: Questo argomento fornisce una guida su come utilizzare i consigli sui prodotti omnicanale in ambienti one-box di livello 1 utilizzando dati dimostrativi precompilati e personalizzabili.
author: bebeale
manager: AnnBe
ms.date: 03/30/20
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ec23461352abc53b90b6af539a3dd1764e4b5460
ms.sourcegitcommit: 67cf9e2cf0f75e90526cae6bf176a40156c62a53
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175551"
---
# <a name="create-recommendations-with-demo-data"></a><span data-ttu-id="d22a4-103">Crea suggerimenti con dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="d22a4-103">Create recommendations with demo data</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d22a4-104">Questo argomento fornisce una guida su come utilizzare i consigli sui prodotti omnicanale in ambienti one-box di livello 1 utilizzando dati dimostrativi precompilati e personalizzabili.</span><span class="sxs-lookup"><span data-stu-id="d22a4-104">This topic provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="d22a4-105">I suggerimenti sul prodotto omnicanale forniscono un set di elenchi di prodotti curati in modo editoriale o generati a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="d22a4-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="d22a4-106">Gli elenchi possono essere utilizzati in vari scenari, in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="d22a4-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="d22a4-107">Per ulteriori informazioni sugli elenchi di suggerimenti sul prodotto, vedere [Panoramica dei suggerimenti sul prodotto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="d22a4-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="d22a4-108">Per gli ambienti Dynamics 365 di livello 2 e superiore, i suggerimenti sui prodotti vengono calcolati automaticamente in base ai dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="d22a4-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="d22a4-109">L'uso dei dati dimostrativi dei suggerimenti sui prodotti non disabilita alcuna soluzione di suggerimenti sui prodotti già predisposta nell'ambiente e i costi associati al suo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="d22a4-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="d22a4-110">Per gli ambienti di livello 1, i suggerimenti sui prodotti si basano solo sui dati dimostrativi statici memorizzati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="d22a4-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="d22a4-111">Abilitazione dei dati dimostrativi dei suggerimenti sui prodotti in un ambiente</span><span class="sxs-lookup"><span data-stu-id="d22a4-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="d22a4-112">Per abilitare i dati dimostrativi dei suggerimenti sui prodotti, è necessario distribuire l'Estensione dimostrativa dell'anteprima di Dynamics 365 Commerce al rispettivo ambiente.</span><span class="sxs-lookup"><span data-stu-id="d22a4-112">To enable product recommendations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="d22a4-113">In questo modo, si abilitano i dati dimostrativi dei suggerimenti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="d22a4-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="d22a4-114">Dati dimostrativi predefiniti</span><span class="sxs-lookup"><span data-stu-id="d22a4-114">Default demo data</span></span>
<span data-ttu-id="d22a4-115">Ogni ambiente di tipo Onebox viene fornito con un set precaricato di dati dimostrativi di suggerimenti sui prodotti memorizzati nel file "reco_demo_data.csv", situato in Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="d22a4-115">Each OneBox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated 'reco_demo_data.csv' file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="d22a4-116">I dati sono strutturati nelle seguenti colonne.</span><span class="sxs-lookup"><span data-stu-id="d22a4-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="d22a4-117">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="d22a4-117">Column name</span></span>         | <span data-ttu-id="d22a4-118">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="d22a4-118">Mandatory</span></span>          | <span data-ttu-id="d22a4-119">descrizione</span><span class="sxs-lookup"><span data-stu-id="d22a4-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="d22a4-120">Possibili valori</span><span class="sxs-lookup"><span data-stu-id="d22a4-120">Possible values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="d22a4-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="d22a4-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="d22a4-123">Il tipo di elenco di suggerimenti sul prodotto specifico che deve essere generato dal punto dei dati dimostrativi.</span><span class="sxs-lookup"><span data-stu-id="d22a4-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="d22a4-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="d22a4-124">RecoBestSelling</span></span></li><li><span data-ttu-id="d22a4-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="d22a4-125">RecoNew</span></span></li><li><span data-ttu-id="d22a4-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="d22a4-126">RecoTrending</span></span></li><li><span data-ttu-id="d22a4-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="d22a4-127">RecoCart</span></span></li><li><span data-ttu-id="d22a4-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="d22a4-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="d22a4-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="d22a4-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="d22a4-131">Il numero specifico dell'unità operativa in cui sono previsti i suggerimenti sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="d22a4-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="d22a4-132">Categoria</span><span class="sxs-lookup"><span data-stu-id="d22a4-132">Category</span></span>            |                    |    <span data-ttu-id="d22a4-133">La categoria per cui deve essere restituito l'elenco specifico.</span><span class="sxs-lookup"><span data-stu-id="d22a4-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="d22a4-134">Se non viene specificata alcuna categoria, l'elenco è solo per la parte superiore della gerarchia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="d22a4-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="d22a4-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="d22a4-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="d22a4-136">Per gli elenchi che richiedono seed (RecoPeopleAlsoBuy e RecoCart) il prodotto per cui tali elenchi devono mostrare prodotti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d22a4-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="d22a4-137">Cliente </span><span class="sxs-lookup"><span data-stu-id="d22a4-137">CustomerId</span></span>          |                    |    <span data-ttu-id="d22a4-138">Per gli elenchi che richiedono un identificativo cliente (RecoPicks).</span><span class="sxs-lookup"><span data-stu-id="d22a4-138">For lists that require a customer identifier (RecoPicks).</span></span>  <span data-ttu-id="d22a4-139">Il valore predefinito "0" si applica a tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="d22a4-139">The default value '0' applies to all customers.</span></span>          |                                                                              |
| <span data-ttu-id="d22a4-140">ItemIds</span><span class="sxs-lookup"><span data-stu-id="d22a4-140">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="d22a4-142">Uno o più prodotti da restituire come risultato, separati da ";".</span><span class="sxs-lookup"><span data-stu-id="d22a4-142">One or more products to be returned as the result, separated by ';'.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="d22a4-143">Personalizzare i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="d22a4-143">Customize demo data</span></span>
<span data-ttu-id="d22a4-144">Puoi modificare i dati dimostrativi predefiniti con qualsiasi informazione su prodotto e categoria configurata nella sede centrale.</span><span class="sxs-lookup"><span data-stu-id="d22a4-144">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="d22a4-145">Dopo aver aggiornato il file CSV, i suggerimenti sul prodotto restituiti ai clienti rifletteranno immediatamente le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d22a4-145">After you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="d22a4-146">L'estensione contiene un file di dati chiamato RecoMockDataset.csv, che consente di controllare il set di dati utilizzato per potenziare i risultati dei suggerimenti simulati.</span><span class="sxs-lookup"><span data-stu-id="d22a4-146">The extension contains a datafile called 'RecoMockDataset.csv', which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="d22a4-147">Il nome del file può essere controllato tramite la configurazione dell'estensione usando l'impostazione **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="d22a4-147">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="d22a4-148">In tal modo è possibile disporre di più set di dati che possono essere commutati facilmente attraverso la configurazione.</span><span class="sxs-lookup"><span data-stu-id="d22a4-148">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a><span data-ttu-id="d22a4-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d22a4-149">Additional resources</span></span>

[<span data-ttu-id="d22a4-150">Panoramica suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="d22a4-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="d22a4-151">Abilitare ADLS in un ambiente Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="d22a4-151">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="d22a4-152">Abilita suggerimenti sul prodotto</span><span class="sxs-lookup"><span data-stu-id="d22a4-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="d22a4-153">Abilitare i suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="d22a4-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="d22a4-154">Rifiuto esplicito dei suggerimenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="d22a4-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="d22a4-155">Aggiungere suggerimenti sul prodotto su POS</span><span class="sxs-lookup"><span data-stu-id="d22a4-155">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="d22a4-156">Aggiungere suggerimenti alla schermata della transazione</span><span class="sxs-lookup"><span data-stu-id="d22a4-156">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="d22a4-157">Regolare i risultati dei suggerimenti AI-ML</span><span class="sxs-lookup"><span data-stu-id="d22a4-157">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="d22a4-158">Creare manualmente suggerimenti mirati</span><span class="sxs-lookup"><span data-stu-id="d22a4-158">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="d22a4-159">Domande frequenti su suggerimenti prodotto</span><span class="sxs-lookup"><span data-stu-id="d22a4-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
