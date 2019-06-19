---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (8 ottobre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
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
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 34216e2181915cf615e6e77fa2a10d06a4e9db85
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617274"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-8-2018"></a><span data-ttu-id="ff555-103">Novità o modifiche in Dynamics 365 for Talent Core HR (8 ottobre 2018)</span><span class="sxs-lookup"><span data-stu-id="ff555-103">What's new or changed in Dynamics 365 for Talent Core HR (October 8, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ff555-104">**Build 8.1.1050.0**</span><span class="sxs-lookup"><span data-stu-id="ff555-104">**Build 8.1.1050.0**</span></span>

<span data-ttu-id="ff555-105">Questo argomento descrive le funzionalità nuove o modificate di Core HR.</span><span class="sxs-lookup"><span data-stu-id="ff555-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a><span data-ttu-id="ff555-106">Consentire l'utilizzo di altre date in base al livello di congedo (Gestione di congedo)</span><span class="sxs-lookup"><span data-stu-id="ff555-106">Allow other dates to be used on leave tier basis (Leave Management)</span></span>

<span data-ttu-id="ff555-107">Quando si assegna il congedo ai dipendenti, la base del livello del premio determina la quantità di tempo di assenza maturata da un dipendente.</span><span class="sxs-lookup"><span data-stu-id="ff555-107">When awarding leave to employees, the award tier basis determines how much time off an employee accrues.</span></span> <span data-ttu-id="ff555-108">Attualmente, questi livelli si basano sulla data di inizio e la data di anzianità del dipendente.</span><span class="sxs-lookup"><span data-stu-id="ff555-108">Currently, these tiers are based on employee start date and seniority date.</span></span> <span data-ttu-id="ff555-109">In alcuni scenari le organizzazioni hanno bisogno che questi livelli si basino su altre date, come la data di anniversario o la data di assunzione originale.</span><span class="sxs-lookup"><span data-stu-id="ff555-109">In some scenarios, organizations need these tiers to be based on other dates, like anniversary date or original hire date.</span></span> <span data-ttu-id="ff555-110">Queste date sono già utilizzate nel piano di congedo per verificare se i ratei verranno eseguiti; la possibilità per queste stesse date di essere utilizzate quando un dipendente è iscritto a un piano è stata aggiunta per determinare l'importo di attribuzione per competenza.</span><span class="sxs-lookup"><span data-stu-id="ff555-110">These dates are already used on the leave plan to determine when accruals happen, the ability for these same dates to be used when an employee is enrolled in a plan have been added to determine the accrual amount.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="ff555-111">Altre modifiche</span><span class="sxs-lookup"><span data-stu-id="ff555-111">Other changes</span></span>
<span data-ttu-id="ff555-112">Correzioni varie sono state incluse in questa versione.</span><span class="sxs-lookup"><span data-stu-id="ff555-112">Miscellanous fixes have been included in this release.</span></span>

## <a name="known-issue"></a><span data-ttu-id="ff555-113">Problema noto</span><span class="sxs-lookup"><span data-stu-id="ff555-113">Known issue</span></span>

<span data-ttu-id="ff555-114">**Problema:** quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** appaiono disattivati. **Soluzione alternativa:** prima di aprire la pagina degli allegati, assicurarsi che i riquadri Dettaglio informazioni nella pagina **Lavoratore** siano chiusi.</span><span class="sxs-lookup"><span data-stu-id="ff555-114">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="ff555-115">Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli allegati saranno abilitati.</span><span class="sxs-lookup"><span data-stu-id="ff555-115">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="ff555-116">Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ff555-116">(This issue will be fixed in the next platform update.)</span></span>
