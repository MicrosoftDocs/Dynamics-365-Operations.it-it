---
title: Creare regole per il consulente dell'ottimizzazione
description: In questo argomento viene descritto come aggiungere nuove regole al consulente dell'ottimizzazione.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: e64d4fc1a7425d38d728b11e503d3e7289312495
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---

# <a name="create-rules-for-optimization-advisor"></a>Creare regole per il consulente dell'ottimizzazione

[!include[banner](../includes/banner.md)]

In questo argomento viene spiegato come creare nuove regole per il **consulente dell'ottimizzazione**. Ad esempio, è possibile creare una nuova regola che identifica quali casi di richieste di offerta (RdO) hanno un titolo vuoto. L'uso di titoli nei casi li rende facilmente identificabili e ricercabili. Anche se abbastanza semplice, questo esempio mostra i risultatiti che è possibile ottenere con le regole di ottimizzazione. 

Una *regola* è un controllo sui dati dell'applicazione. Se la condizione che la regola valuta è soddisfatta, vengono create opportunità per ottimizzare i processi o migliorare i dati. È possibile agire sulle opportunità e, facoltativamente, misurare l'impatto delle azioni. 

Per creare una nuova regola per il **Consulente dell'ottimizzazione**, aggiungere una nuova classe che estende la classe astratta **SelfHealingRule**, implementa l'interfaccia **IDiagnosticsRule** e viene decorata con l'attributo **DiagnosticRule**. La classe deve avere anche un metodo decorato con l'attributo **DiagnosticsRuleSubscription**. Per convenzione, questo viene effettuato sul metodo **opportunityTitle**, che verrà descritto in un secondo momento. Questa nuova classe può essere aggiunta a un modello personalizzato con una dipendenza dal modello **SelfHealingRules**. Nell'esempio seguente, la regola implementata è denominata **RFQTitleSelfHealingRule**.

```
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

La classe astratta **SelfHealingRule** include metodi astratti che devono essere implementati nelle classi che ereditano. Il centro è il metodo **evaluate**, che restituisce un elenco delle opportunità identificate dalla regola. Le opportunità possono essere per persona giuridica o possono essere applicate all'intero sistema.

```
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

Il metodo mostrato sopra esegue il ciclo sulle società e seleziona i casi di RdO con titoli vuoti nel metodo **findRFQCasesWithEmptyTitle**. Se viene rilevato almeno un caso, viene creata un'opportunità specifica della società con il metodo **getOpportunityForCompany**. Si noti che il campo **Dati** nella tabella **SelfHealingOpportunity** è di tipo **Container** e può quindi contenere qualsiasi dato pertinente alla logica specifica di questa regola. Impostazione di **OpportunityDate** con il timbro data/ora corrente registra l'ora dell'ultima valutazione dell'opportunità.  

Le opportunità possono inoltre essere interaziendali. In questo caso, il ciclo sulle società non è necessario e l'opportunità deve essere creata con il metodo **getOpportunityAcrossCompanies**. 

Il seguente codice mostra il metodo **findRFQCasesWithEmptyTitle**, che restituisce gli ID dei casi RdO con titoli vuoti.

```
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

I due nuovi metodi che devono essere implementati sono **opportunityTitle** e **opportunityDetails**. Il primo restituisce un titolo breve per l'opportunità, il secondo restituisce una descrizione dettagliata dell'opportunità, che può anche includere dati.

Il titolo restituito per **opportunityTitle** sarà disponibile nella colonna **Opportunità di ottimizzazione** nell'area di lavoro **Consulente dell'ottimizzazione**. Viene inoltre visualizzato come intestazione del riquadro laterale che mostra ulteriori informazioni sull'opportunità. Per convenzione, questo metodo è decorato con l' attributo **DiagnosticRuleSubscription**, che accetta i seguenti argomenti: 

* **Area diagnostica** - Un valore di enumerazione di tipo **DiagnosticArea** che descrive l'area dell'applicazione a cui appartiene la regola, ad esempio **DiagnosticArea::SCM**. 

* **Nome della regola** - Una stringa con il nome della regola. Questo valore verrà visualizzato nella colonna **Nome regola** del modulo **Regola di convalida diagnostica** (**DiagnosticsValidationRuleMaintain**). 

* **Frequenza di esecuzione** - Un valore di enumerazione di tipo **DiagnosticRunFrequency** che descrive la frequenza con cui deve essere eseguita la regola, ad esempio **DiagnosticRunFrequency::Daily**. 

* **Descrizione della regola** - Una stringa con una descrizione più dettagliata della regola. Questo valore verrà visualizzato nella colonna **Descrizione regola** del modulo **Regola di convalida diagnostica** (**DiagnosticsValidationRuleMaintain**). 

> [!NOTE]
> L'attributo **DiagnosticRuleSubscription** è necessario per il funzionamento della regola. In genere, viene utilizzato in **opportunityTitle**, ma può decorare qualsiasi metodo della classe.

Di seguito è riportato un esempio di implementazione: Le stringhe non elaborate vengono utilizzate per semplicità, ma una corretta implementazione richiede etichette. 

```
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

La descrizione restituita da **opportunityDetails** viene visualizzata nel riquadro laterale contenente ulteriori informazioni sull'opportunità. Questo richiede l'argomento **SelfHealingOpportunity**, ovvero il campo **Dati** che può essere utilizzato per fornire ulteriori dettagli sull'opportunità. Nell'esempio, il metodo restituisce gli ID dei casi di RdO con un titolo vuoto. 

```
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

I due restanti metodi astratti da implementare sono **provideHealingAction** e **securityMenuItem**. 

**provideHealingAction** restituisce true se viene fornita un'azione di correzione, altrimenti restituisce false. Se viene restituito true, il metodo **performAction** deve essere implementato o verrà generato un errore. Il metodo **performAction** accetta un argomento **SelfHealingOpportunity**, in cui i dati possono essere utilizzati per l'azione. In questo esempio, l'azione apre **PurchRFQCaseTableListPage** per la correzione manuale. 

```
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

A seconda delle specifiche della regola, potrebbe essere possibile intraprendere azioni automatiche utilizzando i dati dell'opportunità. In questo esempio, il sistema può generare automaticamente i titoli dei casi RdO. 

**securityMenuItem** restituisce il nome di una voce del menu di azione in modo tale che la regola sia visibile solo agli utenti che possono accedere alla voce del menu azione. La sicurezza potrebbe richiedere che regole e opportunità specifiche siano accessibili solo agli utenti autorizzati. In questo esempio, solo gli utenti che hanno accesso a **PurchRFQCaseTitleAction** possono visualizzare l'opportunità. Si noti che questa voce di menu azione è stata creata per questo esempio ed è stata aggiunta come punto di ingresso per il privilegio di sicurezza **PurchRFQCaseTableMaintain**. 

> [!NOTE]
> La voce di menu deve essere una voce di menu azione per il corretto funzionamento di sicurezza. Altri tipi di voci di menu, ad esempio **Voci di menu Visualizza** non funzioneranno correttamente.

```
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

Dopo aver compilato la regola, eseguire il seguente processo per visualizzarlo nell'interfaccia utente.

```
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

La regola viene visualizzata nel modulo **Regola di convalida diagnostica**, disponibile in **Amministrazione sistema** > **Attività periodiche** > **Gestisci regola di convalida diagnostica**. Per una valutazione, passare ad **Amministrazione sistema** > **Attività periodiche** > ,**Programma regola di convalida diagnostica** selezionare la frequenza della regola, ad esempio **Giornaliera**. Fare clic su **OK**. Passare ad **Amministrazione sistema** > **Consulente dell'ottimizzazione** per visualizzare la nuova opportunità. 

L'esempio seguente è un frammento di codice con lo scheletro di una regola che include tutti i metodi e gli attributi richiesti. Consente di iniziare la scrittura di nuove regole. Le etichette e le voci di menu azione utilizzate nell'esempio sono utilizzate solo a scopo dimostrativo.

```
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

Per ulteriori informazioni, guardare un breve di YouTube:

> [!Video https://www.youtube.com/embed/MRsAzgFCUSQ]

