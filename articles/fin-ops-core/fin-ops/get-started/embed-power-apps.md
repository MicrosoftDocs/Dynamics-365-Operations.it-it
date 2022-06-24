---
title: Incorporare app canvas da Power Apps
description: In questo articolo viene spiegato come incorporare app canvas da Microsoft Power Apps nel client per aumentare la funzionalità del prodotto.
author: jasongre
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: fb81aa058e749df346ee87bbe83427b20b234b72
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898400"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Incorporare app canvas da Power Apps

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Microsoft Power Apps è un servizio che consente agli sviluppatori che agli utenti non tecnici di creare app aziendali personalizzate per dispositivi mobili, tablet e il Web senza dover scrivere codice. Integrazione del supporto per le app per finanza e operazioni con Power Apps. Le app canvas sviluppate da te, dall'organizzazione o dall'ecosistema più ampio possono essere incorporate nelle app per finanza e operazioni per aumentare la funzionalità del prodotto. Ad esempio, è possibile creare un'app canvas da Power Apps che completi l'app per finanza e operazioni con informazioni recuperate da un altro sistema.

Per ulteriori informazioni sull'incorporamento di app canvas, guardare il breve video su [Come incorporare app canvas](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Aggiunta di un'app canvas da Power Apps a una pagina

Prima di incorporare un'app canvas da Power Apps nel client, è necessario dapprima trovare o creare un'app con gli oggetti visivi e/o le funzionalità desiderati. Questo articolo non include una descrizione dettagliata del processo per la creazione di app. Se non conosci Power Apps, vedi la [documentazione di Power Apps](/powerapps/).

Esistono tre modi per incorporare un'app canvas in un'app per finanza e operazioni. Puoi utilizzare l'approccio che meglio si adatta al tuo scenario. 

- Incorpora l'app canvas nel pulsante **Power Apps** nel riquadro Azioni standard di una pagina. Le app che aggiungi in questo modo vengono visualizzate come elementi nel pulsante del menu **Power Apps** e le app si aprono nei riquadri laterali. 
- Incorpora l'app canvas direttamente in una pagina esistente come nuova scheda (scheda pivot, Scheda dettaglio, pannello o sezione dell'area di lavoro).
- Crea una nuova esperienza a tutta pagina per l'app canvas dalla dashboard.

Durante la configurazione dell'app canvas incorporata, è possibile selezionare un singolo campo che si desidera inviare come contesto all'app. Questo passaggio consente all'app di essere reattiva in base ai dati correntemente visualizzati.

> [!NOTE]
> Non puoi utilizzare questo meccanismo per incorporare app basate su modello.

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>Incorporare un'app canvas in una pagina esistente

La procedura seguente mostra come incorporare un'app canvas in una pagina esistente da Power Apps.

1. Passa alla pagina in cui vuoi incorporare l'app canvas. Questa pagina conterrà tutti i dati che devono essere passati all'app come input.
2. Aprire il riquadro **Aggiungi un'app da Power Apps**:

    - Se l'app verrà incorporata direttamente nella pagina, seleziona **Opzioni** \> **Personalizza questa pagina** \> **Altro**, quindi segui uno di questi passaggi:

        - Se la funzionalità **App a tutta pagina** è attivata, seleziona **Aggiungi una pagina**, quindi seleziona l'area geografica in cui desideri aggiungere l'app. Per incorporare l'app nel pulsante del menu **Power Apps**, seleziona il riquadro Azioni. Per incorporare l'app direttamente nella pagina, seleziona la scheda, la Scheda dettaglio, il pannello o la sezione (se in un'area di lavoro) appropriata. Poi, nel riquadro **Aggiungi un'app**, seleziona **Power Apps**.
        - Se la funzionalità **App a tutta pagina** è disattivata, seleziona **Aggiungi un'app da Power Apps**, quindi seleziona l'area geografica in cui desideri aggiungere l'app. Per incorporare l'app nel pulsante del menu **Power Apps**, seleziona il riquadro Azioni. Per incorporare l'app direttamente nella pagina, seleziona la scheda, la Scheda dettaglio, il pannello o la sezione (se in un'area di lavoro) appropriata.

    - Se si accederà all'app utilizzando il pulsante di menu **Power Apps**, puoi selezionare il pulsante di menu **Power Apps** nel riquadro Azioni standard e quindi seleziona **Aggiungi un'app**.

3. Configura l'app incorporata. Per ulteriori informazioni, vedi la sezione [Configurazione di un'app canvas](#configuring-a-canvas-app) più avanti in questo articolo.
4. Dopo aver confermato che la configurazione è corretta, seleziona **Inserisci**.

    - Se la funzionalità **Visualizzazioni salvate** è disattivata, ti viene chiesto di aggiornare il browser per vedere l'app incorporata.
    - Se la funzionalità **Visualizzazioni salvate** è attivata, devi salvare la visualizzazione affinché la modifica venga mantenuta.

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>Incorporare un'app canvas come esperienza a tutta pagina dalla dashboard

Puoi incorporare un'app canvas dalla dashboard se l'app non è correlata a una pagina esistente o se vuoi solo utilizzare l'app come esperienza a tutta pagina all'interno dell'app per finanza e operazioni.

> [!NOTE]
> Per rendere disponibile questa funzionalità, è necessario attivare la funzionalità **App a tutta pagina** in Gestione funzionalità. 

1. Aprire il dashboard.
2. Seleziona e tieni premuta la pagina (o fai clic con il pulsante destro del mouse), seleziona **Personalizza** e quindi seleziona **Aggiungi una pagina**.
3. Nel riquadro **Aggiungi una pagina** seleziona **Power Apps**.
4. Configura l'app incorporata. Per ulteriori informazioni, vedi la sezione [Configurazione di un'app canvas](#configuring-a-canvas-app) più avanti in questo articolo.
5. Selezionare **Salva** per aggiungere l'app al dashboard come nuovo riquadro.
6. Seleziona il nuovo riquadro nella dashboard e conferma che l'app canvas viene visualizzata come previsto.

### <a name="configuring-a-canvas-app"></a>Configurazione di un'app canvas

Quando incorpori un'app canvas, devi impostare i seguenti parametri:

- **Nome**: immetti il testo da visualizzare per il pulsante o la scheda che conterrà l'app incorporata. È spesso possibile che si intenda ripetere il nome dell'app in questo campo.
- **ID app**: specifica l'identificatore univoco globale (GUID) per l'app canvas che desideri incorporare. Per ripristinare questo valore, trovare l'app in [make.powerapps.com](https://make.powerapps.com) e quindi individua il campo **ID app** sotto **Dettagli**.
- **Contesto di input per l'app**: puoi scegliere di selezionare il campo che contiene i dati da passare all'app come input. Per informazioni sul modo in cui l'app può accedere ai dati inviati dalle app per finanza e operazioni, vedi la sezione [Creazione di una Power App che sfrutta i dati inviati dalle app per finanza e operazioni](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) più avanti in questo articolo.

    A partire dalla versione 10.0.19, anche la persona giuridica corrente viene passata all'app canvas come contesto tramite il parametro URL **cmp**. Questo comportamento non avrà effetto sull'app canvas di destinazione finché l'app utilizza tali informazioni.

- **Dimensione dell'applicazione**: seleziona il tipo di app da incorporare. Seleziona **Ridotte** per le app create per dispositivi mobili o **Ampie** per le app create per tablet. Questo parametro garantisce l'assegnazione di spazio sufficiente per l'app incorporata.
- **Persone giuridiche**: puoi selezionare le persone giuridiche per le quali l'app dovrebbe essere disponibile. Per impostazione predefinita, l'app è disponibile per tutte le persone giuridiche. Questa opzione è disponibile solo quando si incorpora direttamente in una pagina esistente e la funzionalità **[Visualizzazioni salvate](saved-views.md)** è disattivata.

## <a name="sharing-an-embedded-app"></a>Condivisione di un'app incorporata

Dopo avere incorporato un'app in una pagina e averne verificato il corretto funzionamento, è possibile che si desideri condividerla con altri utenti del sistema. Per condividere un'app canvas incorporata, segui questi passaggi.

1. [Condividi l'app canvas in Power Apps](/powerapps/maker/canvas-apps/share-app) con gli utenti appropriati, in modo che possano accedere all'app direttamente in Power Apps.
2. Condividi le personalizzazioni associate all'app incorporata con gli utenti desiderati. Puoi utilizzare uno dei seguenti approcci:

    - **Pubblica la visualizzazione (consigliato):** se la funzionalità **[Visualizzazioni salvate](saved-views.md)** è attivata, l'approccio consigliato e preferito consiste nel creare una visualizzazione che includa l'app canvas incorporata e quindi pubblicare tale visualizzazione per gli utenti desiderati. Questo approccio garantisce che tutti gli utenti che dispongono dei ruoli di sicurezza individuati dalla visualizzazione pubblicata vedranno l'app canvas nella pagina.

        Puoi anche pubblicare un'app canvas che è stata incorporata come esperienza a tutta pagina dalla dashboard. Nel dashboard, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il riquadro associato all'app, seleziona **Personalizza** e quindi seleziona **Pubblica pagina**. Un'esperienza simile all'esperienza *Pubblicazione di visualizzazioni* viene mostrata e puoi selezionare i ruoli di sicurezza per cui pubblicare. Nell'aggiornamento 10.0.21 o successivo, se la funzionalità **Supporto migliorato delle persone giuridiche per le visualizzazioni salvate** è attivata, puoi anche pubblicare l'app per le persone giuridiche desiderate.

    - Se la funzionalità **Visualizzazioni salvate** è disattivata, l'amministratore di sistema può fornire una personalizzazione che includa l'app canvas per il set di utenti appropriato tramite la pagina **Personalizzazione**. In alternativa, puoi esportare le personalizzazioni della tua pagina e quindi inviarle a uno o più utenti. Ciascuno di questi utenti può quindi importare la personalizzazione. La barra degli strumenti di personalizzazione contiene dei pulsanti che consentono di esportare e importare le personalizzazioni.

> [!NOTE]
> Se l'app canvas è stata condivisa con utenti esterni, tali utenti non possono utilizzare l'app incorporata all'interno delle app per finanza e operazioni. Tuttavia, possono accedere all'app direttamente all'interno di Power Apps. Gli utenti esterni includono guest e utenti che non appartengono alla directory di Microsoft 365 Azure dove viene distribuita l'app per finanza e operazioni.

Per ulteriori informazioni sulle funzionalità di personalizzazione nel prodotto e su come utilizzarle, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Creazione di un'app canvas che utilizza i dati inviati dalle app per finanza e operazioni

Quando crei un'app canvas che verrà incorporata in un'app per finanza e operazioni, una parte importante del processo consiste nell'utilizzare i dati di input dall'app per finanza e operazioni. Nell'esperienza di sviluppo di Power Apps, è possibile accedere ai dati di input passati da un'app per finanza e operazioni utilizzando la variabile **Param ("EntityId")**. Inoltre, a partire dalla versione 10.0.19, anche la persona giuridica corrente verrà passata come contesto all'app canvas tramite la variabile **Param("cmp")**. 

Ad esempio, nella funzione OnStart dell'app, è possibile impostare i dati di input dalle app per finanza e operazioni su una variabile come la seguente:

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>Visualizzazione di un'app canvas

Per visualizzare un'app canvas in una pagina nelle app per finanza e operazioni, è sufficiente accedere a una pagina che include un'app incorporata. Ricorda che è possibile accedere alle app utilizzando il pulsante **Power Apps** nel riquadro azioni standard. In alternativa, possono apparire direttamente in una pagina come nuova scheda, Scheda dettaglio o sezione in un'area di lavoro. Quando gli utenti tentano per la prima volta di caricare un'app in una pagina, verrà richiesto di accedere. Questo passaggio garantisce che gli utenti dispongano delle autorizzazioni appropriate per utilizzare l'app.

## <a name="editing-an-embedded-app"></a>Modifica di un'app incorporata

Dopo che un'app è stata incorporata in una pagina, potrebbe essere necessario apportare alcune modifiche alla configurazione dell'app. Ad esempio, si desidera modificare l'etichetta associata all'app incorporata oppure è stata creata una nuova versione di un'app ed è necessario aggiornare l'ID App per puntare all'app più recente.

Per modificare la configurazione di un'app incorporata, seguire questi passaggi:

1. Passare al riquadro **Modifica l'app**.

    - Se si accede all'app incorporata tramite il pulsante di menu Power Apps, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il pulsante di menu Power Apps e seleziona **Personalizza**. Selezionare l'app che si desidera configurare dal menu a discesa **Seleziona un'app**.
    - Se l'app incorporata viene visualizzata direttamente nella pagina, selezionare **Opzioni**, quindi selezionare **Personalizza questa pagina**. Mediante lo strumento **Seleziona**, fare clic sull'app incorporata.
    - Se l'app incorporata è stata aggiunta dalla dashboard, apri la dashboard, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il riquadro associato all'app canvas, seleziona **Personalizza**, quindi seleziona **Modifica pagina**.

2. Apportare le modifiche necessarie alla configurazione dell'app, quindi fare clic su **Salva**.

## <a name="removing-an-app"></a>Rimozione di un'app

Dopo che un'app è stata incorporata in una pagina, esistono diversi modi per rimuoverla se necessario:

- Passa al riquadro **Modifica un'app** attenendoti alle istruzioni indicate nella precedente sezione [Modifica di un'app incorporata](#editing-an-embedded-app) in questo articolo. Verificare che il riquadro visualizzi le informazioni per l'app incorporata che si desidera rimuovere, quindi fare clic sul pulsante **Elimina**.
- Se l'app incorporata è stata aggiunta dalla dashboard, apri la dashboard, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il riquadro associato all'app canvas, seleziona **Personalizza**, quindi seleziona **Rimuovi pagina**. 
- Poiché l'app incorporata viene salvata come dati di personalizzazione, la cancellazione della personalizzazione della pagina determinerà anche la rimozione di tutte le app incorporate nella pagina. Tenere presente che la cancellazione della personalizzazione della pagina è permanente e non può essere annullata. Per rimuovere le personalizzazioni in una pagina, selezionare **Opzioni** e fare clic su **Personalizza questa pagina**, infine fare clic sul pulsante **Cancella**. Dopo avere aggiornato la pagina del browser, tutte le precedenti personalizzazioni della pagina saranno rimosse. Per ulteriori informazioni su come ottimizzare le pagine utilizzando la personalizzazione, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

## <a name="appendix"></a>Appendice

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[Sviluppatore] Modellazione di un'app canvas su un modulo

Sebbene questo articolo si concentri sull'incorporamento di app canvas tramite la personalizzazione, gli sviluppatori hanno anche la possibilità di aggiungere un'app canvas a un modulo utilizzando l'esperienza di sviluppo di Visual Studio. Per fare ciò, aggiungi semplicemente un PowerAppsHostControl al modulo. Le proprietà dei metadati disponibili nel controllo forniscono le stesse funzionalità dell'esperienza di personalizzazione.

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
