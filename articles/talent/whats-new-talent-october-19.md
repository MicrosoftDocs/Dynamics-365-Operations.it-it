---
title: Novità o modifiche in Dynamics 365 Talent - Core HR (16 ottobre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
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
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d5f2aea5fcc81d0b4c1d8a392a3e56c888440a94
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897398"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-16-2018"></a><span data-ttu-id="ff73b-103">Novità o modifiche in Dynamics 365 Talent - Core HR (16 ottobre 2018)</span><span class="sxs-lookup"><span data-stu-id="ff73b-103">What's new or changed in Dynamics 365 Talent - Core HR (October 16, 2018)</span></span>

<span data-ttu-id="ff73b-104">**Build 8.1.1067**</span><span class="sxs-lookup"><span data-stu-id="ff73b-104">**Build 8.1.1067**</span></span>

<span data-ttu-id="ff73b-105">Questo argomento descrive le funzionalità nuove o modificate di Core HR.</span><span class="sxs-lookup"><span data-stu-id="ff73b-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-managers-to-update-time-off-requests"></a><span data-ttu-id="ff73b-106">Consentire ai responsabili di aggiornare le richieste di permesso</span><span class="sxs-lookup"><span data-stu-id="ff73b-106">Allow managers to update time off requests</span></span>

<span data-ttu-id="ff73b-107">Può essere necessario aggiornare le richieste di permesso dei dipendenti dopo che sono state approvate tramite il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ff73b-107">Employee time off requests may need to be updated after they are approved through the workflow.</span></span> <span data-ttu-id="ff73b-108">In molti casi il responsabile effettua questi aggiornamenti per conto del dipendente.</span><span class="sxs-lookup"><span data-stu-id="ff73b-108">In many cases, the manager makes these updates on the employee’s behalf.</span></span> <span data-ttu-id="ff73b-109">Questa nuova funzionalità offre la possibilità ai responsabili di aggiornare o annullare le richieste di permesso per conto dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ff73b-109">This new feature provides the ability for managers to update time off or cancel time off requests on behalf of their employees.</span></span> <span data-ttu-id="ff73b-110">Questa possibilità è controllata dal parametro **Lavoro svolto per conto di** che può essere impostato nella pagina **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="ff73b-110">This capability is controlled by the **Work on behalf** parameter that can be set on the **Human Resource Parameters** page.</span></span> 
 
## <a name="allow-hr-to-update-time-off-requests"></a><span data-ttu-id="ff73b-111">Consentire alle Risorse umane di aggiornare le richieste di permesso</span><span class="sxs-lookup"><span data-stu-id="ff73b-111">Allow HR to update time off requests</span></span>

<span data-ttu-id="ff73b-112">Analogamente alla funzionalità descritta in precedenza, le richieste di permesso dei dipendenti possono essere aggiornate dalle Risorse umane dopo che sono state in precedenza approvate tramite il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ff73b-112">Similar to the feature above, employee time off requests may need to be updated by HR after they have been previously approved through the workflow.</span></span> <span data-ttu-id="ff73b-113">Questa funzionalità consente agli utenti delle Risorse umane di aggiornare le richieste di permesso.</span><span class="sxs-lookup"><span data-stu-id="ff73b-113">This feature provides the ability for HR users to update time off requests.</span></span> <span data-ttu-id="ff73b-114">Questa possibilità viene attivata nell'area di lavoro **Persone** e nella pagina **Lavoratore**, utilizzando una nuova opzione denominata **Visualizza tempo libero**.</span><span class="sxs-lookup"><span data-stu-id="ff73b-114">The capability is enabled in the **People** workspace and on the **Worker** page, using a new option called **View time off**.</span></span> <span data-ttu-id="ff73b-115">Su tali pagine gli utenti delle Risorse umane potranno visualizzare le richieste e aggiornare le transazioni relative ai permessi, analogamente a come i responsabili possono eseguire queste azioni.</span><span class="sxs-lookup"><span data-stu-id="ff73b-115">On those pages, HR users can view requests and update time off transactions, similar to how managers can perform these actions.</span></span>

<span data-ttu-id="ff73b-116">I diritti di sicurezza che controllano l'accesso a questa funzionalità sono:</span><span class="sxs-lookup"><span data-stu-id="ff73b-116">The security duty that controls access to this functionality is:</span></span>
- <span data-ttu-id="ff73b-117">Diritti: gestire i processi di congedo e assenza specifici del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="ff73b-117">Duty: Maintain worker-specific leave and absence processes.</span></span>
- <span data-ttu-id="ff73b-118">Privilegio: gestire le richieste di congedo e assenza per tutti i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="ff73b-118">Privilege: Maintain leave and absence requests for all workers.</span></span>

## <a name="other-changes"></a><span data-ttu-id="ff73b-119">Altre modifiche</span><span class="sxs-lookup"><span data-stu-id="ff73b-119">Other changes</span></span>
<span data-ttu-id="ff73b-120">I seguenti aggiornamenti sono stati effettuati in questa versione:</span><span class="sxs-lookup"><span data-stu-id="ff73b-120">The following updates have been made in this release:</span></span>
- <span data-ttu-id="ff73b-121">Modifiche alle azioni di assunzione dei lavoratori in modo che non siano più "bloccate" nello stato **Flusso di lavoro completato**.</span><span class="sxs-lookup"><span data-stu-id="ff73b-121">Changes to worker hire actions so that they are no longer "stuck" in **Workflow complete** state.</span></span>
- <span data-ttu-id="ff73b-122">È ora possibile creare il record di impiego senza una data di inizio impiego.</span><span class="sxs-lookup"><span data-stu-id="ff73b-122">Employment record can now be created without an employment start date.</span></span>
- <span data-ttu-id="ff73b-123">La data di registrazione di Dynamics 365 Talent per un corso tenuto in Dipendente self-service applica ora la differenza del fuso orario alla data.</span><span class="sxs-lookup"><span data-stu-id="ff73b-123">The Dynamics 365 Talent registration date for a course shown in Employee self-service now applies the time zone offset to the date.</span></span>
- <span data-ttu-id="ff73b-124">I file di Excel possono essere importati più volte senza alcun errore utilizzando **Dipendenti**.</span><span class="sxs-lookup"><span data-stu-id="ff73b-124">Excel files can be imported multiple times without any errors using **Employee Entity**.</span></span>

## <a name="known-issue"></a><span data-ttu-id="ff73b-125">Problema noto</span><span class="sxs-lookup"><span data-stu-id="ff73b-125">Known issue</span></span>

- <span data-ttu-id="ff73b-126">**Problema**: quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** sono inattivi.</span><span class="sxs-lookup"><span data-stu-id="ff73b-126">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="ff73b-127">**Soluzione alternativa:** prima di aprire la pagina dell'allegato, verificare che le schede dettaglio della pagina **Lavoratore** siano chiuse.</span><span class="sxs-lookup"><span data-stu-id="ff73b-127">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="ff73b-128">Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli allegati saranno abilitati.</span><span class="sxs-lookup"><span data-stu-id="ff73b-128">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="ff73b-129">Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ff73b-129">(This issue will be fixed in the next platform update.)</span></span>
