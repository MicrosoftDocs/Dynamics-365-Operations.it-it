---
title: Riutilizzare le configurazioni prodotto
description: "È possibile specificare che si desidera automaticamente riutilizzare una configurazione esistente per un prodotto. Quindi quando l'utente termina una sessione di configurazione, il sistema verifica se è già presente una configurazione corrispondente alle selezioni dell'utente. Se viene rilevata una configurazione corrispondente, vengono riutilizzati l'ID di configurazione, la distinta base (DBA) corrispondente e il ciclo di lavorazione."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: c447440c33c1f80c6056974086b90d3b43e8499e
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---

# <a name="reuse-product-configurations"></a><span data-ttu-id="56acc-105">Riutilizzare le configurazioni prodotto</span><span class="sxs-lookup"><span data-stu-id="56acc-105">Reuse product configurations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="56acc-106">È possibile specificare che si desidera automaticamente riutilizzare una configurazione esistente per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="56acc-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="56acc-107">Quindi quando l'utente termina una sessione di configurazione, il sistema verifica se è già presente una configurazione corrispondente alle selezioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="56acc-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="56acc-108">Se viene rilevata una configurazione corrispondente, vengono riutilizzati l'ID di configurazione, la distinta base (DBA) corrispondente e il ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="56acc-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="56acc-109">Requisiti per il riutilizzo delle configurazioni</span><span class="sxs-lookup"><span data-stu-id="56acc-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="56acc-110">Per abilitare il riutilizzo delle configurazioni, è necessario specificare le seguenti informazioni per i componenti e gli attributi nella pagina **Dettagli modello configurazione prodotto**:</span><span class="sxs-lookup"><span data-stu-id="56acc-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="56acc-111">**Componenti e sottocomponenti** - Nella Scheda dettaglio **Generale**, campo **Riutilizza configurazioni**, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="56acc-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="56acc-112">**Attributi** - Nella scheda dettaglio **Attributi**, selezionare l'opzione **Includi in riutilizzo**.</span><span class="sxs-lookup"><span data-stu-id="56acc-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="56acc-113">Questa opzione viene visualizzata solo se il componente correlato è abilitato per il riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="56acc-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="56acc-114">Se non si seleziona alcun attributo per il riutilizzo, la configurazione verrà sempre riutilizzata, indipendentemente dalle selezioni dell'utente durante una sessione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="56acc-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="56acc-115">I valori degli attributi della configurazione esistente devono corrispondere alle selezioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="56acc-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="56acc-116">Ad esempio, se l'utente seleziona il colore **Blu** come colore durante una sessione di configurazione, il sistema verifica se una configurazione esistente del componente presenta il colore blu.</span><span class="sxs-lookup"><span data-stu-id="56acc-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="56acc-117">Reimpostazione del riutilizzo configurazioni</span><span class="sxs-lookup"><span data-stu-id="56acc-117">Resetting configuration reuse</span></span>
<span data-ttu-id="56acc-118">Quando si reimposta il riutilizzo delle configurazioni, le configurazioni create in precedenza non sono più considerate.</span><span class="sxs-lookup"><span data-stu-id="56acc-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="56acc-119">È possibile reimpostare il riutilizzo configurazioni se la DBA o il ciclo di lavorazione è stato modificato, ma nessun attributo correlato è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="56acc-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="56acc-120">È possibile reimpostare il riutilizzo configurazioni nella scheda dettaglio **Generale** del componente.</span><span class="sxs-lookup"><span data-stu-id="56acc-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>




