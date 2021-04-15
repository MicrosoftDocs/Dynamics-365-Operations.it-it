---
title: Creare fatture di pagamento
description: In questo argomento viene illustrato come creare fatture di leasing mensili. Puoi creare fatture per singoli leasing oppure utilizzare un processo batch per crearli per più leasing.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 51e4c44cf192754a832132ea1942baf18b43a755
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816006"
---
# <a name="create-payment-invoices"></a><span data-ttu-id="23a81-104">Creare fatture di pagamento</span><span class="sxs-lookup"><span data-stu-id="23a81-104">Create payment invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23a81-105">Puoi creare fatture mensili per singoli leasing oppure utilizzare un processo batch per crearli per più leasing.</span><span class="sxs-lookup"><span data-stu-id="23a81-105">You can create monthly invoices for individual leases, or you can use a batch process to create them for multiple leases.</span></span> <span data-ttu-id="23a81-106">La procedura seguente mostra come creare una singola voce di canone di leasing quando il parametro **Paga a fornitore** nella pagina **Configurazione libro di leasing** è attivata.</span><span class="sxs-lookup"><span data-stu-id="23a81-106">The following procedure shows how to create an individual lease payment entry when the **Pay to Vendor** parameter on the **Lease book setup** page is turned on.</span></span>

1. <span data-ttu-id="23a81-107">Nella pagina **Riepilogo leasing**, seleziona un leasing, quindi seleziona **Libri \> Scadenziaio dei pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="23a81-107">On the **Lease summary** page, select a lease, and then select **Books \> Payment schedule**.</span></span>
2. <span data-ttu-id="23a81-108">Seleziona il pagamento che deve essere effettuato, quindi seleziona **Crea giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="23a81-108">Select the payment that must be made, and then select **Create journal**.</span></span> <span data-ttu-id="23a81-109">Ricevi un messaggio che informa che è stato creato un giornale di registrazione a fronte del pagamento selezionato.</span><span class="sxs-lookup"><span data-stu-id="23a81-109">You receive a message that states that a journal was created against the selected payment.</span></span>
3. <span data-ttu-id="23a81-110">Seleziona **Giornali di registrazione fatture**, quindi seleziona la fattura che deve essere pagata.</span><span class="sxs-lookup"><span data-stu-id="23a81-110">Select **Invoice journals**, and then select the invoice that must be paid.</span></span>
4. <span data-ttu-id="23a81-111">Nella scheda **Righe**, rivedi la scrittura contabile prima di registrarla nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="23a81-111">On the **Lines** tab, review the journal entry before you post it to the general ledger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23a81-112">Per impostazione predefinita, le righe della fattura fornitore create utilizzano il profilo di registrazione fornitore dalla pagina **Parametri di contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="23a81-112">By default, the vendor invoice lines that are created use the vendor posting profile from the **Accounts payable parameters** page.</span></span>

5. <span data-ttu-id="23a81-113">Seleziona il giornale di registrazione corretto, quindi seleziona la fattura che deve essere pagata.</span><span class="sxs-lookup"><span data-stu-id="23a81-113">Select the correct journal, and then select the invoice that must be paid.</span></span>

    <span data-ttu-id="23a81-114">Per questo esempio, il parametro **Paga a fornitore** sul libro dei leasing è attivato.</span><span class="sxs-lookup"><span data-stu-id="23a81-114">For this example, the **Pay to Vendor** parameter on the lease book is turned on.</span></span> <span data-ttu-id="23a81-115">Pertanto, la fattura sarà inclusa nel giornale di registrazione fatture.</span><span class="sxs-lookup"><span data-stu-id="23a81-115">Therefore, the invoice will be in the invoice journal.</span></span> <span data-ttu-id="23a81-116">La sezione **Panoramica** mostra un riepilogo della scrittura contabile e la sezione **Righe** mostra i dettagli delle righe di giornale effettive.</span><span class="sxs-lookup"><span data-stu-id="23a81-116">The **Overview** section shows a summary of the journal entry, and the **Lines** section shows details of the actual journal lines.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23a81-117">Se il parametro **Paga a fornitore** è disattivato, le scritture contabili dei pagamenti verranno elencate nella pagina **Leasing cespite** per il libro dei leasing e il sistema creerà una voce di leasing di cespite invece di una fattura.</span><span class="sxs-lookup"><span data-stu-id="23a81-117">If the **Pay to Vendor** parameter is turned off, payment journal entries will be listed on the **Asset leasing** page for the lease book, and the system will create an asset leasing entry instead of an invoice.</span></span> <span data-ttu-id="23a81-118">La voce di canone di leasing verrà registrata nel nome del giornale di registrazione specificato nel campo **Giornale di registrazione leasing mensile**.</span><span class="sxs-lookup"><span data-stu-id="23a81-118">The lease payment entry will be posted to the journal name that is specified in the **Monthly lease journal** field.</span></span>

6. <span data-ttu-id="23a81-119">Dopo la registrazione della transazione, puoi visualizzare le informazioni sulla transazione e il valore contabile dell'obbligazione sul leasing selezionando **Transazioni di passività** nel libro di leasing.</span><span class="sxs-lookup"><span data-stu-id="23a81-119">After the transaction is posted, you can view the transaction information and the carrying value of the lease liability by selecting **Liability transactions** in the lease book.</span></span>

    <span data-ttu-id="23a81-120">Nello scadenzario dei pagamenti, verrà selezionata la casella di controllo **Giornale di registrazione registrato** e la riga mostrerà il numero di giornale di registrazione fattura.</span><span class="sxs-lookup"><span data-stu-id="23a81-120">In the payment schedule, the **Journal posted** check box will be selected, and the line will show the invoice journal number.</span></span> <span data-ttu-id="23a81-121">Dopo aver creato un giornale di registrazione pagamenti e una registrazione per quel giornale, è necessario stornare il movimento prima che possa essere ricreato.</span><span class="sxs-lookup"><span data-stu-id="23a81-121">After a payment journal and an entry for that journal have been created, you must reverse the entry before it can be re-created.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]