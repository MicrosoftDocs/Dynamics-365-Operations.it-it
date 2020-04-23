---
title: Configurare i parametri di congedo e assenza
description: Definire i parametri delle risorse umane per congedo e assenza in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb992cbfbed33f88e125d3a8b721f8815414599a
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197983"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="31405-103">Configurare i parametri di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="31405-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="31405-104">Prima di impostare i piani di congedo e assenza in Dynamics 365 Human Resources, è una buona idea verificare le impostazioni per tutti i parametri delle risorse umane correlati, tra cui:</span><span class="sxs-lookup"><span data-stu-id="31405-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="31405-105">La sequenza numerica per richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="31405-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="31405-106">Impostazioni relative alla normativa per il congedo per motivi medici e familiari (FMLA)</span><span class="sxs-lookup"><span data-stu-id="31405-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="31405-107">Impostazioni di Dipendente self-service per richieste di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="31405-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="31405-108">Parametri di congedi e assenze</span><span class="sxs-lookup"><span data-stu-id="31405-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="31405-109">Visualizzare e modificare parametri delle risorse umane</span><span class="sxs-lookup"><span data-stu-id="31405-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="31405-110">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="31405-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="31405-111">Sotto **Impostazione**, selezionare **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="31405-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="31405-112">Nella scheda **Sequenze numeriche**, verificare il **Codice sequenza numerica** per **ID richiesta congedo** e modificare come necessario.</span><span class="sxs-lookup"><span data-stu-id="31405-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="31405-113">Questa impostazione determina la sequenza utilizzata per assegnare automaticamente gli ID alle richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="31405-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="31405-114">Nella scheda **FMLA**, verificare le impostazioni FMLA e modificare come necessario.</span><span class="sxs-lookup"><span data-stu-id="31405-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="31405-115">Nella scheda **Dipendente self-service**, indicare se i manager possono immettere richieste di congedo e assenza per conto dei propri dipendenti.</span><span class="sxs-lookup"><span data-stu-id="31405-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="31405-116">Nella scheda **Congedo e assenza**, verificare le impostazioni e modificare come necessario.</span><span class="sxs-lookup"><span data-stu-id="31405-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="31405-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="31405-117">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="31405-118">Visualizzare e modificare i parametri di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="31405-118">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="31405-119">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="31405-119">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="31405-120">Sotto **Impostazione**, selezionare **Parametri di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="31405-120">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="31405-121">Nella scheda **Generale**, impostare i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="31405-121">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="31405-122">Impostare **Unità per ferie e assenze** su ore o giorni.</span><span class="sxs-lookup"><span data-stu-id="31405-122">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="31405-123">Se in giorni, è possibile selezionare **Abilita la definizione di mezza giornata** per consentire ai dipendenti di scegliere la prima o la seconda metà del giorno nelle richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="31405-123">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="31405-124">Selezionare **Mesi della data di entrata in servizio** per stabilire quando il coefficiente di accumulo diventa effettivo per i piani di congedo che utilizzano mesi di servizio.</span><span class="sxs-lookup"><span data-stu-id="31405-124">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="31405-125">Selezionare **Calcolo del saldo** per visualizzare i saldi visualizzati a partire dalla data odierna o dal periodo di competenza.</span><span class="sxs-lookup"><span data-stu-id="31405-125">Select **Balance calculation** to display balances display as of today or as of the accrual period.</span></span> <span data-ttu-id="31405-126">Se viene selezionato **Saldo dalla data odierna**, il saldo mostra il totale di tutti gli accumuli, rettifiche e richieste all data odierna.</span><span class="sxs-lookup"><span data-stu-id="31405-126">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="31405-127">Se viene selezionato **Saldo dal periodo di competenza**, il saldo mostra il totale di tutti gli accumuli, rettifiche e richieste dal periodo di competenza definito dalla frequenza nel piano di ferie.</span><span class="sxs-lookup"><span data-stu-id="31405-127">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

## <a name="configure-calendar-parameters"></a><span data-ttu-id="31405-128">Configurare i parametri del calendario</span><span class="sxs-lookup"><span data-stu-id="31405-128">Configure calendar parameters</span></span>

1. <span data-ttu-id="31405-129">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="31405-129">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="31405-130">Sotto **Impostazione**, selezionare **Parametri di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="31405-130">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="31405-131">Nella scheda **Calendario**, modificare le impostazioni del calendario come necessario.</span><span class="sxs-lookup"><span data-stu-id="31405-131">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="31405-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="31405-132">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="31405-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31405-133">See also</span></span>

- [<span data-ttu-id="31405-134">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="31405-134">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
