---
title: Conti separati per note di credito
description: Questo argomento spiega come impostare e utilizzare account separati per le note di credito.
author: ilkond
manager: AnnBe
ms.date: 09/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2019-11-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 61d5915d730c953a6e96fb9cf08f2e1e6be311ca
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214466"
---
# <a name="separate-accounts-for-credit-notes"></a><span data-ttu-id="9dd8a-103">Conti separati per note di credito</span><span class="sxs-lookup"><span data-stu-id="9dd8a-103">Separate accounts for credit notes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9dd8a-104">In Italia, una società può definire i criteri contabili in modo che gli importi delle note di credito vengano registrati nei conti CoGe che differiscono dai conti ricavi.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-104">In Italy, a company can define the accounting policy so that credit note amounts are posted to ledger accounts that differ from the revenue accounts.</span></span> <span data-ttu-id="9dd8a-105">Questo approccio viene utilizzato per tenere traccia dell'importo emesso sulle note di credito.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-105">This approach is used to track the amount that is issued on credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9dd8a-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9dd8a-106">Prerequisites</span></span>

- <span data-ttu-id="9dd8a-107">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-107">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="9dd8a-108">Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Conti separati per note di credito**.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-108">In the **Feature management** workspace, turn on the **Separate accounts for credit notes** feature.</span></span> <span data-ttu-id="9dd8a-109">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9dd8a-109">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="set-up-posting-accounts"></a><span data-ttu-id="9dd8a-110">Impostare i conti di registrazione</span><span class="sxs-lookup"><span data-stu-id="9dd8a-110">Set up posting accounts</span></span>

<span data-ttu-id="9dd8a-111">È possibile definire conti CoGe specifici da utilizzare per gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-111">You can define specific ledger accounts that should be used for sales orders.</span></span> <span data-ttu-id="9dd8a-112">Per completare la configurazione, sulla pagina **Registrazione**, selezionare l'opzione **Nota di credito**, quindi specificare i conti CoGe.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-112">To complete the setup, on the **Posting** page, select the **Credit note** option, and then specify the ledger accounts.</span></span>

<span data-ttu-id="9dd8a-113">Puoi anche usare la pagine **Registrazione** per impostare account diversi per varie combinazioni di clienti, articoli e gruppi correlati.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-113">You can also use the **Posting** page to set up different accounts for various combinations of customers, items, and related groups.</span></span>

![Configurazione della registrazione dei conti](media/emea-ita-exil-separate-account-credit-pic1.jpg)

## <a name="post-credit-notes"></a><span data-ttu-id="9dd8a-115">Registrazione delle note di credito</span><span class="sxs-lookup"><span data-stu-id="9dd8a-115">Post credit notes</span></span>

### <a name="post-a-new-credit-note"></a><span data-ttu-id="9dd8a-116">Registrare una nuova nota di credito.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-116">Post a new credit note</span></span>

<span data-ttu-id="9dd8a-117">Quando si registra una nuova nota di credito, viene utilizzato il conto CoGe anziché il conto ricavi standard definito nell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-117">When you post a new credit note, the ledger account is used instead of the standard revenue account that is defined on the sales order.</span></span>

<span data-ttu-id="9dd8a-118">Se non viene definito un conto CoGe separato per la nota di credito o se non viene trovata una combinazione richiesta di cliente e articolo, per la registrazione viene utilizzato un conto ricavi ordine cliente standard.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-118">If no separate ledger account is defined for the credit note, or if a required combination of a customer and an item isn't found, a standard sales order revenue account is used for posting.</span></span>

### <a name="post-a-credit-note-that-was-created-from-a-sales-order"></a><span data-ttu-id="9dd8a-119">Registrare una nota di credito creata da un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="9dd8a-119">Post a credit note that was created from a sales order</span></span>

<span data-ttu-id="9dd8a-120">Se si crea una nota di credito basata su un ordine cliente esistente, deselezionare il campo **Conto principale** per ogni riga della nota di credito.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-120">If you create a credit note that is based on an existing sales order, clear the **Main account** field for each credit note line.</span></span> <span data-ttu-id="9dd8a-121">Nel campo potrebbe essere stato inserito automaticamente un conto ricavi dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-121">A revenue account from the sales order might have been automatically entered in the field.</span></span>

![Compensazione del conto principale](media/emea-ita-exil-separate-account-credit-pic2.jpg)

> [!NOTE]
> <span data-ttu-id="9dd8a-123">Conti separati sono applicabili solo alle note di credito basate su ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-123">Separate accounts are applicable only to credit notes that are based on sales orders.</span></span> <span data-ttu-id="9dd8a-124">Non sono applicabili alle note di credito a testo libero, poiché le note di credito a testo libero richiedono l'inserimento esplicito di un conto CoGe.</span><span class="sxs-lookup"><span data-stu-id="9dd8a-124">They aren't applicable to free-text credit notes, because free-text credit notes require that a ledger account be explicitly entered.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]