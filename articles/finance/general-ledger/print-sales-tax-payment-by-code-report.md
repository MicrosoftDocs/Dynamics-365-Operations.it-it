---
title: Stampare il report Pagamento IVA per codice
description: Questo argomento fornisce informazioni sulle impostazioni e le azioni necessarie per stampare il report Pagamento IVA per codice nella valuta contabile o nella valuta del codice IVA.
author: anasyash
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: dd490663e66d1eda0eb0ea052e5b54fb867f81df
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990299"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a><span data-ttu-id="ecc4c-103">Stampare il report Pagamento IVA per codice</span><span class="sxs-lookup"><span data-stu-id="ecc4c-103">Print the Sales tax payment by code report</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ecc4c-104">Per stampare il report **Pagamento IVA per codice**, andare a **Imposta** \> **Richieste di informazioni e report** \> **Report IVA** \> **Pagamento IVA per codice**.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-104">To print the **Sales tax payment by code** report, go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span> <span data-ttu-id="ecc4c-105">Per impostazione predefinita, gli importi dei report vengono generati nella valuta contabile della persona giuridica per tutti i codici di reporting impostati nella pagina **Codici reporting IVA**.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-105">By default, report amounts are generated in the accounting currency of the legal entity for all reporting codes that are set up on the **Sales tax reporting codes** page.</span></span>

<span data-ttu-id="ecc4c-106">È inoltre possibile generare questo report in modo che mostri gli importi del pagamento dell'IVA nelle valute dei codici IVA per tutti i codici di reporting assegnati ai codici IVA nella pagina **Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-106">You can also generate this report so that it shows the sales tax payment amounts in the currencies of sales tax codes for all reporting codes that are assigned to sales tax codes on the **Sales tax codes** page.</span></span>

## <a name="turn-on-the-feature"></a><span data-ttu-id="ecc4c-107">Attivare la funzionalità</span><span class="sxs-lookup"><span data-stu-id="ecc4c-107">Turn on the feature</span></span>

<span data-ttu-id="ecc4c-108">Nell'area di lavoro **Gestione delle funzionalità**, attivare la seguente funzione: **Genera il report Pagamento IVA per codice nella valuta del codice IVA**.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-108">In the **Feature management** workspace, turn on the following feature: **Generate the Sales tax payment by code report in the sales tax code currency**.</span></span>

## <a name="run-the-report"></a><span data-ttu-id="ecc4c-109">Eseguire il report</span><span class="sxs-lookup"><span data-stu-id="ecc4c-109">Run the report</span></span>

1. <span data-ttu-id="ecc4c-110">Andare a **Imposta** \> **Richieste di informazioni e report** \> **Report IVA** \> **Pagamento IVA per codice**.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-110">Go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span>
2. <span data-ttu-id="ecc4c-111">Nel campo **Descrizione valuta**, selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ecc4c-111">In the **Report currency** field, select one of the following values:</span></span>

    - <span data-ttu-id="ecc4c-112">**Valuta di contabilizzazione** - Stampare gli importi del report nella valuta di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-112">**Accounting currency** – Print the report amounts in the accounting currency.</span></span>
    - <span data-ttu-id="ecc4c-113">**Valuta del codice IVA** - Stampare gli importi del report nelle valute dei codici IVA.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-113">**Sales tax code currency** – Print the report amounts in the currencies of sales tax codes.</span></span>

    ![Finestra di dialogo Pagamento IVA per codice](media/Sales-tax-payment-by-code.png)

<span data-ttu-id="ecc4c-115">La seguente illustrazione mostra un esempio del report che viene generato.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-115">The following illustration shows an example of the report that is generated.</span></span> <span data-ttu-id="ecc4c-116">Il report mostra che il codice di segnalazione **101** ha la valuta **Euro** se il campo **Valuta IVA** è impostato su **Euro** per il codice IVA a cui è assegnato il codice di reporting.</span><span class="sxs-lookup"><span data-stu-id="ecc4c-116">The report shows that reporting code **101** has the **EUR** currency if the **Sales tax currency** field is set to **EUR** for the sales tax code that the reporting code is assigned to.</span></span>

![Esempio di report Pagamento IVA per codice](media/Sales-tax-payment-by-code-2.png)
