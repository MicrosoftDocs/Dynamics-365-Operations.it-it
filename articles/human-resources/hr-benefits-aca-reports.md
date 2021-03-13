---
title: Generare report Affordable Care Act (ACA)
description: La rendicontazione Affordable Care Act (ACA) genera i moduli 1095-B e 1095-C a sostegno della quota **Mandato del datore di lavoro** dell'Affordable Care Act.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 56ff879603a31956db877b45aec11b15371b69f5
ms.sourcegitcommit: 5c1b5ef40ce7359b3f1955535a250718d863badb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "5142158"
---
# <a name="generate-aca-reports"></a><span data-ttu-id="92b18-103">Generare report ACA</span><span class="sxs-lookup"><span data-stu-id="92b18-103">Generate ACA reports</span></span>

<span data-ttu-id="92b18-104">La rendicontazione Affordable Care Act (ACA) genera i moduli 1095-B e 1095-C a sostegno della quota **Mandato del datore di lavoro** dell'Affordable Care Act.</span><span class="sxs-lookup"><span data-stu-id="92b18-104">Affordable Care Act (ACA) reporting generates forms 1095-B and 1095-C in support of the **Employer Mandate** portion of the Affordable Care Act.</span></span>

> [!NOTE]
> <span data-ttu-id="92b18-105">La rendicontazione ACA è abilitato solo per le persone giuridiche negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="92b18-105">ACA reporting is only enabled for legal entities in the United States.</span></span>

## <a name="getting-started"></a><span data-ttu-id="92b18-106">Introduzione</span><span class="sxs-lookup"><span data-stu-id="92b18-106">Getting started</span></span>

<span data-ttu-id="92b18-107">Per tenere traccia delle informazioni per i moduli 1095-B e 1095-C, creare prima uno o più gruppi di copertura Affordable Care.</span><span class="sxs-lookup"><span data-stu-id="92b18-107">To track information for forms 1095-B and 1095-C, you must first create one or more Affordable care coverage groups.</span></span> <span data-ttu-id="92b18-108">I gruppi di copertura Affordable Care indicano:</span><span class="sxs-lookup"><span data-stu-id="92b18-108">Affordable Care coverage groups indicate:</span></span>

- <span data-ttu-id="92b18-109">L'offerta di copertura per un dipendente</span><span class="sxs-lookup"><span data-stu-id="92b18-109">The offer of coverage for an employee</span></span>
- <span data-ttu-id="92b18-110">La quota del dipendente del premio mensile più basso, se il costo è superiore alla soglia di povertà federale</span><span class="sxs-lookup"><span data-stu-id="92b18-110">The employee’s share of the lowest cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="92b18-111">Safe Harbor utilizzato dal datore di lavoro, se applicabile</span><span class="sxs-lookup"><span data-stu-id="92b18-111">Safe Harbor used by the employer, if applicable</span></span>

<span data-ttu-id="92b18-112">I gruppi di copertura Affordable Care consente di gestire le informazioni relative a questi campi senza dover cambiare record dipendente per il quale le condizioni siano identiche.</span><span class="sxs-lookup"><span data-stu-id="92b18-112">Affordable Care coverage groups allow you to manage the information for these fields without changing every employee record where the conditions are the same.</span></span> <span data-ttu-id="92b18-113">Puoi facilmente assegnare gruppi di copertura Affordable Care a uno o più dipendenti utilizzando l'opzione **Assegnazione di massa** nella pagina.</span><span class="sxs-lookup"><span data-stu-id="92b18-113">You can easily assign Affordable Care coverage groups to one or more employees by using the **Mass assign** option on the page.</span></span>

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a><span data-ttu-id="92b18-114">Gestione di più versioni di un gruppo di copertura</span><span class="sxs-lookup"><span data-stu-id="92b18-114">Maintaining multiple versions of a coverage group</span></span>

<span data-ttu-id="92b18-115">Puoi mantenere più versioni di qualsiasi gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="92b18-115">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="92b18-116">Questa funzionalità consente di apportare modifiche senza dover creare un nuovo gruppo e riassegnarvi i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="92b18-116">This functionality allows you to make changes without having to create a new group and reassign employees to it.</span></span> 

<span data-ttu-id="92b18-117">Dopo aver creato i gruppi di copertura ACA, è possibile assegnare in massa i gruppi ai dipendenti con l'opzione **Assegnazione di massa**.</span><span class="sxs-lookup"><span data-stu-id="92b18-117">After you’ve created ACA coverage groups, you can mass assign the groups to employees with the **Mass assignment** option.</span></span> <span data-ttu-id="92b18-118">Puoi anche indicare singolarmente se monitorare e segnalare le informazioni ACA e assegnare un dipendente a un gruppo di copertura Affordable Care.</span><span class="sxs-lookup"><span data-stu-id="92b18-118">You can also individually indicate whether to track and report ACA information, and assign an employee to an Affordable Care coverage group.</span></span>

<span data-ttu-id="92b18-119">Non è necessario tenere traccia di alcune informazioni sulla copertura ACA, ad esempio per i dipendenti part-time.</span><span class="sxs-lookup"><span data-stu-id="92b18-119">You don't need to track some ACA coverage information, such as for part-time employees.</span></span> <span data-ttu-id="92b18-120">In questo caso, imposta il campo **Copertura del rapporto** su **No**.</span><span class="sxs-lookup"><span data-stu-id="92b18-120">In this case, set the **Report coverage** field to **No**.</span></span> <span data-ttu-id="92b18-121">Sebbene sia necessario assegnare a ciascun dipendente informazioni ACA tracciabili a un gruppo di copertura Affordable Care, puoi comunque modificare le seguenti opzioni per mesi con valori diversi:</span><span class="sxs-lookup"><span data-stu-id="92b18-121">Although you must assign each employee with trackable ACA information to an Affordable Care coverage group, you can still change the following options for months with different values:</span></span>

- <span data-ttu-id="92b18-122">**Offerta di copertura**</span><span class="sxs-lookup"><span data-stu-id="92b18-122">**Offer of coverage**</span></span>
- <span data-ttu-id="92b18-123">**Quota costo dipendente**</span><span class="sxs-lookup"><span data-stu-id="92b18-123">**Employee share of cost**</span></span>
- <span data-ttu-id="92b18-124">**Safe Harbor**</span><span class="sxs-lookup"><span data-stu-id="92b18-124">**Safe Harbor**</span></span>

<span data-ttu-id="92b18-125">Per immettere le eccezioni per i valori di gruppo di copertura Affordable Care, seleziona il collegamento **Copertura Affordable Care** nella pagina **Dettagli lavoratore**, che si trova sotto la sezione **Informazioni aggiuntive** nella **scheda Impiego**.</span><span class="sxs-lookup"><span data-stu-id="92b18-125">To enter exceptions for Affordable Care coverage group values, select the **Affordable Care Coverage** link on the **Worker detail** page under the **Additional information** section on the **Employment tab**.</span></span>

## <a name="reporting-health-care-coverage"></a><span data-ttu-id="92b18-126">Report di copertura delle spese mediche</span><span class="sxs-lookup"><span data-stu-id="92b18-126">Reporting health care coverage</span></span>

<span data-ttu-id="92b18-127">Oltre a tenere traccia di qualsiasi copertura di assicurazione sanitaria offerta a dipendenti a tempo pieno, se il datore di lavoro offre una copertura sanitaria autoassicurata patrocinata dal datore di lavoro per cui il dipendente è iscritto (indipendentemente dal fatto che si tratti di un dipendente a tempo pieno o parziale), le informazioni aggiuntive devono essere dichiarate nel modulo 1095-C.</span><span class="sxs-lookup"><span data-stu-id="92b18-127">In addition to tracking health insurance coverage offered to full-time employees, if the employer offers employer-sponsored self-insured health coverage for which the employee is enrolled (regardless of whether their employment status is full-time or part-time), additional information needs to be reported on the 1095-C.</span></span> <span data-ttu-id="92b18-128">Ciascun dipendente (dipendenti inclusi) coperto dai piani di benefit patrocinati da datore di lavoro deve essere incluso nel report per i mesi per cui sono stati coperti.</span><span class="sxs-lookup"><span data-stu-id="92b18-128">Each employee (including dependents) covered by the employer-sponsored benefit plans needs to be included on the report for the months they were covered.</span></span> 

<span data-ttu-id="92b18-129">Puoi indicare se si desidera che ciascun piano di benefit debba essere dichiarato selezionando la casella di controllo **Dichiarabile all'ACA**.</span><span class="sxs-lookup"><span data-stu-id="92b18-129">You can indicate whether or not each benefit plan must be reported by selecting the **ACA reportable** check box.</span></span>

<span data-ttu-id="92b18-130">Inoltre, se i dipendenti hanno scelto di avere uno dei relativi dipendenti coperti da un benefit, è possibile indicare le date in cui il dipendente era coperto per ciascun dipendente nella pagina **Gestisci benefit**.</span><span class="sxs-lookup"><span data-stu-id="92b18-130">In addition, if employees have chosen to have any of their dependents covered under a benefit, you can indicate the dates the dependent was covered for each employee on the **Maintain benefits** page.</span></span> <span data-ttu-id="92b18-131">Per indicare che il dipendente è coperto dal benefit, seleziona il pulsante **Modifica** nel riquadro azioni della Scheda dettaglio **Dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="92b18-131">To indicate that the dependent is covered under the benefit, select the **Edit** button in the action pane of the **Dependents** fast tab.</span></span>

<span data-ttu-id="92b18-132">Nella pagina **Gestione date di copertura persone a carico**, è possibile indicare le date in cui il dipendente è stato coperto dal benefit.</span><span class="sxs-lookup"><span data-stu-id="92b18-132">On the **Dependent coverage date manager** page, you can indicate the dates the dependent was covered by the benefit.</span></span> <span data-ttu-id="92b18-133">Immettendo le date in questa pagina verrà automaticamente selezionata la casella di controllo **Coperto** nella pagina **Gestisci benefit**.</span><span class="sxs-lookup"><span data-stu-id="92b18-133">Entering dates on this page will automatically select the **Covered** checkbox on the **Maintain benefits** page.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="92b18-134">Genera moduli 1095-B e 1095-C</span><span class="sxs-lookup"><span data-stu-id="92b18-134">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="92b18-135">Puoi inoltre generare i moduli 1095-B e 1095-C dal prodotto e distribuirli a ciascuno dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="92b18-135">You can also generate 1095-B and 1095-C forms from within the product, and distribute them to each of your employees.</span></span> <span data-ttu-id="92b18-136">Il sistema può anche generare elettronicamente moduli 1095-C e file di trasmissione IRS 1094-C.</span><span class="sxs-lookup"><span data-stu-id="92b18-136">The system can also electronically generate 1095-C forms and the 1094-C IRS transmittal files.</span></span>  

<span data-ttu-id="92b18-137">Durante la generazione del modulo 1095-C, immettere l'anno fiscale appropriato e indicare se i numeri di previdenza sociale devono essere mascherati.</span><span class="sxs-lookup"><span data-stu-id="92b18-137">When generating the 1095-C form, enter the appropriate tax year and indicate if social security numbers should be masked.</span></span> <span data-ttu-id="92b18-138">Quando si stampano moduli 1095-C per più di 500 dipendenti, si riceveranno più di un file PDF.</span><span class="sxs-lookup"><span data-stu-id="92b18-138">If you're printing 1095-C forms for more than 500 employees, you'll receive more than one PDF file.</span></span> <span data-ttu-id="92b18-139">Si consiglia di aumentare il valore **Dimensioni massime di file** nella finestra **Parametri di gestione documenti** a 150 MB.</span><span class="sxs-lookup"><span data-stu-id="92b18-139">It’s recommended that you increase the **Maximum file size** in the **Document management parameters** window to 150 MB.</span></span>

## <a name="viewing-information"></a><span data-ttu-id="92b18-140">Visualizzazione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="92b18-140">Viewing information</span></span>

<span data-ttu-id="92b18-141">È possibile utilizzare la pagina **Copertura Affordable Care Act del lavoratore** per visualizzare i dipendenti assegnati a ciascun gruppo di copertura, quelli che non devono essere inclusi in un report e i dipendenti che non sono assegnati.</span><span class="sxs-lookup"><span data-stu-id="92b18-141">You can use the **Worker Affordable Care coverage** page to see which employees have been assigned to each coverage group, which employees don’t need to be included on a report, and which employees are unassigned.</span></span>

<span data-ttu-id="92b18-142">Se uno qualsiasi dei valori predefiniti del gruppo di copertura Affordable Care viene sovrascritto, un asterisco verrà visualizzato accanto al valore modificato.</span><span class="sxs-lookup"><span data-stu-id="92b18-142">If any of the default values from the Affordable Care coverage group have been overridden, an asterisk will appear next to the value that was changed.</span></span> <span data-ttu-id="92b18-143">Se i valori per tutti i 12 mesi sono uguali e non sono stati ignorati, il valore verrà stampato nella colonna **Tutti i 12 mesi**.</span><span class="sxs-lookup"><span data-stu-id="92b18-143">If the values for all 12 months are the same and haven’t been overridden, the value will print in the **All 12 months** column.</span></span>

<span data-ttu-id="92b18-144">Puoi, inoltre, utilizzare la finestra di richiesta per capire quali dipendenti sono stati contrassegnati come non soggetti a comunicazione ACA.</span><span class="sxs-lookup"><span data-stu-id="92b18-144">You can also use the inquiry window to understand which employees have been flagged as not ACA reportable.</span></span> <span data-ttu-id="92b18-145">Non è necessario monitorare se è stata offerta loro la copertura e non sarà necessario emettere un 1095-C alla fine dell'anno.</span><span class="sxs-lookup"><span data-stu-id="92b18-145">You don’t need to track whether coverage was offered to them and won't need to issue a 1095-C to them at the end of the year.</span></span> <span data-ttu-id="92b18-146">Seleziona **Non segnalabile ACA** nel campo **Filtra per** per generare un elenco di tutti i dipendenti che non riceveranno un 1095-C.</span><span class="sxs-lookup"><span data-stu-id="92b18-146">Select **Not ACA reportable** in the **Filter by** field to generate a list of all employees who won't receive a 1095-C.</span></span>

<span data-ttu-id="92b18-147">Oltre a visualizzare i dipendenti che non sono assegnati (il campo **Dichiara copertura ACA** è vuoto) o assegnati a un gruppo di copertura Affordable Care che è scaduto per l'anno selezionato nel campo **Anno**.</span><span class="sxs-lookup"><span data-stu-id="92b18-147">In addition, you can view any employees who are unassigned (the **ACA Report coverage** field is empty) or who have been assigned to an Affordable Care coverage group that is expired for the year selected in the **Year** field.</span></span>

<span data-ttu-id="92b18-148">È possibile esportare gli elenchi di dipendenti generati mediante una delle opzioni di filtro in Excel.</span><span class="sxs-lookup"><span data-stu-id="92b18-148">You can export lists of employees that were generated using any of the filtering options to Excel.</span></span>

<span data-ttu-id="92b18-149">Se devi segnalare le persone coperte perché fornisci una copertura autoassicurata, puoi visualizzare qualsiasi dipendente coperto da piani di benefit che sono contrassegnati come **Non segnalabile ACA**.</span><span class="sxs-lookup"><span data-stu-id="92b18-149">If you need to report covered individuals because you provide self-insured coverage, you can view any dependents covered under benefit plans marked as **ACA reportable**.</span></span> <span data-ttu-id="92b18-150">Seleziona **Visualizza copertura dipendente** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="92b18-150">Select **View Dependent coverage** on the action pane.</span></span>

> [!NOTE]
> <span data-ttu-id="92b18-151">Solo i piani di benefit contrassegnati come **Segnalabile ACA** vengono visualizzati nella finestra di richiesta di informazioni.</span><span class="sxs-lookup"><span data-stu-id="92b18-151">Only benefit plans marked as **ACA reportable** display in the inquiry window.</span></span>
