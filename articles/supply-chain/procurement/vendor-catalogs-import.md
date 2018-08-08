---
title: Importa cataloghi fornitore
description: In questo argomento viene descritto il processo di importazione dei dati del catalogo fornitore.
author: mkirknel
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.search.region: Global
ms.search.industry: 
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: cf81823de46da9a834f0214896b9e634989cac0e
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="import-vendor-catalogs"></a><span data-ttu-id="85335-103">Importa cataloghi fornitore</span><span class="sxs-lookup"><span data-stu-id="85335-103">Import vendor catalogs</span></span>
[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a><span data-ttu-id="85335-104">Importazione cataloghi fornitore</span><span class="sxs-lookup"><span data-stu-id="85335-104">Vendor catalogs import</span></span>

<span data-ttu-id="85335-105">In Microsoft Dynamics 365 for Finance and Operations, i professionisti degli acquisti possono creare e gestire cataloghi che i dipendenti possono utilizzare quando ordinano articoli e servizi per uso interno.</span><span class="sxs-lookup"><span data-stu-id="85335-105">In Microsoft Dynamics 365 for Finance and Operations, purchasing professionals can create and maintain catalogs for company employees to use when they order items and services for internal use.</span></span> <span data-ttu-id="85335-106">Per creare un catalogo di approvvigionamento, è possibile aggiungere gli articoli e i servizi che si desidera rendere disponibili ai dipendenti, importando i dati del catalogo prodotti oppure aggiungendo manualmente i dati del catalogo prodotti alla rappresentazione generale prodotto.</span><span class="sxs-lookup"><span data-stu-id="85335-106">To create a procurement catalog, you can add the items and services that you want to make available to employees, either by importing the product catalog data or by manually adding the product catalog data to the product master.</span></span> 

<span data-ttu-id="85335-107">È possibile caricare i dati del catalogo inviati da un fornitore dal client di Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="85335-107">You can upload catalog data submitted by a vendor from the Microsoft Dynamics 365 client.</span></span>

<span data-ttu-id="85335-108">I dati dei prodotti che un fornitore invia all'utente sotto forma di un file di richiesta di gestione catalogo devono essere in formato XML.</span><span class="sxs-lookup"><span data-stu-id="85335-108">The product data that a vendor submits to you, in the form of a catalog maintenance request (CMR) file, must be in XML file format.</span></span> <span data-ttu-id="85335-109">Il file di richiesta di gestione catalogo deve contenere i dettagli dei prodotti che il fornitore fornisce alla società.</span><span class="sxs-lookup"><span data-stu-id="85335-109">The CMR file should contain the details for the products that the vendor supplies to your company.</span></span>

## <a name="import-vendor-catalog-data"></a><span data-ttu-id="85335-110">Importare i dati del catalogo fornitore</span><span class="sxs-lookup"><span data-stu-id="85335-110">Import vendor catalog data</span></span>

<span data-ttu-id="85335-111">Per importare i dati del catalogo fornitore, è necessario completare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="85335-111">To import vendor catalog data, you must complete the following tasks:</span></span>

1.  <span data-ttu-id="85335-112">Impostare un progetto nell'area di lavoro Gestione dati in cui sono state definite le regole di mapping dei dati.</span><span class="sxs-lookup"><span data-stu-id="85335-112">Set up a project in the Data management workspace where you have defined your data mapping rules.</span></span> <span data-ttu-id="85335-113">Selezionare **Gestione dati** e quindi **Imposta ruoli per progetti dati**.</span><span class="sxs-lookup"><span data-stu-id="85335-113">Select **Data management** and then select **Set up roles for data projects**.</span></span> 

2.  <span data-ttu-id="85335-114">Impostare una gerarchia di categorie di approvvigionamento e assegnare i fornitori alle categorie di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="85335-114">Set up a procurement category hierarchy, and assign your vendors to procurement categories.</span></span> <span data-ttu-id="85335-115">Se si utilizzano codici di voce doganale, aggiungere i codici alle categorie di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="85335-115">If you use commodity codes, add the commodity codes to the procurement categories.</span></span> <span data-ttu-id="85335-116">Per informazioni su come impostare una gerarchia di categorie di approvvigionamento, vedere [Impostare una gerarchia di categorie di approvvigionamento](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="85335-116">For information about setting up a procurement category hierarchy, see [Set up a procurement category hierarchy](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span></span>

3.  <span data-ttu-id="85335-117">Configurare il fornitore per l'importazione del catalogo.</span><span class="sxs-lookup"><span data-stu-id="85335-117">Configure the vendor for catalog import.</span></span> <span data-ttu-id="85335-118">Selezionare un fornitore e quindi **Approvvigionamento** > **Impostazione** > **Configura fornitore per importazione catalogo**.</span><span class="sxs-lookup"><span data-stu-id="85335-118">Select a vendor, and then select **Procurement** > **Set up** > **Configure vendor for catalog import**.</span></span>

4.  <span data-ttu-id="85335-119">Configurare il flusso di lavoro per l'importazione del catalogo.</span><span class="sxs-lookup"><span data-stu-id="85335-119">Configure workflow for catalog import.</span></span> <span data-ttu-id="85335-120">Creare un modello di file di richiesta di gestione catalogo e condividerlo con il fornitore.</span><span class="sxs-lookup"><span data-stu-id="85335-120">Create a CMR file template and share this with your vendor.</span></span>

5.  <span data-ttu-id="85335-121">Selezionare **Approvvigionamento** \> **Comune** \> **Cataloghi** \> **Cataloghi fornitore** per creare un catalogo fornitore.</span><span class="sxs-lookup"><span data-stu-id="85335-121">Select **Procurement and sourcing** \> **Common** \> **Catalogs** \> **Vendor catalogs** to create a vendor catalog.</span></span> <span data-ttu-id="85335-122">I file di richiesta di gestione catalogo ricevuti dal fornitore vengono raggruppati in questo catalogo.</span><span class="sxs-lookup"><span data-stu-id="85335-122">The catalog maintenance request (CMR) files that you receive from your vendor are grouped in this catalog.</span></span> 

6.  <span data-ttu-id="85335-123">Caricare il file di richiesta di gestione catalogo.</span><span class="sxs-lookup"><span data-stu-id="85335-123">Upload the CMR file.</span></span>

7.  <span data-ttu-id="85335-124">Verificare, approvare o rifiutare i prodotti del catalogo fornitore.</span><span class="sxs-lookup"><span data-stu-id="85335-124">Review, approve, or reject the products in the vendor catalog.</span></span> <span data-ttu-id="85335-125">I prodotti vengono mappati automaticamente alle categorie di approvvigionamento in Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="85335-125">The products are automatically mapped to the procurement categories in Dynamics 365 for Finance and Operations.</span></span> 
    
<span data-ttu-id="85335-126">I prodotti approvati vengono aggiunti alla rappresentazione generale prodotto e vengono rilasciati alle persone giuridiche selezionate.</span><span class="sxs-lookup"><span data-stu-id="85335-126">Approved products are added to the product master and are released to the selected legal entities.</span></span> <span data-ttu-id="85335-127">Solo i prodotti approvati possono essere aggiunti al catalogo di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="85335-127">Only approved products can be added to the procurement catalog.</span></span>

## <a name="generate-a-catalog-import-file-template"></a><span data-ttu-id="85335-128">Generazione di un modello di file di importazione catalogo</span><span class="sxs-lookup"><span data-stu-id="85335-128">Generate a catalog import file template</span></span>

<span data-ttu-id="85335-129">Il modello di file di importazione catalogo è un file XSD utilizzabile per creare un file di richiesta di gestione catalogo per i prodotti di un fornitore.</span><span class="sxs-lookup"><span data-stu-id="85335-129">The catalog import file template is an XSD file that you use to create a CMR file for a vendor’s products.</span></span> <span data-ttu-id="85335-130">È possibile utilizzare il file di richiesta di gestione catalogo per creare un nuovo catalogo oppure sostituire o modificare un catalogo esistente.</span><span class="sxs-lookup"><span data-stu-id="85335-130">You can use the CMR file to create a new catalog, replace an existing catalog, or modify an existing catalog.</span></span>

1.  <span data-ttu-id="85335-131">Selezionare **Approvvigionamento** \> **Cataloghi** \> **Cataloghi fornitore** e fare doppio clic sul catalogo che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="85335-131">Select **Procurement and sourcing** \> **Catalogs** \> **Vendor catalogs** and double-click the catalog that you want to work with.</span></span>

2.  <span data-ttu-id="85335-132">Scaricare un modello di importazione catalogo corrente (file XSD).</span><span class="sxs-lookup"><span data-stu-id="85335-132">Download a current catalog import template (XSD file).</span></span> <span data-ttu-id="85335-133">Nella pagina **Aggiorna catalogo**, nel **Riquadro azioni**, scheda **Cataloghi**, nel gruppo **Informazioni correlate**, fare clic su **Genera modello catalogo** e selezionare **Categoria di approvvigionamento**.</span><span class="sxs-lookup"><span data-stu-id="85335-133">On the **Update catalog** page, on the **Action Pane**, on the **Catalogs** tab, in the **Related information** group, click **Generate catalog template** and select **Procurement category**.</span></span>

    -   <span data-ttu-id="85335-134">Con l'opzione **Categoria di approvvigionamento** è possibile generare un modello di catalogo che include le categorie di approvvigionamento in cui il fornitore è autorizzato a fornire prodotti.</span><span class="sxs-lookup"><span data-stu-id="85335-134">With the **Procurement category** option you can generate a catalog template that includes the procurement categories in which the vendor is authorized to provide products.</span></span>

3. <span data-ttu-id="85335-135">Nella finestra di dialogo **Salva con nome** selezionare il percorso in cui si desidera archiviare il modello di file di catalogo e salvare il file.</span><span class="sxs-lookup"><span data-stu-id="85335-135">In the **Save as** dialog box, select the location where you want to store the catalog file template and save the file.</span></span>

<span data-ttu-id="85335-136">Per esempi e ulteriori informazioni, vedere questo post di blog: [Cataloghi fornitore in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span><span class="sxs-lookup"><span data-stu-id="85335-136">For more information and for examples, refer to this blog post: [Vendor catalogs in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span></span>

