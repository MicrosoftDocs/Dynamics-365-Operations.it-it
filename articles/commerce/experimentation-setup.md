---
title: Configurare un esperimento
description: In questo articolo viene descritto come configurare un esperimento in un servizio di terze parti.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1073cdc509622279ce7388b8b406079a4e6e9e09
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946168"
---
# <a name="set-up-an-experiment"></a>Configurare un esperimento

Dopo che hai [definito un'ipotesi e determinato quali metriche desideri utilizzare](experimentation-identify.md), dovrai configurare l'esperimento nel servizio di terze parti. Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce. I passaggi aggiuntivi sono esposti in articoli separati.

[ ![Percorso utente sperimentazione - Configurazione.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Configurare l'esperimento nel servizio di terze parti
A questo punto dovresti aver scelto il servizio di terze parti per eseguire e monitorare l'esperimento e configurare il connettore di sperimentazione. Questi prerequisiti sono elencati in [Sperimentazione in Dynamics 365 Commerce](experimentation-overview.md).

Segui i passaggi necessari per creare l'esperimento nel servizio di terze parti. Se il connettore è configurato correttamente, l'elenco completo degli esperimenti che hai configurato nel servizio di terze parti sarà visualizzato in Creazione di siti Web di Commerce nel giro di 5 minuti.

## <a name="set-up-your-success-metrics"></a>Configurare le metriche
Per ogni esperimento sono necessarie metriche per misurare l'impatto delle varianti e per convalidare l'ipotesi. Segui i passaggi seguenti per abilitare il calcolo delle metriche nel servizio di terze parti utilizzando eventi di telemetria in tempo reale di Dynamics 365 Commerce.

Per impostare le tue metriche ottimali per i moduli predefiniti, segui questi passaggi.

1. In Creazione di siti Web di Commerce, selezionare **Pagine** nel riquadro di spostamento a sinistra e quindi selezionare la pagina per la quale si desidera raccogliere metriche. 
1. Vai alla sezione **ID evento da monitorare** nel riquadro delle proprietà a destra della pagina o del modulo che desideri monitorare.
1. Seleziona **Visualizza**. Viene visualizzato un elenco di tutti gli ID evento clic. Copia l'evento che desideri monitorare e incolla la chiave dell'evento nella posizione designata nel servizio di terze parti. Se hai bisogno di più eventi, copia le chiavi una alla volta. 
1. Per le visualizzazioni di pagina, utilizza il valore hash SHA-256 del nome della pagina in Creazione di siti Web aggiunto con `.PageView`. Ad esempio, l'ID evento per `Homepage.PageView` sarebbe `e217eb66c7808ecc43b0f5c517c6a83b39d72b91412fbd54a485da9d8e186a9`.
1. Esegui altri passaggi per il monitoraggio delle metriche come richiesto nel servizio di terze parti.

Per i clic sui moduli personalizzati, attieniti alla seguente procedura per strumentare gli eventi clic:

1. Prepara un oggetto **TelemetryContent** per il modulo utilizzando la funzione seguente. Questa funzione accetta come input il nome della pagina, il nome del modulo e l'oggetto di telemetria predefinito fornito dall'SDK.

    ```TypeScript
    getTelemetryObject(pageName: string, moduleName: string, telemetry: ITelemetry): ITelemetryContent
    ```
    
    Quanto segue è un esempio: 
    
    ```TypeScript
    private readonly telemetryContent: ITelemetryContent = getTelemetryObject(this.props.context.request.telemetryPageName!, this.props.friendlyName, this.props.telemetry);
    ```
    
1. Crea i dati del payload che contengono informazioni su ciò che deve essere acquisito. Per i pulsanti e altri controlli statici, puoi includere **etext** come "Acquista ora" o "Cerca". E per i componenti con clic come il clic su una scheda prodotto, puoi inviare il **recid** che è l'ID record del prodotto o l'ID prodotto.

    ```TypeScript
    getPayloadObject(eventType: string, telemetryContent: ITelemetryContent, etext: string, recid?: string): IPayLoad
    ```
    Come esempio per i controlli statici, passa la stringa di testo del pulsante come mostrato di seguito:

    ```TypeScript
    const payLoad = getPayloadObject('click', this.props.telemetryContent, 'Shop Now', '');
    ```
    Come esempio per i clic sui prodotti, passa il recordId del prodotto come mostrato di seguito:

    ```TypeScript
    const payLoad = getPayloadObject('click', telemetryContent!, '', product.RecordId.toString());
    ```
    
1. Chiama la funzione **OnClick** per registrare l'evento.

    ```TypeScript
    onTelemetryClick = (telemetryContent: ITelemetryContent, payLoad: IPayLoad, linkText: string) => () =>
    ```

    Quanto segue è un esempio:

    ```TypeScript
    onClick: onTelemetryClick(this.props.telemetryContent, payLoad, linkText)
    ```

## <a name="previous-step"></a>Passaggio precedente
[Identificare un'ipotesi e determina le metriche per un esperimento](experimentation-identify.md) 


## <a name="next-step"></a>Passaggio successivo
[Collegare e modificare un esperimento](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
