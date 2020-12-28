---
title: Abilitare l'integrazione di Broadbean in Attract
description: In questo argomento viene descritto come configurare Microsoft Dynamics 365 Talent - Attract per pubblicare le posizioni in bacheche mansioni esterne, ad esempio in Broadbean.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 10b612711e81b2b368ed23fdd95ab6a66451f0ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461698"
---
# <a name="enable-broadbean-integration-in-attract"></a><span data-ttu-id="f2d28-103">Abilitare l'integrazione di Broadbean in Attract</span><span class="sxs-lookup"><span data-stu-id="f2d28-103">Enable Broadbean integration in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f2d28-104">Se si desidera rendere visibili le posizioni aperte nella propria azienda al maggior numero possibile di candidati,</span><span class="sxs-lookup"><span data-stu-id="f2d28-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="f2d28-105">esistono siti di reclutamento come Broadbean che consentono di soddisfare tale esigenza.</span><span class="sxs-lookup"><span data-stu-id="f2d28-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="f2d28-106">Microsoft Dynamics 365 Talent: Attract consente ora di pubblicare posizioni in Broadbean e Microsoft pubblica costantemente nuove offerte in quest'area.</span><span class="sxs-lookup"><span data-stu-id="f2d28-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

> [!NOTE]
> - <span data-ttu-id="f2d28-107">Per pubblicare annunci di lavoro su siti esterni, è necessario disporre del [componente aggiuntivo per l'assunzione a livello globale](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="f2d28-107">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="f2d28-108">Per pubblicare annunci di lavoro tramite Attract, è necessario disporre di una sottoscrizione Broadbend.</span><span class="sxs-lookup"><span data-stu-id="f2d28-108">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="f2d28-109">Questa funzionalità è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="f2d28-109">This feature is currently in preview.</span></span> <span data-ttu-id="f2d28-110">Se si desidera provarlo, è necessario [attivarlo nelle impostazioni di amministrazione di Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="f2d28-110">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

## <a name="configure-broadbean-integration"></a><span data-ttu-id="f2d28-111">Configurare l'integrazione di Broadbean</span><span class="sxs-lookup"><span data-stu-id="f2d28-111">Configure Broadbean integration</span></span>

1. <span data-ttu-id="f2d28-112">Accedere a Attract come amministratore.</span><span class="sxs-lookup"><span data-stu-id="f2d28-112">Sign in to Attract as an admin.</span></span>

2. <span data-ttu-id="f2d28-113">Selezionare il pulsante **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro della pagina, quindi selezionare **Interfaccia di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="f2d28-113">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>

3. <span data-ttu-id="f2d28-114">Contattare Broadbean e immettere le informazioni nei campi **Nome utente**, **ID client** e **Token di crittografia**.</span><span class="sxs-lookup"><span data-stu-id="f2d28-114">Contact Broadbean, and enter your information in the **Username**, **Client ID**, and **Encryption Token** fields.</span></span>

4. <span data-ttu-id="f2d28-115">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2d28-115">Select **Save**.</span></span>

> [!WARNING]
> <span data-ttu-id="f2d28-116">Le credenziali Broadbean sono sensibili e riservate.</span><span class="sxs-lookup"><span data-stu-id="f2d28-116">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="f2d28-117">Di conseguenza, conservarle e condividerle in modo responsabile.</span><span class="sxs-lookup"><span data-stu-id="f2d28-117">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="f2d28-118">Chiunque abbia un ruolo di amministratore in Attract può visualizzare tali credenziali.</span><span class="sxs-lookup"><span data-stu-id="f2d28-118">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="f2d28-119">Microsoft e Attract non partecipano alla creazione e alla gestione di tali dati.</span><span class="sxs-lookup"><span data-stu-id="f2d28-119">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="f2d28-120">È responsabilità dell'utente mantenerli aggiornati in Attract e collaborare con Broadbean per risolvere eventuali problemi relativi alle credenziali.</span><span class="sxs-lookup"><span data-stu-id="f2d28-120">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>
