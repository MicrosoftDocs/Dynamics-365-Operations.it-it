---
title: Disabilitare le regole nel controllo di coerenza per le transazioni di vendita al dettaglio
description: In questo argomento viene descritta la funzionalità per disabilitare le regole del controllo di coerenza per le transazioni in Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 51a02d6f305cbad9784cf1b811188d0e06b6f15b
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057639"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="a3345-103">Disabilitare le regole nel controllo di coerenza per le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="a3345-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="a3345-104">Ogni rivenditore può avere scenari e processi aziendali molto specifici.</span><span class="sxs-lookup"><span data-stu-id="a3345-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="a3345-105">Pertanto, non tutte le regole incluse nel controllo di coerenza per le transazioni di commercio sono applicabili a tutti i rivenditori.</span><span class="sxs-lookup"><span data-stu-id="a3345-105">Therefore, not all the rules that are included by default in the commerce transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="a3345-106">Per soddisfare le diverse esigenze, Microsoft Dynamics 365 Commerce offre funzionalità che possono essere utilizzate per disabilitare le regole che non sono applicabili.</span><span class="sxs-lookup"><span data-stu-id="a3345-106">To accommodate differences, Microsoft Dynamics 365 Commerce provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="a3345-107">Per visualizzare l'elenco delle regole disponibili nel controllo di coerenza per le transazioni di vendita al dettaglio nel proprio ambiente e lo stato di ogni regola, andare a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri Commerce** e selezionare la scheda **Convalida transazioni**.</span><span class="sxs-lookup"><span data-stu-id="a3345-107">To view the list of rules that are available in the transaction consistency checker in your environment, and to see the status of each rule, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="a3345-108">Per impostazione predefinita, lo stato di ogni regola è impostato su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="a3345-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="a3345-109">Pertanto, vengono utilizzate tutte le regole per convalidare le transazioni prima che queste vengano inserite nei relativi rendiconti.</span><span class="sxs-lookup"><span data-stu-id="a3345-109">Therefore, all the rules are used to validate transactions before they are pulled into the commerce statements.</span></span> <span data-ttu-id="a3345-110">Per disabilitare una regola, modificarne lo stato in **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="a3345-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="a3345-111">Le regole disabilitate non vengono prese in considerazione per convalidare le transazioni durante il processo di calcolo dei rendiconti.</span><span class="sxs-lookup"><span data-stu-id="a3345-111">Disabled rules aren't considered when transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="a3345-112">Per ignorare l'intero processo di convalida, indipendentemente da quali regole siano abilitate, andare a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri Commerce** e, nella scheda **Convalida transazioni**, impostare l'opzione **Disabilita controllo di coerenza per le transazioni di commercio** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a3345-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Commerce transactions** option to **Yes**.</span></span> <span data-ttu-id="a3345-113">Una volta impostata su **No**, questa opzione non può essere impostata nuovamente su **Sì** dall'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="a3345-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>