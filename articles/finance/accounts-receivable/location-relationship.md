---
title: Aggiungere tipi di relazione tra ruolo ubicazione e parte
description: In questo argomento viene descritto come aggiungere un nuovo tipo di relazione tra ruolo ubicazione e parte.
author: ShivamPandey-msft
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 71e4c8ad122bc52103bda04144222785e9a059f8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817247"
---
# <a name="add-location-and-party-relationship-types"></a><span data-ttu-id="92807-103">Aggiungere tipi di relazione tra ruolo ubicazione e parte</span><span class="sxs-lookup"><span data-stu-id="92807-103">Add location and party relationship types</span></span> 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a><span data-ttu-id="92807-104">Aggiungi ruoli ubicazioni</span><span class="sxs-lookup"><span data-stu-id="92807-104">Add location roles</span></span>

<span data-ttu-id="92807-105">Sono disponibili due modi per aggiungere nuovi ruoli ubicazione per le informazioni su indirizzo e contatto:</span><span class="sxs-lookup"><span data-stu-id="92807-105">There are two ways to add a new location roles for address and contact information:</span></span>

-  <span data-ttu-id="92807-106">Aggiungerlo tramite la pagina **Tipo informazioni contatto e indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="92807-106">Add it through the **Address and contact information purpose** page.</span></span> <span data-ttu-id="92807-107">Il nuovo ruolo verrà salvato nella tabella **LogisticsLocationRole** con tipo = 0, che indica che il ruolo non è un ruolo di sistema definito nell'enumerazione **LogisticsLocationRoleType** e le relative estensioni.</span><span class="sxs-lookup"><span data-stu-id="92807-107">The new role will be saved to the **LogisticsLocationRole** table with type = 0, which indicates that the role is not a system role defined in the **LogisticsLocationRoleType** enum and its extensions.</span></span> <span data-ttu-id="92807-108">Un utente potrà utilizzare questo ruolo durante la creazione delle informazioni su indirizzo o contatto.</span><span class="sxs-lookup"><span data-stu-id="92807-108">A user will be able to use this role when creating address or contact information.</span></span>

    ![Tipo informazioni contenuto e indirizzo](media/Address-Contact.PNG)

-  <span data-ttu-id="92807-110">Aggiungerlo all'estensione di enumerazione **LogisticsLocationRoleType** e popolarlo automaticamente tramite il processo di sincronizzazione del database.</span><span class="sxs-lookup"><span data-stu-id="92807-110">Add it to the **LogisticsLocationRoleType** enum extension, and let it populate through the database sync process.</span></span>

    1.  <span data-ttu-id="92807-111">Creare un'estensione all'enumerazione **LogisticsLocationRoleType** e aggiungere il nuovo ruolo nell'estensione.</span><span class="sxs-lookup"><span data-stu-id="92807-111">Create an extension to the **LogisticsLocationRoleType** enum and add the new role in the extension.</span></span> 
  
        ![Estensione dell'enumerazione LogisticsLocationRoleType](media/Logistics.PNG)

    2. <span data-ttu-id="92807-113">Creare un nuovo file di risorse per il nuovo ruolo e quindi assegnare un valore per le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="92807-113">Create a new resource file for the new role, and then assign a value for its properties.</span></span>
     
     ![Nuovo file di risorse](media/Resource.PNG)
        
    3.  <span data-ttu-id="92807-115">Creare una classe di popolamento dati e immettere un metodo di gestore per popolare il nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="92807-115">Create a data population class and provide a handler method to populate the new role.</span></span> 

        ![Popolamento dati](media/Dirdata.PNG)

    4.  <span data-ttu-id="92807-117">Per testare il popolamento del nuovo ruolo ubicazione, è possibile creare una classe eseguibile e richiamare DirDataPopulation::insertLogisticsLocationRoles() in Main().</span><span class="sxs-lookup"><span data-stu-id="92807-117">To test populating the new location role, you can create a runnable class, and call DirDataPopulation::insertLogisticsLocationRoles() in Main().</span></span> <span data-ttu-id="92807-118">Al termine del processo, di dovrebbe vedere il nuovo ruolo popolato nella tabella **LogisticsLocationRole** con tipo \> 0.</span><span class="sxs-lookup"><span data-stu-id="92807-118">After this process is complete, you should see the new role populated in the **LogisticsLocationRole** table with type \> 0.</span></span> <span data-ttu-id="92807-119">Il nuovo ruolo verrà visualizzato nella pagina **Tipo informazioni contatto e indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="92807-119">The new role will display on the **Address and contact information purpose** page.</span></span>

        ![Inserire nuova ubicazione](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a><span data-ttu-id="92807-121">Aggiungere tipi di relazione parte</span><span class="sxs-lookup"><span data-stu-id="92807-121">Add party relationship types</span></span> 

<span data-ttu-id="92807-122">Sono disponibili due modi per aggiungere un nuovo tipo di relazione:</span><span class="sxs-lookup"><span data-stu-id="92807-122">There are two ways to add a new relationship type:</span></span>

-   <span data-ttu-id="92807-123">Aggiungerlo tramite la pagina **Tipi di relazione**.</span><span class="sxs-lookup"><span data-stu-id="92807-123">Add it through the **Relationship types** page.</span></span> <span data-ttu-id="92807-124">La nuova relazione verrà salvata in **DirRelationshipTypeTable** con systemtype = 0.</span><span class="sxs-lookup"><span data-stu-id="92807-124">The new relationship will be saved to **DirRelationshipTypeTable** with systemtype = 0.</span></span>

    ![Tipi di relazione](media/Relationship.PNG)

-  <span data-ttu-id="92807-126">Aggiungerlo all'estensione dell'enumerazione **DirSystemRelationshipType** e popolarlo automaticamente tramite il processo di sincronizzazione del database.</span><span class="sxs-lookup"><span data-stu-id="92807-126">Add it to the extension of the **DirSystemRelationshipType** enum, and let it populate through database sync process.</span></span>

    1.  <span data-ttu-id="92807-127">Creare un'estensione all'enumerazione **DirSystemRelationshipType** e aggiungere il nuovo tipo di relazione.</span><span class="sxs-lookup"><span data-stu-id="92807-127">Create an extension to the **DirSystemRelationshipType** enum and add the new relationship type.</span></span>

    2. <span data-ttu-id="92807-128">Creare un inizializzatore per questo nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="92807-128">Create an initializer for this new type.</span></span> <span data-ttu-id="92807-129">È possibile trovare molti esempi nel codice di base, uno di questi è **DirRelationshipTypeChildInitialize**.</span><span class="sxs-lookup"><span data-stu-id="92807-129">You can find several examples in the core code, one of them is  **DirRelationshipTypeChildInitialize**.</span></span> <span data-ttu-id="92807-130">Si tratta di una classe di inizializzatore per il tipo di relazione della parte "figlio".</span><span class="sxs-lookup"><span data-stu-id="92807-130">This is an initializer class for party relationship type “Child”.</span></span> <span data-ttu-id="92807-131">È possibile iniziare con l'inizializzatore copiando e incollando questo codice e quindi aggiornare le aree evidenziate.</span><span class="sxs-lookup"><span data-stu-id="92807-131">You can start with your initializer by copying and pasting this code and then update the highlighted areas.</span></span>
    
    ![Inizializzatore DirRelationshipChild](media/DirRelationship.PNG)

    3.  <span data-ttu-id="92807-133">Per testare il popolamento del nuovo tipo di relazione, è possibile creare una classe eseguibile e richiamare DirDataPopulation::insertDirRelationshipTypes() in Main().</span><span class="sxs-lookup"><span data-stu-id="92807-133">To test populating the new relationship type, you can create a runnable class, and call DirDataPopulation::insertDirRelationshipTypes() in Main().</span></span> <span data-ttu-id="92807-134">Si dovrebbe visualizzare il nuovo tipo di relazione in **DirRelationshipTypeTable** e il nuovo tipo di relazione sarà disponibile nella pagina **Tipi di relazione**.</span><span class="sxs-lookup"><span data-stu-id="92807-134">You should see the new relationship type in the **DirRelationshipTypeTable**, and the new relationship type will be available on the **Relationship types** page.</span></span>

        ![Classe eseguibile](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]