---
title: Risoluzione dei problemi di integrazione con LinkedIn e Microsoft Dynamics 365 Talent - Attract
description: In questo argomento viene descritto come risolvere eventuali problemi quando di prova a pubblicare posizioni in LinkedIn da Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: b031fd95d2e7fc8405ad96139779091e00bb4d46
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551474"
---
# <a name="troubleshoot-integration-with-linkedin-and-microsoft-dynamics-365-talent---attract"></a><span data-ttu-id="7ca50-103">Risolvere i problemi di integrazione con LinkedIn e Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="7ca50-103">Troubleshoot integration with LinkedIn and Microsoft Dynamics 365 Talent - Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7ca50-104">Utilizzare le seguenti informazioni per risolvere i problemi relativi alla pubblicazione di posizioni in LinkedIn da Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="7ca50-104">Use the following information to help troubleshoot issues that you might have when you try to post jobs to LinkedIn from Microsoft Dynamics 365 Talent: Attract.</span></span>

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a><span data-ttu-id="7ca50-105">Non è possibile accedere a LinkedIn da Attract</span><span class="sxs-lookup"><span data-stu-id="7ca50-105">You can't sign in to LinkedIn from Attract</span></span>

<span data-ttu-id="7ca50-106">Se non si riesce ad accedere a LinkedIn da Attract, provare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ca50-106">If you're having trouble signing in to LinkedIn from Attract, try these steps:</span></span>

1. <span data-ttu-id="7ca50-107">Verificare che le credenziali di LinkedIn immesse in Attract siano valide e corrette.</span><span class="sxs-lookup"><span data-stu-id="7ca50-107">Verify that the LinkedIn credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="7ca50-108">Se le credenziali sono valide e corrette, contattare il [Supporto tecnico di LinkedIn](https://www.linkedin.com/help/linkedin).</span><span class="sxs-lookup"><span data-stu-id="7ca50-108">If the credentials are valid and correct, contact [LinkedIn support](https://www.linkedin.com/help/linkedin).</span></span>
3. <span data-ttu-id="7ca50-109">Se il problema persiste, contattare il [supporto tecnico Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="7ca50-109">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a><span data-ttu-id="7ca50-110">Le pubblicazioni delle posizioni da Attract non vengono visualizzate in LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7ca50-110">Job posts from Attract don't appear on LinkedIn</span></span>

<span data-ttu-id="7ca50-111">Se la posizione non viene visualizzata su LinkedIn dopo 24 ore, provare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ca50-111">If your job hasn't appeared on LinkedIn after 24 hours, try these steps:</span></span>

1. <span data-ttu-id="7ca50-112">Verificare che il proprio ID società di LinkedIn sia mappato alla pagina della società su LinkedIn e che sia immesso in modo corretto nell'interfaccia di amministrazione di Attract.</span><span class="sxs-lookup"><span data-stu-id="7ca50-112">Make sure that your LinkedIn Company ID maps to your LinkedIn company page and is correctly entered in the Attract Admin center.</span></span> <span data-ttu-id="7ca50-113">Per ulteriori informazioni sulla modifica delle impostazioni di LinkedIn nell'interfaccia di amministrazione, vedere [Impostare l'integrazione con LinkedIn](attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="7ca50-113">For more information about how to change LinkedIn settings in the Admin center, see [Set up integration with LinkedIn](attract-admin-linkedin.md).</span></span> <span data-ttu-id="7ca50-114">Per ulteriori informazioni sugli ID società LinkedIn, vedere [Associazione dell'ID società di LinkedIn alla bacheca di lavoro di LinkedIn - domande frequenti](https://www.linkedin.com/help/linkedin/answer/98972).</span><span class="sxs-lookup"><span data-stu-id="7ca50-114">For more information about LinkedIn Company IDs, see [Associating your LinkedIn Company ID with the LinkedIn Job Board - Frequently Asked Questions](https://www.linkedin.com/help/linkedin/answer/98972).</span></span>
2. <span data-ttu-id="7ca50-115">Verificare i dettagli della posizione su LinkedIn per assicurarsi che l'indirizzo sia completo.</span><span class="sxs-lookup"><span data-stu-id="7ca50-115">Check the job details on LinkedIn to make sure that the address is complete.</span></span> <span data-ttu-id="7ca50-116">Affinché la pubblicazione della posizione sia completata correttamente, è necessario specificare in LinkedIn almeno la città e il paese della posizione.</span><span class="sxs-lookup"><span data-stu-id="7ca50-116">To post a job successfully, LinkedIn needs at least the city and country or region of the job.</span></span>
3. <span data-ttu-id="7ca50-117">Assicurarsi che la posizione non sia un duplicato di un'altra posizione già pubblicata su LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="7ca50-117">Make sure that the job doesn't duplicate another job that has been posted on LinkedIn.</span></span> <span data-ttu-id="7ca50-118">LinkedIn non pubblica posizioni che sono già pubblicate negli slot di lavoro Premium o nelle inserzioni limitate di LinkedIn da un'altra fonte.</span><span class="sxs-lookup"><span data-stu-id="7ca50-118">LinkedIn won't post jobs that are duplicates of either LinkedIn Premium Job Slots or Limited Listings from another source.</span></span> <span data-ttu-id="7ca50-119">Verificare che un altro utente della stessa azienda non abbia già pubblicato la posizione manualmente.</span><span class="sxs-lookup"><span data-stu-id="7ca50-119">Verify that another person at your company didn't already post the job manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ca50-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ca50-120">See also</span></span>

[<span data-ttu-id="7ca50-121">Domande frequenti su LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7ca50-121">LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="7ca50-122">Pubblicare posizioni in LinkedIn da Attract</span><span class="sxs-lookup"><span data-stu-id="7ca50-122">Post jobs to LinkedIn from Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="7ca50-123">Selezionare i candidati con LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="7ca50-123">Source candidates with LinkedIn Recruiter</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="7ca50-124">Creare posizioni</span><span class="sxs-lookup"><span data-stu-id="7ca50-124">Create jobs</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="7ca50-125">Risoluzione dei problemi di integrazione con LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7ca50-125">Troubleshoot integration with LinkedIn</span></span>](./attract-troubleshoot-linkedin.md)
