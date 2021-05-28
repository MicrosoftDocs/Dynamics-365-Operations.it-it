---
title: Panoramica sull'imposta dedotta all'origine (TDS) indiana
description: Questo argomento fornisce informazioni dettagliate sull'imposta dedotta all'origine (TDS) indiana. La documentazione TDS copre la funzionalità di questa capacità.
author: kailiang
ms.date: 03/19/2021
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
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 28ee843036e11bd37b97a065ce53d2eb860c79d9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023371"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a><span data-ttu-id="dd805-104">Panoramica sull'imposta dedotta all'origine (TDS) indiana</span><span class="sxs-lookup"><span data-stu-id="dd805-104">Indian Tax Deducted at Source (TDS) overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd805-105">Questo argomento fornisce informazioni dettagliate sull'imposta dedotta all'origine (TDS) indiana.</span><span class="sxs-lookup"><span data-stu-id="dd805-105">This topic provides detailed information about Indian Tax Deducted at Source (TDS).</span></span>

<span data-ttu-id="dd805-106">La documentazione TDS copre la funzionalità di questa capacità.</span><span class="sxs-lookup"><span data-stu-id="dd805-106">The TDS documentation covers the functionality of this capability.</span></span> <span data-ttu-id="dd805-107">Descrive inoltre come eseguire l'impostazione di base per la TDS, calcolare la TDS sulle transazioni, completare il processo di liquidazione della TDS, registrare i numeri di certificato TDS e generare richieste TDS, dichiarazioni TDS e certificati TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-107">It also explains how to do the basic setup for TDS, calculate TDS on transactions, complete the TDS settlement process, record TDS certificate numbers, and generate TDS inquiries, TDS statements, and TDS certificates.</span></span> <span data-ttu-id="dd805-108">La documentazione include i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="dd805-108">The documentation includes the following topics:</span></span>

- [<span data-ttu-id="dd805-109">Impostazione di base per TDS</span><span class="sxs-lookup"><span data-stu-id="dd805-109">Basic setup for TDS</span></span>](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [<span data-ttu-id="dd805-110">Designer formula e funzionalità del limite di soglia utilizzati per il calcolo della TDS</span><span class="sxs-lookup"><span data-stu-id="dd805-110">Formula designer and threshold limit functionality used for TDS calculation</span></span>](apac-ind-TDS-Formula-designer.md)
- [<span data-ttu-id="dd805-111">Calcolo della TDS su fatture, pagamenti, effetti passivi e transazioni interaziendali</span><span class="sxs-lookup"><span data-stu-id="dd805-111">Calculation of TDS on invoices, payments, promissory notes, and intercompany transactions</span></span>](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [<span data-ttu-id="dd805-112">Processo di liquidazione TDS periodico e liquidazione degli importi TDS ai fornitori dell'autorità TDS</span><span class="sxs-lookup"><span data-stu-id="dd805-112">Periodic TDS settlement process and settlement of TDS amounts to TDS authority vendors</span></span>](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [<span data-ttu-id="dd805-113">Registrazione e aggiornamento delle date e dei numeri di certificato TDS</span><span class="sxs-lookup"><span data-stu-id="dd805-113">Recording and updating TDS certificate numbers and dates</span></span>](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a><span data-ttu-id="dd805-114">Introduzione a TDS</span><span class="sxs-lookup"><span data-stu-id="dd805-114">Introduction to TDS</span></span>

<span data-ttu-id="dd805-115">Conformemente all'Income tax Act del 1961, l'imposta sul reddito viene dedotta alla fonte dal beneficiario del servizio al momento del pagamento anticipato o della contabilizzazione del credito, a seconda di quale si verifica per primo.</span><span class="sxs-lookup"><span data-stu-id="dd805-115">Per the Income tax Act, 1961, income tax is deducted at the source by the receiver of the service at the time of advance payment or accounting of credit, whichever occurs first.</span></span> <span data-ttu-id="dd805-116">La persona che effettua il pagamento deve detrarre l'importo dell'imposta e pagare solo il saldo netto al fornitore del servizio.</span><span class="sxs-lookup"><span data-stu-id="dd805-116">The person who makes the payment must deduct the tax amount and pay only the net balance to the provider of the service.</span></span> <span data-ttu-id="dd805-117">La TDS viene applicata ai servizi specificati dal governo e l'imposta viene detratta utilizzando le aliquote specificate dal governo relative a un periodo.</span><span class="sxs-lookup"><span data-stu-id="dd805-117">TDS is applied on services that the government specifies, and the tax is deducted by using the rates that the government specifies for a period.</span></span> <span data-ttu-id="dd805-118">Il tasso di detrazione si basa sullo stato dell'entità che riceve il pagamento o fornisce il servizio.</span><span class="sxs-lookup"><span data-stu-id="dd805-118">The rate of deduction is based on the status of the entity that receives the payment or provides the service.</span></span> <span data-ttu-id="dd805-119">Gli stati sono **Persona fisica**, **Famiglia hindu completa** (**HUF**), **Società**, **Ditta**, **Associazione di persone** (**AOP**), **Corpo di individui** (**BOI**) e **Autorità locale**.</span><span class="sxs-lookup"><span data-stu-id="dd805-119">Statuses include **Individual**, **Hindu Undivided Family** (**HUF**), **Company**, **Firm**, **Association of Persons** (**AOP**), **Body of Individuals** (**BOI**), and **Local authority**.</span></span>

<span data-ttu-id="dd805-120">Le sezioni seguenti elencano i servizi a cui viene applicata la TDS, come specificato dal governo indiano.</span><span class="sxs-lookup"><span data-stu-id="dd805-120">The following sections list the services that TDS is applied on, as specified by the Government of India.</span></span>

<span data-ttu-id="dd805-121">**Residenti**</span><span class="sxs-lookup"><span data-stu-id="dd805-121">**Residents**</span></span>

- <span data-ttu-id="dd805-122">Reddito da stipendi (sezione 192)</span><span class="sxs-lookup"><span data-stu-id="dd805-122">Income from salaries (Under section 192)</span></span>
- <span data-ttu-id="dd805-123">Reddito da interessi su titoli (sezione 193)</span><span class="sxs-lookup"><span data-stu-id="dd805-123">Income from interest on securities (Under section 193)</span></span>
- <span data-ttu-id="dd805-124">Reddito da dividendi (sezione 194)</span><span class="sxs-lookup"><span data-stu-id="dd805-124">Income from dividend (Under section 194)</span></span>
- <span data-ttu-id="dd805-125">Reddito da interessi (sezione 194A)</span><span class="sxs-lookup"><span data-stu-id="dd805-125">Income from interest (Under section 194A)</span></span>
- <span data-ttu-id="dd805-126">Reddito da lotterie o giochi (sezione 194B)</span><span class="sxs-lookup"><span data-stu-id="dd805-126">Income from lotteries or puzzles (Under section 194B)</span></span>
- <span data-ttu-id="dd805-127">Vincite da corse di cavalli ecc. (sezione 194BB)</span><span class="sxs-lookup"><span data-stu-id="dd805-127">Winning from horse races etc. (Under section 194BB)</span></span>
- <span data-ttu-id="dd805-128">Appaltatori e subappaltatori (sezione 194C)</span><span class="sxs-lookup"><span data-stu-id="dd805-128">Contractors and sub-contractors (Under section 194C)</span></span>
- <span data-ttu-id="dd805-129">Commissione assicurativa (sezione 194D)</span><span class="sxs-lookup"><span data-stu-id="dd805-129">Insurance commission (Under section 194D)</span></span>
- <span data-ttu-id="dd805-130">Reddito da depositi nel quadro di un regime di risparmio nazionale (sezione 194EE)</span><span class="sxs-lookup"><span data-stu-id="dd805-130">Income from deposit under national saving scheme (Under section 194EE)</span></span>
- <span data-ttu-id="dd805-131">Reddito da fondi comuni di investimento o UTI (sezione 194F)</span><span class="sxs-lookup"><span data-stu-id="dd805-131">Income from mutual fund or UTI (Under section 194F)</span></span>
- <span data-ttu-id="dd805-132">Commissioni, remunerazioni, premi ecc., per vendita o lotteria (sezione 194G)</span><span class="sxs-lookup"><span data-stu-id="dd805-132">Commission, Remuneration, Prize etc., on sale or lottery (Under section 194G)</span></span>
- <span data-ttu-id="dd805-133">Pagamento di commissioni o intermediazione (sezione 194H)</span><span class="sxs-lookup"><span data-stu-id="dd805-133">Payment of Commission or brokerage (Under section 194H)</span></span>
- <span data-ttu-id="dd805-134">Affitto (sezione 194I)</span><span class="sxs-lookup"><span data-stu-id="dd805-134">Rent (Under section 194I)</span></span>
- <span data-ttu-id="dd805-135">Servizio professionale (sezione 194J)</span><span class="sxs-lookup"><span data-stu-id="dd805-135">Professional service (Under section 194J)</span></span>
- <span data-ttu-id="dd805-136">Reddito da unità (sezione 194K)</span><span class="sxs-lookup"><span data-stu-id="dd805-136">Income from Units (Under section 194K)</span></span>
- <span data-ttu-id="dd805-137">Pagamento di compensazioni per l'acquisizione di determinati beni immobili (sezione 194LA)</span><span class="sxs-lookup"><span data-stu-id="dd805-137">Payment of compensation on acquisition of certain immovable property (Under section 194LA)</span></span>

<span data-ttu-id="dd805-138">**Non residenti**</span><span class="sxs-lookup"><span data-stu-id="dd805-138">**Non-residents**</span></span>

- <span data-ttu-id="dd805-139">Pagamenti a sportivi o associazioni sportive non residenti (sezione 194E)</span><span class="sxs-lookup"><span data-stu-id="dd805-139">Payments to Non-resident sportsmen or sports association (Under section 194E)</span></span>
- <span data-ttu-id="dd805-140">Altre somme (sezione 195)</span><span class="sxs-lookup"><span data-stu-id="dd805-140">Other sums (Under section 195)</span></span>
- <span data-ttu-id="dd805-141">Reddito relativo a unità di non residenti (sezione 196A)</span><span class="sxs-lookup"><span data-stu-id="dd805-141">Income in respect of units of non-residents (Under section 196A)</span></span>

    - <span data-ttu-id="dd805-142">Reddito da obbligazioni o azioni in valuta estera della Indian Company (sezione 196C)</span><span class="sxs-lookup"><span data-stu-id="dd805-142">Income from foreign currency bonds or shares of Indian Company (Under section 196C)</span></span>
    - <span data-ttu-id="dd805-143">Redditi di investitori istituzionali esteri da titoli (sezione 196D)</span><span class="sxs-lookup"><span data-stu-id="dd805-143">Incomes of foreign institutional investors from securities (Under section 196D)</span></span>
    - <span data-ttu-id="dd805-144">Stipendio e tutti gli altri redditi positivi sotto qualsiasi reddito nominale (sezione 192)</span><span class="sxs-lookup"><span data-stu-id="dd805-144">Salary and all other positive incomes under any head on income (Section 192)</span></span>
    - <span data-ttu-id="dd805-145">Interessi su titoli (sezione 193)</span><span class="sxs-lookup"><span data-stu-id="dd805-145">Interest on securities (Section 193)</span></span>
    - <span data-ttu-id="dd805-146">Interessi diversi da interessi su titoli (sezione 194A)</span><span class="sxs-lookup"><span data-stu-id="dd805-146">Interest other than interest on securities (Section 194A)</span></span>
    - <span data-ttu-id="dd805-147">Pagamenti ad appaltatori e subappaltatori (sezione 194C)</span><span class="sxs-lookup"><span data-stu-id="dd805-147">Payments to contractors and sub-contractors (Section 194C)</span></span>
    - <span data-ttu-id="dd805-148">Vincite da lotterie o cruciverba (sezione 194B)</span><span class="sxs-lookup"><span data-stu-id="dd805-148">Winnings from Lottery or crossword puzzles (Section 194B)</span></span>
    - <span data-ttu-id="dd805-149">Vincite da corse di cavalli (in virtù della sezione 194BB)</span><span class="sxs-lookup"><span data-stu-id="dd805-149">Winnings from horse races (Section 194BB)</span></span>
    - <span data-ttu-id="dd805-150">Commissione assicurativa che copre tutti i pagamenti per l'acquisizione di attività assicurative (sezione 194D)</span><span class="sxs-lookup"><span data-stu-id="dd805-150">Insurance Commission covering all payments for procuring Insurance business (Section 194D)</span></span>
    - <span data-ttu-id="dd805-151">Qualsiasi interesse diverso dagli interessi su titoli pagabili a non residenti che non sono una società o una società estera (sezione 195)</span><span class="sxs-lookup"><span data-stu-id="dd805-151">Any interest other than interest on securities payable to non-residents not being a company or to a foreign company (Section 195)</span></span>
    - <span data-ttu-id="dd805-152">Pagamento a uno sportivo non residente compreso un'atleta o un'associazione o un ente sportivo.</span><span class="sxs-lookup"><span data-stu-id="dd805-152">Payment to non-resident sportsman including athlete or sports association or institution.</span></span> <span data-ttu-id="dd805-153">In caso di sportivo non residente, sono inclusi pagamenti relativi a pubblicità e articoli su qualsiasi gioco/sport in India in giornali, riviste e così via</span><span class="sxs-lookup"><span data-stu-id="dd805-153">In case of non-resident sportsman, payments in respect of advertisements as well as articles on any game/sports in India in newspapers, magazines, and so.</span></span> <span data-ttu-id="dd805-154">(sezione 194E)</span><span class="sxs-lookup"><span data-stu-id="dd805-154">is included (Section 194E)</span></span>
    - <span data-ttu-id="dd805-155">Pagamento in relazione a depositi sotto NSS \[Programma di risparmio nazionale\] (sezione 194EE)</span><span class="sxs-lookup"><span data-stu-id="dd805-155">Payment in respect of deposits under NSS \[National Savings Scheme\] (Section 194EE)</span></span>
    - <span data-ttu-id="dd805-156">Pagamento a seguito di riacquisto di unità da parte di un Fondo Comune o UTI (sezione 194F)</span><span class="sxs-lookup"><span data-stu-id="dd805-156">Payment on account of repurchase of Units by Mutual Fund or UTI (Section 194F)</span></span>
    - <span data-ttu-id="dd805-157">Pagamento per commissioni o intermediazione (sezione 194H)</span><span class="sxs-lookup"><span data-stu-id="dd805-157">Payment for Commission or brokerage (Section 194H)</span></span>
    - <span data-ttu-id="dd805-158">Pagamento di affitto (sezione 194I)</span><span class="sxs-lookup"><span data-stu-id="dd805-158">Payment of rent (Section 194I)</span></span>
    - <span data-ttu-id="dd805-159">Pagamento di compensi per servizi professionali o tecnici (sezione 194J)</span><span class="sxs-lookup"><span data-stu-id="dd805-159">Payment of fees for professional or technical services (Section 194J)</span></span>
    - <span data-ttu-id="dd805-160">Commissione a stocchisti, distributori, acquirenti e venditori di biglietti della lotteria, inclusa la remunerazione o il premio di tali biglietti (sezione 194G)</span><span class="sxs-lookup"><span data-stu-id="dd805-160">Commission to Stockiest, distributors, buyers and sellers of Lottery tickets including remuneration or prize on such tickets (Section 194G)</span></span>
    - <span data-ttu-id="dd805-161">Reddito da unità acquistate in valuta estera o plusvalenza a lungo termine derivante dal trasferimento di tali unità acquistate in valuta estera (sezione 196B)</span><span class="sxs-lookup"><span data-stu-id="dd805-161">Income from Units purchased in foreign currency or long-term capital gain arising from the transfer of such Units purchased in foreign currency (Section 196B)</span></span>
    - <span data-ttu-id="dd805-162">Pagamento di qualsiasi reddito a non residenti in relazione a interessi o dividendi su obbligazioni e azioni (sezione 196C)</span><span class="sxs-lookup"><span data-stu-id="dd805-162">Payment of any income to non-residents in respect of interest or dividend on bonds and shares (Section 196C)</span></span>

<span data-ttu-id="dd805-163">La TDS viene calcolata su acquisti, vendite, resi di vendita, note di accredito, acquisizioni di cespiti, pagamenti anticipati, effetti passivi, imposte su lavori e transazioni interaziendali.</span><span class="sxs-lookup"><span data-stu-id="dd805-163">TDS is calculated on purchases, sales, sales returns, credit notes, fixed asset acquisitions, prepayments, advance payments, promissory notes, works tax, and intercompany transactions.</span></span>

> [!NOTE]
> <span data-ttu-id="dd805-164">Nello scenario fiscale indiano attuale, la TDS non viene calcolata sulle transazioni di vendita.</span><span class="sxs-lookup"><span data-stu-id="dd805-164">In the current Indian tax scenario, TDS isn't calculated on sales transactions.</span></span> <span data-ttu-id="dd805-165">Tuttavia, il sistema include una disposizione per calcolare la TDS recuperabile su transazioni di vendita, in particolare per le transazioni interaziendali.</span><span class="sxs-lookup"><span data-stu-id="dd805-165">However, the system includes a provision to calculate TDS recoverable on sales transactions, especially for intercompany transactions.</span></span>

<span data-ttu-id="dd805-166">Il calcolo della TDS prende sempre in considerazione la soglia e la soglia di eccezione definite per il componente TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-166">The calculation of TDS always considers the threshold and the exception threshold that are defined for the TDS component.</span></span>

<span data-ttu-id="dd805-167">È necessario eseguire il processo di liquidazione periodica della TDS e i pagamenti della TDS devono essere liquidati ai fornitori dell'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-167">The periodic TDS settlement process must be run, and the TDS payments must be settled to TDS authority vendors.</span></span>

<span data-ttu-id="dd805-168">Le date e i numeri dei certificati TDS ricevuti da fornitori o clienti possono essere registrati e aggiornati.</span><span class="sxs-lookup"><span data-stu-id="dd805-168">The certificate numbers and dates for TDS certificates that are received from vendors or customers can be recorded and updated.</span></span> <span data-ttu-id="dd805-169">Inoltre, le dichiarazioni trimestrali con moduli 26Q e 27Q e il certificato con modulo 16A per la TDS possono essere generati in Finance.</span><span class="sxs-lookup"><span data-stu-id="dd805-169">Additionally, Form 26Q and Form 27Q quarterly statements, and the Form 16A certificate for TDS, can be generated in Finance.</span></span>

## <a name="setting-up-and-working-with-tds"></a><span data-ttu-id="dd805-170">Impostazione e utilizzo della TDS</span><span class="sxs-lookup"><span data-stu-id="dd805-170">Setting up and working with TDS</span></span>

<span data-ttu-id="dd805-171">Di seguito è riportata una panoramica del processo di impostazione e utilizzo della TDS:</span><span class="sxs-lookup"><span data-stu-id="dd805-171">Here is an overview of the process for setting up and working with TDS:</span></span>

1. <span data-ttu-id="dd805-172">**Impostazione TDS**</span><span class="sxs-lookup"><span data-stu-id="dd805-172">**TDS setup:**</span></span>

    - <span data-ttu-id="dd805-173">Impostazione dei parametri:</span><span class="sxs-lookup"><span data-stu-id="dd805-173">Parameter setup:</span></span>

        - <span data-ttu-id="dd805-174">In Parametri di contabilità generale, attiva i parametri correlati alla TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-174">In General ledger parameters, activate parameters that are related to TDS.</span></span>
        - <span data-ttu-id="dd805-175">In Parametri di contabilità generale, imposta la sequenza numerica per i pagamenti della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="dd805-175">In General ledger parameters, set up the number sequence for withholding tax payments.</span></span>
        - <span data-ttu-id="dd805-176">Imposta i parametri in Contabilità fornitori e Contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="dd805-176">Set up parameters in Accounts payable and Accounts receivable.</span></span>

    - <span data-ttu-id="dd805-177">Impostazione di base:</span><span class="sxs-lookup"><span data-stu-id="dd805-177">Basic setup:</span></span>

        - <span data-ttu-id="dd805-178">Imposta i numeri di registrazione TDS per un'azienda, clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="dd805-178">Set up TDS registration numbers for a company, customers, and vendors.</span></span>
        - <span data-ttu-id="dd805-179">Imposta gruppi di componenti TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-179">Set up TDS component groups.</span></span>
        - <span data-ttu-id="dd805-180">Imposta componenti TDS, associaci gruppi di componenti TDS e definisci la soglia e la soglia di eccezione per gli stessi.</span><span class="sxs-lookup"><span data-stu-id="dd805-180">Set up TDS components, attach TDS component groups to them, and define the threshold and exception threshold for them.</span></span>
        - <span data-ttu-id="dd805-181">Imposta le autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-181">Set up TDS authorities.</span></span>
        - <span data-ttu-id="dd805-182">Imposta i periodi di liquidazione TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-182">Set up TDS settlement periods.</span></span>
        - <span data-ttu-id="dd805-183">Imposta i codici imposta TDS e associaci i componenti TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-183">Set up TDS tax codes, and attach TDS components to them.</span></span>
        - <span data-ttu-id="dd805-184">Imposta i gruppi di imposte TDS e associaci i codici imposta TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-184">Set up TDS tax groups, and attach TDS tax codes to them.</span></span>
        - <span data-ttu-id="dd805-185">In Designer formula, definisci una formula per calcolare la TDS per un gruppo TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-185">In the formula designer, define a formula to calculate TDS for a TDS group.</span></span>
        - <span data-ttu-id="dd805-186">Registra i numeri di certificato delle concessioni TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-186">Record TDS concession certificate numbers.</span></span>

    - <span data-ttu-id="dd805-187">Impostazione di conti CoGe e società:</span><span class="sxs-lookup"><span data-stu-id="dd805-187">Ledger accounts and company setup:</span></span>

        - <span data-ttu-id="dd805-188">Imposta i conti CoGe TDS a debito e a credito.</span><span class="sxs-lookup"><span data-stu-id="dd805-188">Set up TDS payable and receivable ledger accounts.</span></span>
        - <span data-ttu-id="dd805-189">Imposta una detrazione fiscale e un numero di conto imposta (TAN) nonché una categoria di tipo di detrazione per la società.</span><span class="sxs-lookup"><span data-stu-id="dd805-189">Set up a Tax Deduction and Collection Account Number (TAN) and a deductor type category for the company.</span></span>

    - <span data-ttu-id="dd805-190">Altre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dd805-190">Other setup:</span></span>

        - <span data-ttu-id="dd805-191">Imposta uno scadenziario pagamenti che includa l'allocazione TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-191">Set up a payment schedule that includes TDS allocation.</span></span>
        - <span data-ttu-id="dd805-192">Imposta un tipo di commissione pagamento per i pagamenti all'autorità TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-192">Set up a payment fee type for payments to the TDS authority.</span></span>
        - <span data-ttu-id="dd805-193">Imposta le informazioni su gruppi TDS, numeri di conto permanenti (PAN) e TAN per fornitori e clienti.</span><span class="sxs-lookup"><span data-stu-id="dd805-193">Set up information about TDS groups, permanent account numbers (PANs), and TANs for vendors and customers.</span></span>

2. <span data-ttu-id="dd805-194">**Calcolo della TDS nelle transazioni:**</span><span class="sxs-lookup"><span data-stu-id="dd805-194">**Calculation of TDS in transactions:**</span></span>

    - <span data-ttu-id="dd805-195">Fatture e pagamenti</span><span class="sxs-lookup"><span data-stu-id="dd805-195">Invoices and payments</span></span>
    - <span data-ttu-id="dd805-196">Effetti passivi</span><span class="sxs-lookup"><span data-stu-id="dd805-196">Promissory notes</span></span>
    - <span data-ttu-id="dd805-197">Pagamenti anticipati</span><span class="sxs-lookup"><span data-stu-id="dd805-197">Advance payments</span></span>
    - <span data-ttu-id="dd805-198">Anticipi</span><span class="sxs-lookup"><span data-stu-id="dd805-198">Prepayments</span></span>

3. <span data-ttu-id="dd805-199">**Liquidazione TDS:**</span><span class="sxs-lookup"><span data-stu-id="dd805-199">**TDS settlement:**</span></span>

    - <span data-ttu-id="dd805-200">Processo di liquidazione TDS periodico</span><span class="sxs-lookup"><span data-stu-id="dd805-200">Periodic TDS settlement process</span></span>
    - <span data-ttu-id="dd805-201">Liquidazione di pagamenti TDS ai fornitori dell'autorità TDS e generazione del challan TDS</span><span class="sxs-lookup"><span data-stu-id="dd805-201">Settlement of TDS payments to TDS authority vendors and generation of TDS challan</span></span>

4. <span data-ttu-id="dd805-202">**Richieste, dichiarazioni e certificati TDS:**</span><span class="sxs-lookup"><span data-stu-id="dd805-202">**TDS inquiries, statements, and certificate:**</span></span>

    - <span data-ttu-id="dd805-203">Registra e aggiorna date e numeri di certificati TDS.</span><span class="sxs-lookup"><span data-stu-id="dd805-203">Record and update TDS certificate numbers and dates.</span></span>
    - <span data-ttu-id="dd805-204">Genera una richiesta TDS e una richiesta TDS registrata.</span><span class="sxs-lookup"><span data-stu-id="dd805-204">Generate a TDS inquiry and a posted TDS inquiry.</span></span>
    - <span data-ttu-id="dd805-205">Genera dichiarazioni trimestrali TDS e e-TDS con modulo 27A, modulo 26Q e modulo 27Q.</span><span class="sxs-lookup"><span data-stu-id="dd805-205">Generate Form 27A, Form 26Q, and Form 27Q TDS and e-TDS quarterly statements.</span></span>
    - <span data-ttu-id="dd805-206">Genera un certificato TDS con modulo 16A.</span><span class="sxs-lookup"><span data-stu-id="dd805-206">Generate a Form 16A TDS certificate.</span></span>
