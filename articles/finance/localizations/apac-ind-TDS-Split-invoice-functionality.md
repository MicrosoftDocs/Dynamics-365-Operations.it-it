---
title: Funzionalità di divisione delle fatture
description: Questo argomento descrive la configurazione della funzionalità per la divisione delle fatture in base all'indirizzo di consegna e al numero di conto imposta (TAN).
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
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023363"
---
# <a name="split-invoice-functionality"></a><span data-ttu-id="2c786-103">Funzionalità di divisione delle fatture</span><span class="sxs-lookup"><span data-stu-id="2c786-103">Split invoice functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c786-104">Questo argomento descrive la configurazione della funzionalità per la divisione delle fatture in base all'indirizzo di consegna e al numero di conto imposta (TAN).</span><span class="sxs-lookup"><span data-stu-id="2c786-104">This topic describes the setup and functionality for splitting invoices by delivery address and tax account number (TAN).</span></span>

<span data-ttu-id="2c786-105">Nella pagina **Parametri contabilità fornitori**, nella scheda **Generale**, seleziona la casella di controllo **Entrata prodotti** o **Fattura** per registrare e dividere un'entrata prodotti o una fattura con indirizzi di consegna e TAN diversi nella pagina **Ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="2c786-105">On the **Accounts payable parameters** page, on the **General** tab, select the **Product receipt** or **Invoice** checkbox to post and split a product receipt or invoice that has different delivery addresses and TANs on the **Purchase order** page.</span></span> <span data-ttu-id="2c786-106">La fattura registrata verrà quindi divisa in base all'indirizzo di consegna e al TAN.</span><span class="sxs-lookup"><span data-stu-id="2c786-106">The posted invoice will then be split by delivery address and TAN.</span></span>

<span data-ttu-id="2c786-107">Nella scheda **Aggiornamento riepilogativo**, nella Scheda dettaglio **Dividi in base a**, nella riga **Informazioni consegna**, imposta l'opzione **Conferma**, **Distinta di prelievo**, **Documento di trasporto** o **Fattura** su **Sì** per registrare e suddividere una conferma, una distinta di prelievo, un documento di trasporto o una fattura in cui sono definiti indirizzi di consegna e TAN diversi per righe di fattura diverse nella pagina **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="2c786-107">On the **Summary update** tab, on the **Split based on** FastTab, in the **Delivery information** row, set the **Confirmation**, **Picking list**, **Packing slip**, or **Invoice** option to **Yes** to post and split a confirmation, picking list, packing slip, or invoice where different delivery addresses and TANs are defined for different invoice lines on the **Sales order** page.</span></span> <span data-ttu-id="2c786-108">La fattura verrà quindi divisa dapprima in base all'indirizzo di consegna e quindi in base al TAN.</span><span class="sxs-lookup"><span data-stu-id="2c786-108">The invoice will be split first by delivery address and then by TAN.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="2c786-109">Se non ci sono opzioni di **Informazioni consegna** impostate su **Sì**, la fattura verrà registrata come singola fattura.</span><span class="sxs-lookup"><span data-stu-id="2c786-109">If no options for **Delivery information** are set to **Yes**, the invoice will be posted as a single invoice.</span></span> <span data-ttu-id="2c786-110">Non si verificherà alcuna divisione di fattura.</span><span class="sxs-lookup"><span data-stu-id="2c786-110">No invoice splitting will occur.</span></span>
> - <span data-ttu-id="2c786-111">Per dividere e registrare un documento di trasporto in cui le righe di fattura hanno indirizzi di consegna e TAN diversi, devi impostare l'opzione **Documento di trasporto** di **Informazioni consegna** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2c786-111">To split and post a packing slip where the invoice lines have different delivery addresses and TANs, you must set the **Packing slip** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="2c786-112">Per dividere e registrare una fattura in cui le righe di fattura hanno indirizzi di consegna e TAN diversi, devi impostare l'opzione **Fattura** di **Informazioni consegna** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2c786-112">To split and post an invoice where the invoice lines have different delivery addresses and TANs, you must set the **Invoice** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="2c786-113">Per dividere una fattura in cui le righe di fattura hanno indirizzi di consegna differenti ma lo stesso TAN, imposta l'opzione **Fattura** di **Informazioni consegna** su **No**.</span><span class="sxs-lookup"><span data-stu-id="2c786-113">To post an invoice where the invoice lines have different delivery addresses but the same TAN, set the **Invoice** option for **Delivery information** to **No**.</span></span> <span data-ttu-id="2c786-114">La fattura verrà divisa dapprima in base all'indirizzo di consegna.</span><span class="sxs-lookup"><span data-stu-id="2c786-114">The invoice will be split by delivery address.</span></span>

## <a name="example"></a><span data-ttu-id="2c786-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c786-115">Example</span></span>

<span data-ttu-id="2c786-116">In questo esempio, l'opzione **Fattura** di **Informazioni consegna** è impostata su **Sì** nella scheda **Aggiornamento riepilogativo** della pagina **Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="2c786-116">In this example, the **Invoice** option for **Delivery information** is set to **Yes** on the **Summary update** tab of the **Accounts payable parameters** page.</span></span> <span data-ttu-id="2c786-117">Viene registrata una fattura di acquisto con la seguente impostazione per indirizzi di consegna e TAN nelle righe:</span><span class="sxs-lookup"><span data-stu-id="2c786-117">A purchase invoice is posted that has the following setup for delivery addresses and TANs on the lines:</span></span>

- <span data-ttu-id="2c786-118">**Riga articolo 1:** Indirizzo di consegna 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="2c786-118">**Item line 1:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="2c786-119">**Riga articolo 2:** Indirizzo di consegna 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="2c786-119">**Item line 2:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="2c786-120">**Riga articolo 3:** Indirizzo di consegna 2, TAN-ABCE12345B</span><span class="sxs-lookup"><span data-stu-id="2c786-120">**Item line 3:** Delivery address 2, TAN-ABCE12345B</span></span>
- <span data-ttu-id="2c786-121">**Riga articolo 4:** Indirizzo di consegna 3, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="2c786-121">**Item line 4:** Delivery address 3, TAN-ABCD12345A</span></span>

<span data-ttu-id="2c786-122">In questo caso, la fattura originale viene divisa in due fatture e registrata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="2c786-122">In this case, the original invoice is split into two invoices and posted in the following way:</span></span>

- <span data-ttu-id="2c786-123">La fattura 1 viene registrata per la riga articolo 1 e la riga articolo 2, poiché entrambe le righe hanno lo stesso indirizzo di consegna e TAN.</span><span class="sxs-lookup"><span data-stu-id="2c786-123">Invoice 1 is posted for item line 1 and item line 2, because both lines have the same delivery address and TAN.</span></span>
- <span data-ttu-id="2c786-124">La fattura 2 viene registrata per la riga articolo 3.</span><span class="sxs-lookup"><span data-stu-id="2c786-124">Invoice 2 is posted for item line 3.</span></span>
- <span data-ttu-id="2c786-125">La fattura 3 viene registrata per la riga articolo 4.</span><span class="sxs-lookup"><span data-stu-id="2c786-125">Invoice 3 is posted for item line 4.</span></span>
