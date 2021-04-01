---
title: Ritenuta d'acconto globale
description: Questo argomento fornisce informazioni sulla funzionalità della ritenuta d'acconto globale e su come configurarla. La funzionalità della ritenuta d'acconto globale è stata migliorata per le transazioni di fornitori e clienti, in modo che la ritenuta d'acconto venga calcolata a livello di articolo.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 17ed1dcae97f6cd28175c483be5ca3ce96d59e05
ms.sourcegitcommit: 053f4cda6862fbcd9e3aa6e9cb009e7de833beac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "5075740"
---
# <a name="global-withholding-tax"></a><span data-ttu-id="efe46-104">Ritenuta d'acconto globale</span><span class="sxs-lookup"><span data-stu-id="efe46-104">Global withholding tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efe46-105">Questo argomento fornisce informazioni sulla funzionalità della ritenuta d'acconto globale e spiega come configurarla.</span><span class="sxs-lookup"><span data-stu-id="efe46-105">This topic provides information about global withholding tax functionality and explains how to set it up.</span></span> <span data-ttu-id="efe46-106">La nuova funzionalità è disponibile nella versione 10.0.17 e successive.</span><span class="sxs-lookup"><span data-stu-id="efe46-106">The new functionality is available in version 10.0.17 and later.</span></span>

<span data-ttu-id="efe46-107">La funzionalità della ritenuta d'acconto globale è stata migliorata per le transazioni di fornitori e clienti, in modo che la ritenuta d'acconto venga calcolata a livello di articolo.</span><span class="sxs-lookup"><span data-stu-id="efe46-107">Global withholding tax functionality is enhanced for vendor and customer transactions, so that withholding tax is calculated at the item level.</span></span> <span data-ttu-id="efe46-108">Il saldo nel conto della ritenuta d'acconto derivante dalle transazioni di acquisto può essere regolato eseguendo il processo di pagamento della ritenuta d'acconto sul conto liquidazione della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="efe46-108">The balance in the withholding tax account from purchase transactions can be settled by running the withholding tax payment job against the withholding tax settlement account.</span></span>

> [!NOTE]
> <span data-ttu-id="efe46-109">La ritenuta d'acconto globale non supporta la funzione **Gestisci spese** nelle pagine dell'ordine di acquisto, della fattura fornitore e dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="efe46-109">Global withholding tax doesn't support the **Maintain charges** function on the purchase order, vendor invoice, and sales order pages.</span></span>

## <a name="turn-on-global-withholding-tax"></a><span data-ttu-id="efe46-110">Attivare la ritenuta d'acconto globale</span><span class="sxs-lookup"><span data-stu-id="efe46-110">Turn on global withholding tax</span></span>

1. <span data-ttu-id="efe46-111">Nell'area di lavoro **Gestione funzionalità**, seleziona **Ritenuta d'acconto globale** nell'elenco, quindi seleziona **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="efe46-111">In the **Feature management** workspace, select **Global withholding tax**, and then select **Enable now**.</span></span>
2. <span data-ttu-id="efe46-112">Vai a **Imposta \> Impostazione \> Parametri \> Parametri di contabilità generale** e quindi nella scheda **Ritenuta d'acconto** imposta l'opzione **Attiva ritenuta d'acconto globale** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="efe46-112">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Withholding tax** tab, set the **Enable global withholding tax** option to **Yes**.</span></span>
3. <span data-ttu-id="efe46-113">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="efe46-113">Select **Save**.</span></span>
4. <span data-ttu-id="efe46-114">Aggiorna la pagina nel tuo browser web.</span><span class="sxs-lookup"><span data-stu-id="efe46-114">Refresh the page in your web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="efe46-115">La funzionalità ritenuta d'acconto globale non può essere attivata per paesi/aree geografiche in cui esistono già soluzioni di ritenuta d'acconto localizzate.</span><span class="sxs-lookup"><span data-stu-id="efe46-115">Global withholding tax functionality can’t be turned on for countries/regions where localized withholding tax solutions already exist.</span></span> <span data-ttu-id="efe46-116">Queste aree includono ma non sono limitate a India, Brasile, Tailandia, Arabia Saudita, Irlanda, Gran Bretagna e Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="efe46-116">These areas include but are not restricted to India, Brazil, Thailand, Saudi Arabia, Ireland, Great Britain and the United States.</span></span>