---
title: (ER) Importare configurazioni da RCS
description: In questo argomento vengono fornite informazioni su come un utente può importare una nuova versione di una configurazione ER da RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
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
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c458cf815837fb7e4688c4c0443b7962cac403a5
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727008"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="1cbdb-103">(ER) Importare configurazioni da RCS</span><span class="sxs-lookup"><span data-stu-id="1cbdb-103">(ER) Import configurations from RCS</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1cbdb-104">I passaggi seguenti illustrano come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può importare una nuova configurazione per la creazione di report elettronici (ER) da Microsoft Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="1cbdb-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="1cbdb-105">In questo esempio si selezionerà la versione della configurazione ER configurata in un'istanza di RCS e la si importerà nell'istanza di Finance and Operations corrente per la società di esempio, Litware, Inc. Questi passaggi possono essere eseguiti in qualsiasi società in quanto le configurazioni ER sono condivise tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current Finance and Operations instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="1cbdb-106">Per completare questi passaggi, è necessario dapprima completare i passaggi dell'argomento [Creare un provider di configurazione e contrassegnarlo come attivo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1cbdb-106">To complete these steps, you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="1cbdb-107">Per effettuare questi passaggi, è inoltre necessario accedere a un'istanza di RCS che contiene almeno una configurazione ER il cui stato è **Completato** o **Condiviso**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="1cbdb-108">Andare a **Amministrazione organizzazione** > **Aree di lavoro** > **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="1cbdb-109">Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="1cbdb-110">Se il provider di configurazione non è visualizzato, completare i passaggi dell'argomento [Creare un provider di configurazione e contrassegnarlo come attivo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1cbdb-110">If you don’t see this configuration provider, complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="1cbdb-111">Se si dispone di un ambiente RCS di cui è stato effettuato il provisioning per la società, fare clic sul collegamento esterno **Regulatory services - Configurazione** e seguire le istruzioni per il provisioning di un ambiente RCS.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-111">If you have no RCS environment provisioned to your company, click **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="1cbdb-112">Fare clic su **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-112">Click **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="1cbdb-113">Fare clic sulla scheda **RCS**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-113">Click the **RCS** tab.</span></span> 
6. <span data-ttu-id="1cbdb-114">Se si è già eseguito il provisioning dell'ambiente RCS per la società, utilizzare gli URL nella pagina per accedervi.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="1cbdb-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="1cbdb-116">Registrare un nuovo archivio ER.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="1cbdb-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="1cbdb-118">Selezionare il provider Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="1cbdb-119">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-119">Click Repositories.</span></span> 
4. <span data-ttu-id="1cbdb-120">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-120">Click Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="1cbdb-121">Nel campo Tipo di archivio di configurazioni immettere "RCS".</span><span class="sxs-lookup"><span data-stu-id="1cbdb-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="1cbdb-122">Fare clic su Crea archivio.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-122">Click Create repository.</span></span> 
7. <span data-ttu-id="1cbdb-123">Nel campo Nome visualizzato ambiente RCS, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="1cbdb-124">Selezionare l'istanza di RCS desiderata.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-124">Select the desired RCS instance.</span></span> <span data-ttu-id="1cbdb-125">Tenere presente che possono esistere varie istanze.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-125">Note that you can have several of them.</span></span> 
9. <span data-ttu-id="1cbdb-126">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-126">Click OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="1cbdb-127">Importare le configurazioni ER dall'archivio basato su RCS</span><span class="sxs-lookup"><span data-stu-id="1cbdb-127">Import ER configurations from RCS based repository</span></span>
1. <span data-ttu-id="1cbdb-128">Fare clic su **Mostra filtri**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-128">Click **Show filters**.</span></span> 
2. <span data-ttu-id="1cbdb-129">Immettere un valore di filtro "RCS" nel campo **Nome** utilizzando l'operatore di filtro **inizia con**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="1cbdb-130">Quando si apre l'archivio selezionato, nella pagina **Connessione a Regulatory Configuration Service**, fare clic sul collegamento **Fare clic qui per connettersi a Regulatory Configuration Services**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, click **Click here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="1cbdb-131">Fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-131">Click **Open**.</span></span> 
5. <span data-ttu-id="1cbdb-132">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-132">Click **Close**.</span></span> 
6. <span data-ttu-id="1cbdb-133">Selezionare la versione desiderata della configurazione ER e fare clic su **Importa** per importarla nell'istanza di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-133">Select the desired version of ER configuration and click **Import** to bring it in the current Finance and Operations instance.</span></span>
