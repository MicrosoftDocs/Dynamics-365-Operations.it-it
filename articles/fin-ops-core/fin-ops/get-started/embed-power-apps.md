---
title: Incorporare Power Apps
description: In questo argomento viene descritto come incorporare Power Apps nel client per aumentare la funzionalità del prodotto.
author: jasongre
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 90422a34499dab7302ad7722cf84d40e1815991c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042944"
---
# <a name="embed-microsoft-power-apps"></a>Incorporare Microsoft Power Apps

[!include [banner](../includes/banner.md)]

Finance and Operations supporta l'integrazione con Microsoft Power Apps, un servizio rivolto a utenti non tecnici e sviluppatori che consente di creare app aziendali per dispositivi mobili, tablet e Web senza scrivere codice. Le app Power Apps sviluppate dall'utente, dall'organizzazione o dall'ecosistema più ampio potranno quindi essere incluse nelle app Finance and Operations per aumentare la funzionalità del prodotto. Ad esempio, è possibile creare un'app da Power Apps che completi l'app Finance and Operations con informazioni recuperate da un altro sistema.

Per ulteriori informazioni sull'integrazione di Power Apps, guardare il breve video [Come integrare Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-app-from-power-apps-to-a-page"></a>Aggiunta di un'app da Power Apps a una pagina

### <a name="overview"></a>Panoramica

Prima di incorporare un'app da Power Apps nel client, è necessario dapprima trovare o creare un'app con gli oggetti visivi e/o le funzionalità desiderati. Il processo dettagliato per la creazione di app non viene descritto in questo argomento. L'argomento che [introduce le Power Apps](https://docs.microsoft.com/powerapps/getting-started) è un'ottima risorsa per acquisire familiarità con le Power Apps.

Quando si è pronti a incorporare una specifica app, è possibile scegliere tra uno dei due modi di accesso all'app in una pagina, a seconda di quale è più appropriato per lo scenario corrente. Il primo modo è tramite il pulsante Power Apps aggiunto al riquadro azioni standard. Le app aggiunte tramite questo meccanismo saranno visualizzate come voci di menu nel pulsante di menu Power Apps. Se una di queste voci di menu viene selezionata, aprirà un riquadro laterale contenente l'app incorporata. In alternativa, è possibile scegliere di incorporare un'app direttamente in una pagina come nuova scheda, Scheda dettaglio o sezione in un'area di lavoro.

Durante la configurazione dell'app incorporata, è possibile selezionare un singolo campo che si desidera inviare come contesto all'app. Ciò consente all'app di essere reattiva in base ai dati correntemente visualizzati.

### <a name="details"></a>Dettagli

Le istruzioni seguenti mostrano come incorporare un'app da Power Apps nel client Web.

1. Passare alla pagina in cui si desidera incorporare l'app. Sarà la stessa pagina contenente tutti i dati che devono essere passati all'app come input.
2. Aprire il riquadro **Aggiungi un'app da Power Apps**:

    - Fare clic su **Opzioni**, quindi selezionare **Personalizza questa pagina**. Sotto il menu **Inserisci**, scegliere **Power Apps**. Infine, selezionare la regione in cui si desidera aggiungere l'app. Se si desidera incorporare l'app sotto il pulsante di menu Power Apps, scegliere il riquadro azioni. Se si desidera incorporare l'app direttamente nella pagina, scegliere la scheda, la Scheda dettaglio, il pannello o la sezione (se in un'area di lavoro) appropriata.
    - Se si accederà all'app utilizzando il pulsante di menu Power Apps, si può scegliere di fare clic sul pulsante di menu **Power Apps** nel riquadro azioni standard e quindi selezionare **Aggiungi un'app**.

3. Configurare l'app incorporata:

    - Il campo **Nome** indica il testo visualizzato per il pulsante o la scheda che conterrà l'app incorporata. È spesso possibile che si intenda ripetere il nome dell'app in questo campo.
    - **ID app** è il GUID per l'app che si desidera incorporare. Per ripristinare questo valore, trovare l'app in [web.powerapps.com](https://web.powerapps.com) e quindi individuare il campo **ID app** sotto **Dettagli**.
    - Per **Contesto di input per l'app**, si può scegliere di selezionare il campo che contiene i dati da passare all'app come input. Vedere la sezione [Creazione di un'app che sfrutta i dati inviati dalle app Finance and Operations](#building-an-app-that-leverages-data-sent-from-finance-and-operations-apps) più avanti in questo argomento per dettagli su come l'app può accedere ai dati inviati dalle app Finance and Operations.
    - Scegliere la **Dimensione dell'applicazione** che corrisponde al tipo di app che si intende incorporare. Selezionare **Ridotte** per le app create per dispositivi mobili e **Ampie** per le app create per tablet. Ciò garantisce l'assegnazione di una quantità di spazio sufficiente per l'app incorporata.
    - La Scheda dettaglio **Persone giuridiche** consente di scegliere le persone giuridiche per le quali l'app è disponibile. Il valore predefinito rende l'app accessibile a tutte le persone giuridiche. Questa opzione è disponibile solo quando la funzionalità [Visualizzazioni salvate](saved-views.md) è disabilitata. 

4. Dopo avere confermato la correttezza della configurazione, fare clic su **Inserisci** per incorporare la Power App nella pagina. Verrà richiesto di aggiornare il browser per visualizzare l'app incorporata.

## <a name="sharing-an-embedded-app"></a>Condivisione di un'app incorporata

Dopo avere incorporato un'app in un pagina e averne verificato il corretto funzionamento con il contesto di dati, è possibile che si desideri condividerla con altri utenti del sistema. Questo può essere realizzato in due modi diversi utilizzando le capacità di personalizzazione del prodotto:

- Lo scenario consigliato è attraverso l'amministratore di sistema, che può inviare una personalizzazione a tutti gli utenti o a un sottoinsieme di utenti.
- In alternativa, è possibile esportare le personalizzazioni della pagina, inviarle a uno o più utenti e chiedere a ciascuno di questi utenti di importarle. La barra degli strumenti di personalizzazione include azioni che consentono di esportare e importare le personalizzazioni.

Per ulteriori informazioni sulle funzionalità di personalizzazione nel prodotto e su come utilizzarle, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

## <a name="building-an-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Creazione di un'app che sfrutta i dati inviati dalle app Finance and Operations

Una parte importante della creazione di un'app da Power Apps che verrà incorporata in un'app Finance and Operations sta utilizzando i dati di input di quell'applicazione. Nell'esperienza di sviluppo di Power Apps, è possibile accedere ai dati di input passati da un'app Finance and Operations utilizzando la variabile Param ("EntityId").

Ad esempio, nella funzione OnStart dell'app, è possibile impostare i dati di input dalle app Finance and Operations su una variabile come la seguente:

```powerapps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-app"></a>Visualizzazione di un'app

Per visualizzare un'app incorporata in una pagina nelle app Finance and Operations, accedere a una pagina con un'app incorporata. Da notare che alle app è possibile accedere tramite il pulsante Power Apps nel riquadro azioni standard, oppure che possono essere visualizzate direttamente nella pagina come nuova scheda, Scheda dettaglio, pannello o come nuova sezione in un'area di lavoro. Quando un utente tenta per la prima volta di caricare un'app in una pagina, gli viene richiesto di eseguire l'accesso per assicurarsi di disporre delle autorizzazioni necessarie per utilizzare l'app.

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

### <a name="developer-control-over-where-an-app-can-be-embedded"></a>Controllo dello sviluppatore sulla posizione in cui può essere incorporata un'app

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
