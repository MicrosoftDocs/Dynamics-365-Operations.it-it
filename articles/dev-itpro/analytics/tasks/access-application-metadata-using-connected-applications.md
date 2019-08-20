---
title: Accedere ai metadati dell'applicazione utilizzando applicazioni connesse
description: I passaggi in questo argomento descrivono come un utente di Regulatory Configuration Service (RCS) può progettare un nuovo mapping di modello per la creazione di report elettronici (ER) utilizzando i metadati in Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d3581f6ae2d91b9648da3ba69e6b1d36cd08196
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727054"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="39239-103">Accedere ai metadati dell'applicazione utilizzando applicazioni connesse</span><span class="sxs-lookup"><span data-stu-id="39239-103">Access application metadata by using connected applications</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="39239-104">I passaggi seguenti illustrano come un utente di Regulatory Configuration Service (RCS) con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare un nuovo mapping di modello per la creazione di report elettronici (ER) utilizzando i metadati in Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="39239-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="39239-105">Per accedere ai metadati dell'applicazione online si utilizza l'applicazione connessa RCS.</span><span class="sxs-lookup"><span data-stu-id="39239-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="39239-106">Il mapping di modello ER di esempio verrà configurato per accedere alle transazioni del commercio estero.</span><span class="sxs-lookup"><span data-stu-id="39239-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="39239-107">Per completare questi passaggi, in RCS è necessario dapprima completare i passaggi dell'argomento [Creare un provider di configurazione e contrassegnarlo come attivo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="39239-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="39239-108">Se i passaggi nell'argomento [Accedere ai metadati dell'applicazione utilizzando una configurazione ER](access-application-metadata-er-configuration.md) non sono stati completati, accedere alla [pagina degli esempi di creazione di report elettronici](https://go.microsoft.com/fwlink/?linkid=862266) per scaricare e salvare le seguenti configurazioni ER: Metadati del commercio estero.xml; Modello del commercio estero.xml; Mapping del commercio estero.xml. Completare quindi i passaggi della procedura.</span><span class="sxs-lookup"><span data-stu-id="39239-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39239-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="39239-109">Prerequisites</span></span>
1. <span data-ttu-id="39239-110">Andare a **Tutte le aree di lavoro** > **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="39239-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="39239-111">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="39239-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="39239-112">Se il provider di configurazione non è visualizzato, completare i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="39239-112">If you don’t see this configuration provider, complete the steps in the procedure [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="39239-113">Ottenere le configurazioni ER necessarie</span><span class="sxs-lookup"><span data-stu-id="39239-113">Get required ER configurations</span></span>
1. <span data-ttu-id="39239-114">Fare clic su **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="39239-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="39239-115">Se i passaggi nella procedura [(RCS) Accedere ai metadati dell'applicazione utilizzando una configurazione ER](access-application-metadata-er-configuration.md) sono stati completati, si dispone già di tutte le configurazioni ER necessarie (configurazioni di metadati, modello e mapping del commercio estero) nell'istanza di RCS corrente.</span><span class="sxs-lookup"><span data-stu-id="39239-115">If you already completed the steps in the [(RCS) Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="39239-116">È possibile ignorare tutti i passaggi rimanenti di questa sottoattività.</span><span class="sxs-lookup"><span data-stu-id="39239-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="39239-117">Fare clic su **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="39239-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="39239-118">Fare clic su **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="39239-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="39239-119">Fare clic **Sfoglia** e selezionare il file **Metadati del commercio estero.xml**.</span><span class="sxs-lookup"><span data-stu-id="39239-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="39239-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39239-120">Click **OK**.</span></span> 
7. <span data-ttu-id="39239-121">Fare clic su **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="39239-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="39239-122">Fare clic su **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="39239-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="39239-123">Fare clic **Sfoglia** e selezionare il file **Modello del commercio estero.xml**.</span><span class="sxs-lookup"><span data-stu-id="39239-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="39239-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39239-124">Click **OK**.</span></span> 
11. <span data-ttu-id="39239-125">Fare clic su **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="39239-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="39239-126">Fare clic su **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="39239-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="39239-127">Fare clic **Sfoglia** e selezionare il file **Mapping del commercio estero.xml**.</span><span class="sxs-lookup"><span data-stu-id="39239-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="39239-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="39239-128">Click **OK**.</span></span> 

## <a name="register-connected-dynamics-365-for-finance-and-operations-application"></a><span data-ttu-id="39239-129">Registrare l'applicazione Dynamics 365 for Finance and Operations connessa</span><span class="sxs-lookup"><span data-stu-id="39239-129">Register connected Dynamics 365 for Finance and Operations application</span></span>
1. <span data-ttu-id="39239-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="39239-130">Close the page.</span></span> 
2. <span data-ttu-id="39239-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="39239-131">Close the page.</span></span> 
3. <span data-ttu-id="39239-132">Andare a **Tutte le aree di lavoro** > **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="39239-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="39239-133">Fare clic su **Applicazioni connesse**.</span><span class="sxs-lookup"><span data-stu-id="39239-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="39239-134">Assicurarsi che l'applicazione configurata sia basata su Azura e accessibile all'utente RCS corrente.</span><span class="sxs-lookup"><span data-stu-id="39239-134">Make sure that the configured application is Azura based and accessible for the current RCS user.</span></span> <span data-ttu-id="39239-135">È inoltre necessario che l'utente RCS corrente abbia accesso all'applicazione selezionata, sia stato registrato come utente di questa applicazione e disponga di un ruolo con privilegi di accesso ai metadati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="39239-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving him privileges to access application’s metadata.</span></span> 
6. <span data-ttu-id="39239-136">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="39239-136">Click **New**.</span></span> 
7. <span data-ttu-id="39239-137">Nel campo **Nome** digitare "MiaAppConnessa".</span><span class="sxs-lookup"><span data-stu-id="39239-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="39239-138">Nel campo **Applicazione**, immettere "https:// miasocietà.operations.dynamics.com".</span><span class="sxs-lookup"><span data-stu-id="39239-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="39239-139">Nel campo **Tenant**, immettere "miasocietà.onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="39239-139">In the **Tenant** field, type ‘mycompany.onmicrosoft.com’.</span></span> 
10. <span data-ttu-id="39239-140">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="39239-140">Click **Save**.</span></span> 
11. <span data-ttu-id="39239-141">Quando si verifica la connessione all'applicazione configurata, nella pagina **Connettersi all'applicazione remota**, fare clic sul collegamento **Fare clic qui per la connessione all'applicazione remota selezionata**.</span><span class="sxs-lookup"><span data-stu-id="39239-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="39239-142">Fare clic su **Verifica connessione**.</span><span class="sxs-lookup"><span data-stu-id="39239-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="39239-143">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="39239-143">Click **Close**.</span></span> 
14. <span data-ttu-id="39239-144">Quando la connessione viene convalidata, i dettagli relativi a tenant e versione verranno aggiornati per l'applicazione configurata nella griglia corrente.</span><span class="sxs-lookup"><span data-stu-id="39239-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="39239-145">Esaminare una configurazione del mapping di modello ER esistente</span><span class="sxs-lookup"><span data-stu-id="39239-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="39239-146">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="39239-146">Close the page.</span></span> 
2. <span data-ttu-id="39239-147">Fare clic su **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="39239-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="39239-148">Nella struttura espandere **Modello del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="39239-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="39239-149">Nella struttura, selezionare **Modello del commercio estero\Mapping del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="39239-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="39239-150">Espandere la sezione **Prerequisiti**.</span><span class="sxs-lookup"><span data-stu-id="39239-150">Expand the **Prerequisites** section.</span></span> 

> [!NOTE]
> <span data-ttu-id="39239-151">Attualmente, questo mapping fa riferimento alla configurazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="39239-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="39239-152">I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello.</span><span class="sxs-lookup"><span data-stu-id="39239-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="39239-153">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="39239-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="39239-154">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="39239-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="39239-155">Nella struttura selezionare **Dynamics 365 for Operations'\Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="39239-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="39239-156">Fare clic su **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="39239-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="39239-157">Nel campo **Tabella** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="39239-157">In the **Table** field, enter or select a value.</span></span> 

> [!NOTE]
> <span data-ttu-id="39239-158">Attualmente, questo mapping fa riferimento alla configurazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="39239-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="39239-159">I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello.</span><span class="sxs-lookup"><span data-stu-id="39239-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="39239-160">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="39239-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="39239-161">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="39239-161">Close the page.</span></span> 
13. <span data-ttu-id="39239-162">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="39239-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="39239-163">Assegnare un'applicazione connessa al mapping di modello</span><span class="sxs-lookup"><span data-stu-id="39239-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="39239-164">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="39239-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="39239-165">Selezionare l'applicazione **MiaAppConnessa**.</span><span class="sxs-lookup"><span data-stu-id="39239-165">Select **MyConnectedApp** application.</span></span> 

> [!NOTE]
> <span data-ttu-id="39239-166">Attualmente, questo mapping fa riferimento ai metadati dell'applicazione connessa selezionata.</span><span class="sxs-lookup"><span data-stu-id="39239-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="39239-167">Quando lo stesso mapping fa riferimento contemporaneamente alla configurazione dei metadati e all'applicazione connessa, verranno utilizzati i metadati dell'applicazione connessa.</span><span class="sxs-lookup"><span data-stu-id="39239-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="39239-168">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="39239-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="39239-169">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="39239-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="39239-170">Nella struttura selezionare **Dynamics 365 for Operations'\Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="39239-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="39239-171">Fare clic su **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="39239-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="39239-172">Nel campo **Tabella** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="39239-172">In the **Table** field, enter or select a value.</span></span> 

> [!NOTE]
> <span data-ttu-id="39239-173">Sono disponibili più di due tabelle dell'applicazione in quanto questo mapping utilizza tutti i metadati dell'applicazione connessa che è stata assegnata agli stessi.</span><span class="sxs-lookup"><span data-stu-id="39239-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="39239-174">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="39239-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="39239-175">Fare clic su **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="39239-175">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="39239-176">Abbiamo associato gli elementi del modello di dati ad articoli delle origini dati descritte utilizzando i dettagli dei metadati dell'applicazione connessa che è stata assegnata a questo mapping.</span><span class="sxs-lookup"><span data-stu-id="39239-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="39239-177">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="39239-177">Close the page.</span></span> 
11. <span data-ttu-id="39239-178">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="39239-178">Close the page.</span></span> 

<span data-ttu-id="39239-179">Quando è necessario valutare questo mapping di modello utilizzando i metadati di un'altra versione dell'applicazione, registrare un'altra applicazione connessa, assegnarla a questo mapping di modello e convalidarla in base ai nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="39239-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>