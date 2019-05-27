---
title: Configurare la gestione delle spese
description: Questo articolo descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di configurare la gestione delle spese in Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GlobalCategory, ProjCategory, TrvLocations, TrvParameters, TrvPaymethod, TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23001
ms.assetid: aa3fd14d-7e94-4603-985f-ca26d6f860ea
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ac9959a4ee66e52ead5050897403602e407ca10
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570624"
---
# <a name="configure-expense-management"></a><span data-ttu-id="0c36e-103">Configurare la gestione delle spese</span><span class="sxs-lookup"><span data-stu-id="0c36e-103">Configure expense management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c36e-104">Questo argomento descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di configurare la gestione delle spese in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0c36e-104">This topic describes the considerations and the decisions that you must make during the planning process before you configure Expense management in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="0c36e-105">In Gestione spese, è possibile archiviare informazioni su metodi di pagamento, richieste di viaggio, note spese, criteri e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="0c36e-105">In Expense management, you can store information about payment methods, travel requisitions, expense reports, policies, and so on.</span></span>

<span data-ttu-id="0c36e-106">Poiché molte decisioni che prese quando si pianifica la configurazione per la gestione delle spese si basano sulla struttura finanziaria e gerarchica dell'organizzazione, è necessario fare riferimento ai documenti di pianificazione per le aree.</span><span class="sxs-lookup"><span data-stu-id="0c36e-106">Because many of the decisions that you make when you plan your configuration for Expense management are based on your organization’s hierarchy and financial structure, you must refer to the planning documents for those areas.</span></span>

## <a name="intercompany-expenses"></a><span data-ttu-id="0c36e-107">Spese interaziendali</span><span class="sxs-lookup"><span data-stu-id="0c36e-107">Intercompany expenses</span></span>

<span data-ttu-id="0c36e-108">Quando si abilitano le spese interaziendali, si consente alle persone giuridiche e ai dipendenti di effettuare spese per conto di un'altra persona giuridica, e riscuotere il pagamento dalla persona giuridica di impiego all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c36e-108">When you enable intercompany expenses, you allow legal entities and employees to incur expenses on behalf of another legal entity, and collect payment from the legal entity of employment within your organization.</span></span> <span data-ttu-id="0c36e-109">Ad esempio, un dipendente nella persona giuridica A completa un progetto per la persona giuridica B e il progetto comporta spese di viaggio.</span><span class="sxs-lookup"><span data-stu-id="0c36e-109">For example, an employee in legal entity A completes a project for legal entity B, and the project incurs travel related expenses.</span></span> <span data-ttu-id="0c36e-110">Se le spese interaziendali sono abilitate, il dipendente può quindi creare una nota spese che registrerà le spese per la persona giuridica B e le spese devono quindi essere pagate dalla persona giuridica A. Se l'organizzazione non ha molteplici persone giuridiche, non sarà necessario abilitare le spese interaziendali.</span><span class="sxs-lookup"><span data-stu-id="0c36e-110">If intercompany expenses are enabled, the employee can then file an expense report that will post the expense to legal entity B, and the expense must then be paid by legal entity A. If your organization doesn’t have multiple legal entities, you don’t have to enable intercompany expenses.</span></span>

<span data-ttu-id="0c36e-111">**Decisione:** Si desidera abilitare le spese interaziendali?</span><span class="sxs-lookup"><span data-stu-id="0c36e-111">**Decision:** Do you want to enable intercompany expenses?</span></span>

## <a name="financial-management"></a><span data-ttu-id="0c36e-112">Gestione finanziaria</span><span class="sxs-lookup"><span data-stu-id="0c36e-112">Financial management</span></span>

<span data-ttu-id="0c36e-113">La gestione delle spese è strettamente integrata alla gestione finanziaria dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c36e-113">Expense management is tightly integrated with the financial management of your organization.</span></span> <span data-ttu-id="0c36e-114">Gran parte della configurazione per la gestione delle spese verrà basata sulle decisioni prese riguardo le finanze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c36e-114">Lots of your configuration for Expense management will be based on the decisions that you’ve made about your organization’s finances.</span></span> <span data-ttu-id="0c36e-115">Nelle sezioni seguenti vengono descritte le varie aree che richiedono pianificazione e decisioni, in base alle decisioni finanziarie dell'organizzazione e alle indicazioni del team di responsabili.</span><span class="sxs-lookup"><span data-stu-id="0c36e-115">The following sections describe the various areas that require planning and decisions, based on your organization’s financial decisions and guidance from your leadership team.</span></span>

### <a name="per-diems"></a><span data-ttu-id="0c36e-116">Trasferte giornaliere</span><span class="sxs-lookup"><span data-stu-id="0c36e-116">Per diems</span></span>

<span data-ttu-id="0c36e-117">È necessario definire le trasferte giornaliere del dipendente che l'organizzazione garantisce.</span><span class="sxs-lookup"><span data-stu-id="0c36e-117">You must define the employee per diems that your organization provides.</span></span> <span data-ttu-id="0c36e-118">Poiché le trasferte giornaliere sono in genere utilizzate per coprire le spese quali vitto, alloggio e altre spese extra, è possibile creare regole per le indennità di trasferta giornaliera che l'organizzazione offre.</span><span class="sxs-lookup"><span data-stu-id="0c36e-118">Because per diems are typically used to cover expenses such as meals, lodging, and other incidental expenses, you can create rules for the per diem allowances that your organization offers.</span></span> <span data-ttu-id="0c36e-119">Le tariffe giornaliere infatti possono essere impostate in base al periodo dell'anno, alla destinazione di viaggio o a entrambi gli elementi.</span><span class="sxs-lookup"><span data-stu-id="0c36e-119">per diem rates can be based on the time of year, the travel location, or both.</span></span> <span data-ttu-id="0c36e-120">Quando si definisce una regola per le trasferte giornaliere, è possibile specificare che verrà trattenuta una percentuale della tariffa prevista se il lavoratore usufruisce gratuitamente di pasti o servizi.</span><span class="sxs-lookup"><span data-stu-id="0c36e-120">When you define a per diem rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services.</span></span> <span data-ttu-id="0c36e-121">È anche possibile definire livelli di tariffe giornaliere per impostare un numero minimo e massimo di ore a cui la tariffa giornaliera può essere applicata per una trasferta di un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="0c36e-121">You can also define per diem rate tiers to set the minimum and maximum number of hours that the per diem rate can be applied to a worker’s travel.</span></span>

<span data-ttu-id="0c36e-122">**Decisioni:**</span><span class="sxs-lookup"><span data-stu-id="0c36e-122">**Decisions:**</span></span>

- <span data-ttu-id="0c36e-123">Regole relative alla trasferta giornaliera predefinite per il primo e l'ultimo giorno:</span><span class="sxs-lookup"><span data-stu-id="0c36e-123">Default per diem rules for the first and last days:</span></span>

    - <span data-ttu-id="0c36e-124">Qual è il numero minimo di ore che un dipendente può richiedere per un giorno e ricevere comunque una trasferta giornaliera?</span><span class="sxs-lookup"><span data-stu-id="0c36e-124">What is the minimum number of hours that an employee can claim for a day and still receive a per diem?</span></span>
    - <span data-ttu-id="0c36e-125">Esiste una riduzione dell'importo che viene offerto per il vitto per il primo e l'ultimo giorno?</span><span class="sxs-lookup"><span data-stu-id="0c36e-125">Is there a reduction in the amount that is offered for meals for the first day and last day?</span></span> <span data-ttu-id="0c36e-126">Se sì, qual è la percentuale di riduzione?</span><span class="sxs-lookup"><span data-stu-id="0c36e-126">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="0c36e-127">Esiste una riduzione dell'importo che viene offerto per l'alloggio per il primo e l'ultimo giorno?</span><span class="sxs-lookup"><span data-stu-id="0c36e-127">Is there a reduction in the amount that is offered for a hotel for the first day and last day?</span></span> <span data-ttu-id="0c36e-128">Se sì, qual è la percentuale di riduzione?</span><span class="sxs-lookup"><span data-stu-id="0c36e-128">If there is a reduction, what is the percentage of the reduction?</span></span>
    - <span data-ttu-id="0c36e-129">Esiste una riduzione dell'importo che viene offerto per le altre spese sostenute il primo e l'ultimo giorno?</span><span class="sxs-lookup"><span data-stu-id="0c36e-129">Is there a reduction in the amount that is offered for other expenses that are incurred on the first day and last day?</span></span> <span data-ttu-id="0c36e-130">Se sì, qual è la percentuale di riduzione?</span><span class="sxs-lookup"><span data-stu-id="0c36e-130">If there is a reduction, what is the percentage of the reduction?</span></span>

- <span data-ttu-id="0c36e-131">Regole relative alla trasferta giornaliera predefinite:</span><span class="sxs-lookup"><span data-stu-id="0c36e-131">Default per diem rules:</span></span>

    - <span data-ttu-id="0c36e-132">Esiste una riduzione percentuale di indennità di trasferta giornaliera per ogni pasto se, ad esempio, il pasto è extra?</span><span class="sxs-lookup"><span data-stu-id="0c36e-132">Is there a percentage reduction in the per diem allowance for each meal if, for example, the meal is complimentary?</span></span> <span data-ttu-id="0c36e-133">Se sì, qual è la relativa percentuale per ogni pasto?</span><span class="sxs-lookup"><span data-stu-id="0c36e-133">If there is a reduction, what is the reduction percentage for each meal?</span></span>
    - <span data-ttu-id="0c36e-134">La riduzione per vitto viene calcolata al giorno, per viaggio, o per numero di pasti al giorno?</span><span class="sxs-lookup"><span data-stu-id="0c36e-134">Is the meal reduction calculated per day, per trip, or by the number of meals per day?</span></span>
    - <span data-ttu-id="0c36e-135">Gli importi di trasferta giornaliera devono essere arrotondati normalmente o per eccesso?</span><span class="sxs-lookup"><span data-stu-id="0c36e-135">Should per diem amounts be rounded in the regular manner or rounded up?</span></span>
    - <span data-ttu-id="0c36e-136">Gli importi di trasferta giornaliera vengono calcolati su un periodo di 24 ore o su un giorno di calendario?</span><span class="sxs-lookup"><span data-stu-id="0c36e-136">Are per diems calculated on a 24-hour period or on a calendar day?</span></span>

- <span data-ttu-id="0c36e-137">Regole relative alla trasferta giornaliera in base all'ubicazione:</span><span class="sxs-lookup"><span data-stu-id="0c36e-137">Per diem rules that are based on location:</span></span>

    - <span data-ttu-id="0c36e-138">Le tariffe giornaliere variano a seconda dell'ubicazione?</span><span class="sxs-lookup"><span data-stu-id="0c36e-138">Do per diem rates vary according to location?</span></span> <span data-ttu-id="0c36e-139">Quali ubicazioni sono incluse?</span><span class="sxs-lookup"><span data-stu-id="0c36e-139">What locations are included?</span></span>
    - <span data-ttu-id="0c36e-140">Se le tariffe giornalierie variano in base all'ubicazione, per ciascuna ubicazione, quale importo percentuale viene fornito per i seguenti tipi di spese:</span><span class="sxs-lookup"><span data-stu-id="0c36e-140">If per diem rates vary according to location, for each location, what percentage amount is provided for the following types of expenses:</span></span>

        - <span data-ttu-id="0c36e-141">Vitto</span><span class="sxs-lookup"><span data-stu-id="0c36e-141">Meals</span></span>
        - <span data-ttu-id="0c36e-142">Hotel</span><span class="sxs-lookup"><span data-stu-id="0c36e-142">Hotel</span></span>
        - <span data-ttu-id="0c36e-143">Altre spese</span><span class="sxs-lookup"><span data-stu-id="0c36e-143">Other expenses</span></span>

### <a name="expense-management-journals-and-accounts"></a><span data-ttu-id="0c36e-144">Conti e giornali di registrazione di gestione spese</span><span class="sxs-lookup"><span data-stu-id="0c36e-144">Expense management journals and accounts</span></span>

<span data-ttu-id="0c36e-145">La gestione delle spese richiede che vengano utilizzati più giornali di registrazione e conti.</span><span class="sxs-lookup"><span data-stu-id="0c36e-145">Expense management requires that you use multiple journals and accounts.</span></span> <span data-ttu-id="0c36e-146">È possibile, ad esempio, decidere se lo stesso conto viene utilizzato per gli anticipi contanti e le controversie su carta di credito.</span><span class="sxs-lookup"><span data-stu-id="0c36e-146">You must decide, for example, whether the same account is used for cash advances and credit card disputes.</span></span>

<span data-ttu-id="0c36e-147">**Decisioni:**</span><span class="sxs-lookup"><span data-stu-id="0c36e-147">**Decisions:**</span></span>

- <span data-ttu-id="0c36e-148">In quale giornale contabile vengono registrate le note spese approvate?</span><span class="sxs-lookup"><span data-stu-id="0c36e-148">Which ledger journal are approved expense reports posted to?</span></span>
- <span data-ttu-id="0c36e-149">Quale conto viene utilizzato per gli anticipi contanti?</span><span class="sxs-lookup"><span data-stu-id="0c36e-149">Which account is used for cash advances?</span></span>
- <span data-ttu-id="0c36e-150">Gli anticipi contanti devono essere registrati immediatamente?</span><span class="sxs-lookup"><span data-stu-id="0c36e-150">Should cash advances be posted immediately?</span></span>

### <a name="payment-methods"></a><span data-ttu-id="0c36e-151">Metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="0c36e-151">Payment methods</span></span>

<span data-ttu-id="0c36e-152">Quando si consente ai dipendenti di sostenere spese per conto dell'azienda, è necessario definire i metodi di pagamento che ai dipendenti è concesso di utilizzare.</span><span class="sxs-lookup"><span data-stu-id="0c36e-152">When you allow employees to incur expenses on behalf of your business, you must define the payment methods that employees are allowed to use.</span></span> <span data-ttu-id="0c36e-153">Ad esempio, è possibile consentire ai dipendenti di utilizzare contanti o una carta di credito aziendale.</span><span class="sxs-lookup"><span data-stu-id="0c36e-153">For example, you might allow employees to use cash or a corporate credit card.</span></span> <span data-ttu-id="0c36e-154">È inoltre possibile consentire ai dipendenti di utilizzare carte di credito personali e poi rimborsare i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="0c36e-154">You might also allow employees to use personal credit cards, and then reimburse the employees.</span></span> <span data-ttu-id="0c36e-155">È necessario prendere le decisioni seguenti per ciascun metodo di pagamento che si consente.</span><span class="sxs-lookup"><span data-stu-id="0c36e-155">You must make the following decisions for each payment method that you allow.</span></span>

<span data-ttu-id="0c36e-156">**Decisioni:**</span><span class="sxs-lookup"><span data-stu-id="0c36e-156">**Decisions:**</span></span>

- <span data-ttu-id="0c36e-157">Quali metodi di pagamento sono consentiti?</span><span class="sxs-lookup"><span data-stu-id="0c36e-157">What payment methods are allowed?</span></span>
- <span data-ttu-id="0c36e-158">Chi possiede le spese per il metodo di pagamento?</span><span class="sxs-lookup"><span data-stu-id="0c36e-158">Who owns the payment method expenses?</span></span>
- <span data-ttu-id="0c36e-159">Esiste un tipo di conto di contropartita?</span><span class="sxs-lookup"><span data-stu-id="0c36e-159">Is there an offset account type?</span></span> <span data-ttu-id="0c36e-160">Se sì, qual è?</span><span class="sxs-lookup"><span data-stu-id="0c36e-160">If there is an offset account type, what is it?</span></span>
- <span data-ttu-id="0c36e-161">Se è presente un conto di contropartita, qual è il conto?</span><span class="sxs-lookup"><span data-stu-id="0c36e-161">If there is an offset account, what is the account?</span></span>
- <span data-ttu-id="0c36e-162">Se il metodo di pagamento è una carta di credito, il metodo di pagamento deve essere utilizzato solo con le transazioni importate?</span><span class="sxs-lookup"><span data-stu-id="0c36e-162">If the payment method is a credit card, should the payment method be used only with imported transactions?</span></span>

### <a name="expense-categories-and-shared-categories"></a><span data-ttu-id="0c36e-163">Categorie di spesa e condivise</span><span class="sxs-lookup"><span data-stu-id="0c36e-163">Expense categories and shared categories</span></span>

<span data-ttu-id="0c36e-164">Quando i dipendenti creano una nota spese, ogni spesa registrata deve essere associata a una categoria di spesa.</span><span class="sxs-lookup"><span data-stu-id="0c36e-164">When employees create an expense report, each expense that they record must be associated with an expense category.</span></span> <span data-ttu-id="0c36e-165">Le categorie di spesa derivano dalle categorie condivise che possono essere condivise per tutte le persone giuridiche dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c36e-165">Expense categories are derived from shared categories that can be shared across the legal entities in your organization.</span></span> <span data-ttu-id="0c36e-166">Tali categorie possono inoltre essere condivise in Gestione progetti e contabilità, in base al modo in cui l'organizzazione è definita.</span><span class="sxs-lookup"><span data-stu-id="0c36e-166">These categories can also be shared in Project management and accounting, depending on the way that your organization is defined.</span></span> <span data-ttu-id="0c36e-167">In base alla definizione dell'organizzazione e alle istruzioni del team di implementazione, determinare se le categorie utilizzate in Gestione spese saranno utilizzate solo in Gestione spese o se devono essere condivise tra Gestione progetti e contabilità e Gestione spese.</span><span class="sxs-lookup"><span data-stu-id="0c36e-167">Based on the definition of your organization and guidance from the implementation team, determine whether the categories that are used in Expense management will be used only in Expense management, or whether they should be shared between Project management and accounting and Expense management.</span></span> <span data-ttu-id="0c36e-168">Si noti che le categorie possono essere condivise tra progetto e spesa o progetto e produzione, ma non tra spesa e produzione.</span><span class="sxs-lookup"><span data-stu-id="0c36e-168">Note that these categories can be shared between Project and Expense or Project and Production, but not between Expense and Production.</span></span> <span data-ttu-id="0c36e-169">È necessario prendere le seguenti decisioni per ciascuna categoria di spesa.</span><span class="sxs-lookup"><span data-stu-id="0c36e-169">You must make the following decisions for each expense category.</span></span>

<span data-ttu-id="0c36e-170">**Decisioni:**</span><span class="sxs-lookup"><span data-stu-id="0c36e-170">**Decisions:**</span></span>

- <span data-ttu-id="0c36e-171">Qual è la categoria di spesa?</span><span class="sxs-lookup"><span data-stu-id="0c36e-171">What is the expense category?</span></span> <span data-ttu-id="0c36e-172">Le categorie di esempio includono voli, hotel o chilometraggio.</span><span class="sxs-lookup"><span data-stu-id="0c36e-172">Examples include categories for flights, hotel, or mileage.</span></span>
- <span data-ttu-id="0c36e-173">La categoria di spesa può essere utilizzata anche in Gestione progetti e contabilità?</span><span class="sxs-lookup"><span data-stu-id="0c36e-173">Can the expense category also be used in Project management and accounting?</span></span>
- <span data-ttu-id="0c36e-174">Qual è il tipo di spesa?</span><span class="sxs-lookup"><span data-stu-id="0c36e-174">What is the expense type?</span></span>
- <span data-ttu-id="0c36e-175">Qual è il metodo di pagamento predefinito per la categoria di spesa?</span><span class="sxs-lookup"><span data-stu-id="0c36e-175">What is the default payment method for the expense category?</span></span>
- <span data-ttu-id="0c36e-176">Le spese nella categoria di spesa devono essere dettagliate?</span><span class="sxs-lookup"><span data-stu-id="0c36e-176">Do expenses in the expense category have to be itemized?</span></span>
- <span data-ttu-id="0c36e-177">Qual è il conto predefinito principale per la categoria di spesa?</span><span class="sxs-lookup"><span data-stu-id="0c36e-177">What is the main default account for the expense category?</span></span>
- <span data-ttu-id="0c36e-178">Qual è la fascia IVA articoli predefinita per la categoria di spesa?</span><span class="sxs-lookup"><span data-stu-id="0c36e-178">What is the default item sales tax group for the expense category?</span></span>
- <span data-ttu-id="0c36e-179">Sono consentiti metodi di pagamento aggiuntivi per la categoria di spesa?</span><span class="sxs-lookup"><span data-stu-id="0c36e-179">Are additional payment methods allowed for the expense category?</span></span> <span data-ttu-id="0c36e-180">Se sono consentiti ulteriori metodi di pagamento, quali sono?</span><span class="sxs-lookup"><span data-stu-id="0c36e-180">If additional payment methods are allowed, what are they?</span></span>
- <span data-ttu-id="0c36e-181">Sono presenti sottocategorie nella categoria di spesa?</span><span class="sxs-lookup"><span data-stu-id="0c36e-181">Are there subcategories in this expense category?</span></span> <span data-ttu-id="0c36e-182">Se lo sono, è necessario prendere anche le decisioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c36e-182">If there are subcategories, you must also make the following decisions:</span></span>

    - <span data-ttu-id="0c36e-183">Le sottocategorie sono escluse dal recupero imposte?</span><span class="sxs-lookup"><span data-stu-id="0c36e-183">Are any of the subcategories excluded from tax recovery?</span></span>
    - <span data-ttu-id="0c36e-184">Qual è la fascia IVA articoli relativa alle sottocategorie?</span><span class="sxs-lookup"><span data-stu-id="0c36e-184">What is the item sales tax group of the subcategories?</span></span>

<span data-ttu-id="0c36e-185">Se la categoria di spesa viene utilizzata anche in Gestione progetti e contabilità, rispondere alle domande rimanenti.</span><span class="sxs-lookup"><span data-stu-id="0c36e-185">If the expense category is also used in Project management and accounting, answer the remaining questions.</span></span> <span data-ttu-id="0c36e-186">In caso contrario, passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="0c36e-186">Otherwise, move on to the next section.</span></span>

- <span data-ttu-id="0c36e-187">Quali conti costi verranno utilizzati per le spese seguenti?</span><span class="sxs-lookup"><span data-stu-id="0c36e-187">Which cost accounts will be used for the following expenses?</span></span>

    - <span data-ttu-id="0c36e-188">Costo</span><span class="sxs-lookup"><span data-stu-id="0c36e-188">Cost</span></span>
    - <span data-ttu-id="0c36e-189">Allocazione retribuzioni</span><span class="sxs-lookup"><span data-stu-id="0c36e-189">Payroll allocation</span></span>
    - <span data-ttu-id="0c36e-190">WIP - Valore di costo</span><span class="sxs-lookup"><span data-stu-id="0c36e-190">WIP-cost value</span></span>
    - <span data-ttu-id="0c36e-191">Costo - articolo</span><span class="sxs-lookup"><span data-stu-id="0c36e-191">Cost-item</span></span>
    - <span data-ttu-id="0c36e-192">WIP - Valore di costo - Articolo</span><span class="sxs-lookup"><span data-stu-id="0c36e-192">WIP-cost value-item</span></span>
    - <span data-ttu-id="0c36e-193">Ratei e risconti passivi</span><span class="sxs-lookup"><span data-stu-id="0c36e-193">Accrued loss</span></span>
    - <span data-ttu-id="0c36e-194">WIP - Ratei e risconti passivi</span><span class="sxs-lookup"><span data-stu-id="0c36e-194">WIP-accrued loss</span></span>

- <span data-ttu-id="0c36e-195">Quali conti relativi ai ricavi verranno utilizzati per quanto segue?</span><span class="sxs-lookup"><span data-stu-id="0c36e-195">Which revenue accounts will be used for the following?</span></span>

    - <span data-ttu-id="0c36e-196">Ricavi fatturati</span><span class="sxs-lookup"><span data-stu-id="0c36e-196">Invoiced revenue</span></span>
    - <span data-ttu-id="0c36e-197">Ricavi sospesi - Valore netto di vendita</span><span class="sxs-lookup"><span data-stu-id="0c36e-197">Accrued revenue-sales value</span></span>
    - <span data-ttu-id="0c36e-198">WIP - Valore netto di vendita</span><span class="sxs-lookup"><span data-stu-id="0c36e-198">WIP-sales value</span></span>
    - <span data-ttu-id="0c36e-199">Ricavi sospesi - produzione</span><span class="sxs-lookup"><span data-stu-id="0c36e-199">Accrued revenue-production</span></span>
    - <span data-ttu-id="0c36e-200">WIP - produzione</span><span class="sxs-lookup"><span data-stu-id="0c36e-200">WIP-production</span></span>
    - <span data-ttu-id="0c36e-201">Ricavi sospesi - profitto</span><span class="sxs-lookup"><span data-stu-id="0c36e-201">Accrued revenue-profit</span></span>
    - <span data-ttu-id="0c36e-202">WIP - profitto</span><span class="sxs-lookup"><span data-stu-id="0c36e-202">WIP-profit</span></span>
    - <span data-ttu-id="0c36e-203">Ricavi sospesi - Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="0c36e-203">Accrued revenue-subscription</span></span>
    - <span data-ttu-id="0c36e-204">WIP - Sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="0c36e-204">WIP-subscription</span></span>

### <a name="taxes"></a><span data-ttu-id="0c36e-205">Imposte</span><span class="sxs-lookup"><span data-stu-id="0c36e-205">Taxes</span></span>

<span data-ttu-id="0c36e-206">Per le imposte di spesa, è necessario determinare cosa è incluso o abilitato nelle note spese.</span><span class="sxs-lookup"><span data-stu-id="0c36e-206">For expense-related taxes, you must determine what is included or enabled on expense reports.</span></span>

<span data-ttu-id="0c36e-207">**Decisioni:**</span><span class="sxs-lookup"><span data-stu-id="0c36e-207">**Decisions:**</span></span>

- <span data-ttu-id="0c36e-208">L'IVA è inclusa negli importi relativi alle spese?</span><span class="sxs-lookup"><span data-stu-id="0c36e-208">Is sales tax included in the expense amounts?</span></span>
- <span data-ttu-id="0c36e-209">Il recupero imposte deve essere abilitato sulle spese?</span><span class="sxs-lookup"><span data-stu-id="0c36e-209">Should tax recovery be enabled on expenses?</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c36e-210">Se durante la pianificazione della contabilità generale, si è deciso di applicare l'IVA U.S.A. e utilizzare le regole di tassazione, non è possibile abilitare il recupero imposte sulle spese.</span><span class="sxs-lookup"><span data-stu-id="0c36e-210">When you were planning the general ledger, if you decided to apply U.S. sales tax and use tax rules, you can’t enable tax recovery on expenses.</span></span> <span data-ttu-id="0c36e-211">Per applicare l'IVA U.S.A. e utilizzare le regole di tassazione, impostare l'opzione **Applica regole di tassazione IVA** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="0c36e-211">(To apply U.S. sales tax and use tax rules, set the **Apply sales tax taxations rules** option to **Yes**.)</span></span>

## <a name="policies"></a><span data-ttu-id="0c36e-212">Criteri</span><span class="sxs-lookup"><span data-stu-id="0c36e-212">Policies</span></span>

<span data-ttu-id="0c36e-213">Creando criteri delle note spese, è possibile risparmiare tempo e denaro quando i dipendenti sostengono spese per conto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0c36e-213">By creating expense report policies, you can help your organization save time and money when employees incur expenses on its behalf.</span></span> <span data-ttu-id="0c36e-214">Grazie ai criteri i dipendenti non sforano il budget, forniscono tutte le informazioni necessarie e spendono denaro solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="0c36e-214">Policies help guarantee that employees stay in budget, provide all required information, and spend money only as they require it.</span></span> <span data-ttu-id="0c36e-215">È necessario prendere le seguenti decisioni per tutti i criteri delle note spese e tutti i criteri di approvazione della note spese creati.</span><span class="sxs-lookup"><span data-stu-id="0c36e-215">You must make the following decisions for each expense report policy and each expense report approval policy that you create.</span></span>

<span data-ttu-id="0c36e-216">**Decisioni:**</span><span class="sxs-lookup"><span data-stu-id="0c36e-216">**Decisions:**</span></span>

- <span data-ttu-id="0c36e-217">Qual è il nome dei criteri?</span><span class="sxs-lookup"><span data-stu-id="0c36e-217">What is the name of the policy?</span></span>
- <span data-ttu-id="0c36e-218">A cosa servono i criteri di spesa?</span><span class="sxs-lookup"><span data-stu-id="0c36e-218">What is the expense policy for?</span></span>
- <span data-ttu-id="0c36e-219">Se in precedenza è stato deciso di abilitare le spese interaziendali, a quali società dell'organizzazione si applicheranno i criteri?</span><span class="sxs-lookup"><span data-stu-id="0c36e-219">If you previously decided to enable intercompany expenses, which companies in your organization will this policy apply to?</span></span>
- <span data-ttu-id="0c36e-220">Quando i criteri diventano effettivi?</span><span class="sxs-lookup"><span data-stu-id="0c36e-220">When does the policy become effective?</span></span>
- <span data-ttu-id="0c36e-221">Quando i criteri scadono?</span><span class="sxs-lookup"><span data-stu-id="0c36e-221">When does the policy expire?</span></span>
- <span data-ttu-id="0c36e-222">Qual è la regola dei criteri?</span><span class="sxs-lookup"><span data-stu-id="0c36e-222">What is the policy rule?</span></span>
- <span data-ttu-id="0c36e-223">Qual è il risultato della regola dei criteri?</span><span class="sxs-lookup"><span data-stu-id="0c36e-223">What is the outcome of the policy rule?</span></span>
