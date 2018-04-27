---
title: Incorporare PowerApps
description: "In questo argomento viene descritto come incorporare PowerApps nel client di Finance and Operations per aumentare la funzionalità del prodotto."
author: jasongre
manager: AnnBe
ms.date: 04/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 07224faabcf2b183d4c8da0ba4588c33ec140d03
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="embed-powerapps"></a>Incorporare PowerApps

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [banner](../includes/pre-release.md)]

Nell'aggiornamento 14 della piattaforma, Microsoft Dynamics 365 for Finance and Operations supporta l'integrazione con Microsoft PowerApps, un servizio rivolto a utenti non tecnici e sviluppatori che consente di creare app aziendali per dispositivi mobili, tablet e Web senza scrivere codice. Le PowerApps sviluppate dall'utente, l'organizzazione o l'ecosistema più ampio potranno quindi essere inclusi nel client Finance and Operations per aumentare la funzionalità del prodotto. Ad esempio, è possibile creare una PowerApp per completare Finance and Operations con informazioni recuperate da un altro sistema. 

Per ulteriori informazioni sull'integrazione di PowerApps, guardare il breve video su [Come integrare PowerApps in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=x3qyA1bH-NY).

> [!Video https://www.youtube.com/embed/x3qyA1bH-NY]

## <a name="adding-an-embedded-powerapp-to-a-page"></a>Aggiunta di una PowerApp incorporata in una pagina
### <a name="overview"></a>Panoramica
Prima di incorporare una PowerApp nel client Finance and Operations, è necessario trovare o creare una PowerApp con gli oggetti visivi e/o le funzionalità desiderati. Il processo dettagliato per la creazione di una PowerApp non viene descritto in questo argomento. L'argomento che [introduce le PowerApps](https://docs.microsoft.com/en-us/powerapps/getting-started) è un'ottima risorsa per acquisire familiarità con le PowerApps.

Quando si è pronti a incorporare una specifica PowerApp, è possibile scegliere tra uno dei due modi di accesso alla PowerApp in una pagina, a seconda di quale è più appropriato per lo scenario corrente. Il primo modo è tramite il pulsante PowerApps aggiunto al riquadro azioni standard. Le PowerApps aggiunte tramite questo meccanismo saranno visualizzate come voci di menu nel pulsante di menu PowerApps. Se una di queste voci di menu viene selezionata, aprirà un riquadro laterale contenente la PowerApp incorporata. In alternativa, è possibile scegliere di visualizzare una PowerApp direttamente in una pagina come nuova scheda, Scheda dettaglio o sezione in un'area di lavoro. 

Durante la configurazione della PowerApp incorporata in Finance and Operations, è possibile selezionare un singolo campo che si desidera inviare come input alla PowerApp. Ciò consente alla PowerApp di essere reattiva in base ai dati correntemente visualizzati in Finance and Operations.  

### <a name="details"></a>Dettagli
Le istruzioni seguenti mostrano come incorporare una PowerApp Web nel client Web di Finance and Operations.  

1. Passare alla pagina in cui si desidera incorporare la PowerApp. Sarà la stessa pagina contenente tutti i dati che devono essere passati alla PowerApp come input.  
2. Aprire il riquadro **Inserisci una PowerApp**:
   - Fare clic su **Opzioni**, quindi selezionare **Personalizza modulo**. Sotto il menu **Inserisci**, scegliere **PowerApp**. Infine, selezionare la regione in cui si desidera aggiungere la PowerApp. Se si desidera incorporare la PowerApp sotto il pulsante di menu PowerApps, scegliere il riquadro azioni. Se si desidera incorporare la PowerApp direttamente nella pagina, scegliere la scheda, la Scheda dettaglio, il pannello o la sezione (se in un'area di lavoro) appropriata.   
   - Se si accederà alla PowerApp utilizzando il pulsante di menu PowerApps, si può scegliere di fare clic sul pulsante di menu **PowerApps** nel riquadro delle azioni standard e quindi selezionare **Inserisci una PowerApp**.  
3. Configurare la PowerApp incorporata:
   - Il campo **Nome** indica il testo visualizzato per il pulsante o la scheda che conterrà la PowerApp incorporata. È spesso possibile che si intenda ripetere il nome della PowerApp in questo campo.  
   - **ID app** è il GUID per la PowerApp che si desidera incorporare. Per ripristinare questo valore, trovare la PowerApp in [web.powerapps.com](https://web.powerapps.com) e quindi individuare il campo **ID app** sotto **Dettagli**.  
   - Per **Dati di input per la PowerApp**, si può scegliere di selezionare il campo che contiene i dati da passare alla PowerApp come input. Vedere la sezione [Creazione di una PowerApp che sfrutta i dati inviati da Finance and Operations](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations) più avanti in questo argomento per dettagli su come la PowerApp può accedere ai dati inviati da Finance and Operations.  
   - Scegliere la **Dimensione dell'applicazione** che corrisponde al tipo di PowerApp che si intende incorporare. Selezionare **Ridotte** per le PowerApps create per dispositivi mobili e **Ampie** per le PowerApps creata per tablet. Ciò garantisce l'assegnazione di una quantità di spazio sufficiente per la PowerApp incorporata.
   - La Scheda dettaglio **Persone giuridiche** consente di scegliere le persone giuridiche per le quali la PowerApp è disponibile. Il valore predefinito comporta la visualizzazione della PowerApp in tutte le persone giuridiche.  
4. Dopo avere confermato la correttezza della configurazione, fare clic su **Inserisci** per incorporare la PowerApp nella pagina. Verrà richiesto di aggiornare il browser per visualizzare la PowerApp incorporata. 

## <a name="sharing-an-embedded-powerapp"></a>Condivisione di una PowerApp incorporata
Dopo avere incorporato una PowerApp in un pagina e averne verificato il corretto funzionamento con il contesto di dati, è possibile che si desideri condividere la PowerApp incorporata con altri utenti del sistema. Questo può essere realizzato in due modi diversi utilizzando le capacità di personalizzazione del prodotto:

- Lo scenario consigliato è attraverso l'amministratore di sistema, che può inviare una personalizzazione a tutti gli utenti o a un sottoinsieme di utenti. 

- In alternativa, è possibile esportare le personalizzazioni della pagina, inviarle a uno o più utenti e chiedere a ciascuno di questi utenti di importarle. L' opzione Gestisci sulla barra degli strumenti di personalizzazione consente di esportare e importare le personalizzazioni.

Per ulteriori informazioni sulle funzionalità di personalizzazione nel prodotto e su come utilizzarle, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

## <a name="building-a-powerapp-that-leverages-data-sent-from-finance-and-operations"></a>Creazione di una PowerApp che sfrutta i dati inviati da Finance and Operations
Una parte importante della creazione di una PowerApp che verrà incorporata in Finance and Operations sta utilizzando i dati di input di Finance and Operations. Nella PowerApp, è possibile accedere a tali dati di input utilizzando la variabile Param("EntityId").  

Ad esempio, nella funzione OnStart della PowerApp, è possibile impostare i dati di input da Finance and Operations su una variabile come la seguente:

If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, "")); 

## <a name="viewing-an-embedded-powerapp"></a>Visualizzazione di una PowerApp incorporata
Per visualizzare una PowerApp incorporata in una pagina di Finance and Operations, accedere a una pagina con una PowerApp incorporata. Da notare che alle PowerApps è possibile accedere tramite il pulsante PowerApps nel riquadro azioni standard, oppure che possono essere visualizzate direttamente nella pagina come nuova scheda, Scheda dettaglio, pannello o come nuova sezione in un'area di lavoro. Quando un utente tenta per la prima volta di caricare una PowerApp in una pagina, gli viene richiesto di accedere alle PowerApps per assicurarsi di disporre delle autorizzazioni necessarie per utilizzare la PowerApp.   

## <a name="editing-an-embedded-powerapp"></a>Modifica di una PowerApp incorporata
Dopo che una PowerApp è stata incorporata in una pagina, potrebbe essere necessario apportare alcune modifiche alla configurazione della PowerApp. Ad esempio, si desidera modificare l'etichetta associata alla PowerApp incorporata oppure è stata creata una nuova versione di una PowerApp ed è necessario aggiornare l'ID App per puntare alla PowerApp più recente. 

Per modificare la configurazione di una PowerApp incorporata, seguire questi passaggi:
1. Passare al riquadro **Modifica PowerApp**. 
   - Se si accede alla PowerApp incorporata tramite il pulsante di menu PowerApps, fare clic con il pulsante destro del mouse sul pulsante di menu PowerApps e selezionare **Personalizza**. Selezionare la PowerApp che si desidera configurare dal menu a discesa **Seleziona PowerApp**.  
   - Se la PowerApp incorporata viene visualizzata direttamente nella pagina, selezionare **Opzioni**, quindi selezionare **Personalizza modulo**. Mediante lo strumento **Seleziona**, fare clic sulla PowerApp incorporata.  
2. Apportare le modifiche necessarie alla configurazione delle PowerApps, quindi fare clic su **Salva**.  

## <a name="removing-an-embedded-powerapp"></a>Rimozione di una PowerApp incorporata
Dopo che una PowerApp è stata incorporata in una pagina, esistono due modi per rimuoverla se necessario: 

- Passare al riquadro **Modifica PowerApp** attenendosi alle istruzioni indicate nella precedente sezione [Modifica di una PowerApp incorporata](#editing-an-embedded-powerapp) in questo argomento. Verificare che il riquadro visualizzi le informazioni per la PowerApp incorporata che si desidera rimuovere, quindi fare clic sul pulsante **Elimina**. 

- Poiché una PowerApp incorporata viene salvata come dati di personalizzazione, la cancellazione della personalizzazione della pagina determinerà anche la rimozione di tutte le PowerApps incorporate nella pagina. Tenere presente che la cancellazione della personalizzazione della pagina è permanente e non può essere annullata. Per rimuovere le personalizzazioni in una pagina, selezionare **Opzioni** e fare clic su **Personalizza modulo**. Sotto il menu **Gestisci**, selezionare il pulsante **Cancella**. Dopo avere aggiornato la pagina del browser, tutte le precedenti personalizzazioni della pagina saranno rimosse. Per ulteriori informazioni su come ottimizzare le pagine utilizzando la personalizzazione, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).  

## <a name="appendix"></a>Appendice 
### <a name="developer-control-over-where-a-powerapp-can-be-embedded"></a>Controllo dello sviluppatore sulla posizione in cui può essere incorporata una PowerApp
Per impostazione predefinita, gli utenti possono incorporare PowerApps in qualsiasi pagina, sotto il pulsante di menu PowerApps o direttamente come scheda, Scheda dettaglio, pannello o come nuova sezione in un'area di lavoro. Tuttavia, se necessario, gli sviluppatori possono anche configurare questa funzionalità per consentire solo l'incorporamento delle PowerApps in determinate pagine tramite l'implementazione dei seguenti metodi: 

- **isPowerAppPersonalizationEnabled** - Se questo metodo restituisce false per una pagina specifica, il pulsante del menu PowerApps non viene visualizzato e gli utenti non possono incorporare PowerApps nella pagina, neppure come scheda. 

- **isPowerAppTabPersonalizationEnabled** - Se questo metodo restituisce false per una pagina specifica, gli utenti non possono incorporare PowerApps direttamente nella pagina come scheda, Scheda dettaglio o sezione panoramica. Gli utenti saranno ancora in grado di incorporare PowerApps tramite il pulsante di menu PowerApps se l'incorporazione è consentita nella pagina.  

Nel seguente esempio viene illustrata una nuova classe con i due metodi necessari per configurare l'area in cui è possibile incorporare PowerApps.  

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{

    public static boolean isPowerAppPresonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPresonalizationEnabled(pageName);
        return true;
    }

    public static boolean isPowerAppTabPresonalizationEnabled(str pageName)   
    {
        var result = next isPowerAppTabPresonalizationEnabled(pageName);
        return true;
    }
    ```

}


