---
title: Impostare autorità di ritenuta d'acconto per il tipo di imposta TDS
description: Questo argomento descrive come impostare autorità per l'imposta dedotta all'origine (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 5375363a9b1383a83e80fc3c4b841780adab4172
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023350"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a><span data-ttu-id="09510-103">Impostare autorità di ritenuta d'acconto per il tipo di imposta TDS</span><span class="sxs-lookup"><span data-stu-id="09510-103">Set up withholding tax authorities for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09510-104">Questo argomento descrive come impostare autorità per l'imposta dedotta all'origine (TDS).</span><span class="sxs-lookup"><span data-stu-id="09510-104">This topic explains how to set up Tax Deducted at Source (TDS) authorities.</span></span>

1. <span data-ttu-id="09510-105">Seleziona **Imposta \> Imposte indirette \> Uffici ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="09510-105">Go to **Tax \> Indirect taxes \> Withholding tax authorities**.</span></span>

    <span data-ttu-id="09510-106">[![Pagina Uffici ritenuta d'acconto](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span><span class="sxs-lookup"><span data-stu-id="09510-106">[![Withholding tax authorities page](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span></span>

2. <span data-ttu-id="09510-107">Nel campo **Tipo di imposta**, seleziona **TDS** per impostare gli uffici di ritenuta d'acconto per il tipo di imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="09510-107">In the **Tax type** field, select **TDS** to set up withholding tax authorities for the TDS tax type.</span></span>
3. <span data-ttu-id="09510-108">Nel riquadro azioni seleziona **Nuova** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="09510-108">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="09510-109">Nel campo **Uffici ritenuta d'acconto**, immetti il nome dell'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="09510-109">In the **Withholding tax authority** field, enter a name for the TDS authority.</span></span>
5. <span data-ttu-id="09510-110">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="09510-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="09510-111">Nella Scheda dettaglio **Generale**, nel campo **COnto fornitore**, seleziona il conto fornitore per l'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="09510-111">On the **General** FastTab, in the **Vendor account** field, select the vendor account for the TDS authority.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09510-112">Devi definire il nome della banca in cui verranno depositati i fondi dovuti al fornitore dell'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="09510-112">You must define the name of the bank where funds that are owed to the TDS authority vendor will be deposited.</span></span> <span data-ttu-id="09510-113">Il nome della banca è definito nella pagina **Conti bancari** (**Contabilità fornitori \> Tutti i fornitori \> Fornitore \> Configura \> Conti bancari**).</span><span class="sxs-lookup"><span data-stu-id="09510-113">The bank's name is defined on the **Bank accounts** page (**Accounts payable \> All vendors \> Vendor \> Set up \> Bank accounts**).</span></span>

7. <span data-ttu-id="09510-114">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="09510-114">Close the page.</span></span>
