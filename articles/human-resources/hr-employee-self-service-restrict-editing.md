---
title: Impedire la modifica delle informazioni personali
description: Impedire ai dipendenti di modificare i dettagli di contatto in Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c5e3eeb66d4f32b1fea1a43fff9f5b09d87d1f53
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018711"
---
# <a name="restrict-editing-of-personal-information"></a><span data-ttu-id="66101-103">Impedire la modifica delle informazioni personali</span><span class="sxs-lookup"><span data-stu-id="66101-103">Restrict editing of personal information</span></span>

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

<span data-ttu-id="66101-104">In questo argomento viene descritto come impedire ai dipendenti di modificare i dettagli di contatto in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="66101-104">This topic describes how to restrict employees from editing contact details in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="66101-105">È possibile che si voglia impedire ai dipendenti di modificare determinati dettagli di contatto, come il loro indirizzo e-mail aziendale.</span><span class="sxs-lookup"><span data-stu-id="66101-105">You might want to prevent employees from editing certain contact details, such as their business location or email address.</span></span>

> [!NOTE]
> <span data-ttu-id="66101-106">Per utilizzare questa funzionalità, è necessario dapprima abilitare **(Anteprima) Impedire ai dipendenti di aggiungere o modificare l'indirizzo e le informazioni di contatto per determinati scopi** in Gestione funzionalità.</span><span class="sxs-lookup"><span data-stu-id="66101-106">To use this feature, you must first enable **(Preview) Restrict employees from adding or editing address and contact information for select purposes** in Feature management.</span></span> <span data-ttu-id="66101-107">Per ulteriori informazioni sull'abilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="66101-107">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br><br><span data-ttu-id="66101-108">![Abilita funzionalità di anteprima](./media/hr-employee-self-service-restrict-enable.png)</span><span class="sxs-lookup"><span data-stu-id="66101-108">![Enable preview feature](./media/hr-employee-self-service-restrict-enable.png)</span></span>

## <a name="choose-the-information-an-employee-can-add-or-edit"></a><span data-ttu-id="66101-109">Scegliere le informazioni che un dipendente può aggiungere o modificare</span><span class="sxs-lookup"><span data-stu-id="66101-109">Choose the information an employee can add or edit</span></span>

1. <span data-ttu-id="66101-110">In Human Resources, selezionare **Gestione dipendente**, Selezionare **Collegamenti**, quindi selezionare **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="66101-110">In Human Resources, select **Personnel management**, select **Links**, and then select **Human resources parameters**.</span></span>

   ![Accedere a Parametri Risorse umane](./media/hr-employee-self-service-human-resources-parameters.png)

2. <span data-ttu-id="66101-112">Nella pagina **Parametri Risorse umane**, selezionare la scheda **Dipendente self-service**.</span><span class="sxs-lookup"><span data-stu-id="66101-112">On the **Human resources parameters** page, select the **Employee self service** tab.</span></span>

   ![Selezionare Dipendente self-service](./media/hr-employee-self-service-tab.png)

3. <span data-ttu-id="66101-114">Nella scheda **Dipendente self service**, deselezionare tutte le informazioni nella sezione **Informazioni indirizzo e contatto** che i dipendenti non devono aggiungere o modificare.</span><span class="sxs-lookup"><span data-stu-id="66101-114">On the **Employee self service** tab, uncheck all information in the **Address and contact information** section that you don't want employees to add or edit.</span></span> <span data-ttu-id="66101-115">In questo esempio, abbiamo deselezionato le informazioni di contatto **Attività commerciale**.</span><span class="sxs-lookup"><span data-stu-id="66101-115">In this example, we've unchecked **Business** contact information.</span></span>

   ![Impedire la modifica dell'informazione di contatto Attività commerciale](./media/hr-employee-self-service-restrict-business.png)

4. <span data-ttu-id="66101-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="66101-117">Select **Save**.</span></span>

   ![Salva modifiche](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a><span data-ttu-id="66101-119">Esperienza dei dipendenti</span><span class="sxs-lookup"><span data-stu-id="66101-119">Employee experience</span></span>

<span data-ttu-id="66101-120">Dopo aver impedito ai dipendenti l'aggiunta o la modifica dei dettagli di contatto, questi possono vedere le informazioni, ma non possono modificarle.</span><span class="sxs-lookup"><span data-stu-id="66101-120">After you've restricted employees from adding or editing contact details, they can see the information, but can't change it.</span></span>

<span data-ttu-id="66101-121">In questo esempio, in cui ai dipendenti viene impedito di modificare i dettagli di contatto **Attività commerciale**, questi possono ancora vedere le informazioni in Dipendente self-service:</span><span class="sxs-lookup"><span data-stu-id="66101-121">In this example, where employees are restricted from editing **Business** contact details, they can still see the information in Employee self service:</span></span>

![Visualizzare i dettagli di contatto aziendali](./media/hr-employee-self-service-restrict-view.png)

<span data-ttu-id="66101-123">Tuttavia, quando selezionano i dettagli di contatto aziendali, il riquadro **Modifica indirizzo** viene visualizzato come di sola lettura e non possono modificare alcun campo.</span><span class="sxs-lookup"><span data-stu-id="66101-123">However, when they select the business contact details, the **Edit address** pane appears as read-only, and they can't change any of the fields.</span></span>

![Visualizzazione dei dettagli di contatto aziendali come di sola lettura](./media/hr-employee-self-service-restrict-read-only.png)

<span data-ttu-id="66101-125">Inoltre, se selezionano **Aggiungi** per aggiungere un nuovo indirizzo, non possono selezionare **Attività commerciale** nella casella a discesa **Scopo**.</span><span class="sxs-lookup"><span data-stu-id="66101-125">In addition, if they select **Add** to add a new address, they can't select **Business** from the **Purpose** dropdown box.</span></span>

![Il dipendente non può aggiungere un indirizzo aziendale](./media/hr-employee-self-service-restrict-add.png)

<span data-ttu-id="66101-127">La stessa cosa avviene quando i dipendenti selezionano **Dettagli contatto** nella pagina **Informazioni personali** e aggiungono un nuovo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="66101-127">Employees get the same experience when they select **Contact details** on the **Personal information** page and add a new address.</span></span> <span data-ttu-id="66101-128">La casella a discesa **Scopo** mostra solo i tipi di informazioni che possono aggiungere.</span><span class="sxs-lookup"><span data-stu-id="66101-128">The **Purpose** dropdown box only displays the types of information they can add.</span></span> 

![Il dipendente non può selezionare Attività commerciale nella casella a discesa Scopo](./media/hr-employee-self-service-restrict-purpose.png)

<span data-ttu-id="66101-130">**Dettagli contatto** ora mostra **Scopo** nella griglia.</span><span class="sxs-lookup"><span data-stu-id="66101-130">**Contact details** now shows **Purpose** in the grid.</span></span>

![Scopo visualizzato nella griglia Dettagli contatto](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a><span data-ttu-id="66101-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66101-132">See also</span></span>

[<span data-ttu-id="66101-133">Panoramica del dipendente e del responsabile self-service</span><span class="sxs-lookup"><span data-stu-id="66101-133">Employee and Manager self service overview</span></span>](hr-employee-manager-self-service-overview.md)<br>
[<span data-ttu-id="66101-134">Configurare i parametri di Human Resources</span><span class="sxs-lookup"><span data-stu-id="66101-134">Configure Human resources parameters</span></span>](hr-setup-parameters.md)<br>
[<span data-ttu-id="66101-135">Modifica informazioni personali</span><span class="sxs-lookup"><span data-stu-id="66101-135">Edit personal information</span></span>](hr-employee-manager-self-service-edit-personal-information.md)