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
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 262514
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 3e0122d6e61efa012722c707ac4ca74c619e5a20
ms.openlocfilehash: 2981fae40e43dec96b4e5b6c812e96ee3e959a9d
ms.contentlocale: it-it
ms.lasthandoff: 07/31/2017

---

# <a name="file-formats-for-methods-of-payment"></a><span data-ttu-id="61196-103">Formati di file per i metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="61196-103">File formats for methods of payment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="61196-104">In questo argomento vengono descritti i due metodi per ottenere i formati di file che è possibile utilizzare per i metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="61196-104">This topic describes the two methods for getting file formats that you can use for methods of payment.</span></span>

<span data-ttu-id="61196-105">Sono disponibili due metodi che consentono di ottenere i formati di file da utilizzare con i metodi di pagamento, i formati di file di report elettronici (ER) o i formati di file X++.</span><span class="sxs-lookup"><span data-stu-id="61196-105">There are two methods that you can use to get file formats for use with methods of payment, electronic reporting (ER) file formats or X++ file formats.</span></span> <span data-ttu-id="61196-106">Quando si imposta un metodo di pagamento per un cliente o un fornitore, specificare i formati di file e gli standard da utilizzare per i pagamenti e la modalità con cui i pagamenti verranno elaborati.</span><span class="sxs-lookup"><span data-stu-id="61196-106">When you set up a method of payment for a customer or vendor, you indicate which file formats and standards should be used for payments and how payments will be processed.</span></span> <span data-ttu-id="61196-107">È possibile selezionare uno dei seguenti tipi di formati:</span><span class="sxs-lookup"><span data-stu-id="61196-107">You can select from the following types of formats:</span></span>

-   <span data-ttu-id="61196-108">Esportazione</span><span class="sxs-lookup"><span data-stu-id="61196-108">Export</span></span>
-   <span data-ttu-id="61196-109">Importazione</span><span class="sxs-lookup"><span data-stu-id="61196-109">Import</span></span>
-   <span data-ttu-id="61196-110">Restituita</span><span class="sxs-lookup"><span data-stu-id="61196-110">Return</span></span>
-   <span data-ttu-id="61196-111">Rimessa</span><span class="sxs-lookup"><span data-stu-id="61196-111">Remittance</span></span>

### <a name="method-1-electronic-reporting-file-formats"></a><span data-ttu-id="61196-112">Metodo 1: formati di file di report elettronici</span><span class="sxs-lookup"><span data-stu-id="61196-112">Method 1: Electronic reporting file formats</span></span>

<span data-ttu-id="61196-113">Per i formati di file che si basano sulle configurazioni di report elettronici, è necessario importare le configurazioni da Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="61196-113">For file formats that are based on ER configurations, you must import the configurations from Lifecycle Services (LCS).</span></span> <span data-ttu-id="61196-114">Per ulteriori informazioni, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span><span class="sxs-lookup"><span data-stu-id="61196-114">For more information, see [Download Electronic reporting configurations from Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span></span> <span data-ttu-id="61196-115">Dopo che le configurazioni di report per i formati di file sono state importate, i formati importati saranno disponibili per la selezione nella pagina **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="61196-115">After you import reporting configurations for those file formats, the imported formats will be available to select on the **Methods of payment** page.</span></span> <span data-ttu-id="61196-116">Il processo per importare e selezionare i formati di file per l'Europa è simile alla procedura per il Giappone.</span><span class="sxs-lookup"><span data-stu-id="61196-116">The process for importing and selecting file formats for Europe is similar to the procedure for Japan.</span></span> <span data-ttu-id="61196-117">Per ulteriori informazioni, vedere [Abilitare il formato del file di pagamento JBA](/dynamics365/unified-operations/financials/localizations/tasks/jba-payment-file-format)</span><span class="sxs-lookup"><span data-stu-id="61196-117">For more details, see [Enable the JBA payment file format](/dynamics365/unified-operations/financials/localizations/tasks/jba-payment-file-format)</span></span>

### <a name="method-2-x-file-formats"></a><span data-ttu-id="61196-118">Metodo 2: formati di file X++</span><span class="sxs-lookup"><span data-stu-id="61196-118">Method 2: X++ file formats</span></span>

<span data-ttu-id="61196-119">Per selezionare i formati di file basati sul codice X++, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="61196-119">To select file formats that are based on X++ code, complete the following steps.</span></span>

1.  <span data-ttu-id="61196-120">Passare alla pagina **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="61196-120">Go to the **Methods of payment** page.</span></span>
2.  <span data-ttu-id="61196-121">Nella Scheda dettaglio **Formati file** fare clic su **Impostazione**.</span><span class="sxs-lookup"><span data-stu-id="61196-121">On the **File formats** FastTab, click **Setup**.</span></span>
3.  <span data-ttu-id="61196-122">Selezionare la scheda corrispondente al tipo di formato di file.</span><span class="sxs-lookup"><span data-stu-id="61196-122">Select the tab that corresponds with the file format type.</span></span>
4.  <span data-ttu-id="61196-123">Selezionare un formato di file dall'elenco **Disponibile** e spostarlo nell'elenco **Selezionati** utilizzando la freccia.</span><span class="sxs-lookup"><span data-stu-id="61196-123">Select a file format from the **Available** list and move it to the **Selected** list with the arrow control.</span></span>
5.  <span data-ttu-id="61196-124">Chiudere la pagina **Formati di file per i metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="61196-124">Close the **File formats for methods of payment** page.</span></span>
6.  <span data-ttu-id="61196-125">Nella Scheda dettaglio **Formati file** selezionare il formato di file per il metodo di pagamento per il campo di formato di file appropriato.</span><span class="sxs-lookup"><span data-stu-id="61196-125">On the **File formats** FastTab, select the file format to use for the method of payment from the appropriate file format field.</span></span> <span data-ttu-id="61196-126">Le opzioni di report elettronico generali devono essere impostate su **No** per i formati di file X++.</span><span class="sxs-lookup"><span data-stu-id="61196-126">The General electronic reporting options should be set to **No** for X++ file formats.</span></span>





