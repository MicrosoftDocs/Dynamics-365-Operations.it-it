---
title: Accedere ai metadati dell'applicazione utilizzando una configurazione ER
description: Questo argomento descrive come un utente di Regulatory Configuration Service (RCS) può progettare un nuovo mapping di modello per la creazione di report elettronici (ER) utilizzando i metadati.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c50047781fdc21c9157ceb634822c6cfb5a075
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559653"
---
# <a name="access-application-metadata-by-using-er-configuration"></a><span data-ttu-id="c5fb0-103">Accedere ai metadati dell'applicazione utilizzando una configurazione ER</span><span class="sxs-lookup"><span data-stu-id="c5fb0-103">Access application metadata by using ER configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c5fb0-104">I passaggi seguenti illustrano come un utente di Regulatory Configuration Service (RCS) con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare un nuovo mapping di modello per la creazione di report elettronici (ER) utilizzando i metadati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using the application metadata.</span></span> <span data-ttu-id="c5fb0-105">Sarà possibile accedere ai metadati dell'applicazione utilizzando la configurazione dei metadati ER contenente un set di metadati di esempio per accedere alle transazioni del commercio estero.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-105">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span> <span data-ttu-id="c5fb0-106">Per completare questi passaggi, in RCS è necessario dapprima completare i passaggi dell'argomento [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="c5fb0-106">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> <span data-ttu-id="c5fb0-107">Quindi, completare i passaggi nell'argomento [Preparare i metadati dell'applicazione da utilizzare in RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="c5fb0-107">Then complete the steps in the topic, [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5fb0-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c5fb0-108">Prerequisites</span></span>
1. <span data-ttu-id="c5fb0-109">Andare a **Tutte le aree di lavoro** > **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-109">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="c5fb0-110">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="c5fb0-111">Se questo provider di configurazione non è visualizzato, completare i passaggi nella procedura [Creare provider di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="c5fb0-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="import-metadata-configuration"></a><span data-ttu-id="c5fb0-112">Importare una configurazione dei metadati</span><span class="sxs-lookup"><span data-stu-id="c5fb0-112">Import metadata configuration</span></span> 
1. <span data-ttu-id="c5fb0-113">Fare clic su **Configurazioni dei metadati**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-113">Click **Metadata configurations**.</span></span> 
2. <span data-ttu-id="c5fb0-114">Importare la configurazione dei metadati ER che contiene i metadati configurati per generare documenti elettronici per il dominio aziendale per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-114">Import the ER metadata configuration that contains metadata that has been configured to generate electronic documents for foreign trade business.</span></span> <span data-ttu-id="c5fb0-115">Questa configurazione dei metadati ER è stata esportata come file XML durante il completamento dei passaggi della procedura [Preparare i metadati dell'applicazione da utilizzare in RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="c5fb0-115">This ER metadata configuration has been exported as XML file while the steps in the [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md) procedure have been completed.</span></span> 
3. <span data-ttu-id="c5fb0-116">Fare clic su **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-116">Click **Exchange**.</span></span> 
4. <span data-ttu-id="c5fb0-117">Fare clic su **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-117">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="c5fb0-118">Fare clic su **Sfoglia** e selezionare il file "Metadati del commercio estero.xml".</span><span class="sxs-lookup"><span data-stu-id="c5fb0-118">Click **Browse** and select the 'Foreign trade metadata.xml' file.</span></span> 
6. <span data-ttu-id="c5fb0-119">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-119">Click **OK**.</span></span> 
7. <span data-ttu-id="c5fb0-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-120">Close the page.</span></span> 

## <a name="create-data-model-configuration"></a><span data-ttu-id="c5fb0-121">Creare una nuova configurazione del modello di dati</span><span class="sxs-lookup"><span data-stu-id="c5fb0-121">Create data model configuration</span></span>
1. <span data-ttu-id="c5fb0-122">Fare clic su **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-122">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="c5fb0-123">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-123">Click **Create configuration** to open the drop dialog.</span></span> 
3. <span data-ttu-id="c5fb0-124">Nel campo **Nome**, digitare "Modello del commercio estero".</span><span class="sxs-lookup"><span data-stu-id="c5fb0-124">In the **Name** field, type 'Foreign trade model'.</span></span> 
4. <span data-ttu-id="c5fb0-125">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-125">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="c5fb0-126">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-126">Click **Designer**.</span></span> 
6. <span data-ttu-id="c5fb0-127">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-127">Click **New** to open the drop dialog.</span></span> 
7. <span data-ttu-id="c5fb0-128">Digitare "Radice" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-128">In the **Name** field, type 'Root'.</span></span> 
8. <span data-ttu-id="c5fb0-129">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-129">Click **Add**.</span></span> 
9. <span data-ttu-id="c5fb0-130">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-130">Click **New** to open the drop dialog.</span></span> 
10.    <span data-ttu-id="c5fb0-131">Nel campo **Nome** digitare "Transazione".</span><span class="sxs-lookup"><span data-stu-id="c5fb0-131">In the **Name** field, type 'Transaction'.</span></span> 
11.    <span data-ttu-id="c5fb0-132">Nel campo **Tipo di articolo** selezionare **Elenco di record**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-132">In the **Item type** field, select **Record list**.</span></span> 
12.    <span data-ttu-id="c5fb0-133">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-133">Click **Add**.</span></span> 
13.    <span data-ttu-id="c5fb0-134">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-134">Click **New** to open the drop dialog.</span></span> 
14.    <span data-ttu-id="c5fb0-135">Nel campo **Nome** digitare "Codice voce doganale".</span><span class="sxs-lookup"><span data-stu-id="c5fb0-135">In the **Name** field, type 'Commodity code'.</span></span> 
15.    <span data-ttu-id="c5fb0-136">Nel campo **Tipo di articolo** selezionare **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-136">In the **Item type** field, select **String**.</span></span> 
16.    <span data-ttu-id="c5fb0-137">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-137">Click **Add**.</span></span> 
17.    <span data-ttu-id="c5fb0-138">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-138">Click **New** to open the drop dialog.</span></span> 
18.    <span data-ttu-id="c5fb0-139">Nel campo **Nome** digitare "Importo fatturato".</span><span class="sxs-lookup"><span data-stu-id="c5fb0-139">In the **Name** field, type 'Invoiced amount'.</span></span> 
19.    <span data-ttu-id="c5fb0-140">Nel campo **Tipo di articolo** selezionare **Reale**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-140">In the **Item type** field, select **Real**.</span></span> 
20.    <span data-ttu-id="c5fb0-141">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-141">Click **Add**.</span></span> 
21.    <span data-ttu-id="c5fb0-142">Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-142">Click **New** to open the drop dialog.</span></span> 
22.    <span data-ttu-id="c5fb0-143">Digitare "Data" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-143">In the **Name** field, type 'Date'.</span></span> 
23.    <span data-ttu-id="c5fb0-144">Nel campo **Tipo di articolo** selezionare **Data**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-144">In the **Item type** field, select **Date**.</span></span> 
24.    <span data-ttu-id="c5fb0-145">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-145">Click **Add**.</span></span> 
25.    <span data-ttu-id="c5fb0-146">Fare clic su **Riferimento radice**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-146">Click **Root reference**.</span></span> 
26.    <span data-ttu-id="c5fb0-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-147">Click **OK**.</span></span> 
27.    <span data-ttu-id="c5fb0-148">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-148">Click **Save**.</span></span> 
28.    <span data-ttu-id="c5fb0-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-149">Close the page.</span></span> 
29.    <span data-ttu-id="c5fb0-150">Fare clic su **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-150">Click **Change status**.</span></span> 
30.    <span data-ttu-id="c5fb0-151">Fare clic su **Completa**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-151">Click **Complete**.</span></span> 
31.    <span data-ttu-id="c5fb0-152">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-152">Click **OK**.</span></span> 

## <a name="create-model-mapping-configuration"></a><span data-ttu-id="c5fb0-153">Creare una configurazione del mapping di modello</span><span class="sxs-lookup"><span data-stu-id="c5fb0-153">Create model mapping configuration</span></span> 
1. <span data-ttu-id="c5fb0-154">Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-154">Click **Create configuration** to open the drop dialog.</span></span> 
2. <span data-ttu-id="c5fb0-155">Nel campo **Nuovo** immettere "Mapping di modello basato sul modello di dati Modello del commercio estero".</span><span class="sxs-lookup"><span data-stu-id="c5fb0-155">In the **New** field, enter 'Model Mapping based on data model Foreign trade model'.</span></span> 
3. <span data-ttu-id="c5fb0-156">Nel campo **Nome**, digitare "Mapping del commercio estero".</span><span class="sxs-lookup"><span data-stu-id="c5fb0-156">In the **Name** field, type 'Foreign trade mapping'.</span></span> 
4. <span data-ttu-id="c5fb0-157">Fare clic su **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-157">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="c5fb0-158">Espandere la sezione **Prerequisiti**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-158">Expand the **Prerequisites** section.</span></span> 
6. <span data-ttu-id="c5fb0-159">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-159">Click **Edit**.</span></span> 
7. <span data-ttu-id="c5fb0-160">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-160">Click **New**.</span></span> 
8. <span data-ttu-id="c5fb0-161">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-161">In the list, mark the selected row.</span></span> 
9. <span data-ttu-id="c5fb0-162">Nel campo **Tipo di componente prerequisito**, selezionare **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-162">In the **Prerequisite component type** field, select **Configuration**.</span></span> 
10.    <span data-ttu-id="c5fb0-163">Selezionare la configurazione **Metadati del commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-163">Select **Foreign trade metadata** configuration.</span></span> 
11.    <span data-ttu-id="c5fb0-164">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-164">Click **Save**.</span></span> 
12.    <span data-ttu-id="c5fb0-165">Abbiamo aggiunto il riferimento alla versione 1 della configurazione "Metadati del commercio estero".</span><span class="sxs-lookup"><span data-stu-id="c5fb0-165">We added the reference to the version 1 of the 'Foreign trade metadata' configuration.</span></span> <span data-ttu-id="c5fb0-166">I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-166">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 
13.    <span data-ttu-id="c5fb0-167">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-167">Close the page.</span></span> 
14.    <span data-ttu-id="c5fb0-168">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-168">Click **Designer**.</span></span> 
15.    <span data-ttu-id="c5fb0-169">Fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-169">Click **Designer**.</span></span> 
16.    <span data-ttu-id="c5fb0-170">Nella struttura selezionare **Dynamics 365 for Operations'\Record di tabella**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
17.    <span data-ttu-id="c5fb0-171">Fare clic su **Aggiungi radice**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-171">Click **Add root**.</span></span> 
18.    <span data-ttu-id="c5fb0-172">Digitare "Intrastat" nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-172">In the **Name** field, type 'Intrastat'.</span></span> 
19.    <span data-ttu-id="c5fb0-173">Selezionare i record di tabella **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-173">Select **Intrastat** table records.</span></span> 
20.    <span data-ttu-id="c5fb0-174">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-174">Click **OK**.</span></span> 

> [!NOTE]
> <span data-ttu-id="c5fb0-175">Solo 2 tabelle erano disponibili poiché solo 2 tabelle sono state aggiunte al set di metadati attualmente utilizzati.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-175">The only 2 tables were offered as the only 2 tables were added into the set of metadata which is currently in use.</span></span> 

21.    <span data-ttu-id="c5fb0-176">Fare clic su **Associa**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-176">Click **Bind**.</span></span> 
22.    <span data-ttu-id="c5fb0-177">Nella struttura espandere **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-177">In the tree, expand **Intrastat**.</span></span> 
23.    <span data-ttu-id="c5fb0-178">Nella struttura selezionare **Intrastat\AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-178">In the tree, select **Intrastat\AmountMST**.</span></span> 
24.    <span data-ttu-id="c5fb0-179">Nella struttura espandere **Transazione = Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-179">In the tree, expand **Transaction = Intrastat**.</span></span> 
25.    <span data-ttu-id="c5fb0-180">Nella struttura selezionare **Transazione = Intrastat\Importo fatturato**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-180">In the tree, select **Transaction = Intrastat\Invoiced amount**.</span></span> 
26.    <span data-ttu-id="c5fb0-181">Fare clic su **Associa**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-181">Click **Bind**.</span></span> 
27.    <span data-ttu-id="c5fb0-182">Nella struttura selezionare **Intrastat\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-182">In the tree, select **Intrastat\TransDate**.</span></span> 
28.    <span data-ttu-id="c5fb0-183">Nella struttura selezionare **Transazione = Intrastat\Data**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-183">In the tree, select **Transaction = Intrastat\Date**.</span></span> 
29.    <span data-ttu-id="c5fb0-184">Fare clic su **Associa**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-184">Click **Bind**.</span></span> 
30.    <span data-ttu-id="c5fb0-185">Nella struttura espandere **Intrastat\>Relazioni**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-185">In the tree, expand **Intrastat\>Relations**.</span></span> 
31.    <span data-ttu-id="c5fb0-186">Nella struttura espandere **Intrastat\>Relazioni\IntrastatCommodity**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-186">In the tree, expand **Intrastat\>Relations\IntrastatCommodity**.</span></span> 
32.    <span data-ttu-id="c5fb0-187">Nella struttura selezionare **Intrastat\>Relazioni\IntrastatCommodity\Codice**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-187">In the tree, select **Intrastat\>Relations\IntrastatCommodity\Code**.</span></span> 
33.    <span data-ttu-id="c5fb0-188">Nella struttura selezionare **Transazione = Intrastat\Codice voce doganale**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-188">In the tree, select **Transaction = Intrastat\Commodity code**.</span></span> 
34.    <span data-ttu-id="c5fb0-189">Fare clic su **Associa**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-189">Click **Bind**.</span></span> 
35.    <span data-ttu-id="c5fb0-190">Fare clic su **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-190">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="c5fb0-191">Abbiamo associato gli elementi del modello di dati ad articoli delle origini dati descritte utilizzando i dettagli dei metadati dell'applicazione nella configurazione dei metadati ER a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-191">We have successfully bound elements of data model with items of data sources that are described by using details of application metadata from the referred ER metadata configuration.</span></span> 
36.    <span data-ttu-id="c5fb0-192">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-192">Click **Save**.</span></span> 
37.    <span data-ttu-id="c5fb0-193">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-193">Close the page.</span></span> 
38.    <span data-ttu-id="c5fb0-194">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-194">Close the page.</span></span> 
39.    <span data-ttu-id="c5fb0-195">Se necessario, è possibile estendere il set esistente di metadati e quindi esportare la nuova versione completata della configurazione dei metadati di ER.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-195">When needed, you can extend the existing set of metadata and then export the new completed version of ER metadata configuration.</span></span> <span data-ttu-id="c5fb0-196">È quindi possibile importarla in RCS e aggiornare i prerequisiti della configurazione del mapping di modello configurato che fa riferimento a una nuova versione della configurazione dei metadati importata.</span><span class="sxs-lookup"><span data-stu-id="c5fb0-196">You can then import it to RCS, and update the prerequisites of the configured model mapping configuration referring to a new version of imported metadata configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="c5fb0-197">Questo modo di ottenere informazioni sui metadati dell'applicazione è l'unico disponibile per le applicazioni distribuite localmente (quando un modello di distribuzione di dati aziendali locali o on-premises è utilizzato).</span><span class="sxs-lookup"><span data-stu-id="c5fb0-197">This way of getting information about application metadata is the only one available for locally deployed applications (when local business data (LBD), or on-premises, deployment model is used).</span></span>
        


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]