---
title: Configurare eventi reali futuri
description: È possibile pianificare eventi reali futuri in Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d52e91e7b050027485b3536f40f6ad80afd90de8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056734"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="6df69-103">Configurare eventi reali futuri</span><span class="sxs-lookup"><span data-stu-id="6df69-103">Configure future life events</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6df69-104">È possibile pianificare eventi reali futuri in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6df69-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="6df69-105">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Eventi reali futuri**.</span><span class="sxs-lookup"><span data-stu-id="6df69-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="6df69-106">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6df69-106">Select **New**.</span></span>

3. <span data-ttu-id="6df69-107">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="6df69-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="6df69-108">Campo</span><span class="sxs-lookup"><span data-stu-id="6df69-108">Field</span></span> | <span data-ttu-id="6df69-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6df69-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6df69-110">Data evento reale</span><span class="sxs-lookup"><span data-stu-id="6df69-110">Life event date</span></span> | <span data-ttu-id="6df69-111">Il sistema elabora tutti gli eventi durante il periodo di iscrizione che si verificano fino a questa data.</span><span class="sxs-lookup"><span data-stu-id="6df69-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="6df69-112">Evento reale registrato</span><span class="sxs-lookup"><span data-stu-id="6df69-112">Life event logged</span></span> | <span data-ttu-id="6df69-113">Data e ora in cui l'evento reale è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="6df69-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="6df69-114">Tipo di registro</span><span class="sxs-lookup"><span data-stu-id="6df69-114">Log type</span></span> | <span data-ttu-id="6df69-115">Indica se l'azione è una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="6df69-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="6df69-116">- **Aggiorna** - Una modifica a un record esistente che monitora eventi reali</span><span class="sxs-lookup"><span data-stu-id="6df69-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="6df69-117">- **Inserisci** - La creazione di un nuovo record di evento reale</span><span class="sxs-lookup"><span data-stu-id="6df69-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="6df69-118">ID tipo di evento reale</span><span class="sxs-lookup"><span data-stu-id="6df69-118">Life event type ID</span></span> | <span data-ttu-id="6df69-119">Identificatore univoco del tipo di evento reale.</span><span class="sxs-lookup"><span data-stu-id="6df69-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="6df69-120">Tipo di evento reale</span><span class="sxs-lookup"><span data-stu-id="6df69-120">Life event type</span></span> | <span data-ttu-id="6df69-121">Catalizzatore per l'aggiornamento dell'iscrizione ai benefit di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="6df69-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="6df69-122">Per ulteriori dettagli, consultare la sezione Trigger eventi reali.</span><span class="sxs-lookup"><span data-stu-id="6df69-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="6df69-123">Stato</span><span class="sxs-lookup"><span data-stu-id="6df69-123">Status</span></span> | <span data-ttu-id="6df69-124">Indica se l'evento reale è stato elaborato o meno.</span><span class="sxs-lookup"><span data-stu-id="6df69-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="6df69-125">Linea</span><span class="sxs-lookup"><span data-stu-id="6df69-125">Line</span></span> | <span data-ttu-id="6df69-126">Numero di riga dell'evento reale futuro.</span><span class="sxs-lookup"><span data-stu-id="6df69-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="6df69-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6df69-127">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]