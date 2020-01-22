---
title: Evitare il troncamento del testo nella gerarchia posizioni ed esportare in Visio
description: In questo argomento viene descritto come risolvere un problema in cui i nomi di utenti e posizioni vengono troncati quando i clienti visualizzano la gerarchia posizioni in Microsoft Dynamics 365 Talent. Il troncamento di testo può rendere difficile l'acquisizione di una schermata o la stampa della gerarchia.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 22e8570ccb53e8a7be2c57d3f14fe8034bdb699b
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898898"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a><span data-ttu-id="871aa-104">Evitare il troncamento del testo nella gerarchia posizioni ed esportare in Visio</span><span class="sxs-lookup"><span data-stu-id="871aa-104">Avoid text truncation on the position hierarchy and export to Visio</span></span>

<span data-ttu-id="871aa-105">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="871aa-105">**Issue**</span></span>

<span data-ttu-id="871aa-106">Quando un cliente visualizza la gerarchia posizioni in Microsoft Dynamics 365 Talent, i nomi di utenti e posizioni sono troncati.</span><span class="sxs-lookup"><span data-stu-id="871aa-106">When a customer views the position hierarchy in Microsoft Dynamics 365 Talent, the names of individuals and positions are truncated.</span></span> <span data-ttu-id="871aa-107">Di conseguenza, può risultare difficile acquisire una schermata o stampare e distribuire la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="871aa-107">Therefore, it can be difficult to take a screenshot, or to print and distribute the hierarchy.</span></span>

![Gerarchia posizioni](media/position-h.png)

<span data-ttu-id="871aa-109">**Causa**</span><span class="sxs-lookup"><span data-stu-id="871aa-109">**Cause**</span></span>

<span data-ttu-id="871aa-110">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="871aa-110">This behavior is by design.</span></span>

<span data-ttu-id="871aa-111">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="871aa-111">**Resolution**</span></span>

<span data-ttu-id="871aa-112">Purtroppo, gli utenti non possono cambiare facilmente la dimensione del testo.</span><span class="sxs-lookup"><span data-stu-id="871aa-112">Unfortunately, users can't easily change the size of the text.</span></span> <span data-ttu-id="871aa-113">Tuttavia, è possibile esportare la gerarchia posizioni da Talent e quindi importarla in Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="871aa-113">However, you can export the position hierarchy out of Talent and then import it into Microsoft Visio.</span></span> <span data-ttu-id="871aa-114">Sebbene l'articolo successivo sia scritto per Microsoft Dynamics AX 2012, il processo è valido anche per Talent: [Esportare una gerarchia posizioni in Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span><span class="sxs-lookup"><span data-stu-id="871aa-114">Although the following article was written for Microsoft Dynamics AX 2012, the process still applies to Talent: [Export a position hierarchy to Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).</span></span>

<span data-ttu-id="871aa-115">Seguire questa procedura per esportare in Visio.</span><span class="sxs-lookup"><span data-stu-id="871aa-115">Follow these steps to export to Visio.</span></span>

1. <span data-ttu-id="871aa-116">In Talent, aprire la pagina elenco **Posizioni**.</span><span class="sxs-lookup"><span data-stu-id="871aa-116">In Talent, open the **Positions** list page.</span></span>

    <span data-ttu-id="871aa-117">Per includere ulteriori informazioni nel diagramma della struttura organizzativa, aggiungere campi all'elenco **Posizioni**, di modo che siano disponibili quando si utilizza la procedura guidata in seguito in questa procedura.</span><span class="sxs-lookup"><span data-stu-id="871aa-117">To include more information in the organization structure diagram, add fields to the **Positions** list, so that they are available when you use the wizard later in this procedure.</span></span>

2. <span data-ttu-id="871aa-118">Nel riquadro azioni, selezionare il pulsante **Apri in Microsoft Office**, quindi sotto **Esporta in Excel**, selezionare **Posizioni**.</span><span class="sxs-lookup"><span data-stu-id="871aa-118">On the Action Pane, select the **Open in Microsoft Office** button, and then, under **Export to Excel**, select **Positions**.</span></span> <span data-ttu-id="871aa-119">In alternativa, premere CTRL+T.</span><span class="sxs-lookup"><span data-stu-id="871aa-119">Alternatively, press Ctrl+T.</span></span>

    ![Esportare la pagina elenco Posizioni in Excel](media/org-admin.png)

3. <span data-ttu-id="871aa-121">Salvare il file di Excel esportato.</span><span class="sxs-lookup"><span data-stu-id="871aa-121">Save the Excel file that is exported.</span></span>

    ![Finestra di dialogo Esporta in Excel](media/export-excel.png)

4. <span data-ttu-id="871aa-123">In Visio, selezionare **Visio - Crea nuovo**, quindi selezionare la categoria di modelli **Ufficio**.</span><span class="sxs-lookup"><span data-stu-id="871aa-123">In Visio, select **Visio - Create New**, and select the **Business** template category.</span></span>

    ![Nuovo diagramma](media/new.png)

5. <span data-ttu-id="871aa-125">Selezionare **Creazione guidata organigramma** e quindi selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="871aa-125">Select **Organization Chart Wizard**, and then select **Create**.</span></span>

    ![Finestra di dialogo Creazione guidata organigramma](media/orgchart-wizard.png)

6. <span data-ttu-id="871aa-127">Selezionare **Informazioni memorizzate in un file o database** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="871aa-127">Select **Information that's already stored in a file or database**, and then select **Next**.</span></span>

    ![Creazione guidata organigramma 1](media/orgchart-wizard7.png)

7. <span data-ttu-id="871aa-129">Scegliere **Un file di testo, Org Plus (\*.txt) o Excel**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="871aa-129">Choose **A text, Org Plus (\*.txt), or Excel file**, and then select **Next**.</span></span>

    ![Creazione guidata organigramma 2](media/orgchart-wizard3.png)

8. <span data-ttu-id="871aa-131">Selezionare il file di Excel esportato contenente la gerarchia posizioni, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="871aa-131">Browse to select the exported Excel file that contains the position hierarchy, and then select **Next**.</span></span>

    ![Creazione guidata organigramma 3](media/orgchart-wizard2.png)

9. <span data-ttu-id="871aa-133">Impostare il campo **Nome** su **Posizione**, impostare il campo **Subordinato a** su **Subordinato a**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="871aa-133">Set the **Name** field to **Position**, set the **Reports to** field to **Reports to position**, and then select **Next**.</span></span>

    ![Creazione guidata organigramma 4](media/orgchart-wizard1.png)

10. <span data-ttu-id="871aa-135">Selezionare i campi che devono essere visualizzati in ogni nodo, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="871aa-135">Select the fields that should be shown on each node, and then select **Next**.</span></span>

    ![Creazione guidata organigramma 5](media/orgchart-wizard5.png)

11. <span data-ttu-id="871aa-137">Aggiungere la colonna **Posizione** all'elenco **Campi proprietà forme**, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="871aa-137">Add the **Position** column to the **Shape Data fields** list, and then select **Next**.</span></span>

    ![Creazione guidata organigramma 6](media/orgchart-wizard6.png)

12. <span data-ttu-id="871aa-139">Le immagini non sono attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="871aa-139">Pictures aren't currently available.</span></span> <span data-ttu-id="871aa-140">Di conseguenza, nella pagina successiva, selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="871aa-140">Therefore, on the next page, select **Next**.</span></span>
13. <span data-ttu-id="871aa-141">Selezionare **I dati aziendali verranno suddivisi sulle pagine in modo automatico**.</span><span class="sxs-lookup"><span data-stu-id="871aa-141">Select **I want the wizard to automatically break my organization chart across pages**.</span></span>

    ![Creazione guidata organigramma 7](media/orgchart-wizard4.png)

14. <span data-ttu-id="871aa-143">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="871aa-143">Select **Finish**.</span></span>

    <span data-ttu-id="871aa-144">Se sono presenti posizioni non incluse nella struttura, viene richiesto di includerle nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="871aa-144">If there are any positions that aren't in the structure, you're asked to include them in the diagram.</span></span>

<span data-ttu-id="871aa-145">Nel diagramma generato in Visio ogni responsabile è visualizzato su un foglio di lavoro distinto.</span><span class="sxs-lookup"><span data-stu-id="871aa-145">The diagram that is generated in Visio shows each manager on a separate worksheet.</span></span>

<span data-ttu-id="871aa-146">In base ai campi selezionati da includere nel diagramma, ogni nodo visualizza le informazioni appropriate quando il file Visio viene generato.</span><span class="sxs-lookup"><span data-stu-id="871aa-146">Based on the fields that you selected to include in the diagram, each node shows the appropriate information when the Visio file is generated.</span></span>

![Diagramma della gerarchia](media/hierarchy.png)

<span data-ttu-id="871aa-148">**Opzione aggiuntiva**</span><span class="sxs-lookup"><span data-stu-id="871aa-148">**Additional option**</span></span>

<span data-ttu-id="871aa-149">In Talent, è inoltre possibile utilizzare l'area di lavoro **Persone** per visualizzare le informazioni relative alla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="871aa-149">In Talent, you might also be able to use the **People** workspace to view some hierarchy-related information.</span></span>
