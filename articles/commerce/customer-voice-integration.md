---
title: Integrare Customer Voice nelle pagine del sito di e-commerce
description: Questo articolo descrive come integrare Microsoft Dynamics 365 Customer Voice nelle pagine di un sito di e-commerce Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: c8c67ecf4950c92fc91c8d119e06e5e8afff0ddf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850332"
---
# <a name="integrate-customer-voice-into-e-commerce-site-pages"></a>Integrare Customer Voice nelle pagine del sito di e-commerce

[!include [banner](../includes/banner.md)]

Questo articolo descrive come integrare Microsoft Dynamics 365 Customer Voice nelle pagine di un sito di e-commerce Dynamics 365 Commerce.

Puoi integrare [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) nel tuo sito di e-commerce per raccogliere, analizzare e tenere traccia dei feedback dei clienti in tempo reale. Per iniziare l'integrazione, devi creare un account e selezionare un modello di progetto Customer Voice per il tipo di feedback che desideri raccogliere.

## <a name="integrate-the-customer-voice-service"></a>Integrare il servizio Customer Voice

Per creare un account Customer Voice, vai su [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) e segui le istruzioni.

Dopo aver creato un account Customer Voice e aver effettuato l'accesso, il passaggio successivo consiste nel selezionare un modello di progetto per il tipo di feedback che desideri raccogliere.

Per selezionare un modello di progetto di Customer Voice, attieniti alla seguente procedura.

1. Vai alla [Pagina del modello di progetto di Customer Voice](https://customervoice.microsoft.com/Pages/ProjectPage.aspx).
1. Selezionare **Inizia subito**.
1. Seleziona il modello di progetto per il tipo di feedback che desideri raccogliere, quindi seleziona **Avanti**.
1. Sulla scheda **Invia** sotto **Scegli un formato di incorporamento**, seleziona un formato di incorporamento. Il campo **Codice incorporamento** mostra il codice che deve essere incorporato in Creazione di siti di Commerce.

Gli esempi in questo articolo usano il modello di progetto **Sondaggio periodico dei clienti** e il formato di incorporamento **Pulsante**.

L'illustrazione di esempio seguente mostra la pagina del modello di progetto **Sondaggio periodico dei clienti**, dove l'opzione per il formato di incorporamento **Pulsante** è selezionata e il codice di incorporamento per tale opzione viene visualizzato nel campo **Codice incorporamento**. Sono necessarie tre azioni separate per incorporare il codice fornito nelle pagine del tuo sito, come descritto nelle sezioni seguenti.

![Pagina di sondaggio periodico dei clienti di Customer Voice con l'opzione Pulsante selezionata.](media/customer-voice-integration-1.png)

### <a name="embed-the-external-script-url"></a>Incorporare l'URL dello script esterno

In tutte le pagine del sito che devono includere un sondaggio di Customer Voice, devi incorporare l'URL dello script esterno fornito da Customer Voice nel codice di incorporamento. Il modo migliore per incorporare lo script in più pagine del sito consiste nel creare un frammento in Creazione di siti Web che contenga l'URL dello script esterno, quindi aggiungere il frammento ai modelli di pagina appropriati. Dopo aver pubblicato un modello aggiornato, il codice dello script esterno incorporato sarà simile all'esempio seguente nelle pagine del sito interessate.

```html
<script src=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.js type="text/javascript"></script>
```

Per informazioni sui frammenti, vedi [Utilizzare i frammenti](work-with-fragments.md).

> [!NOTE]
> Devi solo aggiungere l'URL al frammento. Il modulo di script esterno aggiungerà l'altro codice di script.

Per incorporare l'URL dello script esterno in un frammento, attieniti alla seguente procedura.

1. In Creazione di siti Web, crea un frammento basato sul [Modulo di script esterno](script-module.md).
1. Nel nuovo frammento seleziona lo slot **Script esterno predefinito**.
1. Nel riquadro delle proprietà **Script esterno predefinito**, nel campo **Origine script** immetti l'URL dello script esterno, come mostrato nell'illustrazione di esempio seguente.

    ![URL dello script esterno nel campo Origine script per il nuovo frammento.](media/customer-voice-integration-2.png)

1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Seleziona **Pubblica** per pubblicare il frammento.

Il nuovo frammento che contiene il blocco di script esterno incorporato è ora pronto per essere aggiunto al modello di pagina appropriato.

### <a name="embed-the-external-style-sheet-code"></a>Incorporare il codice del foglio di stile esterno

Ora in tutte le pagine del sito che devono includere un sondaggio di Customer Voice, devi incorporare il codice del foglio di stile esterno fornito da Customer Voice nel codice di incorporamento. Come nella sezione precedente, il modo migliore per incorporare il codice del foglio di stile esterno su più pagine del sito consiste nel creare un frammento in Creazione di siti Web che contenga il codice del foglio di stile, quindi aggiungere il frammento ai modelli di pagina appropriati. Il codice del foglio di stile esterno incorporato assomiglierà al codice di esempio seguente.

```typescript
<link rel="stylesheet" type="text/css" href=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.css />
```

Per incorporare il codice del foglio di stile esterno in un frammento, attieniti alla seguente procedura.

1. In Creazione di siti Web, crea un frammento basato sul [Modulo di metatag](metatags-module.md).
1. Nel frammento seleziona lo slot **Metatag predefiniti**.
1. Nel riquadro delle proprietà **Metatag predefiniti**, nel campo **Meta tag** immetti il codice del foglio di stile, come mostrato nell'illustrazione di esempio seguente.

    ![Codice del foglio di stile esterno nel campo Meta tag per il nuovo frammento.](media/customer-voice-integration-3.png)

1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Seleziona **Pubblica** per pubblicare il frammento.

Il nuovo frammento che contiene il codice del foglio di stile esterno incorporato è ora pronto per essere aggiunto al modello di pagina appropriato.

### <a name="embed-the-inline-script-code"></a>Incorporare il codice dello script inline 

Ora in tutte le pagine del sito che devono includere un sondaggio di Customer Voice, devi incorporare il codice dello script inline fornito da Customer Voice nel codice di incorporamento. Come nelle sezioni precedenti, il modo migliore per incorporare il codice dello script inline su più pagine del sito consiste nel creare un frammento in Creazione di siti Web che contenga il codice dello script inline, quindi aggiungere il frammento ai modelli di pagina appropriati.

Nel seguente esempio di codice di script inline, **SURVEY\_KEY** è un segnaposto. Il valore per **SURVEY\_KEY** deve corrispondere all'effettiva chiave del sondaggio fornita da Customer Voice nel codice di incorporamento. L'ultima riga richiama il codice per eseguire il rendering del pulsante sondaggio dopo un secondo, per garantire che gli script abbiano il tempo sufficiente per il caricamento. A seconda del sondaggio selezionato, potresti dover aggiungere o aggiornare anche altri metadati, come il nome dell'azienda.

```html
function renderSurveyButton() {
    var se = new SurveyEmbed("SURVEY_KEY","https://customervoice.microsoft.com/","https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/","true");

    var context = {
        "First Name":"",
        "Last Name": "",
        "locale": "en-us",
        "companyname": "Adventure Works"
    };
    se.renderButton(context);
}

setTimeout(renderSurveyButton, 4000);
```

Per incorporare il codice dello script inline in un frammento, attieniti alla seguente procedura.

1. In Creazione di siti Web, crea un frammento basato sul [Modulo di script inline](script-module.md).
1. Nel nuovo frammento seleziona lo slot **Script inline predefinito**.
1. Nel riquadro delle proprietà **Script inline predefinito**, nel campo **Script inline** immetti il codice dello script inline, come mostrato nell'illustrazione di esempio seguente.

    ![Codice dello script inline nel campo Script inline per il nuovo frammento.](media/customer-voice-integration-4.png)

1. Selezionare **Salva** e quindi selezionare **Fine modifica**.
1. Seleziona **Pubblica** per pubblicare il frammento.

Il nuovo frammento che contiene il codice dello script inline incorporato è ora pronto per essere aggiunto al modello di pagina appropriato.

## <a name="add-fragments-to-a-template"></a>Aggiungere frammenti a un modello

Al termine della creazione dei frammenti che contengono il codice incorporato di Customer Voice, devi aggiungerli ai modelli di pagina associati alle pagine del sito in cui desideri utilizzarli. Nell'illustrazione di esempio seguente, i tre frammenti di esempio sono stati aggiunti a un modello di pagina dei dettagli del prodotto.

![Frammenti di esempio aggiunti a un modello di pagina dei dettagli del prodotto.](media/customer-voice-integration-5.png)

Dopo la pubblicazione del modello aggiornato, il sondaggio Customer Voice apparirà su tutte le pagine controllate dal modello.

Per informazioni sui modelli, vedi [Utilizzare i modelli](work-with-templates.md).

## <a name="configure-content-security-policy"></a>Configurare i criteri di sicurezza del contenuto

Per impostazione predefinita, i criteri di sicurezza del contenuto non consentono le chiamate ad altri servizi a meno che non venga eseguita una configurazione aggiuntiva. Pertanto, dopo aver pubblicato i modelli aggiornati, è probabile che il sondaggio non venga caricato nelle pagine del sito pertinenti. Per visualizzare gli errori relativi ai criteri di sicurezza del contenuto, apri gli strumenti per sviluppatori del tuo browser web (F12), quindi vai a una pagina che contiene il sondaggio. Gli errori relativi ai criteri di sicurezza del contenuto verranno visualizzati nell'output della console.

Per configurare i criteri di sicurezza del contenuto in Creazione di siti Web per correggere gli errori, segui questi passaggi.

1. Andare a **Impostazioni del sito \> Estensioni**.
1. Sulla scheda **Criteri di sicurezza dei contenuti** aggiungi `https://customervoice.microsoft.com/` alla direttiva **child-src**.
1. Aggiungi `https://customervoice.microsoft.com/` alla direttiva **frame-src**.
1. Aggiungi `https://mfpembedcdnmsit.azureedge.net` e **.azureedge.net** alla direttiva **img-src**.

Per altre informazioni, vedere [Criteri di sicurezza dei contenuti](manage-csp.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Modulo script esterno](script-module.md)

[Modulo metatag](metatags-module.md)

[Modulo script inline](script-module.md)

[Criteri di sicurezza del contenuto](manage-csp.md)

[Utilizzare i frammenti](work-with-fragments.md)

[Utilizzare i modelli](work-with-templates.md)
