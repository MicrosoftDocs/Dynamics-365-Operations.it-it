---
title: Estendere le entità di dati delle scorte disponibili
description: Questo argomento fornisce un esempio che mostra come aggiungere campi estesi alle viste INVENTORSITEONHANDENTITY e INVENTWAREHOUSEONHANDENTITY, in modo che le funzionalità delle entità di dati disponibili dell'inventario possano funzionare con le estensioni.
author: sherry-zheng
manager: tfehr
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 2e805b9379c73f7b7eb2820662fad70e28181ebf
ms.sourcegitcommit: f59df61799915f6a79aec7e3e8664c02df6597da
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "5043395"
---
# <a name="extend-inventory-on-hand-data-entities"></a><span data-ttu-id="eeba9-103">Estendere le entità di dati delle scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="eeba9-103">Extend inventory on-hand data entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eeba9-104">Microsoft Dynamics 365 Supply Chain Management fornisce funzionalità di [estendibilità](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) che consentono di [aggiungere campi alle tabelle tramite le estensioni](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md).</span><span class="sxs-lookup"><span data-stu-id="eeba9-104">Microsoft Dynamics 365 Supply Chain Management provides [extensibility](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) features that let you [add fields to tables through extension](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md).</span></span> <span data-ttu-id="eeba9-105">Questo argomento fornisce un esempio che mostra come aggiungere campi estesi alle viste `INVENTORSITEONHANDENTITY` e `INVENTWAREHOUSEONHANDENTITY`, in modo che le funzionalità delle entità di dati disponibili dell'inventario possano funzionare con le estensioni.</span><span class="sxs-lookup"><span data-stu-id="eeba9-105">This topic provides an example that shows how to add extended fields to the `INVENTORSITEONHANDENTITY` and `INVENTWAREHOUSEONHANDENTITY` views, so that the capabilities of the inventory on-hand data entities can work with the extensions.</span></span> <span data-ttu-id="eeba9-106">Per ulteriori informazioni sulle entità dei dati, vedere [Panoramica sulla gestione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="eeba9-106">For more information about data entities, see [Data management overview](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="eeba9-107">Ecco un elenco di alcune delle entità di dati disponibili nell'inventario:</span><span class="sxs-lookup"><span data-stu-id="eeba9-107">Here is a list of some of the inventory on-hand data entities:</span></span>
>
> - <span data-ttu-id="eeba9-108">Disponibilità scorte in base al sito</span><span class="sxs-lookup"><span data-stu-id="eeba9-108">Inventory on-hand by site</span></span>
> - <span data-ttu-id="eeba9-109">Disponibilità scorte in base al sito V2</span><span class="sxs-lookup"><span data-stu-id="eeba9-109">Inventory on-hand by site V2</span></span>
> - <span data-ttu-id="eeba9-110">Disponibilità scorte in base al magazzino</span><span class="sxs-lookup"><span data-stu-id="eeba9-110">Inventory on-hand by warehouse</span></span>
> - <span data-ttu-id="eeba9-111">Disponibilità scorte in base al magazzino v2</span><span class="sxs-lookup"><span data-stu-id="eeba9-111">Inventory on-hand by warehouse v2</span></span>

<span data-ttu-id="eeba9-112">Dopo aver aggiunto i campi alle tabelle utilizzate dalla vista `inventSiteOnHandView`, è necessario sincronizzare il motore in modo che le estensioni vengano riconosciute correttamente.</span><span class="sxs-lookup"><span data-stu-id="eeba9-112">After you add fields to tables that are used by the `inventSiteOnHandView` view, you must sync the engine so that the extensions are correctly recognized.</span></span>

1. <span data-ttu-id="eeba9-113">Estendere la vista `InventSiteOnHandView` aggiungendo il campo di estensione.</span><span class="sxs-lookup"><span data-stu-id="eeba9-113">Extend the `InventSiteOnHandView` view by adding the extension field.</span></span>
1. <span data-ttu-id="eeba9-114">Estendere la vista `InventSiteOnHandAggregatedView` con i campi dell'estensione.</span><span class="sxs-lookup"><span data-stu-id="eeba9-114">Extend the `InventSiteOnHandAggregatedView` view with the extension fields.</span></span>
1. <span data-ttu-id="eeba9-115">Estendere la classe `InventSiteOnHandAggregatedViewBuilder` viewBuilder modificando il metodo `getExtensionFields()`.</span><span class="sxs-lookup"><span data-stu-id="eeba9-115">Extend the `InventSiteOnHandAggregatedViewBuilder` viewBuilder class by modifying the `getExtensionFields()` method.</span></span> <span data-ttu-id="eeba9-116">In questo modo, si associano i vecchi campi di visualizzazione a nuovi campi di visualizzazione quando viene eseguita la sincronizzazione di viewBuilder.</span><span class="sxs-lookup"><span data-stu-id="eeba9-116">In this way, you map old view fields to new view fields when viewBuilder synchronization is run.</span></span>

<span data-ttu-id="eeba9-117">Ad esempio, sono stati aggiunti i seguenti quattro campi alla tabella `InventTable` tramite estensione:</span><span class="sxs-lookup"><span data-stu-id="eeba9-117">For example, you've added the following four fields to the `InventTable` table through extension:</span></span>

- <span data-ttu-id="eeba9-118">Campo personalizzato 1</span><span class="sxs-lookup"><span data-stu-id="eeba9-118">Custom field 1</span></span>
- <span data-ttu-id="eeba9-119">Campo personalizzato 2</span><span class="sxs-lookup"><span data-stu-id="eeba9-119">Custom field 2</span></span>
- <span data-ttu-id="eeba9-120">Campo personalizzato 3</span><span class="sxs-lookup"><span data-stu-id="eeba9-120">Custom field 3</span></span>
- <span data-ttu-id="eeba9-121">Campo personalizzato 4</span><span class="sxs-lookup"><span data-stu-id="eeba9-121">Custom field 4</span></span>

<span data-ttu-id="eeba9-122">Nel caso, è necessario modificare il metodo `getExtensionFields()` nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="eeba9-122">In the case, you must modify the `getExtensionFields()` method in the following way.</span></span>

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

<span data-ttu-id="eeba9-123">Dopo aver completato questi passaggi, è possibile estendere l'inventario disponibile per sito e l'inventario disponibile per entità di dati warehouse aggiungendo i nuovi campi.</span><span class="sxs-lookup"><span data-stu-id="eeba9-123">After you complete these steps, you can extend the inventory on-hand by site and inventory on-hand by warehouse data entities by adding the new fields.</span></span> <span data-ttu-id="eeba9-124">In questo modo, i campi estesi verranno riconosciuti e inclusi durante la migrazione dei dati che utilizza tali entità di dati.</span><span class="sxs-lookup"><span data-stu-id="eeba9-124">In this way, you ensure that the extended fields are recognized and included during data migration that uses those data entities.</span></span>
