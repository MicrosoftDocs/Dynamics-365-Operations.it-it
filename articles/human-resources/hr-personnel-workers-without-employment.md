---
title: Lavoratori senza impiego
description: I lavoratori senza impiego futuro, attivo o storico con la tua organizzazione compaiono nel modulo Lavoratori senza impiego.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1a137de25924f4c4ec6f6b1fe70f9d21af591c0
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924573"
---
# <a name="workers-without-employment"></a><span data-ttu-id="5a7af-103">Lavoratori senza impiego</span><span class="sxs-lookup"><span data-stu-id="5a7af-103">Workers without employment</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5a7af-104">I lavoratori senza impiego futuro, attivo o storico con la tua organizzazione compaiono nel modulo **Lavoratori senza impiego**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-104">Workers with no future, active, or historical employment with your organization appear in the **Workers without employment** form.</span></span> <span data-ttu-id="5a7af-105">I lavoratori con questo stato possono essere visualizzati quando si importano lavoratori senza un record di impiego o quando si elimina l'impiego di un lavoratore tramite **Lavoratori > Storico esperienze lavorative**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-105">Workers with this status can appear when you import workers without an employment record, or when you delete a worker's employment via **Workers > Employment history**.</span></span>

<span data-ttu-id="5a7af-106">Per impostazione predefinita, il modulo **Lavoratori senza impiego** è disponibile per i seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="5a7af-106">By default, the **Workers without employment** form is available to the following roles:</span></span>

- <span data-ttu-id="5a7af-107">Assistente risorse umane</span><span class="sxs-lookup"><span data-stu-id="5a7af-107">Human Resources Assistant</span></span>
- <span data-ttu-id="5a7af-108">Responsabile risorse umane</span><span class="sxs-lookup"><span data-stu-id="5a7af-108">Human Resources Manager</span></span>
- <span data-ttu-id="5a7af-109">Selezionatore</span><span class="sxs-lookup"><span data-stu-id="5a7af-109">Recruiter</span></span>
- <span data-ttu-id="5a7af-110">Responsabile retribuzioni e benefit</span><span class="sxs-lookup"><span data-stu-id="5a7af-110">Comp and Benefits Manager</span></span>
- <span data-ttu-id="5a7af-111">Amministratore retribuzioni</span><span class="sxs-lookup"><span data-stu-id="5a7af-111">Payroll Administrator</span></span>
- <span data-ttu-id="5a7af-112">Responsabile retribuzioni</span><span class="sxs-lookup"><span data-stu-id="5a7af-112">Payroll Manager</span></span>
- <span data-ttu-id="5a7af-113">Responsabile formazione</span><span class="sxs-lookup"><span data-stu-id="5a7af-113">Training Manager</span></span>

<span data-ttu-id="5a7af-114">Nell'elenco **Lavoratori senza impiego**, puoi eliminare le persone elencate.</span><span class="sxs-lookup"><span data-stu-id="5a7af-114">In the **Workers without employment** list, you can delete the individuals listed.</span></span> <span data-ttu-id="5a7af-115">Per impostazione predefinita, questo privilegio viene assegnato al ruolo di Assistente risorse umane.</span><span class="sxs-lookup"><span data-stu-id="5a7af-115">By default, this privilege is given to the Human Resources Assistant role.</span></span> <span data-ttu-id="5a7af-116">Puoi assegnare questo privilegio ad altri ruoli con i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="5a7af-116">You can give this privilege to other roles with the following steps:</span></span>

1. <span data-ttu-id="5a7af-117">Selezionare **Amministrazione sistema** e quindi **Configurazione sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-117">Select **System administration**, and then select **Security configuration**.</span></span>

2. <span data-ttu-id="5a7af-118">Nella scheda **Privilegi**, filtrare l'elenco **Privilegi** in base a **Gestisci lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-118">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>

   <span data-ttu-id="5a7af-119">[![Filtra l'elenco dei privilegi](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span><span class="sxs-lookup"><span data-stu-id="5a7af-119">[![Filter Privileges list](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span></span>

3. <span data-ttu-id="5a7af-120">Nella colonna **Riferimenti**, selezionare colonna, selezionare **Voci di menu Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-120">In the **References** column, select **Display menu items**.</span></span>

4. <span data-ttu-id="5a7af-121">In **Voci di menu Visualizza**, selezionare **HcmWorkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-121">In **Display menu items**, select **HcmWorkersWithoutEmployment**.</span></span>

   <span data-ttu-id="5a7af-122">[![Seleziona modulo](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span><span class="sxs-lookup"><span data-stu-id="5a7af-122">[![Select form](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span></span>

5. <span data-ttu-id="5a7af-123">Impostare l'autorizzazione **Elimina** su **Concedi**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-123">Set the **Delete** permission to **Grant**.</span></span>

6. <span data-ttu-id="5a7af-124">Selezionare la scheda **Oggetti non pubblicati**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-124">Select the **Unpublished objects** tab.</span></span>

7. <span data-ttu-id="5a7af-125">Selezionare **Pubblica tutto**.</span><span class="sxs-lookup"><span data-stu-id="5a7af-125">Select **Publish all**.</span></span>

   <span data-ttu-id="5a7af-126">[![Pubblica modifiche](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span><span class="sxs-lookup"><span data-stu-id="5a7af-126">[![Publish changes](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]