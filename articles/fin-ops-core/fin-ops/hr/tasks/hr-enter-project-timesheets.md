---
title: Immettere fogli presenze di progetto
description: Questa procedura consente di creare un foglio presenze utilizzando un modulo vuoto.
author: andreabichsel
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.search.industry: Service industries
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4a600137fc583aef8c85c920ca3cd2949a1a19d
ms.sourcegitcommit: 0cca2f82ae5c91c409e2abbf5867ff4e59ba71d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2021
ms.locfileid: "5055941"
---
# <a name="enter-project-timesheets"></a><span data-ttu-id="bd773-103">Immettere fogli presenze di progetto</span><span class="sxs-lookup"><span data-stu-id="bd773-103">Enter project timesheets</span></span>

<span data-ttu-id="bd773-104">Questa procedura consente di creare un foglio presenze utilizzando un modulo vuoto.</span><span class="sxs-lookup"><span data-stu-id="bd773-104">This procedure lets you create a timesheet by using an empty timesheet form.</span></span> <span data-ttu-id="bd773-105">Il nuovo foglio presenze può essere basato sulle informazioni da un foglio precedente o dalle assegnazioni di progetti e attività della pagina **Preferiti**.</span><span class="sxs-lookup"><span data-stu-id="bd773-105">The new timesheet can be based on information from a previous timesheet, or from project and activity assignments in the **My favorites** page.</span></span> <span data-ttu-id="bd773-106">Per impostazione predefinita, la pagina elenco **Tutti i fogli presenze** visualizza tutti i fogli presenze per il periodo corrente.</span><span class="sxs-lookup"><span data-stu-id="bd773-106">By default, the **All timesheets** list page displays all your timesheets for the current period.</span></span> <span data-ttu-id="bd773-107">È possibile utilizzare l'elenco a discesa del campo **Mostra** nella pagina **Fogli presenze personali** per filtrare l'elenco dei fogli presenze in base al periodo o al progetto o per visualizzare i fogli presenze creati per conto di altri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="bd773-107">You can use the drop-down list for the **Show** field in the **My timesheets** page to filter the timesheet list by time period or project, or to view timesheets that were created on behalf of other workers.</span></span> <span data-ttu-id="bd773-108">La società di dati dimostrativi utilizzata per creare questa procedura è USSI.</span><span class="sxs-lookup"><span data-stu-id="bd773-108">The demo data company used to create this procedure is USSI.</span></span>  

1. <span data-ttu-id="bd773-109">Nel **pannello di navigazione**, andare a **Moduli > Gestione progetti e contabilità > Fogli presenze > Fogli presenze personali**.</span><span class="sxs-lookup"><span data-stu-id="bd773-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Timesheets > My timesheets**.</span></span>
2. <span data-ttu-id="bd773-110">Per immettere un nuovo foglio presenze, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bd773-110">To enter a new timesheet, click **New**.</span></span>
    - <span data-ttu-id="bd773-111">Nell'elenco a discesa Risorsa viene visualizzato il lavoratore assegnato all'utente corrente, per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bd773-111">The Resource drop-down list shows the worker assigned to the current user, by default.</span></span>  
    - <span data-ttu-id="bd773-112">Se l'utente è definito come delegato, verranno elencati i nomi in modo che un utente può immettere un foglio presenze in vece di altri.</span><span class="sxs-lookup"><span data-stu-id="bd773-112">If the user is designated as a delegate, this will list the names so that a user can enter a timesheet on their behalf.</span></span>  
3. <span data-ttu-id="bd773-113">Nel campo **Data** immettere una data.</span><span class="sxs-lookup"><span data-stu-id="bd773-113">In the **Date** field, enter a date.</span></span> <span data-ttu-id="bd773-114">Se l'opzione è selezionata, le nuove righe del foglio presenze verranno create utilizzando le impostazioni del foglio presenze che sono state configurate come preferite.</span><span class="sxs-lookup"><span data-stu-id="bd773-114">If this option is selected, new timesheet lines will be created by using the timesheet settings that were configured as favorites.</span></span>  
4. <span data-ttu-id="bd773-115">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd773-115">Click **OK**.</span></span>
5. <span data-ttu-id="bd773-116">Fare clic su **Nuova riga**.</span><span class="sxs-lookup"><span data-stu-id="bd773-116">Click **New line**.</span></span>
6. <span data-ttu-id="bd773-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bd773-117">In the list, mark the selected row.</span></span> <span data-ttu-id="bd773-118">Nel campo **Persona giuridica** viene visualizzata la persona giuridica corrente per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bd773-118">The **Legal Entity** field displays the current Legal entity by default.</span></span>   
7. <span data-ttu-id="bd773-119">Nel campo **Progetto** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bd773-119">In the **Project** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="bd773-120">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd773-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="bd773-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bd773-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="bd773-122">Nel campo **Numero attività** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bd773-122">In the **Activity number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="bd773-123">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="bd773-123">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="bd773-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bd773-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="bd773-125">Nel campo **Categoria** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bd773-125">In the **Category** field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="bd773-126">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bd773-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="bd773-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bd773-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="bd773-128">Immettere il numero di ore lavorative per ogni giorno.</span><span class="sxs-lookup"><span data-stu-id="bd773-128">Enter the number of hours worked each day.</span></span> <span data-ttu-id="bd773-129">Immettere le ore in un formato decimale.</span><span class="sxs-lookup"><span data-stu-id="bd773-129">Enter the hours in decimal format.</span></span> <span data-ttu-id="bd773-130">Se ad esempio si è lavorato per due ore e quindici minuti, immettere 2,25.</span><span class="sxs-lookup"><span data-stu-id="bd773-130">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
17. <span data-ttu-id="bd773-131">In **Dettagli riga** sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="bd773-131">In **Line details**, the following options are available:</span></span>
    - <span data-ttu-id="bd773-132">Aggiungere informazioni sulle dimensioni finanziarie e sulle imposte in **Generale** e nella scheda **Dimensioni finanziarie**.</span><span class="sxs-lookup"><span data-stu-id="bd773-132">Add information about taxes and financial dimensions in the **General** and the **Financial Dimensions** tab.</span></span>
    - <span data-ttu-id="bd773-133">Aggiungere commenti sulla riga del foglio presenze nella scheda **Commento**.</span><span class="sxs-lookup"><span data-stu-id="bd773-133">Add comments about the timesheet line in the **Comment** tab.</span></span>
20. <span data-ttu-id="bd773-134">Nel **Riquadro azioni**, fare clic su **Flusso di lavoro** per aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="bd773-134">In the **Action pane**, click **Workflow** to open the drop dialog.</span></span>
21. <span data-ttu-id="bd773-135">Fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="bd773-135">Click **Submit**.</span></span>
22. <span data-ttu-id="bd773-136">Fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="bd773-136">Click **Submit**.</span></span>
