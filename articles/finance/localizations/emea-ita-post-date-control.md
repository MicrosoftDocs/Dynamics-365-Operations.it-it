---
title: Controllo unificato della data di registrazione
description: In questo argomento viene illustrato come configurare il controllo cronologico per le date di registrazione delle fatture.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 537707
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: db74b34bf0c11a7b3b38f4b3f41b475464722b6e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830411"
---
# <a name="unified-posting-date-control"></a><span data-ttu-id="459bb-103">Controllo unificato della data di registrazione</span><span class="sxs-lookup"><span data-stu-id="459bb-103">Unified posting date control</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="459bb-104">In questo argomento viene illustrato come configurare il controllo cronologico delle date di registrazione delle fatture all'interno di una specifica sezione del libro IVA.</span><span class="sxs-lookup"><span data-stu-id="459bb-104">This topic explains how to configure chronology control of invoices posting dates within a specific sales tax book section.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="459bb-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="459bb-105">Prerequisites</span></span>

- <span data-ttu-id="459bb-106">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="459bb-106">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="459bb-107">I libri e le sezioni IVA italiani sono configurati nel sistema.</span><span class="sxs-lookup"><span data-stu-id="459bb-107">Italian sales tax books and sections are configured in the system.</span></span> <span data-ttu-id="459bb-108">Per ulteriori informazioni, vedere [Libri IVA italiani](emea-ita-fiscal-books.md).</span><span class="sxs-lookup"><span data-stu-id="459bb-108">For more information, see [Italian sales tax books](emea-ita-fiscal-books.md).</span></span>
- <span data-ttu-id="459bb-109">Nell'area di lavoro Gestione funzionalità, attiva la funzionalità **Controllo unificato della data di registrazione (Italia)**.</span><span class="sxs-lookup"><span data-stu-id="459bb-109">In the Feature management workspace, turn on the **(Italy) Unified posting date control** feature.</span></span> <span data-ttu-id="459bb-110">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="459bb-110">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-posting-date-control"></a><span data-ttu-id="459bb-111">Configurare il controllo unificato della registrazione</span><span class="sxs-lookup"><span data-stu-id="459bb-111">Configure posting date control</span></span>
<span data-ttu-id="459bb-112">Completa i seguenti passaggi per configurare il controllo della data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="459bb-112">Complete the following steps to configure posting date control.</span></span>

1. <span data-ttu-id="459bb-113">Vai a **Imposta** > **Impostazione** > **IVA** > **Sezioni libro IVA italiano**.</span><span class="sxs-lookup"><span data-stu-id="459bb-113">Go to **Tax** > **Setup** > **Sales tax** > **Italian sales tax book sections**.</span></span> 
2. <span data-ttu-id="459bb-114">Nella colonna **Ignora controllo data di registrazione** seleziona se il controllo della data di registrazione è necessario per una sezione del libro IVA selezionata.</span><span class="sxs-lookup"><span data-stu-id="459bb-114">In the **Skip posting date control** column, select whether posting date control is required for a selected sales tax book section.</span></span>

![Controllo della data di registrazione](media/emea-ita-post-date-control.jpg)

 - <span data-ttu-id="459bb-116">Se il campo non è abilitato, che è l'opzione predefinita, il sistema non consente la registrazione di nuove fatture con date precedenti alla data dell'ultima fattura registrata.</span><span class="sxs-lookup"><span data-stu-id="459bb-116">If the field isn't enabled, which is the default option, the system doesn't allow posting of new invoices with dates earlier than the date of the latest posted invoice.</span></span>  
 - <span data-ttu-id="459bb-117">Se il campo è abilitato, il sistema consente la registrazione con qualsiasi data.</span><span class="sxs-lookup"><span data-stu-id="459bb-117">If the field is enabled, the system allows posting with any date.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
