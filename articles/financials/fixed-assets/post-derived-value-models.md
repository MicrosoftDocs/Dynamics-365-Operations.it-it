---
title: Registrare con i libri derivati
description: In questo articolo viene descritta la procedura per utilizzare i libri derivati.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: aaacf596f2ea1107a53647d779e9d2b6c37ab530
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="post-with-derived-books"></a><span data-ttu-id="297a9-103">Registrare con i libri derivati</span><span class="sxs-lookup"><span data-stu-id="297a9-103">Post with derived books</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="297a9-104">In questo articolo viene descritta la procedura per utilizzare i libri derivati.</span><span class="sxs-lookup"><span data-stu-id="297a9-104">This article describes how to use derived books.</span></span>

<span data-ttu-id="297a9-105">Quando si registrano transazioni per un libro contenente libri derivati, le transazioni relative ai libri derivati vengono registrate automaticamente in giornali di registrazione, ordini fornitore o fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="297a9-105">When you post transactions for a book that contains derived books, the derived book transactions are posted automatically in journals, purchase orders, or free text invoices.</span></span> <span data-ttu-id="297a9-106">Se tuttavia si preparano le transazioni del libro principale nel giornale di registrazione cespiti, sarà possibile visualizzare e modificare gli importi delle transazioni derivate prima di effettuarne la registrazione.</span><span class="sxs-lookup"><span data-stu-id="297a9-106">However, if you prepare the primary book transactions in the Fixed assets journal, you can view and modify the amounts of the derived transactions before you post them.</span></span>
-   <span data-ttu-id="297a9-107">Alcuni conti, ad esempio i conti IVA o i conti cliente o fornitore, vengono aggiornati una sola volta mediante la registrazione del libro principale.</span><span class="sxs-lookup"><span data-stu-id="297a9-107">Certain accounts, such as sales tax and customer or vendor accounts, are updated only once by postings of the primary book.</span></span> <span data-ttu-id="297a9-108">Le transazioni del libro derivato vengono registrate nei conti definiti per il libro derivato nella pagina Profili registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="297a9-108">The derived book transactions are posted to the accounts that have been defined for the derived book in the Fixed asset posting profiles page.</span></span>
-   <span data-ttu-id="297a9-109">L'acquisizione viene spesso utilizzata come tipo di transazione per i libri derivati.</span><span class="sxs-lookup"><span data-stu-id="297a9-109">Acquisition is often used as the transaction type for the derived books.</span></span> <span data-ttu-id="297a9-110">È opportuno utilizzare questa impostazione quando è necessario che il libro e il libro derivato siano applicati al cespite dal momento dell'acquisizione.</span><span class="sxs-lookup"><span data-stu-id="297a9-110">You use this when the book and the derived book should be applied to the fixed asset from the time of the acquisition of the fixed asset.</span></span>
-   <span data-ttu-id="297a9-111">Per il tipo di transazione è possibile applicare anche altri valori.</span><span class="sxs-lookup"><span data-stu-id="297a9-111">Other values for the transaction type can also apply.</span></span> <span data-ttu-id="297a9-112">Ad esempio, se per il libro principale e i libri derivati sono stati impostati gli stessi intervalli relativi a vendita o dismissione, per l'impostazione di un libro derivato saranno disponibili tutti i tipi di transazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="297a9-112">For example, if the primary book and the derived books have the same intervals regarding sale or disposal, all fixed asset transaction types are available for the setup of a derived book.</span></span>

> [!WARNING]
> <span data-ttu-id="297a9-113">L'ammortamento registrato nel libro derivato corrisponderà all'importo registrato per il libro principale.</span><span class="sxs-lookup"><span data-stu-id="297a9-113">Depreciation posted in the derived book will be the same amount as was posted for the primary book.</span></span> <span data-ttu-id="297a9-114">Se i metodi di ammortamento utilizzati per i libri sono diversi, evitare di generare transazioni di ammortamento utilizzando il processo derivato.</span><span class="sxs-lookup"><span data-stu-id="297a9-114">If the depreciation methods are different between the books, you should not generate depreciation transactions using the derived process.</span></span> |

## <a name="example"></a><span data-ttu-id="297a9-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="297a9-115">Example</span></span> 
<span data-ttu-id="297a9-116">Di seguito viene descritto come impostare le transazioni di acquisizione con la funzionalità libro derivato.</span><span class="sxs-lookup"><span data-stu-id="297a9-116">The following information describes how to set up acquisition transactions with the derived book functionality.</span></span>

1.  <span data-ttu-id="297a9-117">Creare i libri nella pagina Libri.</span><span class="sxs-lookup"><span data-stu-id="297a9-117">Create the books on the Books page.</span></span>
    -   <span data-ttu-id="297a9-118">Il libro per la contabilità: VM 1, livello di registrazione Corrente</span><span class="sxs-lookup"><span data-stu-id="297a9-118">The book for accounting: VM 1, Current posting layer</span></span>
    -   <span data-ttu-id="297a9-119">Libro per scopi fiscali: VM 2, livello di registrazione Imposta</span><span class="sxs-lookup"><span data-stu-id="297a9-119">The book for tax purposes: VM 2, Tax posting layer</span></span>

2.  <span data-ttu-id="297a9-120">In VM 1 fare clic sulla scheda Libri derivati. Selezionare VM 2 nel campo Libro e Acquisizione nel campo Tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="297a9-120">On VM 1, click the Derived books tab. Select VM 2 in the Book field, and Acquisition in the Transaction type field.</span></span>

<span data-ttu-id="297a9-121">I libri possono quindi essere collegati ai cespiti specifici.</span><span class="sxs-lookup"><span data-stu-id="297a9-121">The books then can be attached to specific fixed assets.</span></span> 

<span data-ttu-id="297a9-122">Quando si registra un'acquisizione per un cespite con il libro VM 1, la registrazione viene effettuata non solo in VM 1, ma anche nel libro derivato VM 2.</span><span class="sxs-lookup"><span data-stu-id="297a9-122">When an acquisition is posted for a fixed asset with book VM 1, the acquisition is posted not only on VM 1, but also on the derived book VM 2.</span></span> <span data-ttu-id="297a9-123">Lo stato di entrambi i libri cespiti viene aggiornato in Aperto.</span><span class="sxs-lookup"><span data-stu-id="297a9-123">The status of both fixed asset books is updated to Open.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="297a9-124">Se non si utilizzano libri derivati, è necessario registrare l'acquisizione del cespite sia per il libro VM 1 sia per il libro VM 2.</span><span class="sxs-lookup"><span data-stu-id="297a9-124">If you do not use derived books, you must post the acquisition of the fixed asset both for book VM 1 and book VM 2.</span></span>

<span data-ttu-id="297a9-125">Per ulteriori informazioni, vedere [Libri derivati](derived-books.md).</span><span class="sxs-lookup"><span data-stu-id="297a9-125">For more information, see [Derived books](derived-books.md)</span></span>




