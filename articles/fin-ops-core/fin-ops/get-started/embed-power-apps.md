---
title: Incorporare app canvas da Power Apps
description: In questo argomento viene spiegato come incorporare app canvas da Microsoft Power Apps nel client per aumentare la funzionalità del prodotto.
author: jasongre
manager: AnnBe
ms.date: 11/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: fbdd4dd1bb0b850319b12e55b0e68d6fdc516ad6
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798379"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Incorporare app canvas da Power Apps

[!include [banner](../includes/banner.md)]

Microsoft Power Apps è un servizio che consente agli sviluppatori che agli utenti non tecnici di creare app aziendali personalizzate per dispositivi mobili, tablet e il Web senza dover scrivere codice. Le app Finance and Operations supportano l'integrazione con Power Apps. Le app canvas sviluppate da te, dall'organizzazione o dall'ecosistema più ampio possono essere incorporate nelle app Finance and Operations per aumentare la funzionalità del prodotto. Ad esempio, è possibile creare un'app canvas da Power Apps che completi l'app Finance and Operations con informazioni recuperate da un altro sistema.

Per ulteriori informazioni sull'integrazione di Power Apps, guardare il breve video [Come integrare Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Aggiunta di un'app canvas da Power Apps a una pagina

### <a name="overview"></a>Panoramica

Prima di incorporare un'app canvas da Power Apps nel client, è necessario dapprima trovare o creare un'app con gli oggetti visivi e/o le funzionalità desiderati. Questo argomento non include una descrizione dettagliata del processo per la creazione di app. Se non conosci Power Apps, vedi la [documentazione di Power Apps](https://docs.microsoft.com/powerapps/).

Esistono due modi per accedere a un'app canvas specifica su una pagina quando sei pronto per incorporare l'app. Puoi scegliere quale approccio si adatta meglio al tuo scenario. Il primo approccio utilizza il pulsante **Power Apps** aggiunto al riquadro azioni standard. Le app che aggiungi utilizzando questo approccio vengono visualizzate come elementi nel pulsante Menu di **Power Apps**. Quando selezioni una di queste voci di menu, viene visualizzato un riquadro laterale contenente l'app incorporata. In alternativa, puoi incorporare un'app direttamente in una pagina come nuova scheda, Scheda dettaglio o sezione in un'area di lavoro.

Durante la configurazione dell'app canvas incorporata, è possibile selezionare un singolo campo che si desidera inviare come contesto all'app. Questo passaggio consente all'app di essere reattiva in base ai dati correntemente visualizzati.

> [!NOTE]
> Al momento non puoi utilizzare questo meccanismo per incorporare app modellate.  

### <a name="details"></a>Dettagli

La procedura seguente mostra come incorporare un'app canvas da Power Apps nel client Web.

1. Passa alla pagina in cui vuoi incorporare l'app canvas. Sarà la stessa pagina contenente tutti i dati che devono essere passati all'app come input.
2. Aprire il riquadro **Aggiungi un'app da Power Apps**:

    - Fare clic su **Opzioni**, quindi selezionare **Personalizza questa pagina**. Sotto il menu **Inserisci**, scegliere **Power Apps**. Infine, selezionare la regione in cui si desidera aggiungere l'app. Se si desidera incorporare l'app sotto il pulsante di menu Power Apps, scegliere il riquadro azioni. Se si desidera incorporare l'app direttamente nella pagina, scegliere la scheda, la Scheda dettaglio, il pannello o la sezione (se in un'area di lavoro) appropriata.
    - Se si accederà all'app utilizzando il pulsante di menu Power Apps, si può scegliere di fare clic sul pulsante di menu **Power Apps** nel riquadro azioni standard e quindi selezionare **Aggiungi un'app**.

3. Configurare l'app incorporata:

    - Il campo **Nome** indica il testo visualizzato per il pulsante o la scheda che conterrà l'app incorporata. È spesso possibile che si intenda ripetere il nome dell'app in questo campo.
    - Il campo **ID app** indica l'identificatore univoco globale (GUID) per l'app canvas che desideri incorporare. Per ripristinare questo valore, trovare l'app in [make.powerapps.com](https://make.powerapps.com) e quindi individua il campo **ID app** sotto **Dettagli**.
    - Per **Contesto di input per l'app**, si può scegliere di selezionare il campo che contiene i dati da passare all'app come input. Vedere la sezione [Creazione di un'app che sfrutta i dati inviati dalle app Finance and Operations](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) più avanti in questo argomento per dettagli su come l'app può accedere ai dati inviati dalle app Finance and Operations.
    - Scegliere la **Dimensione dell'applicazione** che corrisponde al tipo di app che si intende incorporare. Selezionare **Ridotte** per le app create per dispositivi mobili e **Ampie** per le app create per tablet. Ciò garantisce l'assegnazione di una quantità di spazio sufficiente per l'app incorporata.
    - La Scheda dettaglio **Persone giuridiche** consente di scegliere le persone giuridiche per le quali l'app è disponibile. Il valore predefinito rende l'app accessibile a tutte le persone giuridiche. Questa opzione è disponibile solo quando la funzionalità [Visualizzazioni salvate](saved-views.md) è disabilitata. 

4. Dopo avere confermato la correttezza della configurazione, fare clic su **Inserisci** per incorporare la Power App nella pagina. Verrà richiesto di aggiornare il browser per visualizzare l'app incorporata.

## <a name="sharing-an-embedded-app"></a>Condivisione di un'app incorporata

Dopo avere incorporato un'app in un pagina e averne verificato il corretto funzionamento con il contesto di dati, è possibile che si desideri condividerla con altri utenti del sistema. Per condividere un'app canvas incorporata, segui questi passaggi.

1. [Condividi l'app canvas](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) con gli utenti appropriati, in modo che possano accedere all'app in Power Apps. 

2. Assicurati che gli utenti di destinazione abbiano le personalizzazioni appropriate, in modo che l'app incorporata venga visualizzata quando quegli utenti visualizzano la pagina. Puoi utilizzare uno dei seguenti approcci:

    - Consigliato: utilizza la funzionalità [Visualizzazioni salvate](saved-views.md) per creare e pubblicare una visualizzazione che includa l'app incorporata. Questo approccio garantisce che tutti gli utenti che dispongono dei ruoli di sicurezza individuati dalla visualizzazione pubblicata vedranno l'app tra le app Finance and Operations. 
    - Se non hai attivato la funzione Visualizzazioni salvate, puoi fare in modo che l'amministratore di sistema invii una personalizzazione che includa l'app incorporata a tutti gli utenti o a un sottoinsieme di utenti. In alternativa, puoi esportare le personalizzazioni della tua pagina e inviarle a uno o più utenti. Ciascuno di questi utenti può quindi importare le personalizzazioni. La barra degli strumenti di personalizzazione consente di esportare e importare le personalizzazioni. 
    
> [!NOTE]
> Se l'app canvas è stata condivisa con utenti esterni, tali utenti non possono utilizzare l'app incorporata all'interno delle app Finance and Operations. Tuttavia, possono accedere all'app direttamente all'interno di Power Apps. Gli utenti esterni includono guest e utenti che non appartengono alla directory di Microsoft 365 Azure in cui l'app Finance and Operations viene distribuita.

Per ulteriori informazioni sulle funzionalità di personalizzazione nel prodotto e su come utilizzarle, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Creazione di un'app canvas che utilizza i dati inviati dalle app Finance and Operations

Quando crei un'app canvas che verrà incorporata in un'app Finance and Operations, una parte importante del processo consiste nell'utilizzare i dati di input dall'app Finance and Operations. Nell'esperienza di sviluppo di Power Apps, è possibile accedere ai dati di input passati da un'app Finance and Operations utilizzando la variabile **Param ("EntityId")**.

Ad esempio, nella funzione OnStart dell'app, è possibile impostare i dati di input dalle app Finance and Operations su una variabile come la seguente:

```powerapps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-a-canvas-app"></a>Visualizzazione di un'app canvas

Per visualizzare un'app canvas in una pagina nelle app Finance and Operations, è sufficiente accedere a una pagina che include un'app incorporata. Ricorda che è possibile accedere alle app utilizzando il pulsante **Power Apps** nel riquadro azioni standard. In alternativa, possono apparire direttamente in una pagina come nuova scheda, Scheda dettaglio o sezione in un'area di lavoro. Quando gli utenti tentano per la prima volta di caricare un'app in una pagina, verrà richiesto di accedere. Questo passaggio garantisce che gli utenti dispongano delle autorizzazioni appropriate per utilizzare l'app.

## <a name="editing-an-embedded-app"></a>Modifica di un'app incorporata

Dopo che un'app è stata incorporata in una pagina, potrebbe essere necessario apportare alcune modifiche alla configurazione dell'app. Ad esempio, si desidera modificare l'etichetta associata all'app incorporata oppure è stata creata una nuova versione di un'app ed è necessario aggiornare l'ID App per puntare all'app più recente.

Per modificare la configurazione di un'app incorporata, seguire questi passaggi:

1. Passare al riquadro **Modifica l'app**.

    - Se si accede all'app incorporata tramite il pulsante di menu Power Apps, fare clic con il pulsante destro del mouse sul pulsante di menu Power Apps e selezionare **Personalizza**. Selezionare l'app che si desidera configurare dal menu a discesa **Seleziona un'app**.
    - Se l'app incorporata viene visualizzata direttamente nella pagina, selezionare **Opzioni**, quindi selezionare **Personalizza questa pagina**. Mediante lo strumento **Seleziona**, fare clic sull'app incorporata.

2. Apportare le modifiche necessarie alla configurazione dell'app, quindi fare clic su **Salva**.

## <a name="removing-an-app"></a>Rimozione di un'app

Dopo che un'app è stata incorporata in una pagina, esistono due modi per rimuoverla se necessario:

- Passare al riquadro **Modifica un'app** attenendosi alle istruzioni indicate nella precedente sezione [Modifica di un'app incorporata](#editing-an-embedded-app) in questo argomento. Verificare che il riquadro visualizzi le informazioni per l'app incorporata che si desidera rimuovere, quindi fare clic sul pulsante **Elimina**.
- Poiché l'app incorporata viene salvata come dati di personalizzazione, la cancellazione della personalizzazione della pagina determinerà anche la rimozione di tutte le app incorporate nella pagina. Tenere presente che la cancellazione della personalizzazione della pagina è permanente e non può essere annullata. Per rimuovere le personalizzazioni in una pagina, selezionare **Opzioni** e fare clic su **Personalizza questa pagina**, infine fare clic sul pulsante **Cancella**. Dopo avere aggiornato la pagina del browser, tutte le precedenti personalizzazioni della pagina saranno rimosse. Per ulteriori informazioni su come ottimizzare le pagine utilizzando la personalizzazione, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

## <a name="appendix"></a>Appendice

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[Sviluppatore] Specifica dove può essere incorporata un'app

Per impostazione predefinita, gli utenti possono incorporare app in qualsiasi pagina, sotto il pulsante di menu Power Apps o direttamente come scheda, Scheda dettaglio, pannello o come nuova sezione in un'area di lavoro. Tuttavia, se necessario, gli sviluppatori possono anche configurare questa funzionalità per consentire solo l'incorporamento delle app in determinate pagine tramite l'implementazione dei seguenti metodi:

- **isPowerAppPersonalizationEnabled** – Se questo metodo restituisce false per una pagina specifica, il pulsante del menu Power Apps non viene visualizzato e gli utenti non possono incorporare app nella pagina, neppure come scheda.
- **isPowerAppTabPersonalizationEnabled** – Se questo metodo restituisce false per una pagina specifica, gli utenti non possono incorporare app direttamente nella pagina come scheda, Scheda dettaglio o sezione panoramica. Gli utenti saranno ancora in grado di incorporare app tramite il pulsante di menu Power Apps se l'incorporazione è consentita nella pagina.

Nel seguente esempio viene illustrata una nuova classe con i due metodi necessari per configurare l'area in cui è possibile incorporare app.

```powerapps
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]