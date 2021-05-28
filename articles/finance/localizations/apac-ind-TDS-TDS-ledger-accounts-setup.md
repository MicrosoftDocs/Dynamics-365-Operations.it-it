---
title: Impostare conti CoGe TDS
description: Questo argomento spiega come impostare conti CoGe per la funzionalità TDS.
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
ms.openlocfilehash: 93d4cb54488ec0eeee40ca56f3e46f30012f54f5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023357"
---
# <a name="set-up-tds-ledger-accounts"></a><span data-ttu-id="31079-103">Impostare conti CoGe TDS</span><span class="sxs-lookup"><span data-stu-id="31079-103">Set up TDS ledger accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="31079-104">Questo argomento spiega come impostare conti CoGe per la funzionalità TDS.</span><span class="sxs-lookup"><span data-stu-id="31079-104">This topic explains how to set up ledger accounts for the Tax Deducted at Source (TDS) feature.</span></span> <span data-ttu-id="31079-105">Per impostare i conti CoGe per TDS si utilizza la pagina **Piano dei conti**.</span><span class="sxs-lookup"><span data-stu-id="31079-105">You use the **Chart of accounts** page to set up ledger accounts for TDS.</span></span>

1. <span data-ttu-id="31079-106">Via a **Contabilità generale \> Piano dei conti \> Conti \> Conti principali**.</span><span class="sxs-lookup"><span data-stu-id="31079-106">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**.</span></span>
2. <span data-ttu-id="31079-107">Nella scheda **Panoramica**, seleziona **ALT+N** per creare un conto CoGe TDS e inserisci i dettagli necessari.</span><span class="sxs-lookup"><span data-stu-id="31079-107">On the **Overview** tab, select **Alt+N** to create a TDS ledger account, and enter the required details.</span></span>
3. <span data-ttu-id="31079-108">Nella scheda **Impostazione**, nel campo **Tipo di registrazione**, seleziona **Ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="31079-108">On the **Setup** tab, in the **Posting type** field, select **Withholding tax**.</span></span>     

    > [!NOTE]
    > <span data-ttu-id="31079-109">I conti CoGe il cui tipo di registrazione **Ritenuta d'acconto** possono essere definiti solo come conti fornitore utilizzati per registrare l'importo contabilità clienti TDS per un codice imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="31079-109">Ledger accounts that have a posting type of **Withholding tax** can be defined only as receivable accounts that are used to post the TDS receivable amount for a TDS tax code.</span></span>

4. <span data-ttu-id="31079-110">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="31079-110">Close the page.</span></span>
