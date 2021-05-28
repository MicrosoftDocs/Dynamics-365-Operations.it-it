---
title: Il profilo ubicazione impedisce le scorte negative ma non le scorte disponibili negative
description: L'opzione Consenti inventario negativo del profilo ubicazione è impostata su No, ma il sistema consente comunque scorte disponibili negative.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026641"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a><span data-ttu-id="564f9-103">Il profilo ubicazione impedisce le scorte negative ma non le scorte disponibili negative</span><span class="sxs-lookup"><span data-stu-id="564f9-103">Location profile disallows negative inventory, but negative on-hand inventory is permitted</span></span>

<span data-ttu-id="564f9-104">Numero KB: 4613622</span><span class="sxs-lookup"><span data-stu-id="564f9-104">KB number: 4613622</span></span>

## <a name="symptoms"></a><span data-ttu-id="564f9-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="564f9-105">Symptoms</span></span>

<span data-ttu-id="564f9-106">L'opzione **Consenti inventario negativo** del profilo ubicazione è impostata su *No*, ma il sistema consente comunque scorte disponibili negative.</span><span class="sxs-lookup"><span data-stu-id="564f9-106">The **Allow negative inventory** option for the location profile is set to *No*, but the system still allows negative on-hand inventory.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="564f9-107">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="564f9-107">Example scenario</span></span>

<span data-ttu-id="564f9-108">Per le transazioni regolamentate dal governo, il sistema deve essere in grado di registrare scorte negative per registrare le perdite.</span><span class="sxs-lookup"><span data-stu-id="564f9-108">For government-regulated transactions, the system must be able to record negative inventory to book losses.</span></span> <span data-ttu-id="564f9-109">Desideri che un articolo possa mostrare scorte negative, ma solo in ubicazioni designate, come i serbatoi.</span><span class="sxs-lookup"><span data-stu-id="564f9-109">You want an item to be able to show negative inventory, but only in designated locations, such as tanks.</span></span> <span data-ttu-id="564f9-110">Tuttavia, se il gruppo di modelli di articoli consente scorte negative, non importa se l'ubicazione è impostata o meno per consentire le scorte negative.</span><span class="sxs-lookup"><span data-stu-id="564f9-110">However, if the item model group allows negative inventory, you find that it doesn't matter whether the location is set to allow negative inventory.</span></span> <span data-ttu-id="564f9-111">Se l'articolo è impostato di modo che le scorte negative non siano consentite, non importa come è impostato il profilo ubicazione.</span><span class="sxs-lookup"><span data-stu-id="564f9-111">If the item is set up so that negative inventory isn't allowed, it doesn't matter how the location profile is set up.</span></span>

## <a name="resolution"></a><span data-ttu-id="564f9-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="564f9-112">Resolution</span></span>

<span data-ttu-id="564f9-113">L'impostazione **Consenti inventario negativo** del profilo ubicazione si applica solo ai processi di magazzino, come il prelievo.</span><span class="sxs-lookup"><span data-stu-id="564f9-113">The **Allow negative inventory** setting from the location profile applies only to warehouse processes, such as picking.</span></span> <span data-ttu-id="564f9-114">Tuttavia, i gruppi di modelli di articoli impostati per consentire scorte negative influiscono su tutti i processi dei moduli Gestione inventario e Gestione magazzino e il profilo ubicazione non sovrascriverà l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="564f9-114">However, item model groups that are set to allow negative inventory affect all processes from the Inventory management and Warehouse management modules, and the location profile won't override the setting.</span></span>

<span data-ttu-id="564f9-115">Puoi controllare se per un magazzino è consentito avere scorte negative.</span><span class="sxs-lookup"><span data-stu-id="564f9-115">You can control whether a warehouse is allowed to carry negative inventory.</span></span> <span data-ttu-id="564f9-116">Imposta i gruppi di modelli di articoli per disabilitare le scorte fisiche negative e imposta solo il magazzino pertinente per consentire le scorte negative.</span><span class="sxs-lookup"><span data-stu-id="564f9-116">Set your item model groups to disallow negative physical inventory, and set only the relevant warehouse to allow negative inventory.</span></span>
