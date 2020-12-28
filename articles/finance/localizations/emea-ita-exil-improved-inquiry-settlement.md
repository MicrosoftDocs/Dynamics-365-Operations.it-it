---
title: Richiesta di informazioni migliorata sulla liquidazione dare/avere
description: Questo argomento spiega come visualizzare le informazioni relative alla fatturazione e ai pagamenti in un formato comodo e semplice.
author: ilkond
manager: AnnBe
ms.date: 11/21/2019
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
ms.search.validFrom: 2019-11-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 531dfa6ff058e2c91cbdf1c7b8bb5ec67d127393
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408108"
---
# <a name="improved-inquiry-on-debitcredit-settlement"></a><span data-ttu-id="d413a-103">Richiesta di informazioni migliorata sulla liquidazione dare/avere</span><span class="sxs-lookup"><span data-stu-id="d413a-103">Improved inquiry on debit/credit settlement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d413a-104">Questo argomento spiega come visualizzare le informazioni relative alla fatturazione e ai pagamenti in un formato comodo e semplice.</span><span class="sxs-lookup"><span data-stu-id="d413a-104">This topic explains how you can view invoice and payment settlement information in a convenient and simple format.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d413a-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d413a-105">Prerequisites</span></span>

<span data-ttu-id="d413a-106">Per poter utilizzare questa funzionalità è necessario soddisfare i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="d413a-106">Before you can use this functionality, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d413a-107">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="d413a-107">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="d413a-108">Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Miglioramento della richiesta informazioni sulle liquidazioni a debito o credito**.</span><span class="sxs-lookup"><span data-stu-id="d413a-108">In the **Feature management** workspace, turn on the **Improved inquiry on debit/credit settlement** feature.</span></span> <span data-ttu-id="d413a-109">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d413a-109">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="use-the-invoicepayments-list-page"></a><span data-ttu-id="d413a-110">Utilizzare la pagina Elenco fatture/pagamenti</span><span class="sxs-lookup"><span data-stu-id="d413a-110">Use the Invoice/payments list page</span></span>

<span data-ttu-id="d413a-111">Eseguire uno dei passaggi riportati di seguito per aprire la pagina elenco **Fatture/pagamenti**:</span><span class="sxs-lookup"><span data-stu-id="d413a-111">Follow one of these steps to open the **Invoice/payments** list page:</span></span> 

- <span data-ttu-id="d413a-112">Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="d413a-112">Go to **Accounts receivable \> Customers \> All customers**.</span></span> <span data-ttu-id="d413a-113">Quindi, nella scheda **Fattura** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Fatture/pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="d413a-113">Then, on the Action Pane, on the **Invoice** tab, in the **Related information** group, select **Invoice/Payments**.</span></span>
- <span data-ttu-id="d413a-114">Andare a **Contabilità fornitori \>Fornitori \> Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="d413a-114">Go to **Accounts payable \> Vendors \> All vendors**.</span></span> <span data-ttu-id="d413a-115">Quindi, nella scheda **Fattura** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Fatture/pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="d413a-115">Then, on the Action Pane, on the **Invoice** tab, in the **Related information** group, select **Invoice/Payments**.</span></span>

<span data-ttu-id="d413a-116">La griglia nella parte superiore della pagina mostra le fatture cliente o le fatture fornitore.</span><span class="sxs-lookup"><span data-stu-id="d413a-116">The grid in the upper part of the page shows the customer invoices or vendor invoices.</span></span> <span data-ttu-id="d413a-117">Queste fatture sono ordinate per numero e data della fattura.</span><span class="sxs-lookup"><span data-stu-id="d413a-117">These invoices are sorted by invoice number and date.</span></span> 

<span data-ttu-id="d413a-118">La griglia nella parte inferiore della pagina mostra le transazioni di addebito e credito del cliente o fornitore selezionato.</span><span class="sxs-lookup"><span data-stu-id="d413a-118">The grid in the lower part of the page shows the debit and credit transactions of the selected customer or vendor.</span></span> <span data-ttu-id="d413a-119">Questi tipi di transazione includono fatture, pagamenti e transazioni di rivalutazione in valuta estera.</span><span class="sxs-lookup"><span data-stu-id="d413a-119">These transaction types include invoices, payments, and foreign currency revaluation transactions.</span></span> <span data-ttu-id="d413a-120">Qualsiasi saldo diverso da zero per le fatture è evidenziato in rosso.</span><span class="sxs-lookup"><span data-stu-id="d413a-120">Any non-zero balance for invoices is highlighted in red.</span></span>

![Pagina Elenco fatture/pagamenti](media/emea-ita-exil-DC-inquiry-vendor-invoice-payment.png)

<span data-ttu-id="d413a-122">Nel riquadro azioni selezionare **Parametri** per impostare un filtro in modo che la pagina elenco **Fatture/pagamenti** mostri solo i dati specifici.</span><span class="sxs-lookup"><span data-stu-id="d413a-122">On the Action Pane, select **Parameters** to set a filter so that the **Invoice/payments** list page shows only specific data.</span></span>

![Finestra di dialogo a discesa dei parametri](media/emea-ita-exil-DC-inquiry-parameters.png)
