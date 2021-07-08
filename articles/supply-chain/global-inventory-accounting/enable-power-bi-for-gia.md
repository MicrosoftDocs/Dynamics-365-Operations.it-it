---
title: Abilitare Power BI per contabilità inventario globale
description: Questo argomento descrive come abilitare Microsoft Power BI per la contabilità dell'inventario globale.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273179"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a><span data-ttu-id="f463c-103">Abilitare Power BI per contabilità inventario globale</span><span class="sxs-lookup"><span data-stu-id="f463c-103">Enable Power BI for Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="f463c-104">Puoi aggiungere riquadri, dashboard e report dal tuo account [PowerBI.com](https://powerbi.com/) nella tua area di lavoro dell'applicazione Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f463c-104">You can pin tiles, dashboards, and reports from your [PowerBI.com](https://powerbi.com/) account to your Microsoft Dynamics 365 application workspace.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f463c-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f463c-105">Prerequisites</span></span>

<span data-ttu-id="f463c-106">I seguenti prerequisiti devono essere presenti prima di poter abilitare la creazione di report Power BI:</span><span class="sxs-lookup"><span data-stu-id="f463c-106">The following prerequisites must be in place before you can enable Power BI reporting:</span></span>

- <span data-ttu-id="f463c-107">Devi essere un amministratore di sistema nell'applicazione Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f463c-107">You must be a system administrator in the Dynamics 365 application.</span></span>
- <span data-ttu-id="f463c-108">Devi avere un account [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="f463c-108">You must have a [PowerBI.com](https://powerbi.com/) account.</span></span>
- <span data-ttu-id="f463c-109">Devi avere almeno un dashboard e un report nel tuo account Power BI.</span><span class="sxs-lookup"><span data-stu-id="f463c-109">You must have at least one dashboard and one report in your Power BI account.</span></span>
- <span data-ttu-id="f463c-110">Devi essere un amministratore per il tuo account Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f463c-110">You must be an administrator for your Azure Active Directory (Azure AD) account.</span></span>
- <span data-ttu-id="f463c-111">Il dominio Azure AD deve essere lo stesso che hai usato per il tuo account [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="f463c-111">The Azure AD domain must be the same domain that you used for your [PowerBI.com](https://powerbi.com/) account.</span></span>

## <a name="setup"></a><span data-ttu-id="f463c-112">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="f463c-112">Setup</span></span>

<span data-ttu-id="f463c-113">Seguire questi passaggi per configurare Power BI.</span><span class="sxs-lookup"><span data-stu-id="f463c-113">To set up the Power BI integration, follow these steps.</span></span>

1. <span data-ttu-id="f463c-114">Accedi a [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="f463c-114">Sign in to [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="f463c-115">Vai a **Raccolta di risorse condivise**, seleziona **Modello di report Power BI** come tipo di risorsa e scarica il pacchetto **Contabilità inventario globale**.</span><span class="sxs-lookup"><span data-stu-id="f463c-115">Go to **Shared asset library**, select **Power BI report model** as the asset type, and download the **Global Inventory Accounting** package.</span></span> 
1. <span data-ttu-id="f463c-116">Accedi a [PowerBI.com](https://app.powerbi.com/), e carica il file di report Power BI **Contabilità inventario globale** seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="f463c-116">Sign in to [PowerBI.com](https://app.powerbi.com/), and upload the **Global Inventory Accounting** Power BI report file by following these steps:</span></span>

    1. <span data-ttu-id="f463c-117">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f463c-117">Select **New**.</span></span>
    1. <span data-ttu-id="f463c-118">Seleziona **Carica un file**.</span><span class="sxs-lookup"><span data-stu-id="f463c-118">Select **Upload a file**.</span></span>
    1. <span data-ttu-id="f463c-119">Seleziona il file di report Power BI **Contabilità inventario globale**.</span><span class="sxs-lookup"><span data-stu-id="f463c-119">Select the **Global Inventory Accounting** Power BI report file.</span></span>

1. <span data-ttu-id="f463c-120">Configura il report Power BI **Contabilità inventario globale** seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="f463c-120">Configure the **Global Inventory Accounting** Power BI report by following these steps:</span></span>

    1. <span data-ttu-id="f463c-121">Vai a **Area di lavoro personale**, trova il set di dati per Contabilità inventario globale, quindi, sul menu **Opzioni** seleziona **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="f463c-121">Go to **My workspace**, find the dataset for Global Inventory Accounting, and then, on the **Options** menu, select **Settings**.</span></span>
    1. <span data-ttu-id="f463c-122">In **Impostazioni per Contabilità inventario globale**, espandi **Parametri** e aggiorna tutti i parametri come richiesto.</span><span class="sxs-lookup"><span data-stu-id="f463c-122">In **Settings for Global inventory accounting**, expand **Parameters**, and update all parameters as required.</span></span>

1. <span data-ttu-id="f463c-123">Registra l'applicazione come descritto in [Configurare l'integrazione di PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span><span class="sxs-lookup"><span data-stu-id="f463c-123">Register the application as described in [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span></span>
1. <span data-ttu-id="f463c-124">Integra il file di report Power BI **Contabilità inventario globale** in Dynamics 365 Supply Chain Management seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="f463c-124">Integrate the **Global Inventory Accounting** Power BI report file into Dynamics 365 Supply Chain Management by following these steps:</span></span>

    1. <span data-ttu-id="f463c-125">Accedere a **Amministrazione sistema \> Impostazioni \> Configurazione PowerBI.com**.</span><span class="sxs-lookup"><span data-stu-id="f463c-125">Go to **System administration \> Setup \> PowerBI.com configuration**.</span></span>
    1. <span data-ttu-id="f463c-126">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="f463c-126">Select **Edit**.</span></span>
    1. <span data-ttu-id="f463c-127">Seleziona **Abilita integrazione PowerBI.Com**.</span><span class="sxs-lookup"><span data-stu-id="f463c-127">Select **Enable PowerBI.Com integration**.</span></span>
    1. <span data-ttu-id="f463c-128">Nel campo **ID applicazione** immetti l'ID applicazione.</span><span class="sxs-lookup"><span data-stu-id="f463c-128">In the **Application ID** field, enter the application ID.</span></span>
    1. <span data-ttu-id="f463c-129">Nel campo **Chiave applicazione** immetti la chiave dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f463c-129">In the **Application key** field, enter the application key.</span></span>
    1. <span data-ttu-id="f463c-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f463c-130">Select **Save**.</span></span>

1. <span data-ttu-id="f463c-131">Aggiorna la pagina in modo che viene visualizzata la finestra di dialogo di accesso Power BI.</span><span class="sxs-lookup"><span data-stu-id="f463c-131">Refresh the page so that the Power BI sign-in dialog box appears.</span></span>
1. <span data-ttu-id="f463c-132">Nella scheda **Opzioni** seleziona **Apri catalogo di report**, quindi seleziona il file di report Power BI **Contabilità inventario globale** che hai caricato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f463c-132">On the **Options** tab, select **Open report catalog**, and then select the **Global Inventory Accounting** Power BI report file that you uploaded earlier.</span></span>
1. <span data-ttu-id="f463c-133">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="f463c-133">Refresh the page.</span></span> <span data-ttu-id="f463c-134">Dovresti vedere che il tuo report è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="f463c-134">You should see that your report has been added.</span></span>
1. <span data-ttu-id="f463c-135">In **Report Power BI**, seleziona il collegamento **Contabilità inventario globale**.</span><span class="sxs-lookup"><span data-stu-id="f463c-135">Under **Power BI reports**, select the **Global Inventory Accounting** link.</span></span>

<span data-ttu-id="f463c-136">Per ulteriori informazioni, vedi [Configurare l'integrazione di PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span><span class="sxs-lookup"><span data-stu-id="f463c-136">For more information, see [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span></span>
