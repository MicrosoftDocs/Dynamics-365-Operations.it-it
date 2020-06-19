---
title: Configurare eventi reali futuri
description: È possibile pianificare eventi reali futuri in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 78c65faa4ae0f428184700a912998e9dded026c5
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429407"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="7b19a-103">Configurare eventi reali futuri</span><span class="sxs-lookup"><span data-stu-id="7b19a-103">Configure future life events</span></span>

<span data-ttu-id="7b19a-104">È possibile pianificare eventi reali futuri in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7b19a-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="7b19a-105">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Eventi reali futuri**.</span><span class="sxs-lookup"><span data-stu-id="7b19a-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="7b19a-106">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7b19a-106">Select **New**.</span></span>

3. <span data-ttu-id="7b19a-107">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="7b19a-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="7b19a-108">Campo</span><span class="sxs-lookup"><span data-stu-id="7b19a-108">Field</span></span> | <span data-ttu-id="7b19a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b19a-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7b19a-110">Data evento reale</span><span class="sxs-lookup"><span data-stu-id="7b19a-110">Life event date</span></span> | <span data-ttu-id="7b19a-111">Il sistema elabora tutti gli eventi durante il periodo di iscrizione che si verificano fino a questa data.</span><span class="sxs-lookup"><span data-stu-id="7b19a-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="7b19a-112">Evento reale registrato</span><span class="sxs-lookup"><span data-stu-id="7b19a-112">Life event logged</span></span> | <span data-ttu-id="7b19a-113">Data e ora in cui l'evento reale è stato registrato.</span><span class="sxs-lookup"><span data-stu-id="7b19a-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="7b19a-114">Tipo di registro</span><span class="sxs-lookup"><span data-stu-id="7b19a-114">Log type</span></span> | <span data-ttu-id="7b19a-115">Indica se l'azione è una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b19a-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="7b19a-116">- **Aggiorna** - Una modifica a un record esistente che monitora eventi reali</span><span class="sxs-lookup"><span data-stu-id="7b19a-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="7b19a-117">- **Inserisci** - La creazione di un nuovo record di evento reale</span><span class="sxs-lookup"><span data-stu-id="7b19a-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="7b19a-118">ID tipo di evento reale</span><span class="sxs-lookup"><span data-stu-id="7b19a-118">Life event type ID</span></span> | <span data-ttu-id="7b19a-119">Identificatore univoco del tipo di evento reale.</span><span class="sxs-lookup"><span data-stu-id="7b19a-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="7b19a-120">Tipo di evento reale</span><span class="sxs-lookup"><span data-stu-id="7b19a-120">Life event type</span></span> | <span data-ttu-id="7b19a-121">Catalizzatore per l'aggiornamento dell'iscrizione ai benefit di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="7b19a-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="7b19a-122">Per ulteriori dettagli, consultare la sezione Trigger eventi reali.</span><span class="sxs-lookup"><span data-stu-id="7b19a-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="7b19a-123">Stato</span><span class="sxs-lookup"><span data-stu-id="7b19a-123">Status</span></span> | <span data-ttu-id="7b19a-124">Indica se l'evento reale è stato elaborato o meno.</span><span class="sxs-lookup"><span data-stu-id="7b19a-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="7b19a-125">Linea</span><span class="sxs-lookup"><span data-stu-id="7b19a-125">Line</span></span> | <span data-ttu-id="7b19a-126">Numero di riga dell'evento reale futuro.</span><span class="sxs-lookup"><span data-stu-id="7b19a-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="7b19a-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7b19a-127">Select **Save**.</span></span> 
