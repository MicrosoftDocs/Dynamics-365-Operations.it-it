--- 
title: Gestire le configurazioni di mapping modello per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato con il ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può gestire mapping di modello ER in configurazioni ER separate."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5c6804291752b6a187b2855c2a8feb92181dca24
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="manage-model-mapping-configurations-for-electronic-reporting-er"></a><span data-ttu-id="a1a79-103">Gestire le configurazioni di mapping modello per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="a1a79-103">Manage model mapping configurations for electronic reporting (ER)</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a1a79-104">I passaggi seguenti illustrano come un utente assegnato con il ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può gestire mapping di modello ER in configurazioni ER separate.</span><span class="sxs-lookup"><span data-stu-id="a1a79-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="a1a79-105">In questa guida attività verranno create le configurazioni ER necessarie per la società di esempio Litware, Inc. Per completare questa guida attività, è necessario prima completare i passaggi della guida attività "ER Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="a1a79-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, “ER Create a configuration provider” and mark it as active.</span></span> 

<span data-ttu-id="a1a79-106">Poiché le configurazioni ER sono condivise tra le società, è possibile completare questa guida attività utilizzando il set di dati della società scelta.</span><span class="sxs-lookup"><span data-stu-id="a1a79-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="a1a79-107">La funzionalità di questa guida attività è disponibile se è stato installato uno dei seguenti aggiornamenti rapidi: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 per la versione Dynamics AX 7.0 o https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 per la versione Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="a1a79-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="a1a79-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="a1a79-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="a1a79-109">Verificare che il provider di configurazione per la società di esempio 'Litware, Inc.' sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="a1a79-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="a1a79-110">Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo" nella guida attività.</span><span class="sxs-lookup"><span data-stu-id="a1a79-110">If you don’t see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="a1a79-111">Aggiungere una nuova configurazione del modello ER</span><span class="sxs-lookup"><span data-stu-id="a1a79-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="a1a79-112">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="a1a79-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="a1a79-113">Aggiungere una nuova configurazione del modello.</span><span class="sxs-lookup"><span data-stu-id="a1a79-113">Add a new model configuration.</span></span> <span data-ttu-id="a1a79-114">Il nome deve essere univoco nella struttura delle configurazioni.</span><span class="sxs-lookup"><span data-stu-id="a1a79-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="a1a79-115">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="a1a79-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="a1a79-116">Nel campo Nome digitare "Modello dati di esempio".</span><span class="sxs-lookup"><span data-stu-id="a1a79-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="a1a79-117">Modello dati di esempio</span><span class="sxs-lookup"><span data-stu-id="a1a79-117">Sample data model</span></span>  
4. <span data-ttu-id="a1a79-118">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-118">Click Create configuration.</span></span>
5. <span data-ttu-id="a1a79-119">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-119">Click Designer.</span></span>
6. <span data-ttu-id="a1a79-120">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="a1a79-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="a1a79-121">Digitare 'Nodo principale' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="a1a79-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="a1a79-122">Nodo principale</span><span class="sxs-lookup"><span data-stu-id="a1a79-122">Root</span></span>  
8. <span data-ttu-id="a1a79-123">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a1a79-123">Click Add.</span></span>
9. <span data-ttu-id="a1a79-124">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="a1a79-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="a1a79-125">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="a1a79-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="a1a79-126">Società</span><span class="sxs-lookup"><span data-stu-id="a1a79-126">Company</span></span>  
11. <span data-ttu-id="a1a79-127">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="a1a79-127">Click Add.</span></span>
12. <span data-ttu-id="a1a79-128">Nel campo Descrizione, immettere la descrizione della persona giuridica o della società in cui un utente ha eseguito l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="a1a79-129">Descrizione della persona giuridica o della società a cui un utente ha eseguito l'accesso in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="a1a79-130">Fare clic su Riferimento radice.</span><span class="sxs-lookup"><span data-stu-id="a1a79-130">Click Root reference.</span></span>
14. <span data-ttu-id="a1a79-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1a79-131">Click OK.</span></span>
15. <span data-ttu-id="a1a79-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a1a79-132">Click Save.</span></span>
16. <span data-ttu-id="a1a79-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a1a79-133">Close the page.</span></span>
17. <span data-ttu-id="a1a79-134">Fare clic su Cambia stato.</span><span class="sxs-lookup"><span data-stu-id="a1a79-134">Click Change status.</span></span>
18. <span data-ttu-id="a1a79-135">Fare clic su Completa.</span><span class="sxs-lookup"><span data-stu-id="a1a79-135">Click Complete.</span></span>
19. <span data-ttu-id="a1a79-136">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1a79-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="a1a79-137">Aggiungere una nuova configurazione del mapping di modello ER</span><span class="sxs-lookup"><span data-stu-id="a1a79-137">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="a1a79-138">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="a1a79-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="a1a79-139">Nel campo Nuovo immettere "Mapping modello in base al modello dati di esempio".</span><span class="sxs-lookup"><span data-stu-id="a1a79-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="a1a79-140">Nel campo Nome digitare "Mapping di esempio".</span><span class="sxs-lookup"><span data-stu-id="a1a79-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="a1a79-141">Mapping di esempio</span><span class="sxs-lookup"><span data-stu-id="a1a79-141">Sample mapping</span></span>  
4. <span data-ttu-id="a1a79-142">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-142">Click Create configuration.</span></span>
5. <span data-ttu-id="a1a79-143">Espandere la sezione Prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="a1a79-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="a1a79-144">Si noti che il gruppo di prerequisiti Implementazioni è stato aggiunto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a1a79-144">Note that the Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="a1a79-145">Questo gruppo include il componente di prerequisiti che fa riferimento alla configurazione del modello dati padre ed è contrassegnato come Implementazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="a1a79-146">Ciò significa che la configurazione di mapping di modello Mapping di esempio viene considerata l'implementazione del modello dati Modello dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="a1a79-146">This means that this Sample mapping model mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="a1a79-147">Di conseguenza, questo componente comporterà il download da parte di ER della configurazione del mapping di modello da un archivio quando viene scaricata la configurazione del modello dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="a1a79-147">Therefore, this component will force ER to download the model mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="a1a79-148">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-148">Click Designer.</span></span>
    * <span data-ttu-id="a1a79-149">Si noti che la configurazione di mapping di modello creata contiene un nuovo mapping vuoto con lo stesso nome della configurazione creata.</span><span class="sxs-lookup"><span data-stu-id="a1a79-149">Note that the created model mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="a1a79-150">Tenere presente che quando una configurazione di modelli padre selezionata contiene mapping di modello, questi ultimi verranno copiati in una nuova configurazione di mapping di modello.</span><span class="sxs-lookup"><span data-stu-id="a1a79-150">Be aware that when a selected parent model configuration contains model mappings, they will be copied to a new model mapping configuration.</span></span>   
7. <span data-ttu-id="a1a79-151">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-151">Click Designer.</span></span>
8. <span data-ttu-id="a1a79-152">Nella struttura selezionare "Dynamics 365 for Operations\Table".</span><span class="sxs-lookup"><span data-stu-id="a1a79-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="a1a79-153">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="a1a79-153">Click Add root.</span></span>
10. <span data-ttu-id="a1a79-154">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="a1a79-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="a1a79-155">Società</span><span class="sxs-lookup"><span data-stu-id="a1a79-155">Company</span></span>  
11. <span data-ttu-id="a1a79-156">Nel campo Tabella digitare "CompanyInfo".</span><span class="sxs-lookup"><span data-stu-id="a1a79-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="a1a79-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="a1a79-157">CompanyInfo</span></span>  
12. <span data-ttu-id="a1a79-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1a79-158">Click OK.</span></span>
13. <span data-ttu-id="a1a79-159">Nella struttura espandere "Company".</span><span class="sxs-lookup"><span data-stu-id="a1a79-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="a1a79-160">Nella struttura espandere "Company\find()".</span><span class="sxs-lookup"><span data-stu-id="a1a79-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="a1a79-161">Nella struttura selezionare "Company\find()\Name".</span><span class="sxs-lookup"><span data-stu-id="a1a79-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="a1a79-162">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="a1a79-162">Click Bind.</span></span>
17. <span data-ttu-id="a1a79-163">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a1a79-163">Click Save.</span></span>
18. <span data-ttu-id="a1a79-164">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a1a79-164">Close the page.</span></span>
19. <span data-ttu-id="a1a79-165">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a1a79-165">Close the page.</span></span>
20. <span data-ttu-id="a1a79-166">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="a1a79-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="a1a79-167">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="a1a79-167">Click User parameters.</span></span>
22. <span data-ttu-id="a1a79-168">Selezionare Sì nel campo Esegui impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a1a79-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="a1a79-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1a79-169">Click OK.</span></span>
24. <span data-ttu-id="a1a79-170">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a1a79-170">Click Edit.</span></span>
25. <span data-ttu-id="a1a79-171">Selezionare Sì nel campo Esegui bozza.</span><span class="sxs-lookup"><span data-stu-id="a1a79-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="a1a79-172">Aggiungere una nuova configurazione di formato ER</span><span class="sxs-lookup"><span data-stu-id="a1a79-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="a1a79-173">Nella struttura selezionare "Sample data model".</span><span class="sxs-lookup"><span data-stu-id="a1a79-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="a1a79-174">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="a1a79-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="a1a79-175">Nel campo Nuovo immettere "Formato in base al modello dati Modello dati di esempio".</span><span class="sxs-lookup"><span data-stu-id="a1a79-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="a1a79-176">Nel campo Nome digitare "Formato di esempio".</span><span class="sxs-lookup"><span data-stu-id="a1a79-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="a1a79-177">Formato di esempio</span><span class="sxs-lookup"><span data-stu-id="a1a79-177">Sample format</span></span>  
5. <span data-ttu-id="a1a79-178">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-178">Click Create configuration.</span></span>
6. <span data-ttu-id="a1a79-179">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-179">Click Designer.</span></span>
7. <span data-ttu-id="a1a79-180">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="a1a79-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="a1a79-181">Nella struttura selezionare "Testo\Stringa".</span><span class="sxs-lookup"><span data-stu-id="a1a79-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="a1a79-182">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1a79-182">Click OK.</span></span>
10. <span data-ttu-id="a1a79-183">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="a1a79-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="a1a79-184">Nella struttura , espandere il "modello".</span><span class="sxs-lookup"><span data-stu-id="a1a79-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="a1a79-185">Nella struttura selezionare "model\Company".</span><span class="sxs-lookup"><span data-stu-id="a1a79-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="a1a79-186">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="a1a79-186">Click Bind.</span></span>
14. <span data-ttu-id="a1a79-187">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a1a79-187">Click Save.</span></span>
15. <span data-ttu-id="a1a79-188">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a1a79-188">Close the page.</span></span>
    * <span data-ttu-id="a1a79-189">Eseguire la versione bozza del formato creato a scopo di verifica.</span><span class="sxs-lookup"><span data-stu-id="a1a79-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="a1a79-190">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="a1a79-190">Click Run.</span></span>
    * <span data-ttu-id="a1a79-191">Nella scheda dettaglio Versioni fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="a1a79-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="a1a79-192">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1a79-192">Click OK.</span></span>
    * <span data-ttu-id="a1a79-193">Verificare l'uscita che contiene il nome della società a cui l'utente che ha esegue questa configurazione di formato ha eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a1a79-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="a1a79-194">Si noti che la configurazione di mapping di modello creata viene utilizzata da questa configurazione di formato perché è presente una sola configurazione disponibile contenente i mapping di modello richiesti.</span><span class="sxs-lookup"><span data-stu-id="a1a79-194">Note that the created model mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="a1a79-195">Aggiungere una configurazione del mapping di modello ER alternativa</span><span class="sxs-lookup"><span data-stu-id="a1a79-195">Add alternative ER model mapping configuration</span></span>
1. <span data-ttu-id="a1a79-196">Nella struttura selezionare "Sample data model".</span><span class="sxs-lookup"><span data-stu-id="a1a79-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="a1a79-197">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="a1a79-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="a1a79-198">Nel campo Nuovo immettere "Mapping modello in base al modello dati di esempio".</span><span class="sxs-lookup"><span data-stu-id="a1a79-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="a1a79-199">Nel campo Nome digitare "Mapping di esempio (alternative)".</span><span class="sxs-lookup"><span data-stu-id="a1a79-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="a1a79-200">Mapping di esempio (alternativo)</span><span class="sxs-lookup"><span data-stu-id="a1a79-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="a1a79-201">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-201">Click Create configuration.</span></span>
6. <span data-ttu-id="a1a79-202">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-202">Click Designer.</span></span>
7. <span data-ttu-id="a1a79-203">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-203">Click Designer.</span></span>
8. <span data-ttu-id="a1a79-204">Nella struttura selezionare "Dynamics 365 for Operations\Table".</span><span class="sxs-lookup"><span data-stu-id="a1a79-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="a1a79-205">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="a1a79-205">Click Add root.</span></span>
10. <span data-ttu-id="a1a79-206">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="a1a79-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="a1a79-207">Società</span><span class="sxs-lookup"><span data-stu-id="a1a79-207">Company</span></span>  
11. <span data-ttu-id="a1a79-208">Nel campo Tabella digitare "CompanyInfo".</span><span class="sxs-lookup"><span data-stu-id="a1a79-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="a1a79-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="a1a79-209">CompanyInfo</span></span>  
12. <span data-ttu-id="a1a79-210">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1a79-210">Click OK.</span></span>
13. <span data-ttu-id="a1a79-211">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a1a79-211">Click Edit.</span></span>
14. <span data-ttu-id="a1a79-212">Nella struttura selezionare "Stringa\CONCATENATE".</span><span class="sxs-lookup"><span data-stu-id="a1a79-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="a1a79-213">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-213">Click Add function.</span></span>
16. <span data-ttu-id="a1a79-214">Nella struttura espandere "Company".</span><span class="sxs-lookup"><span data-stu-id="a1a79-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="a1a79-215">Nella struttura espandere "Company\find()".</span><span class="sxs-lookup"><span data-stu-id="a1a79-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="a1a79-216">Nella struttura selezionare "Company\find()\Name".</span><span class="sxs-lookup"><span data-stu-id="a1a79-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="a1a79-217">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="a1a79-217">Click Add data source.</span></span>
20. <span data-ttu-id="a1a79-218">Digitare un valore nel campo Formula.</span><span class="sxs-lookup"><span data-stu-id="a1a79-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="a1a79-219">CONCATENATE(Company.'find()'.Name, ";",</span><span class="sxs-lookup"><span data-stu-id="a1a79-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="a1a79-220">Nella struttura selezionare "Company\find()\Company(DataArea)".</span><span class="sxs-lookup"><span data-stu-id="a1a79-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="a1a79-221">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="a1a79-221">Click Add data source.</span></span>
23. <span data-ttu-id="a1a79-222">Digitare un valore nel campo Formula.</span><span class="sxs-lookup"><span data-stu-id="a1a79-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="a1a79-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span><span class="sxs-lookup"><span data-stu-id="a1a79-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="a1a79-224">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a1a79-224">Click Save.</span></span>
25. <span data-ttu-id="a1a79-225">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a1a79-225">Close the page.</span></span>
26. <span data-ttu-id="a1a79-226">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a1a79-226">Click Save.</span></span>
27. <span data-ttu-id="a1a79-227">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a1a79-227">Close the page.</span></span>
28. <span data-ttu-id="a1a79-228">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="a1a79-228">Close the page.</span></span>
29. <span data-ttu-id="a1a79-229">Selezionare Sì nel campo Esegui bozza.</span><span class="sxs-lookup"><span data-stu-id="a1a79-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="a1a79-230">Utilizzare una configurazione del mapping di modello ER esistente</span><span class="sxs-lookup"><span data-stu-id="a1a79-230">Use an existing ER model mapping configuration</span></span>
1. <span data-ttu-id="a1a79-231">Nella struttura selezionare "Sample data model\Sample format".</span><span class="sxs-lookup"><span data-stu-id="a1a79-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="a1a79-232">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="a1a79-232">Click Run.</span></span>
    * <span data-ttu-id="a1a79-233">Si noti che la versione bozza della configurazione di formato ER non può essere eseguita perché è presente più di una configurazione di mapping di modello disponibile per il modello dati non definito selezionato come origine dati del formato ER in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-233">Note that the selected draft version of the ER format configuration can’t be executed because there is more than one model mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="a1a79-234">A questo punto verrà definita la configurazione del mapping di modello alternativo come un configurazione da cui i mapping di modello verranno utilizzati come origini dati per il formato ER in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1a79-234">Next, you will define the alternative model mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="a1a79-235">Nella struttura selezionare "Sample data model\Sample mapping (alternative)".</span><span class="sxs-lookup"><span data-stu-id="a1a79-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="a1a79-236">Selezionare Sì nel campo Impostazione predefinita per mapping di modello.</span><span class="sxs-lookup"><span data-stu-id="a1a79-236">Select Yes in the Default for model mapping field.</span></span>
5. <span data-ttu-id="a1a79-237">Nella struttura selezionare "Sample data model\Sample format".</span><span class="sxs-lookup"><span data-stu-id="a1a79-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="a1a79-238">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="a1a79-238">Click Run.</span></span>
7. <span data-ttu-id="a1a79-239">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="a1a79-239">Click OK.</span></span>
    * <span data-ttu-id="a1a79-240">Si noti che la configurazione del mapping di modello predefinita viene utilizzata da questa configurazione di formato per la generazione di documenti elettronici (l'output creato conterrà il codice della società).</span><span class="sxs-lookup"><span data-stu-id="a1a79-240">Note that the default model mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  


