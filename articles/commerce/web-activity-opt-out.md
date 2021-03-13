---
title: Disattiva la raccolta eventi per attività Web
description: Questo argomento spiega come consentire ai visitatori del tuo sito Web di annullare la raccolta di eventi di attività Web in Microsoft Dynamics 365 Commerce.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2c396060017db6d7ce830b350f242d3097876e50
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012315"
---
# <a name="opt-out-of-web-activity-event-collection"></a><span data-ttu-id="8b815-103">Disattiva la raccolta eventi per attività Web</span><span class="sxs-lookup"><span data-stu-id="8b815-103">Opt out of web activity event collection</span></span>
[!include [banner](includes/banner.md)]

<span data-ttu-id="8b815-104">Questo argomento descrive come è possibile consentire di disattivare la raccolta eventi per l'attività Web in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8b815-104">This topic explains how you can let customers opt out of web activity event collection in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8b815-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8b815-105">Overview</span></span>

<span data-ttu-id="8b815-106">Dynamics 365 Commerce consente agli amministratori del sito di analizzare l'attività Web degli utenti dei loro siti di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="8b815-106">Dynamics 365 Commerce lets site administrators analyze the web activity of users of their e-commerce sites.</span></span> <span data-ttu-id="8b815-107">In questo modo, possono comprendere meglio come vengono utilizzati i loro siti e possono ottimizzare i siti per fornire una migliore esperienza utente e soddisfare gli obiettivi aziendali.</span><span class="sxs-lookup"><span data-stu-id="8b815-107">In that way, they can better understand how their sites are used, and they can optimize the sites to provide an improved user experience and meet business objectives.</span></span>


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a><span data-ttu-id="8b815-108">Metodi di implementazione di un'esperienza di rifiuto esplicito per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="8b815-108">Ways for administrators to implement an opt-out experience</span></span>

<span data-ttu-id="8b815-109">Gli amministratori hanno a disposizione 3 metodi di implementazione di un'esperienza di rifiuto esplicito.</span><span class="sxs-lookup"><span data-stu-id="8b815-109">Administrators have three ways to implement an opt-out experience.</span></span>

### <a name="opt-out-on-behalf-of-users"></a><span data-ttu-id="8b815-110">Rifiuto esplicito per conto degli utenti</span><span class="sxs-lookup"><span data-stu-id="8b815-110">Opt out on behalf of users</span></span>

<span data-ttu-id="8b815-111">Nella gestione degli account in Commerce headquarters (HQ), gli amministratori possono attivare il rifiuto esplicito per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8b815-111">In Account management in Commerce headquarters (HQ), administrators can opt out on behalf of users.</span></span>

1. <span data-ttu-id="8b815-112">Nel client HQ, nella pagina **Tutti i clienti**, cerca e seleziona un cliente.</span><span class="sxs-lookup"><span data-stu-id="8b815-112">In the HQ client, on the **All customers** page, search for and select a customer.</span></span>
1. <span data-ttu-id="8b815-113">Nella pagina dei dettagli del cliente, nella Scheda dettaglio **Retail**, sezione **Privacy**, imposta l'opzione **Non eseguire la traccia dell'attività Web** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8b815-113">On the customer details page, on the **Retail** FastTab, in the **Privacy** section, set the **Do not track web activity** option to **Yes**.</span></span>

    ![Impostazioni di privacy](media/Disablepersonalizationpart2.png)

1. <span data-ttu-id="8b815-115">Selezionare **Salva**, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8b815-115">Select **Save**, and then close the page.</span></span>

### <a name="module-based-opt-out-experience"></a><span data-ttu-id="8b815-116">Esperienza di rifiuto basata su moduli</span><span class="sxs-lookup"><span data-stu-id="8b815-116">Module-based opt-out experience</span></span>

<span data-ttu-id="8b815-117">Gli amministratori possono consentire agli utenti autenticati di rinunciare autonomamente alla raccolta di eventi di attività Web.</span><span class="sxs-lookup"><span data-stu-id="8b815-117">Administrators can let authenticated users opt out of web activity event collection by themselves.</span></span> <span data-ttu-id="8b815-118">Per fornire questa esperienza di rifiuto, aggiungere il modulo di rifiuto esplicito dell'utente alle pagine del profilo dell'account cliente.</span><span class="sxs-lookup"><span data-stu-id="8b815-118">To provide this opt-out experience, add the user opt-out module to customer account profile pages.</span></span>

### <a name="custom-extensions"></a><span data-ttu-id="8b815-119">Estensioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="8b815-119">Custom extensions</span></span>

<span data-ttu-id="8b815-120">Gli amministratori possono creare estensioni personalizzate per gestire l'esperienza di rifiuto per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8b815-120">Administrators can create their own extensions to manage the opt-out experience for users.</span></span> <span data-ttu-id="8b815-121">Per ulteriori informazioni, vedere [Chiamare API Retail Server](e-commerce-extensibility/call-retail-server-apis.md)e [Estendibilità del canale online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="8b815-121">For more information, see [Call Retail Server APIs](e-commerce-extensibility/call-retail-server-apis.md) and [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>
