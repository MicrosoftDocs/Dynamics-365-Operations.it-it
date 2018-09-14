--- 
title: Immettere contratti di vendita
description: In questa procedura vengono descritti i passaggi per creare un contratto di vendita con cui un cliente si impegna ad acquistare un prodotto per un importo concordato in cambio di sconti speciali.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 874fee6de6e5aa5a29c271cc2e3d4cfd96672f3e
ms.contentlocale: it-it
ms.lasthandoff: 09/14/2018

---
# <a name="enter-sales-agreements"></a><span data-ttu-id="8aaa7-103">Immettere contratti di vendita</span><span class="sxs-lookup"><span data-stu-id="8aaa7-103">Enter sales agreements</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8aaa7-104">In questa procedura viene illustrato come creare un contratto di vendita che impegna uno dei clienti ad acquistare un prodotto per un</span><span class="sxs-lookup"><span data-stu-id="8aaa7-104">This procedure shows you how to create a sales agreement that commits one of your customers to buy a product for an</span></span>

<span data-ttu-id="8aaa7-105">importo concordato nel tempo in cambio di sconti speciali.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-105">agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="8aaa7-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="8aaa7-107">Impostare l'intestazione del contratto di vendita</span><span class="sxs-lookup"><span data-stu-id="8aaa7-107">Set up sales agreement header</span></span>
1. <span data-ttu-id="8aaa7-108">Passare a Vendite e marketing > Contratti di vendita > Contratti di vendita.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-108">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="8aaa7-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-109">Click New.</span></span>
3. <span data-ttu-id="8aaa7-110">Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8aaa7-111">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="8aaa7-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8aaa7-113">Nel campo Classificazione contratto di vendita fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-113">In the Sales agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8aaa7-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8aaa7-115">Espandere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-115">Expand the General section.</span></span>
9. <span data-ttu-id="8aaa7-116">Nel campo Impegno predefinito, selezionare 'Impegno valore prodotto'.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-116">In the Default commitment field, select 'Product value commitment'.</span></span>
    * <span data-ttu-id="8aaa7-117">Un tipo di impegno è un criterio obbligatorio che è necessario assegnare al contratto per definire la modalità di evasione del contratto.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-117">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="8aaa7-118">I quattro tipi predefiniti consentono di impostare la destinazione dell'impegno del cliente, espressa come quantità o valore.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-118">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="8aaa7-119">Il tipo di impegno di quantità può applicarsi a un solo prodotto specifico, ma i tipi di valore sono applicabili alle vendite di prodotti specifici e non specifici.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-119">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
10. <span data-ttu-id="8aaa7-120">Nel campo Data di scadenza, impostare una data futura per la scadenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-120">In the Expiration date field, set the date to a future date when you want the agreement to expire.</span></span>
11. <span data-ttu-id="8aaa7-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-121">Click OK.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="8aaa7-122">Impostare le righe di impegno valore prodotto</span><span class="sxs-lookup"><span data-stu-id="8aaa7-122">Set up product value commitment lines</span></span>
1. <span data-ttu-id="8aaa7-123">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-123">Click Add line.</span></span>
2. <span data-ttu-id="8aaa7-124">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="8aaa7-125">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="8aaa7-126">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-126">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8aaa7-127">Il tipo di impegno scelto per il contratto influisce sul tipo di informazioni che è possibile immettere per le righe del contratto.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-127">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="8aaa7-128">Ad esempio, per un contratto in base al valore è necessario specificare l'importo netto totale (nella valuta concordata) per il quale il cliente si impegna ad acquistare beni dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-128">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="8aaa7-129">In questo esempio i campi Unità e Quantità nella riga non sono disponibili perché si sta creando un contratto per cui il cliente compra un valore specifico di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-129">In this example the Quantity and Unit fields on the line are unavailable because you’re creating an agreement for the customer to buy a specific value of a product.</span></span>   
5. <span data-ttu-id="8aaa7-130">Nel campo Importo netto, immettere l'importo monetario che il cliente si è impegnato ad acquistare.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-130">In the Net amount field, enter the monetary amount that the customer has committed to buying.</span></span>
6. <span data-ttu-id="8aaa7-131">Nel campo Percentuale sconto, immettere un valore in percentuale da applicare alle righe dell'ordine cliente collegate a questo contratto.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-131">In the Discount percent field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
7. <span data-ttu-id="8aaa7-132">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-132">Expand the Line details section.</span></span>
8. <span data-ttu-id="8aaa7-133">Selezionare Sì nel campo Valore massimo applicato.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-133">Select Yes in the Max is enforced field.</span></span>
    * <span data-ttu-id="8aaa7-134">Selezionare Valore massimo applicato per indicare che l'importo totale di tutte le righe ordine cliente che utilizzano i prezzi speciali, gli sconti e/o i termini di pagamento dell'impegno non deve superare l'importo specificato nell'impegno.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-134">Selecting Max is enforced means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    * <span data-ttu-id="8aaa7-135">Gli importi di rilascio minimo e massimo specificano un intervallo di valori che devono essere venduti in ogni ordine cliente che utilizza il contratto selezionato.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-135">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
9. <span data-ttu-id="8aaa7-136">Espandere la sezione Intestazione contratto di vendita.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-136">Expand the Sales agreement header section.</span></span>
    * <span data-ttu-id="8aaa7-137">A meno che lo stato del contratto non sia impostato su Validità, gli ordini cliente non possono essere associati al contratto e pertanto non possono contribuire all'evasione del contratto.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-137">Unless the status of the agreement is set to Effective, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="8aaa7-138">È possibile modificare lo stato manualmente in questa fase.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-138">You can change the status manually at this stage.</span></span> <span data-ttu-id="8aaa7-139">Tuttavia, lo stato in genere viene modificato quando si conferma il contratto per il cliente.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-139">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
10. <span data-ttu-id="8aaa7-140">Nel riquadro azioni, fare clic su Contratto di vendita.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-140">On the Action Pane, click Sales agreement.</span></span>
11. <span data-ttu-id="8aaa7-141">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-141">Click Confirmation.</span></span>
    * <span data-ttu-id="8aaa7-142">Verificare che l'opzione Contrassegna contratto come valido sia impostata su Sì.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-142">Make sure that the Mark agreement as effective option is set to Yes.</span></span>  
12. <span data-ttu-id="8aaa7-143">Selezionare Sì nel campo Stampa report.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-143">Select Yes in the Print report field.</span></span>
13. <span data-ttu-id="8aaa7-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-144">Click OK.</span></span>
14. <span data-ttu-id="8aaa7-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-145">Close the page.</span></span>
    * <span data-ttu-id="8aaa7-146">Il contratto è ora effettivo ed è possibile avviare il collegamento degli ordini cliente al contratto, da compensare a fronte della destinazione impegnata.</span><span class="sxs-lookup"><span data-stu-id="8aaa7-146">The agreement is now effective and you can start linking the customer's orders to the agreement, to offset against the committed target.</span></span>  


