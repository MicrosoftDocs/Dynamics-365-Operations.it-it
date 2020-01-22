---
title: Ordinare le righe fattura di vendita per documento di trasporto
description: Questo argomento spiega come impostare e stampare le fatture accompagnatorie che includono i dettagli dei documenti di trasporto richiesti.
author: ilkond
manager: AnnBe
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-29
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 02e95aac186690070bd5af3f2a70c12adebe6491
ms.sourcegitcommit: 1f119d8bb80a69a363c124ece43d7e6ae94bc5de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945026"
---
# <a name="sort-sales-invoice-lines-by-packing-slip"></a><span data-ttu-id="b94ca-103">Ordinare le righe fattura di vendita per documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="b94ca-103">Sort sales invoice lines by packing slip</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="b94ca-104">In Italia, le aziende devono spesso emettere *fatture accompagnatorie*.</span><span class="sxs-lookup"><span data-stu-id="b94ca-104">In Italy, companies must often issue *accompanying invoices*.</span></span> <span data-ttu-id="b94ca-105">Le fatture accompagnatorie sono combinazioni di una fattura ordinaria e un documento di trasporto o bolla di accompagnamento (documento di trasporto o DDT).</span><span class="sxs-lookup"><span data-stu-id="b94ca-105">Accompanying invoices are combinations of an ordinary invoice and a transport document or packing slip (documento di trasporto, or DDT).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b94ca-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b94ca-106">Prerequisites</span></span>

- <span data-ttu-id="b94ca-107">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="b94ca-107">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="b94ca-108">Nell'area di lavoro **Gestione funzionalità**, verificare che la funzionalità **Ordinamento righe fattura fornitore per documento di trasporto** sia attivata.</span><span class="sxs-lookup"><span data-stu-id="b94ca-108">In the **Feature management** workspace, verify that the **Sales invoice lines sorting by packing slips** feature is turned on.</span></span> <span data-ttu-id="b94ca-109">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b94ca-109">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="b94ca-110">Le fatture clienti devono utilizzare il nuovo layout **SalesInvoice.Report \_IT**.</span><span class="sxs-lookup"><span data-stu-id="b94ca-110">Customer invoices must use the new **SalesInvoice.Report\_IT** layout.</span></span> <span data-ttu-id="b94ca-111">Andare a **Contabilità clienti** /> **Impostazioni** /> **Moduli** /> **Impostazione moduli**, quindi sulla scheda **Generale** selezionare **Gestione stampa**.</span><span class="sxs-lookup"><span data-stu-id="b94ca-111">Go to **Accounts receivable** /> **Setup** /> **Forms** /> **Form setup**, and then, on the **General** tab, select **Print management**.</span></span> <span data-ttu-id="b94ca-112">Sulla pagina **Impostazione Gestione stampa**, sotto **Modulo - Contabilità clienti \> Fattura cliente** selezionare **Originale \<Impostazione predefinita\>**.</span><span class="sxs-lookup"><span data-stu-id="b94ca-112">On the **Print management setup** page, under **Module - accounts receivable \> Customer invoice**, select **Original \<Default\>**.</span></span> <span data-ttu-id="b94ca-113">Quindi, nel campo **Formato report** selezionare **SalesInvoice.Report \_IT**.</span><span class="sxs-lookup"><span data-stu-id="b94ca-113">Then, in the **Report format** field, select **SalesInvoice.Report\_IT**.</span></span>

    ![Nuovo layout selezionato per le fatture cliente](media/emea-ita-exil-invoice-packing-slip-pic2.jpg)

> [!NOTE]
> <span data-ttu-id="b94ca-115">Quando è attivata la funzione **Ordinamento righe fattura fornitore per documento di trasporto** è attivata, il sistema ignora l'impostazione della casella di controllo **Stampa specifiche documento di trasporto** sulla scheda **Fattura** della pagina **Impostazione moduli** ( **Contabilità clienti \>Impostazioni \>Moduli \> Impostazione moduli**).</span><span class="sxs-lookup"><span data-stu-id="b94ca-115">When the **Sales invoice lines sorting by packing slips** feature is turned on, the system ignores the setting of the **Print packing slip specifications** check box on the **Invoice** tab of the **Form setup** page (**Accounts receivable \> Setup \> Forms \> Form setup**).</span></span> <span data-ttu-id="b94ca-116">Anche se questa casella di controllo è selezionata, viene trattata come se fosse deselezionata.</span><span class="sxs-lookup"><span data-stu-id="b94ca-116">Even if this check box is selected, it's treated as if it's cleared.</span></span>
>
> ![Casella di controllo Stampa specifiche documento di trasporto](media/emea-ita-exil-invoice-packing-slip-pic3.jpg)

## <a name="printing-accompanying-invoices"></a><span data-ttu-id="b94ca-118">Stampa delle fatture accompagnatorie</span><span class="sxs-lookup"><span data-stu-id="b94ca-118">Printing accompanying invoices</span></span>

<span data-ttu-id="b94ca-119">Dopo aver attivato e impostato la funzionalità, il report sulla fattura stampato conterrà le righe della fattura raggruppate e ordinate per documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="b94ca-119">After you've turned on and set up the feature, the printed invoice report will contain invoice lines that are grouped and sorted by packing slip.</span></span>

![Esempio di fattura in cui le righe della fattura sono raggruppate e ordinate per documento di trasporto](media/emea-ita-exil-invoice-packing-slip-pic.jpg)

> [!NOTE]
> <span data-ttu-id="b94ca-121">Il nuovo layout è applicabile solo alle fatture basate su ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="b94ca-121">The new layout is applicable only to invoices that are based on sales orders.</span></span> <span data-ttu-id="b94ca-122">Non è applicabile alle fatture a testo libero, poiché non utilizzano documenti di trasporto.</span><span class="sxs-lookup"><span data-stu-id="b94ca-122">It isn't applicable to free-text invoices, because they don't use packing slips.</span></span>
