---
title: Impostare la ritenuta d'acconto globale
description: Questo argomento elenca i passaggi per impostare la ritenuta d'acconto globale per vendite e acquisti.
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
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 00c472e90f4926c52ffe9b19661e68cbfa6bd493
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204835"
---
# <a name="set-up-global-withholding-tax"></a><span data-ttu-id="d89cc-103">Impostare la ritenuta d'acconto globale</span><span class="sxs-lookup"><span data-stu-id="d89cc-103">Set up global withholding tax</span></span>

<span data-ttu-id="d89cc-104">Questo argomento elenca i passaggi per impostare la ritenuta d'acconto globale per vendite e acquisti.</span><span class="sxs-lookup"><span data-stu-id="d89cc-104">This topic lists the steps for setting up global withholding tax for sales and purchases.</span></span> 

1. <span data-ttu-id="d89cc-105">Configurare le autorità di ritenuta d'acconto nella pagina **Autorità ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="d89cc-105">Set up withholding tax authorities on the **Withholding tax authorities** page.</span></span>

2. <span data-ttu-id="d89cc-106">Configurare i periodi di liquidazione ritenuta alla fonte nella pagina **Periodi di liquidazione della ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="d89cc-106">Set up withholding settlement periods on the **Withholding tax settlement periods** page.</span></span>

3. <span data-ttu-id="d89cc-107">Configurare il gruppo di registrazione della contabilità generale nella pagina **Ritenuta d'acconto > gruppo registrazione contabile**.</span><span class="sxs-lookup"><span data-stu-id="d89cc-107">Set up withholding ledger posting group on the **Withholding tax > ledger posting group** page.</span></span>

   > [!Note] 
   >
   > <span data-ttu-id="d89cc-108">Il conto **Ritenuta d'acconto** verrà assegnato a un account principale con il **Tipo di registrazione** della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="d89cc-108">**Withholding tax** account will be assigned with a main account with **Posting type** of Withholding tax.</span></span> <span data-ttu-id="d89cc-109">Il conto **Offset ritenuta d'acconto** verrà inoltre assegnato a un conto principale con il **Tipo di registrazione** "offset della ritenuta d'acconto".</span><span class="sxs-lookup"><span data-stu-id="d89cc-109">**Withholding tax offset** account will also be assigned with a main account with **Posting type** "Withholding tax offset".</span></span> <span data-ttu-id="d89cc-110">Vai a **Contabilità generale > Piano dei conti> Conti > Conti principali**, configura il **Tipo di registrazione** nel sottomodulo **Convalida della registrazione** per i conti principali.</span><span class="sxs-lookup"><span data-stu-id="d89cc-110">Go to **General ledger > Chart of accounts > Accounts > Main accounts**, set up the **Posting type** in the **Posting validation** sub-form for the main accounts.</span></span>

4. <span data-ttu-id="d89cc-111">Configurare i codici di ritenuta d'acconto nella pagina **Codici ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="d89cc-111">Set up withholding tax codes on the **Withholding tax codes** page.</span></span>

5. <span data-ttu-id="d89cc-112">Configurare i gruppi di ritenuta d'acconto nella pagina **Gruppi ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="d89cc-112">Set up withholding tax groups on the **Withholding tax groups** page.</span></span>

6. <span data-ttu-id="d89cc-113">Configurare i tipi di ricavi con ritenuta d'acconto nella pagina **Ricavi ritenuta d'acconto** **tipi**.</span><span class="sxs-lookup"><span data-stu-id="d89cc-113">Set up withholding tax revenue types on the **Withholding tax revenue** **types** page.</span></span>

7. <span data-ttu-id="d89cc-114">Configurare i gruppi di ritenuta d'acconto nella pagina **Gruppi ritenute d'acconto articoli**.</span><span class="sxs-lookup"><span data-stu-id="d89cc-114">Set up withholding tax groups on the **Item withholding tax groups** page for an item or service.</span></span>

8. <span data-ttu-id="d89cc-115">Configurare **Importo minimo della fattura** nella pagina **Parametri di contabilità generale > Ritenuta d'acconto**.</span><span class="sxs-lookup"><span data-stu-id="d89cc-115">Set up **Minimum invoice amount** on the **General ledger parameters > Withholding tax** page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]