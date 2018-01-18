---
title: "Estendere la funzionalità di Microsoft Dynamics 365 for Talent"
description: "Se sono state create Microsoft PowerApps, è possibile avviare tali applicazioni dai collegamenti in Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Talent
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 80f6d4e54d103b4511cbbbcce75ee29e8a04811b
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a><span data-ttu-id="0d13b-103">Estendere la funzionalità di Microsoft Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="0d13b-103">Extend the functionality of Microsoft Dynamics 365 for Talent</span></span>
<span data-ttu-id="0d13b-104">Se sono state create Microsoft PowerApps, è possibile avviare tali applicazioni dai collegamenti in Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="0d13b-104">If you’ve created any Microsoft PowerApps, you can start those applications from links within Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="0d13b-105">Per impostare l'accesso alle applicazioni, sarà necessario impostare alcune informazioni in Talent in una pagina di configurazione che è possibile aprire dall'area di lavoro **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="0d13b-105">To set up access to your applications, you’ll need to set up some information in Talent on a configuration page that you can open from the **System administration** workspace.</span></span>

## <a name="configuring-embedded-powerapps-within-talent"></a><span data-ttu-id="0d13b-106">Configurazione di PowerApps incorporate in Talent</span><span class="sxs-lookup"><span data-stu-id="0d13b-106">Configuring embedded PowerApps within Talent</span></span>
<span data-ttu-id="0d13b-107">Utilizzare la pagina **Imposta Microsoft PowerApps incorporate** per configurare le pagine di Talent per l'avvio delle applicazioni PowerApps.</span><span class="sxs-lookup"><span data-stu-id="0d13b-107">Use the **Set embedded Microsoft PowerApps** page to configure Talent pages to start PowerApps applications.</span></span> <span data-ttu-id="0d13b-108">Per aprire la pagina **Imposta Microsoft PowerApps incorporate**, aprire l'area di lavoro **Amministrazione sistema** e quindi aprire la scheda **Collegamenti**. Selezionare **Microsoft PowerApps** dal gruppo **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="0d13b-108">To open the **Set embedded Microsoft PowerApps** page, open the **System administration** workspace and then open the **Links** tab. Select **Microsoft PowerApps** from the **Setup** group.</span></span> 

<span data-ttu-id="0d13b-109">In questa pagina vengono inserite o impostate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d13b-109">The following information is entered or set on this page:</span></span> 

> - <span data-ttu-id="0d13b-110">Un nome descrittivo o un identificatore per ciascuna applicazione PowerApps.</span><span class="sxs-lookup"><span data-stu-id="0d13b-110">A descriptive name or identifier for each PowerApps application.</span></span>
> - <span data-ttu-id="0d13b-111">Un identificatore univoco (GUID) per ciascuna applicazione che si aggiunge a una pagina di Talent.</span><span class="sxs-lookup"><span data-stu-id="0d13b-111">A unique identifier (GUID) for each application that you add to a Talent page.</span></span> <span data-ttu-id="0d13b-112">L'ID app è disponibile nel sito di PowerApps, [powerapps.com](http://powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="0d13b-112">The app ID is available on the PowerApps site, [powerapps.com](http://powerapps.com/).</span></span> 
> - <span data-ttu-id="0d13b-113">La pagina da cui gli utenti possono aprire un'applicazione o un report.</span><span class="sxs-lookup"><span data-stu-id="0d13b-113">The page from which users can open an application or report.</span></span> <span data-ttu-id="0d13b-114">Non tutte le pagine di Talent supportano PowerApps e i report Power BI.</span><span class="sxs-lookup"><span data-stu-id="0d13b-114">Not all Talent pages support embedded PowerApps and Power BI reports.</span></span> 

 > [!NOTE]
 >  <span data-ttu-id="0d13b-115">Immettere il nome interno della pagina, anziché il nome visualizzato che appare in cima alla pagina.</span><span class="sxs-lookup"><span data-stu-id="0d13b-115">Enter the internal name of the page, rather than the display name that appears at the top of the page.</span></span> <span data-ttu-id="0d13b-116">Per trovare il nome interno, aprire la pagina di cui si necessita il nome interno e fare clic con il pulsante destro del mouse in un punto qualsiasi della pagina.</span><span class="sxs-lookup"><span data-stu-id="0d13b-116">To find the internal name, open the page that you need the internal name of, and right-click anywhere on the page.</span></span> <span data-ttu-id="0d13b-117">Quando si apre il menu, posizionare il puntatore del mouse sulla voce **Informazioni modulo**.</span><span class="sxs-lookup"><span data-stu-id="0d13b-117">When the menu opens, hover over the **Form information** item.</span></span> <span data-ttu-id="0d13b-118">Il nome interno del modulo viene visualizzato accanto alla voce **Modulo informazioni** nel menu.</span><span class="sxs-lookup"><span data-stu-id="0d13b-118">The internal form name is displayed next to the **Form information** item in the menu.</span></span>
 
> - <span data-ttu-id="0d13b-119">Specificare il controllo del modulo da cui l'applicazione può recuperare i dati del contesto.</span><span class="sxs-lookup"><span data-stu-id="0d13b-119">Specify the form control from which the application can retrieve context data.</span></span> <span data-ttu-id="0d13b-120">Ad esempio, un'applicazione potrebbe utilizzare i dati di un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="0d13b-120">For example, an application might use data about a worker.</span></span> <span data-ttu-id="0d13b-121">Se si accede alla pagina **Lavoratore** nel campo **Contesto**, la pagina **Lavoratore** si aprirà quando si avvia l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d13b-121">If you enter the **Worker** page in the **Context** field, the **Worker** page will open when you start the application.</span></span> <span data-ttu-id="0d13b-122">Qualsiasi immissione nel campo **Contesto** è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="0d13b-122">An entry in the **Context field** is optional.</span></span> 
> - <span data-ttu-id="0d13b-123">Impostare le dimensioni della finestra di dialogo in cui sarà eseguita l'applicazione PowerApps.</span><span class="sxs-lookup"><span data-stu-id="0d13b-123">Set the size of the dialog box on which the PowerApps application will run.</span></span> <span data-ttu-id="0d13b-124">Le finestre di dialogo sono indicate come "piccole" o "grandi" al fine di ottimizzare l'interfaccia utente quando l'applicazione viene eseguita rispettivamente su un telefono o un dispositivo più grande.</span><span class="sxs-lookup"><span data-stu-id="0d13b-124">The dialog boxes are designated as “small” or “large” to optimize the user interface when your application for running on a phone or a larger device, respectively.</span></span> 

<span data-ttu-id="0d13b-125">È anche possibile specificare le persone giuridiche per le quali un'applicazione sarà disponibile oppure renderla disponibile per tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="0d13b-125">You can also specify which legal entities an application will be available for, or you can make it available to all your legal entities.</span></span> <span data-ttu-id="0d13b-126">Per impostazione predefinita, le applicazioni PowerApps sono disponibili per tutte le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="0d13b-126">By default, your PowerApps applications are available to all legal entities.</span></span>

## <a name="opening-an-application"></a><span data-ttu-id="0d13b-127">Apertura di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="0d13b-127">Opening an application</span></span>
<span data-ttu-id="0d13b-128">Dopo avere configurato le applicazioni PowerApps incorporate, verranno aggiunti collegamenti alle applicazioni specificate nelle pagine all'interno di Talent.</span><span class="sxs-lookup"><span data-stu-id="0d13b-128">When you’ve configured embedded PowerApps applications, links to the applications that you specified will be added to the pages within Talent.</span></span> <span data-ttu-id="0d13b-129">Fare clic sul collegamento per aprire un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0d13b-129">Click a link to open an application.</span></span> 



