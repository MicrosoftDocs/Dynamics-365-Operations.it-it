---
title: Novità o modifiche in Dynamics 365 Talent - Core HR (17 settembre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 558c2cdb4addce54af937ff862535d65f1ebd602
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "2026038"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-september-17-2018"></a><span data-ttu-id="060ca-103">Novità o modifiche in Dynamics 365 Talent: Core HR (17 settembre 2018)</span><span class="sxs-lookup"><span data-stu-id="060ca-103">What's new or changed in Dynamics 365 Talent: Core HR (September 17, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="060ca-104">**Build 8.1.154.0**</span><span class="sxs-lookup"><span data-stu-id="060ca-104">**Build 8.1.154.0**</span></span>

<span data-ttu-id="060ca-105">Questo argomento descrive le funzionalità nuove o modificate di Core HR.</span><span class="sxs-lookup"><span data-stu-id="060ca-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="leave-and-absence--accrue-time-based-on-hours-worked"></a><span data-ttu-id="060ca-106">Congedo e assenza - Tempo di attribuzione basato sulle ore lavorate</span><span class="sxs-lookup"><span data-stu-id="060ca-106">Leave and Absence – Accrue time based on hours worked</span></span>

<span data-ttu-id="060ca-107">È stato aggiunto un nuovo tipo di attribuzione per competenza ai piani di congedo.</span><span class="sxs-lookup"><span data-stu-id="060ca-107">A new accrual type has been added to Leave plans.</span></span> <span data-ttu-id="060ca-108">La programmazione di attribuzione può ora essere basata sui mesi di servizio o sulle ore lavorate.</span><span class="sxs-lookup"><span data-stu-id="060ca-108">The accrual schedule can now be based on months of service or hours worked.</span></span> <span data-ttu-id="060ca-109">Per ulteriori informazioni, vedere [Attribuire permessi in base alle ore lavorate](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="060ca-109">For more information, see [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

## <a name="platform-update-18-for-finance-and-operations"></a><span data-ttu-id="060ca-110">Aggiornamento 18 della piattaforma per Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="060ca-110">Platform update 18 for Finance and Operations</span></span>

<span data-ttu-id="060ca-111">L'aggiornamento 18 della piattaforma per Finance and Operations fa ora parte della versione di Talent.</span><span class="sxs-lookup"><span data-stu-id="060ca-111">Platform update 18 for Finance and Operations is now part of the Talent release.</span></span> 

-   <span data-ttu-id="060ca-112">I campi obbligatori e altri campi possono essere nascosti tramite la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="060ca-112">Mandatory and other fields can be hidden via personalization.</span></span> <span data-ttu-id="060ca-113">Ciò consente a un utente di creare un'esperienza semplificata in cui i campi obbligatori che sono impostati su valori predefiniti dalla logica di business non vengono mostrati.</span><span class="sxs-lookup"><span data-stu-id="060ca-113">This allows a user to create a simplified experience where mandatory fields that are defaulted by business logic are not shown.</span></span> <span data-ttu-id="060ca-114">I campi obbligatori nascosti vengono inoltre resi temporaneamente visibili se sono vuoti quando si prova a eseguire il salvataggio.</span><span class="sxs-lookup"><span data-stu-id="060ca-114">Hidden mandatory fields are also temporarily made visible if they are empty when a save is attempted.</span></span>

-   <span data-ttu-id="060ca-115">Nell'aggiornamento 18 della piattaforma per Finance and Operations, il client Web Talent allinea ora gli elementi visivi a Microsoft Fluent Design.</span><span class="sxs-lookup"><span data-stu-id="060ca-115">In Platform update 18 for Finance and Operations, the Talent web client now aligns its visuals with Microsoft Fluent Design.</span></span>

    -   <span data-ttu-id="060ca-116">Quando i campi sono in "modalità di lettura", è possibile selezionare semplicemente l'opzione di modifica nei campi pe passare al modulo di modifica.</span><span class="sxs-lookup"><span data-stu-id="060ca-116">When fields are in “read mode”, you can simply select the edit option in the fields to switch the form to edit.</span></span>

    -   <span data-ttu-id="060ca-117">Modifiche nel modo in cui i campi appaiono in modalità di lettura.</span><span class="sxs-lookup"><span data-stu-id="060ca-117">Changes in how fields display when in read mode.</span></span>

    -   <span data-ttu-id="060ca-118">Le intestazioni nelle aree di lavoro e nelle pagine sono in grassetto.</span><span class="sxs-lookup"><span data-stu-id="060ca-118">Headings in workspaces and pages are bold.</span></span>

-   <span data-ttu-id="060ca-119">È stato migliorato il comportamento delle ricerche non di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="060ca-119">The behavior of non-replacing lookups has been improved.</span></span> <span data-ttu-id="060ca-120">Per ulteriori informazioni, vedere [Miglioramento del comportamento delle ricerche non di sostituzione](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fbusiness-applications-release-notes%2FOctober18%2Fdynamics365-finance-operations%2Fnon-replacing-lookups&data=02%7C01%7C%7Ce0b3b3bee47b4424aaa208d619ce86f2%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636724772137980342&sdata=RN1qjtZSLtS010zgs0KlcwFrrB8Z7uWWGtFjdxdaamg%3D&reserved=0).</span><span class="sxs-lookup"><span data-stu-id="060ca-120">For more information, see [Improved behavior for non-replacing lookups](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fbusiness-applications-release-notes%2FOctober18%2Fdynamics365-finance-operations%2Fnon-replacing-lookups&data=02%7C01%7C%7Ce0b3b3bee47b4424aaa208d619ce86f2%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636724772137980342&sdata=RN1qjtZSLtS010zgs0KlcwFrrB8Z7uWWGtFjdxdaamg%3D&reserved=0).</span></span>

## <a name="bug-fixes"></a><span data-ttu-id="060ca-121">Correzioni di bug</span><span class="sxs-lookup"><span data-stu-id="060ca-121">Bug fixes</span></span>

<span data-ttu-id="060ca-122">Questa versione include molte correzioni di bug aggiuntive, inclusi i riferimenti ad ACA, ADA e ora I9 verrà abilitato solo nelle società statunitensi.</span><span class="sxs-lookup"><span data-stu-id="060ca-122">This release includes several additional bug fixes, including references to ACA, ADA, and I9 now will only be enabled in US companies.</span></span>
