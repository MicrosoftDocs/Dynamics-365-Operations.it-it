---
title: Configurare i parametri di congedo e assenza
description: Definire i parametri delle risorse umane per congedo e assenza in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009525"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="5b752-103">Configurare i parametri di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="5b752-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="5b752-104">Prima di impostare i piani di congedo e assenza in Dynamics 365 Human Resources, è una buona idea verificare le impostazioni per tutti i parametri delle risorse umane correlati, tra cui:</span><span class="sxs-lookup"><span data-stu-id="5b752-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="5b752-105">La sequenza numerica per richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="5b752-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="5b752-106">Impostazioni relative alla normativa per il congedo per motivi medici e familiari (FMLA)</span><span class="sxs-lookup"><span data-stu-id="5b752-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="5b752-107">Impostazioni di Dipendente self-service per richieste di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="5b752-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="5b752-108">Parametri di congedi e assenze</span><span class="sxs-lookup"><span data-stu-id="5b752-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="5b752-109">Visualizzare e modificare parametri delle risorse umane</span><span class="sxs-lookup"><span data-stu-id="5b752-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="5b752-110">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5b752-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="5b752-111">Sotto **Impostazione**, selezionare **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="5b752-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="5b752-112">Nella scheda **Sequenze numeriche**, verificare il **Codice sequenza numerica** per **ID richiesta congedo** e modificare come necessario.</span><span class="sxs-lookup"><span data-stu-id="5b752-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="5b752-113">Questa impostazione determina la sequenza utilizzata per assegnare automaticamente gli ID alle richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="5b752-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="5b752-114">Nella scheda **FMLA**, verificare le impostazioni FMLA e modificare come necessario.</span><span class="sxs-lookup"><span data-stu-id="5b752-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="5b752-115">Nella scheda **Dipendente self-service**, indicare se i manager possono immettere richieste di congedo e assenza per conto dei propri dipendenti.</span><span class="sxs-lookup"><span data-stu-id="5b752-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="5b752-116">Nella scheda **Congedo e assenza**, verificare le impostazioni e modificare come necessario.</span><span class="sxs-lookup"><span data-stu-id="5b752-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="5b752-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b752-117">Select **Save**.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="5b752-118">Configurare i parametri del calendario</span><span class="sxs-lookup"><span data-stu-id="5b752-118">Configure calendar parameters</span></span>

<span data-ttu-id="5b752-119">Se è stata abilitata la funzione di anteprima Calendario congedo e assenza, è necessario configurare parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="5b752-119">If you have enabled the Leave and absence calendar preview feature, you need to configure additional parameters.</span></span> 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> <span data-ttu-id="5b752-120">Per la versione di anteprima del 3 febbraio 2020, solo le **Richieste di congedo in sospeso** sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="5b752-120">For the preview release on February 3, 2020, only **Pending leave requests** are enabled.</span></span>

1. <span data-ttu-id="5b752-121">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5b752-121">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="5b752-122">Sotto **Impostazione**, selezionare **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="5b752-122">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="5b752-123">Nella scheda **Calendario**, modificare le impostazioni del calendario come necessario.</span><span class="sxs-lookup"><span data-stu-id="5b752-123">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="5b752-124">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5b752-124">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b752-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b752-125">See also</span></span>

- [<span data-ttu-id="5b752-126">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="5b752-126">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)