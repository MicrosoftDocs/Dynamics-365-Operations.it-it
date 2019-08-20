---
title: Importazione pagamenti cliente PVR
description: In questo argomento vengono fornite informazioni sull'importazione dei pagamenti cliente in formato PVR.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264584
ms.search.region: Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dfd005d1eda263fd84d75667e3d8a12e8349088b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852125"
---
# <a name="esr-customer-payments-import"></a><span data-ttu-id="5d7a9-103">Importazione pagamenti cliente PVR</span><span class="sxs-lookup"><span data-stu-id="5d7a9-103">ESR customer payments import</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d7a9-104">In questo argomento vengono fornite informazioni sull'importazione dei pagamenti cliente in formato PVR.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-104">This topic provides information about importing customer payments in the ESR format.</span></span>

<span data-ttu-id="5d7a9-105">PVR è un servizio di addebito elettronico che utilizza distinte di pagamento per raccogliere denaro.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-105">ESR is an electronic debtor service that uses payment slips to collect money.</span></span> <span data-ttu-id="5d7a9-106">Si tratta del sistema di pagamento elettronico standard creato dalla Posta svizzera.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-106">It is the standard electronic payment system created by the Swiss Post.</span></span> <span data-ttu-id="5d7a9-107">È possibile ricevere i file di pagamento clienti in formato PVR, il quale può includere le transazioni e le commissioni bancarie.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-107">You can receive customer payment files in the ESR format, which can include transactions and bank fees.</span></span> <span data-ttu-id="5d7a9-108">Questa funzionalità è progettata per le transazioni clienti importate in base ai riferimenti di pagamento originariamente generati in Microsoft Dynamics 365 for Finance and Operations e stampati nella distinta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-108">This functionality is intended for imported customer transactions based on payment references that were originally generated in Microsoft Dynamics 365 for Finance and Operations and printed on the payment slip.</span></span>

## <a name="generate-payment-references"></a><span data-ttu-id="5d7a9-109">Generare i riferimenti di pagamento</span><span class="sxs-lookup"><span data-stu-id="5d7a9-109">Generate payment references</span></span>
<span data-ttu-id="5d7a9-110">I riferimenti di pagamento devono essere stampati nella distinta di pagamento dopo la registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-110">Payment references should be printed on the payment slip after posting.</span></span> <span data-ttu-id="5d7a9-111">È inoltre possibile verificare i riferimenti di pagamento nella pagina **Giornale di registrazione fatture** per ordine cliente selezionato.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-111">You can also verify payment references on the **Invoice journal** page for the selected sales order.</span></span> <span data-ttu-id="5d7a9-112">Per generare i riferimenti di pagamento, è necessario specificare le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-112">To generate payment references, the following settings must be specified.</span></span>

1.  <span data-ttu-id="5d7a9-113">Configurare le impostazioni del conto bancario in **PVR**, **ID PVRB** e **Numero di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-113">Set the bank account settings to **ESR**, **BESR ID,** and **Routing number**.</span></span>
2.  <span data-ttu-id="5d7a9-114">Impostare il campo **Numero di caratteri per il conto ordini di accredito** nella pagina **Parametri di effetti attivi del conto** della scheda **Contabilità generale e IVA**. In questo modo, si definisce il numero di simboli del conto cliente che devono essere inclusi nel riferimento di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-114">Set the **Number of characters for Giro account** field on the **Account Receivables parameters** page on the **Ledger and sales tax** tab. This defines how many symbols from the customer account should be included in the payment reference.</span></span>
3.  <span data-ttu-id="5d7a9-115">La sequenza numerica della fattura di vendita deve essere nel formato corretto (non deve includere simboli diversi dalle cifre e non deve contenere zeri iniziali).</span><span class="sxs-lookup"><span data-stu-id="5d7a9-115">The sales invoice number sequence should be in the correct format (it should not have symbols other than digits and it should not contain leading zeros).</span></span>
4.  <span data-ttu-id="5d7a9-116">È necessario specificare il formato **Orange** per il conto cliente nel campo **Su fattura cliente** nella scheda **Fattura e consegna**.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-116">The **Orange** format should be specified for the customer account in the **On a customer invoice** field on the **Invoice and delivery** tab.</span></span>

<span data-ttu-id="5d7a9-117">Per ulteriori informazioni, vedere [Report distinta di pagamento (Giro)](emea-eur-payment-slip-report-giro.md).</span><span class="sxs-lookup"><span data-stu-id="5d7a9-117">For more information, see [Payment slip report (Giro)](emea-eur-payment-slip-report-giro.md).</span></span>

## <a name="import-a-payment-file"></a><span data-ttu-id="5d7a9-118">Importare un file di pagamento</span><span class="sxs-lookup"><span data-stu-id="5d7a9-118">Import a payment file</span></span>
1. <span data-ttu-id="5d7a9-119">Passare alla pagina **Giornale di registrazione pagamenti**</span><span class="sxs-lookup"><span data-stu-id="5d7a9-119">Go to the **Payment journal** page</span></span>
2. <span data-ttu-id="5d7a9-120">Fare clic su **Righe**.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-120">Click **Lines**.</span></span>
3. <span data-ttu-id="5d7a9-121">Fare clic su **Funzioni** &gt; **Importa pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-121">Click **Functions** &gt; **Import payments**.</span></span>
4. <span data-ttu-id="5d7a9-122">Nella finestra di dialogo selezionare il metodo di pagamento e quindi selezionare il percorso del file da importare.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-122">In the dialog box, select the method of payment, and then browse to the location of the file to import.</span></span> 
   > [!NOTE]
   >  <span data-ttu-id="5d7a9-123">Prima di completare questo passaggio, è necessario aver già importato le configurazioni **PVR (CH)** da Lifecycle Services (LCS) e aver impostato il metodo di pagamento PVR.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-123">Before you can complete this step, you must have already imported the **ESR (CH)** configurations from Lifecycle Services (LCS) and set up the ESR method of payment.</span></span> <span data-ttu-id="5d7a9-124">Per ulteriori informazioni, vedere [Formati di file per metodi di pagamento](emea-select-file-formats-for-the-method-of-payments.md).</span><span class="sxs-lookup"><span data-stu-id="5d7a9-124">For more information, see [File formats for method of payments](emea-select-file-formats-for-the-method-of-payments.md).</span></span>

<span data-ttu-id="5d7a9-125">Dopo aver importato il file di pagamento, le righe del giornale di registrazione pagamenti vengono create e contrassegnate per la liquidazione con le fatture cliente in base al riferimento di pagamento.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-125">After you import the payment file, payment journal lines are created and marked for settlement with customer invoices based on the payment reference.</span></span> <span data-ttu-id="5d7a9-126">Se nel file sono presenti delle spese specificate per il conto bancario, ad esempio le transazioni tra il conto principale e il conto di addebito commissioni, queste spese verranno aggiunte al giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d7a9-126">If there are any fees specified for the bank account that are represented in the file, such as transactions between the main account and fee account, these fees will be added to the journal.</span></span>



