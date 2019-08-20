---
title: Documenti cespiti
description: In questo argomento vengono descritti i documenti di cespiti in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1c90788da7ad536fb9978db18160ccf6c158033
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783365"
---
# <a name="asset-documents"></a><span data-ttu-id="025c7-103">Documenti cespiti</span><span class="sxs-lookup"><span data-stu-id="025c7-103">Asset documents</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="025c7-104">In questo argomento vengono descritti i documenti di cespiti in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="025c7-104">This topic explains asset documents in Asset Management.</span></span>

<span data-ttu-id="025c7-105">In Gestione cespiti, è possibile impostare documenti in modo da correlarli automaticamente ai tipi di processo, ai produttori cespite, tipi del cespite, o ai cespiti, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="025c7-105">In Asset Management, you can set up documents so that they are automatically related to job types, asset manufacturers, asset types, or assets, for example.</span></span> <span data-ttu-id="025c7-106">Questa funzionalità è utile quando versioni aggiornate dei documenti vengono rilasciate.</span><span class="sxs-lookup"><span data-stu-id="025c7-106">This functionality is useful when updated document versions are released.</span></span> <span data-ttu-id="025c7-107">In questo caso, è sufficiente mettere il documento aggiornato nell'ubicazione standard utilizzata per i documenti di Microsoft Dynamics 365 for Finance and Operations e collegare il documento al record documenti cespiti creato.</span><span class="sxs-lookup"><span data-stu-id="025c7-107">In that case, you just have to put the updated document in the standard location that you use for your Microsoft Dynamics 365 for Finance and Operations documents, and attach the document to the asset document record that you've created.</span></span> <span data-ttu-id="025c7-108">Il documento aggiornato potrà quindi essere accessibile tramite **Tutti i cespiti**, **Cespiti attivi**, **Cespiti attivi personali**, **Tutti gli ordini di lavoro** e **Processi ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="025c7-108">The updated document can then be accessed from the **All assets**, **Active assets**, **My active assets**, **All work orders**, and **Active work order jobs** menu items.</span></span> <span data-ttu-id="025c7-109">Il processo per collegare documenti a un record documenti cespiti utilizza il sistema di gestione documenti standard di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="025c7-109">The process for attaching documents to an asset document record uses the standard document handling system in Finance and Operations.</span></span>

<span data-ttu-id="025c7-110">**Esempio 1:** un documento correlato a un tipo di processo può descrivere una procedura per questo tipo di processo.</span><span class="sxs-lookup"><span data-stu-id="025c7-110">**Example 1:** A document that is related to a job type might describe a procedure for that job type.</span></span>

<span data-ttu-id="025c7-111">**Esempio 2:** un documento correlato a una combinazione di tipo cespite, produttore e modello potrebbe essere il manuale predefinito per il modello del produttore del cespite selezionato.</span><span class="sxs-lookup"><span data-stu-id="025c7-111">**Example 2:** A document that is related to a combination of an asset type, manufacturer, and model might be the standard manual for the selected asset manufacturer model.</span></span>

## <a name="create-asset-document-relation"></a><span data-ttu-id="025c7-112">Creare la relazione dei documenti cespiti</span><span class="sxs-lookup"><span data-stu-id="025c7-112">Create asset document relation</span></span>

1. <span data-ttu-id="025c7-113">Selezionare **Gestione cespiti** \> **Impostazione** \> **Documenti cespiti**.</span><span class="sxs-lookup"><span data-stu-id="025c7-113">Select **Asset management** \> **Setup** \> **Asset documents**.</span></span>
2. <span data-ttu-id="025c7-114">Selezionare **Nuovo** per creare un record documenti cespiti.</span><span class="sxs-lookup"><span data-stu-id="025c7-114">Select **New** to create an asset document record.</span></span>
3. <span data-ttu-id="025c7-115">A seconda del livello di specificità desiderato per la relazione del documento, selezionare opzioni appropriate in uno o più dei campi seguenti: **Tipo di cespite**, **Produttore**, **Modello**, **Cespite**, **Categoria tipo di processo**, **Tipo di processo**, **Variante tipo di processo** e **Fabbisogno processo**.</span><span class="sxs-lookup"><span data-stu-id="025c7-115">Depending on how specific you want the document relation to be, make relevant selections in one or more of the following fields: **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement**.</span></span> <span data-ttu-id="025c7-116">Le opzioni disponibili nei campi **Fabbisogno processo** e **Variante tipo di processo** dipendono dalla selezione effettuata nel campo **Tipo di processo**.</span><span class="sxs-lookup"><span data-stu-id="025c7-116">The options that are available in the **Job type variant** and **Job requirement** fields depend on your selection in the **Job type** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="025c7-117">Quando il sistema cerca i documenti che devono essere correlati a un cespite o un ordine di lavoro, Gestione cespiti analizza tutti i record documenti cespiti per verificare la presenza di una corrispondenza possibile.</span><span class="sxs-lookup"><span data-stu-id="025c7-117">When the system searches for documents that should be related to an asset or a work order, Asset Management goes through all asset document records to check for a possible match.</span></span> <span data-ttu-id="025c7-118">Controlla sempre la combinazione più specifica per prima.</span><span class="sxs-lookup"><span data-stu-id="025c7-118">It always checks the most specific combination first.</span></span> <span data-ttu-id="025c7-119">In altre parole, Gestione cespiti controlla prima **Fabbisogno processo** per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="025c7-119">In other words, Asset Management first checks for a match for the **Job requirement** field.</span></span> <span data-ttu-id="025c7-120">Se non trova corrispondenza, controlla **Variante tipo di processo**.</span><span class="sxs-lookup"><span data-stu-id="025c7-120">If no match is found, it checks for a match for the **Job type variant** field.</span></span> <span data-ttu-id="025c7-121">Se non trova corrispondenza, controlla **Tipo di processo** e così via.</span><span class="sxs-lookup"><span data-stu-id="025c7-121">If no match is found, it checks for a match for the **Job type** field, and so on.</span></span> <span data-ttu-id="025c7-122">Come si vede nel layout della pagina **Documenti cespiti**, questo comportamento significa che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="025c7-122">As you can see in the layout of the **Asset documents** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="025c7-123">È possibile che più documenti possono essere collegati a un cespite o un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="025c7-123">Several documents might be related to an asset or a work order.</span></span> <span data-ttu-id="025c7-124">È possibile modificare il livello di servizio in una richiesta di intervento di manutenzione o un ordine di lavoro in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="025c7-124">You can edit the service level on a maintenance request or a work order as you require.</span></span>

4. <span data-ttu-id="025c7-125">Selezionare **Allegati**.</span><span class="sxs-lookup"><span data-stu-id="025c7-125">Select **Attachments**.</span></span> <span data-ttu-id="025c7-126">Verrà visualizzata la pagina **Gestione documenti** standard in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="025c7-126">The standard **Document handling** page in Finance and Operations appears.</span></span>
5. <span data-ttu-id="025c7-127">Impostare i documenti o note che dovranno essere collegati al record documenti cespiti.</span><span class="sxs-lookup"><span data-stu-id="025c7-127">Set up the documents or notes that should be attached to the asset document record.</span></span> <span data-ttu-id="025c7-128">Dopo aver collegato i documenti, il campo **Allegati** mostra il numero di documenti correlati al record.</span><span class="sxs-lookup"><span data-stu-id="025c7-128">After you attach documents, the **Attachments** field shows the number of documents that are related to the record.</span></span>