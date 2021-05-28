---
title: Impostare i numeri di registrazione TDS per persone giuridiche
description: Questo argomento spiega come impostare i numeri di registrazione dell'imposta dedotta all'origine (TDS, Tax Deducted at Source) per le persone giuridiche.
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
ms.openlocfilehash: 3550b2b7b305702ffc337ba0a9bb79f60a9de120
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023355"
---
# <a name="set-up-tds-registration-numbers-for-legal-entities"></a><span data-ttu-id="9889f-103">Impostare i numeri di registrazione TDS per persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="9889f-103">Set up TDS registration numbers for legal entities</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9889f-104">Questo argomento spiega come impostare i numeri di registrazione dell'imposta dedotta all'origine (TDS, Tax Deducted at Source) per le persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="9889f-104">This topic explains how to set up Tax Deducted at Source (TDS) registration numbers for legal entities.</span></span>

1. <span data-ttu-id="9889f-105">Andare a **Amministrazione organizzazione \> Organizzazioni \> Persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="9889f-105">Go to **Organization administration \> Organizations \> Legal entities**.</span></span>

    <span data-ttu-id="9889f-106">[![Pagina Persone giuridiche](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span><span class="sxs-lookup"><span data-stu-id="9889f-106">[![Legal entities page](./media/apac-ind-TDS-4.png)](./media/apac-ind-TDS-4.png)</span></span>

2. <span data-ttu-id="9889f-107">Nella Scheda dettaglio **Informazioni fiscali**, nel campo **Numero conto permanente**, immetti il numero di conto permanente (PAN) della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="9889f-107">On the **Tax information** FastTab, in the **Permanent account number** field, enter the permanent account number (PAN) of the legal entity.</span></span>
3. <span data-ttu-id="9889f-108">Nel campo **Numero circoscrizione**, immetti il numero di circoscrizione dell'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="9889f-108">In the **Circle number** field, enter the circle number of the TDS authority.</span></span>
4. <span data-ttu-id="9889f-109">Nel campo **Numero distretto**, immetti il numero di distretto dell'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="9889f-109">In the **Ward number** field, enter the ward number of the TDS authority.</span></span>
5. <span data-ttu-id="9889f-110">Nel campo **Funzionario valutatore**, immetti i dettagli del funzionario valutatore per l'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="9889f-110">In the **Assessing officer** field, enter the details of the assessing officer for the TDS authority.</span></span>
6. <span data-ttu-id="9889f-111">Nel campo **Tipo di fattore di detrazione**, seleziona la categoria del tipo di fattore di detrazione per la persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="9889f-111">In the **Type of deductor** field, select the deductor type category for the legal entity.</span></span>
7. <span data-ttu-id="9889f-112">Nel riquadro Azioni, seleziona **ID registrazione** per aprire la pagina **Gestisci indirizzi**.</span><span class="sxs-lookup"><span data-stu-id="9889f-112">On the Action Pane, select **Registration IDs** to open the **Manage addresses** page.</span></span>
8. <span data-ttu-id="9889f-113">Nella Scheda dettaglio **Informazioni fiscali**, seleziona **Aggiungi** o **Modifica** per aprire la pagina **Gestisci informazioni fiscali**, in cui puoi mantenere la voce di registrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="9889f-113">On the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>

    <span data-ttu-id="9889f-114">[![Pagina Gestisci indirizzi](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span><span class="sxs-lookup"><span data-stu-id="9889f-114">[![Manage addresses page](./media/apac-ind-TDS-5.png)](./media/apac-ind-TDS-5.png)</span></span>

9. <span data-ttu-id="9889f-115">Nella Scheda dettaglio **Ritenuta d'acconto**, nel campo **Numero conto imposta (TAN)**, immetti il numero di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9889f-115">On the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the registration number.</span></span> <span data-ttu-id="9889f-116">Questo numero deve essere composto da quattro caratteri alfabetici, quindi cinque caratteri numerici e infine un carattere alfabetico.</span><span class="sxs-lookup"><span data-stu-id="9889f-116">This number must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="9889f-117">Ad esempio: **AXDF87645F**.</span><span class="sxs-lookup"><span data-stu-id="9889f-117">Here is an example: **AXDF87645F**.</span></span>
10. <span data-ttu-id="9889f-118">Nel campo **Nome o descrizione**, immetti una descrizione del numero di registrazione della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="9889f-118">In the **Name or description** field, enter a description of the withholding tax registration number.</span></span>

    <span data-ttu-id="9889f-119">[![Pagina Gestisci informazioni fiscali](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span><span class="sxs-lookup"><span data-stu-id="9889f-119">[![Manage tax information page](./media/apac-ind-TDS-5-1.png)](./media/apac-ind-TDS-5-1.png)</span></span>

11. <span data-ttu-id="9889f-120">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="9889f-120">Close the page.</span></span>
