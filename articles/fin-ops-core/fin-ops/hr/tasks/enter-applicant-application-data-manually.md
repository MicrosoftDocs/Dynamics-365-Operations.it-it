---
title: Immettere manualmente i dati del candidato e della domanda di lavoro
description: Questa procedura illustra come gestire manualmente informazioni sui candidati e sulla relativa domanda di lavoro.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a897fc64ccd125263b30993c1e24a3c6c67bd63
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144020"
---
# <a name="enter-applicant-and-application-data-manually"></a><span data-ttu-id="390a1-103">Immettere manualmente i dati del candidato e della domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="390a1-103">Enter applicant and application data manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="390a1-104">Questa procedura illustra come gestire manualmente informazioni sui candidati e sulla relativa domanda di lavoro.</span><span class="sxs-lookup"><span data-stu-id="390a1-104">This procedure shows how to manually maintain information about applicants and their application.</span></span>   <span data-ttu-id="390a1-105">È possibile immettere e gestire informazioni personali, date e ore del colloquio, referenze, competenze e richieste di facilitazione per i candidati.</span><span class="sxs-lookup"><span data-stu-id="390a1-105">You can enter and maintain personal information, interview dates and times, references, competencies, and accommodation requests for applicants.</span></span> <span data-ttu-id="390a1-106">È inoltre possibile aggiornare lo stato delle domande di lavoro dei candidati e creare lettere o messaggi di posta elettronica per comunicare con i candidati.</span><span class="sxs-lookup"><span data-stu-id="390a1-106">You can also update the status of applicants' applications for employment and create letters or email messages to communicate with applicants.</span></span> <span data-ttu-id="390a1-107">Quando si crea un record candidato, viene creato un record per il candidato nella Rubrica globale.</span><span class="sxs-lookup"><span data-stu-id="390a1-107">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span>       <span data-ttu-id="390a1-108">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="390a1-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-new-applicant-record"></a><span data-ttu-id="390a1-109">Creare un nuovo record della domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="390a1-109">Create a new applicant record</span></span>
1. <span data-ttu-id="390a1-110">Andare a Risorse umane > Selezione del personale > Candidati > Candidati.</span><span class="sxs-lookup"><span data-stu-id="390a1-110">Go to Human resources > Recruitment > Applicants > Applicants.</span></span>
2. <span data-ttu-id="390a1-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="390a1-111">Click New.</span></span>
3. <span data-ttu-id="390a1-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="390a1-112">In the First name field, type a value.</span></span>
4. <span data-ttu-id="390a1-113">Digitare un valore nel campo Cognome.</span><span class="sxs-lookup"><span data-stu-id="390a1-113">In the Last name field, type a value.</span></span>
    * <span data-ttu-id="390a1-114">È possibile immettere informazioni aggiuntive del candidato se sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="390a1-114">You can enter additional applicant information if it's available.</span></span> <span data-ttu-id="390a1-115">Ad esempio, le informazioni possono includere il titolo di studio più alto del candidato, la posizione corrente o il datore di lavoro precedente.</span><span class="sxs-lookup"><span data-stu-id="390a1-115">For example, information can include the applicant's highest degree, current job title, or previous employer.</span></span>  
5. <span data-ttu-id="390a1-116">Attivare/disattivare l'espansione della sezione Informazioni di contatto.</span><span class="sxs-lookup"><span data-stu-id="390a1-116">Toggle the expansion of the Contact information section.</span></span>
6. <span data-ttu-id="390a1-117">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="390a1-117">Click Add.</span></span>
7. <span data-ttu-id="390a1-118">Nel campo Descrizione digitare "Posta elettronica per le comunicazioni".</span><span class="sxs-lookup"><span data-stu-id="390a1-118">In the Description field, type 'Communications email'.</span></span>
8. <span data-ttu-id="390a1-119">Selezionare un'opzione nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="390a1-119">In the Type field, select an option.</span></span>
9. <span data-ttu-id="390a1-120">Digitare un valore nel campo Numero/indirizzo contatto.</span><span class="sxs-lookup"><span data-stu-id="390a1-120">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="390a1-121">Questo indirizzo di posta elettronica verrà utilizzato per generare comunicazioni con il candidato.</span><span class="sxs-lookup"><span data-stu-id="390a1-121">This email address will be used to generate email communication with the applicant.</span></span>  
10. <span data-ttu-id="390a1-122">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="390a1-122">Click Add.</span></span>
11. <span data-ttu-id="390a1-123">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="390a1-123">In the Description field, type a value.</span></span>
12. <span data-ttu-id="390a1-124">Digitare un valore nel campo Numero/indirizzo contatto.</span><span class="sxs-lookup"><span data-stu-id="390a1-124">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="390a1-125">Informazioni personali del candidato.</span><span class="sxs-lookup"><span data-stu-id="390a1-125">Applicant personal information.</span></span>  
    * <span data-ttu-id="390a1-126">È possibile immettere le informazioni personali aggiuntive per il candidato, se necessario,</span><span class="sxs-lookup"><span data-stu-id="390a1-126">You can enter additional personal information for the applicant, if needed.</span></span> <span data-ttu-id="390a1-127">ad esempio data di nascita, origine etnica, sesso o stato civile.</span><span class="sxs-lookup"><span data-stu-id="390a1-127">For example, this can include birth date, ethnic origin, gender, or marital status.</span></span>  
13. <span data-ttu-id="390a1-128">Nel riquadro azioni fare clic su Competenze.</span><span class="sxs-lookup"><span data-stu-id="390a1-128">On the Action Pane, click Competencies.</span></span>
    * <span data-ttu-id="390a1-129">È possibile immettere il profilo di competenza del candidato, incluse competenze, esperienze professionali, formazione, test o certificati.</span><span class="sxs-lookup"><span data-stu-id="390a1-129">You can enter the applicant's competency profile, including their skills, professional experiences, education, tests, or certificates.</span></span>  
    * <span data-ttu-id="390a1-130">Queste informazioni possono essere utilizzate per eseguire il mapping delle competenze del candidato alle competenze associate alle mansioni definite nei dati della società.</span><span class="sxs-lookup"><span data-stu-id="390a1-130">This information can be used to map the applicant's skills to the skills associated with the jobs defined in your company's data.</span></span>   

## <a name="create-an-application-for-the-applicant"></a><span data-ttu-id="390a1-131">Creare una domanda di lavoro per il candidato</span><span class="sxs-lookup"><span data-stu-id="390a1-131">Create an application for the applicant</span></span>
1. <span data-ttu-id="390a1-132">Fare clic su Domande di lavoro</span><span class="sxs-lookup"><span data-stu-id="390a1-132">Click Applications.</span></span>
2. <span data-ttu-id="390a1-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="390a1-133">Click New.</span></span>
3. <span data-ttu-id="390a1-134">Nel campo Progetto di selezione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="390a1-134">In the Recruitment project field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="390a1-135">Selezionando un progetto di selezione, il candidato verrà associato a una posizione aperta specifica associata al progetto di selezione.</span><span class="sxs-lookup"><span data-stu-id="390a1-135">By selecting a recruitment project, the applicant will be associated with a specific opening included in that recruitment project.</span></span>  
4. <span data-ttu-id="390a1-136">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="390a1-136">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="390a1-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="390a1-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="390a1-138">Per impostazione predefinita, la mansione e il reparto sono basati sul progetto di selezione scelto.</span><span class="sxs-lookup"><span data-stu-id="390a1-138">By default, the job and department are based on the selected recruitment project.</span></span>  
6. <span data-ttu-id="390a1-139">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="390a1-139">Click Save.</span></span>
    * <span data-ttu-id="390a1-140">Dopo aver salvato la domanda di lavoro, è possibile allegarvi documenti, ad esempio esperienza del candidato, premi e lettera di presentazione.</span><span class="sxs-lookup"><span data-stu-id="390a1-140">After saving the application, you can attach documents to it, including the applicant's experience, awards, and cover letter.</span></span>  

