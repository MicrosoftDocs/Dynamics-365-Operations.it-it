---
title: Formati di file per i metodi di pagamento
description: "In questo argomento vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 262514
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b6ee0ceb9d773ad1f510a5d192a7094a37061808
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="file-formats-for-methods-of-payment"></a><span data-ttu-id="28c3f-103">Formati di file per i metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="28c3f-103">File formats for methods of payment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="28c3f-104">In questo argomento vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="28c3f-104">This topic describes the two methods for getting file formats that you can use for methods of payment.</span></span>

<span data-ttu-id="28c3f-105">Sono disponibili due metodi che consentono di ottenere i formati di file da utilizzare con i metodi di pagamento, i formati di file di report elettronici (ER) o i formati di file X++.</span><span class="sxs-lookup"><span data-stu-id="28c3f-105">There are two methods that you can use to get file formats for use with methods of payment, electronic reporting (ER) file formats or X++ file formats.</span></span> <span data-ttu-id="28c3f-106">Quando si imposta un metodo di pagamento per un cliente o un fornitore, specificare i formati di file e gli standard da utilizzare per i pagamenti e la modalità con cui i pagamenti verranno elaborati.</span><span class="sxs-lookup"><span data-stu-id="28c3f-106">When you set up a method of payment for a customer or vendor, you indicate which file formats and standards should be used for payments and how payments will be processed.</span></span> <span data-ttu-id="28c3f-107">È possibile selezionare uno dei seguenti tipi di formati:</span><span class="sxs-lookup"><span data-stu-id="28c3f-107">You can select from the following types of formats:</span></span>

-   <span data-ttu-id="28c3f-108">Esportazione</span><span class="sxs-lookup"><span data-stu-id="28c3f-108">Export</span></span>
-   <span data-ttu-id="28c3f-109">Importazione</span><span class="sxs-lookup"><span data-stu-id="28c3f-109">Import</span></span>
-   <span data-ttu-id="28c3f-110">Restituita</span><span class="sxs-lookup"><span data-stu-id="28c3f-110">Return</span></span>
-   <span data-ttu-id="28c3f-111">Rimessa</span><span class="sxs-lookup"><span data-stu-id="28c3f-111">Remittance</span></span>

### <a name="method-1-electronic-reporting-file-formats"></a><span data-ttu-id="28c3f-112">Metodo 1: formati di file di report elettronici</span><span class="sxs-lookup"><span data-stu-id="28c3f-112">Method 1: Electronic reporting file formats</span></span>

<span data-ttu-id="28c3f-113">Per i formati di file che si basano sulle configurazioni di report elettronici, è necessario importare le configurazioni da Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="28c3f-113">For file formats that are based on ER configurations, you must import the configurations from Lifecycle Services (LCS).</span></span> <span data-ttu-id="28c3f-114">Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="28c3f-114">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="28c3f-115">Dopo che le configurazioni di report per i formati di file sono state importate, i formati importati saranno disponibili per la selezione nella pagina **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="28c3f-115">After you import reporting configurations for those file formats, the imported formats will be available to select on the **Methods of payment** page.</span></span> <span data-ttu-id="28c3f-116">Il processo per importare e selezionare i formati di file per l'Europa è simile alla procedura per il Giappone.</span><span class="sxs-lookup"><span data-stu-id="28c3f-116">The process for importing and selecting file formats for Europe is similar to the procedure for Japan.</span></span> <span data-ttu-id="28c3f-117">Per ulteriori informazioni, vedere [Abilitare il formato del file di pagamento JBA](tasks/jba-payment-file-format.md)</span><span class="sxs-lookup"><span data-stu-id="28c3f-117">For more details, see [Enable the JBA payment file format](tasks/jba-payment-file-format.md)</span></span>

### <a name="method-2-x-file-formats"></a><span data-ttu-id="28c3f-118">Metodo 2: formati di file X++</span><span class="sxs-lookup"><span data-stu-id="28c3f-118">Method 2: X++ file formats</span></span>

<span data-ttu-id="28c3f-119">Per selezionare i formati di file basati sul codice X++, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="28c3f-119">To select file formats that are based on X++ code, complete the following steps.</span></span>

1.  <span data-ttu-id="28c3f-120">Passare alla pagina **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="28c3f-120">Go to the **Methods of payment** page.</span></span>
2.  <span data-ttu-id="28c3f-121">Nella Scheda dettaglio **Formati file** fare clic su **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="28c3f-121">On the **File formats** FastTab, click **Setup**.</span></span>
3.  <span data-ttu-id="28c3f-122">Selezionare la scheda corrispondente al tipo di formato di file.</span><span class="sxs-lookup"><span data-stu-id="28c3f-122">Select the tab that corresponds with the file format type.</span></span>
4.  <span data-ttu-id="28c3f-123">Selezionare un formato di file dall'elenco **Disponibile** e spostarlo nell'elenco **Selezionati** utilizzando la freccia.</span><span class="sxs-lookup"><span data-stu-id="28c3f-123">Select a file format from the **Available** list and move it to the **Selected** list with the arrow control.</span></span>
5.  <span data-ttu-id="28c3f-124">Chiudere la pagina **Formati di file per i metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="28c3f-124">Close the **File formats for methods of payment** page.</span></span>
6.  <span data-ttu-id="28c3f-125">Nella Scheda dettaglio **Formati file** selezionare il formato di file per il metodo di pagamento per il campo di formato di file appropriato.</span><span class="sxs-lookup"><span data-stu-id="28c3f-125">On the **File formats** FastTab, select the file format to use for the method of payment from the appropriate file format field.</span></span> <span data-ttu-id="28c3f-126">Le opzioni di report elettronico generali devono essere impostate su **No** per i formati di file X++.</span><span class="sxs-lookup"><span data-stu-id="28c3f-126">The General electronic reporting options should be set to **No** for X++ file formats.</span></span>





