---
title: Creare regole per il consulente dell'ottimizzazione
description: In questo argomento viene descritto come aggiungere nuove regole al consulente dell'ottimizzazione.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: e14949b871534868c42d2b26a116e10ff9f05179
ms.sourcegitcommit: 8ff2413b6cb504d2b36fce2bb50441b2e690330e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "3081998"
---
# <a name="create-rules-for-optimization-advisor"></a><span data-ttu-id="87577-103">Creare regole per il consulente dell'ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="87577-103">Create rules for Optimization advisor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87577-104">In questo argomento viene spiegato come creare nuove regole per il **consulente dell'ottimizzazione**.</span><span class="sxs-lookup"><span data-stu-id="87577-104">This topic explains how to create new rules for **Optimization advisor**.</span></span> <span data-ttu-id="87577-105">Ad esempio, è possibile creare una nuova regola che identifica quali casi di richieste di offerta (RdO) hanno un titolo vuoto.</span><span class="sxs-lookup"><span data-stu-id="87577-105">For example, you can create a new rule that identifies which Request for Quotations (RFQ) cases have an empty title.</span></span> <span data-ttu-id="87577-106">L'uso di titoli nei casi li rende facilmente identificabili e ricercabili.</span><span class="sxs-lookup"><span data-stu-id="87577-106">Using titles on cases makes them easily identifiable and searchable.</span></span> <span data-ttu-id="87577-107">Anche se abbastanza semplice, questo esempio mostra i risultatiti che è possibile ottenere con le regole di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="87577-107">While quite simple, this example shows what can be achieved with optimization rules.</span></span> 

<span data-ttu-id="87577-108">Una *regola* è un controllo sui dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87577-108">A *rule* is a check on application data.</span></span> <span data-ttu-id="87577-109">Se la condizione che la regola valuta è soddisfatta, vengono create opportunità per ottimizzare i processi o migliorare i dati.</span><span class="sxs-lookup"><span data-stu-id="87577-109">If the condition that the rule evaluates is met, opportunities to optimize processes or improve data are created.</span></span> <span data-ttu-id="87577-110">È possibile agire sulle opportunità e, facoltativamente, misurare l'impatto delle azioni.</span><span class="sxs-lookup"><span data-stu-id="87577-110">The opportunities can be acted upon and, optionally, the impact of the actions can be measured.</span></span> 

<span data-ttu-id="87577-111">Per creare una nuova regola per il **Consulente dell'ottimizzazione**, aggiungere una nuova classe che estende la classe astratta **SelfHealingRule**, implementa l'interfaccia **IDiagnosticsRule** e viene decorata con l'attributo **DiagnosticRule**.</span><span class="sxs-lookup"><span data-stu-id="87577-111">To create a new rule for the **Optimization advisor**, add a new class that extends the **SelfHealingRule** abstract class, implements the **IDiagnosticsRule** interface, and is decorated by the **DiagnosticRule** attribute.</span></span> <span data-ttu-id="87577-112">La classe deve avere anche un metodo decorato con l'attributo **DiagnosticsRuleSubscription**.</span><span class="sxs-lookup"><span data-stu-id="87577-112">The class must also have a method decorated with the **DiagnosticsRuleSubscription** attribute.</span></span> <span data-ttu-id="87577-113">Per convenzione, questo viene effettuato sul metodo **opportunityTitle**, che verrà descritto in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="87577-113">By convention, that is done on the **opportunityTitle** method, which will be discussed later.</span></span> <span data-ttu-id="87577-114">Questa nuova classe può essere aggiunta a un modello personalizzato con una dipendenza dal modello **SelfHealingRules**.</span><span class="sxs-lookup"><span data-stu-id="87577-114">This new class can be added to a custom model with a dependency on the **SelfHealingRules** model.</span></span> <span data-ttu-id="87577-115">Nell'esempio seguente, la regola implementata è denominata **RFQTitleSelfHealingRule**.</span><span class="sxs-lookup"><span data-stu-id="87577-115">In the following example, the rule being implemented is called **RFQTitleSelfHealingRule**.</span></span>

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

<span data-ttu-id="87577-116">La classe astratta **SelfHealingRule** include metodi astratti che devono essere implementati nelle classi che ereditano.</span><span class="sxs-lookup"><span data-stu-id="87577-116">The **SelfHealingRule** abstract class has abstract methods that must be implemented in inheriting classes.</span></span> <span data-ttu-id="87577-117">Il centro è il metodo **evaluate**, che restituisce un elenco delle opportunità identificate dalla regola.</span><span class="sxs-lookup"><span data-stu-id="87577-117">The core is the **evaluate** method, which returns a list of the opportunities identified by the rule.</span></span> <span data-ttu-id="87577-118">Le opportunità possono essere per persona giuridica o possono essere applicate all'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="87577-118">Opportunities can be per legal entity or can apply to the whole system.</span></span>

```xpp
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

<span data-ttu-id="87577-119">Il metodo mostrato sopra esegue il ciclo sulle società e seleziona i casi di RdO con titoli vuoti nel metodo **findRFQCasesWithEmptyTitle**.</span><span class="sxs-lookup"><span data-stu-id="87577-119">The method shown above loops over companies and selects RFQ cases with empty titles in the **findRFQCasesWithEmptyTitle** method.</span></span> <span data-ttu-id="87577-120">Se viene rilevato almeno un caso, viene creata un'opportunità specifica della società con il metodo **getOpportunityForCompany**.</span><span class="sxs-lookup"><span data-stu-id="87577-120">If at least one such case is found, then a company-specific opportunity is created with the **getOpportunityForCompany** method.</span></span> <span data-ttu-id="87577-121">Si noti che il campo **Dati** nella tabella **SelfHealingOpportunity** è di tipo **Container** e può quindi contenere qualsiasi dato pertinente alla logica specifica di questa regola.</span><span class="sxs-lookup"><span data-stu-id="87577-121">Notice that the field **Data** in the **SelfHealingOpportunity** table is of type **Container**, and can therefore contain any data relevant to the logic specific to this rule.</span></span> <span data-ttu-id="87577-122">Impostazione di **OpportunityDate** con il timbro data/ora corrente registra l'ora dell'ultima valutazione dell'opportunità.</span><span class="sxs-lookup"><span data-stu-id="87577-122">Setting **OpportunityDate** with the current timestamp registers the time of the latest evaluation of the opportunity.</span></span>  

<span data-ttu-id="87577-123">Le opportunità possono inoltre essere interaziendali.</span><span class="sxs-lookup"><span data-stu-id="87577-123">Opportunities can also be cross-company.</span></span> <span data-ttu-id="87577-124">In questo caso, il ciclo sulle società non è necessario e l'opportunità deve essere creata con il metodo **getOpportunityAcrossCompanies**.</span><span class="sxs-lookup"><span data-stu-id="87577-124">In this case, the loop over companies is not necessary and the opportunity must be created with the **getOpportunityAcrossCompanies** method.</span></span> 

<span data-ttu-id="87577-125">Il seguente codice mostra il metodo **findRFQCasesWithEmptyTitle**, che restituisce gli ID dei casi RdO con titoli vuoti.</span><span class="sxs-lookup"><span data-stu-id="87577-125">The following code shows the **findRFQCasesWithEmptyTitle** method, which returns the IDs of the RFQ cases that have empty titles.</span></span>

```xpp
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

<span data-ttu-id="87577-126">I due nuovi metodi che devono essere implementati sono **opportunityTitle** e **opportunityDetails**.</span><span class="sxs-lookup"><span data-stu-id="87577-126">Two more methods that must be implemented are **opportunityTitle** and **opportunityDetails**.</span></span> <span data-ttu-id="87577-127">Il primo restituisce un titolo breve per l'opportunità, il secondo restituisce una descrizione dettagliata dell'opportunità, che può anche includere dati.</span><span class="sxs-lookup"><span data-stu-id="87577-127">The former returns a short title for the opportunity, the latter returns a detailed description of the opportunity, which can also include data.</span></span>

<span data-ttu-id="87577-128">Il titolo restituito per **opportunityTitle** sarà disponibile nella colonna **Opportunità di ottimizzazione** nell'area di lavoro **Consulente dell'ottimizzazione**.</span><span class="sxs-lookup"><span data-stu-id="87577-128">The title returned by **opportunityTitle** appears under the **Optimization opportunity** column in the **Optimization advisor** workspace.</span></span> <span data-ttu-id="87577-129">Viene inoltre visualizzato come intestazione del riquadro laterale che mostra ulteriori informazioni sull'opportunità.</span><span class="sxs-lookup"><span data-stu-id="87577-129">It also appears as the header of the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="87577-130">Per convenzione, questo metodo è decorato con l' attributo **DiagnosticRuleSubscription**, che accetta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="87577-130">By convention, this method is decorated with the **DiagnosticRuleSubscription** attribute, which takes the following arguments:</span></span> 

* <span data-ttu-id="87577-131">**Area diagnostica** - Un valore di enumerazione di tipo **DiagnosticArea** che descrive l'area dell'applicazione a cui appartiene la regola, ad esempio **DiagnosticArea::SCM**.</span><span class="sxs-lookup"><span data-stu-id="87577-131">**Diagnostic area** – An enum of type **DiagnosticArea** that describes what area of the application the rule belongs to, such as **DiagnosticArea::SCM**.</span></span> 

* <span data-ttu-id="87577-132">**Nome della regola** - Una stringa con il nome della regola.</span><span class="sxs-lookup"><span data-stu-id="87577-132">**Rule name** – A string with the rule name.</span></span> <span data-ttu-id="87577-133">Questo valore verrà visualizzato nella colonna **Nome regola** del modulo **Regola di convalida diagnostica** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="87577-133">This will appear under the **Rule name** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

* <span data-ttu-id="87577-134">**Frequenza di esecuzione** - Un valore di enumerazione di tipo **DiagnosticRunFrequency** che descrive la frequenza con cui deve essere eseguita la regola, ad esempio **DiagnosticRunFrequency::Daily**.</span><span class="sxs-lookup"><span data-stu-id="87577-134">**Run frequency** – An enum of type **DiagnosticRunFrequency** that describes how often the rule should be run, such as **DiagnosticRunFrequency::Daily**.</span></span> 

* <span data-ttu-id="87577-135">**Descrizione della regola** - Una stringa con una descrizione più dettagliata della regola.</span><span class="sxs-lookup"><span data-stu-id="87577-135">**Rule description** – A string with a more detailed description of the rule.</span></span> <span data-ttu-id="87577-136">Questo valore verrà visualizzato nella colonna **Descrizione regola** del modulo **Regola di convalida diagnostica** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="87577-136">This will appear under the **Rule description** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

> [!NOTE]
> <span data-ttu-id="87577-137">L'attributo **DiagnosticRuleSubscription** è necessario per il funzionamento della regola.</span><span class="sxs-lookup"><span data-stu-id="87577-137">The **DiagnosticRuleSubscription** attribute is required for the rule to work.</span></span> <span data-ttu-id="87577-138">In genere, viene utilizzato in **opportunityTitle**, ma può decorare qualsiasi metodo della classe.</span><span class="sxs-lookup"><span data-stu-id="87577-138">Typically, it is used on **opportunityTitle**, but it can decorate any method of the class.</span></span>

<span data-ttu-id="87577-139">Di seguito è riportato un esempio di implementazione:</span><span class="sxs-lookup"><span data-stu-id="87577-139">The following is an example implementation.</span></span> <span data-ttu-id="87577-140">Le stringhe non elaborate vengono utilizzate per semplicità, ma una corretta implementazione richiede etichette.</span><span class="sxs-lookup"><span data-stu-id="87577-140">Raw strings are used for simplicity, but a correct implementation requires labels.</span></span> 

```xpp
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

<span data-ttu-id="87577-141">La descrizione restituita da **opportunityDetails** viene visualizzata nel riquadro laterale contenente ulteriori informazioni sull'opportunità.</span><span class="sxs-lookup"><span data-stu-id="87577-141">The description returned by **opportunityDetails** appears on the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="87577-142">Questo richiede l'argomento **SelfHealingOpportunity**, ovvero il campo **Dati** che può essere utilizzato per fornire ulteriori dettagli sull'opportunità.</span><span class="sxs-lookup"><span data-stu-id="87577-142">This takes the **SelfHealingOpportunity** argument, which is **Data** field that can be used to provide more details about the opportunity.</span></span> <span data-ttu-id="87577-143">Nell'esempio, il metodo restituisce gli ID dei casi di RdO con un titolo vuoto.</span><span class="sxs-lookup"><span data-stu-id="87577-143">In the example, the method returns the IDs of the RFQ cases with an empty title.</span></span> 

```xpp
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

<span data-ttu-id="87577-144">I due restanti metodi astratti da implementare sono **provideHealingAction** e **securityMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="87577-144">The two remaining abstract methods to implement are **provideHealingAction** and **securityMenuItem**.</span></span> 

<span data-ttu-id="87577-145">**provideHealingAction** restituisce true se viene fornita un'azione di correzione, altrimenti restituisce false.</span><span class="sxs-lookup"><span data-stu-id="87577-145">**provideHealingAction** returns true if a healing action is provided, otherwise, it returns false.</span></span> <span data-ttu-id="87577-146">Se viene restituito true, il metodo **performAction** deve essere implementato o verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="87577-146">If true is returned, the method **performAction** must be implemented, or an error will be thrown.</span></span> <span data-ttu-id="87577-147">Il metodo **performAction** accetta un argomento **SelfHealingOpportunity**, in cui i dati possono essere utilizzati per l'azione.</span><span class="sxs-lookup"><span data-stu-id="87577-147">The **performAction** method takes a **SelfHealingOpportunity** argument, in which the data can be used for the action.</span></span> <span data-ttu-id="87577-148">In questo esempio, l'azione apre **PurchRFQCaseTableListPage** per la correzione manuale.</span><span class="sxs-lookup"><span data-stu-id="87577-148">In the example, the action opens the **PurchRFQCaseTableListPage**, for manual correction.</span></span> 

```xpp
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

<span data-ttu-id="87577-149">A seconda delle specifiche della regola, potrebbe essere possibile intraprendere azioni automatiche utilizzando i dati dell'opportunità.</span><span class="sxs-lookup"><span data-stu-id="87577-149">Depending on the specifics of the rule, it might be possible to take an automatic action using the opportunity data.</span></span> <span data-ttu-id="87577-150">In questo esempio, il sistema può generare automaticamente i titoli dei casi RdO.</span><span class="sxs-lookup"><span data-stu-id="87577-150">In this example, the system could generate titles for RFQ cases automatically.</span></span> 

<span data-ttu-id="87577-151">**securityMenuItem** restituisce il nome di una voce del menu di azione in modo tale che la regola sia visibile solo agli utenti che possono accedere alla voce del menu azione.</span><span class="sxs-lookup"><span data-stu-id="87577-151">**securityMenuItem** returns the name of an action menu item such that the rule is only visible to users who can access the action menu item.</span></span> <span data-ttu-id="87577-152">La sicurezza potrebbe richiedere che regole e opportunità specifiche siano accessibili solo agli utenti autorizzati.</span><span class="sxs-lookup"><span data-stu-id="87577-152">Security might require that specific rules and opportunities are accessible only to authorized users.</span></span> <span data-ttu-id="87577-153">In questo esempio, solo gli utenti che hanno accesso a **PurchRFQCaseTitleAction** possono visualizzare l'opportunità.</span><span class="sxs-lookup"><span data-stu-id="87577-153">In the example, only users with access to **PurchRFQCaseTitleAction** can view the opportunity.</span></span> <span data-ttu-id="87577-154">Si noti che questa voce di menu azione è stata creata per questo esempio ed è stata aggiunta come punto di ingresso per il privilegio di sicurezza **PurchRFQCaseTableMaintain**.</span><span class="sxs-lookup"><span data-stu-id="87577-154">Notice that this action menu item was created for this example, and was added as an entry point for the **PurchRFQCaseTableMaintain** security privilege.</span></span> 

> [!NOTE]
> <span data-ttu-id="87577-155">La voce di menu deve essere una voce di menu azione per il corretto funzionamento di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="87577-155">The menu item must be an action menu item for security to work correctly.</span></span> <span data-ttu-id="87577-156">Altri tipi di voci di menu, ad esempio **Voci di menu Visualizza** non funzioneranno correttamente.</span><span class="sxs-lookup"><span data-stu-id="87577-156">Other menu item types, such as **Display menu items** will not work correctly.</span></span>

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

<span data-ttu-id="87577-157">Dopo aver compilato la regola, eseguire il seguente processo per visualizzarlo nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="87577-157">After the rule has compiled, execute the following job to have it display in the user interface (UI).</span></span>

```xpp
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

<span data-ttu-id="87577-158">La regola viene visualizzata nel modulo **Regola di convalida diagnostica**, disponibile in **Amministrazione sistema** > **Attività periodiche** > **Gestisci regola di convalida diagnostica**.</span><span class="sxs-lookup"><span data-stu-id="87577-158">The rule will display in the **Diagnostics validation rule** form, available from **System administration** > **Periodic tasks** > **Maintain diagnostics validation rule**.</span></span> <span data-ttu-id="87577-159">Per una valutazione, passare ad **Amministrazione sistema** > **Attività periodiche** > ,**Programma regola di convalida diagnostica** selezionare la frequenza della regola, ad esempio **Giornaliera**.</span><span class="sxs-lookup"><span data-stu-id="87577-159">To have it evaluated, go to **System administration** > **Periodic tasks** > **Schedule diagnostics validation rule**, select the frequency of the rule, such as **Daily**.</span></span> <span data-ttu-id="87577-160">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="87577-160">Click **OK**.</span></span> <span data-ttu-id="87577-161">Passare ad **Amministrazione sistema** > **Consulente dell'ottimizzazione** per visualizzare la nuova opportunità.</span><span class="sxs-lookup"><span data-stu-id="87577-161">Go to **System administration** > **Optimization advisor** to view the new opportunity.</span></span> 

<span data-ttu-id="87577-162">L'esempio seguente è un frammento di codice con lo scheletro di una regola che include tutti i metodi e gli attributi richiesti.</span><span class="sxs-lookup"><span data-stu-id="87577-162">The following example is a code snippet with the skeleton of a rule including all the required methods and attributes.</span></span> <span data-ttu-id="87577-163">Consente di iniziare la scrittura di nuove regole.</span><span class="sxs-lookup"><span data-stu-id="87577-163">It helps you get started with writing new rules.</span></span><span data-ttu-id="87577-164"> Le etichette e le voci di menu azione utilizzate nell'esempio sono utilizzate solo a scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="87577-164"> The labels and action menu items that are used in the example are only used for demonstration purpose.</span></span>

```xpp
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

<span data-ttu-id="87577-165">Per ulteriori informazioni, guardare il breve video su YouTube sul [Consulente ottimizzazione in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span><span class="sxs-lookup"><span data-stu-id="87577-165">For more information, watch the short YouTube video: [Optimization advisor in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span></span>
