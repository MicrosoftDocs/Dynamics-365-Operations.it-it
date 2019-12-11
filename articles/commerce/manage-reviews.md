---
title: Gestire valutazioni e recensioni
description: In questo argomento viene descritto come gestire valutazioni e recensioni utilizzando lo strumento di moderazione di valutazioni e recensioni di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e9becdce5ae36ac637043b9d0febfbbff2392aa9
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698028"
---
# <a name="manage-ratings-and-reviews"></a>Gestire valutazioni e recensioni

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

In questo argomento viene descritto come gestire valutazioni e recensioni utilizzando lo strumento di moderazione di valutazioni e recensioni di Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Dynamics 365 Commerce utilizza il servizio cognitivo di Microsoft Azure per moderare automaticamente il testo delle recensioni censurando le parole volgari. Inoltre, i moderatori possono utilizzare lo strumento di moderazione di valutazioni e recensioni per le seguenti attività manuali:

- Moderare le recensioni rispondendo alle stesse o rimuovendole.
- Eliminare le recensioni di un cliente su richiesta del cliente.
- Importare in blocco i dati di valutazioni e recensioni per tutti i prodotti in un modello di Microsoft Power BI, di modo che i trend di valutazioni e recensioni possano essere analizzati.

## <a name="read-a-review"></a>Leggere una recensione 

1. Andare a **Home \> Recensioni \> Moderazione**.
1. Utilizzare il campo di ricerca nell'angolo superiore destro della pagina per filtrare le recensioni visualizzate per ID prodotto, nome di prodotto o testo della recensione.

Ulteriori filtri consentono di limitare le recensioni per periodo, valutazione, canale o stato (rimossa, risposta o segnalata).

![Home page di moderazione](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a>Rispondere a una recensione 

Talvolta, i clienti che hanno acquistato un prodotto esprimono la loro soddisfazione o insoddisfazione o non capiscono come utilizzare il prodotto. In veste di moderatore, è possibile pubblicare una risposta a una recensione. Questa risposta viene visualizzata insieme alla recensione nel sito. 

Per rispondere a una recensione, effettuare le seguenti operazioni.

1. Andare a **Home \> Recensioni \> Moderazione**.
1. Individuare e selezionare la recensione che richiede una risposta.
1. Nel riquadro delle proprietà a destra, selezionare **Aggiungi una risposta**.
1. Immettere il testo della risposta e il nome che deve essere visibile alla persona che risponde. Il nome predefinito della persona che risponde è **Moderatore**.
1. Al termine, selezionare **Registra risposta**.

![Rispondere a una recensione](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a>Rimuovere una recensione 

Talvolta, i moderatori rimuovono le recensioni dei clienti per un motivo commerciale. 

Per rimuovere una recensione, effettuare le seguenti operazioni.

1. Andare a **Home \> Recensioni \> Moderazione**.
1. Individuare e selezionare la recensione da rimuovere.
1. Nel riquadro delle proprietà a destra, selezionare il motivo della rimozione e quindi selezionare **Rimuovere**.
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a>Eliminare le recensioni di un cliente su richiesta del cliente. 

Talvolta, i clienti desiderano eliminare in modo permanente i dati delle loro recensioni e valutazioni da un sito Web di e-Commerce. Un moderatore che riceve una richiesta di rimozione da un cliente può rimuovere i dati del cliente mediante la funzionalità di eliminazione di recensioni. Per trovare ed eliminare i dati di un cliente, il moderatore richiede l'indirizzo di posta elettronica che il cliente ha utilizzato per accedere e fornire le recensioni. 

Per trovare ed eliminare i dati dei clienti, effettuare le seguenti operazioni.

1. Andare a **Home \> Recensioni \> Elimina**.
1. Nel campo **Cerca utenti per indirizzo di posta elettronica**, immettere l'indirizzo di posta elettronica del cliente e quindi selezionare **Cerca**.
1. Se il cliente svolge una qualsiasi attività di recensione (ad esempio invio di recensioni, voti sull'utilità delle recensioni di un altro cliente o commenti sulla recensione di un altro cliente), i risultati sono visualizzati. Per ogni elemento, è presente un pulsante **Elimina**.
1. Per ogni elemento che deve essere eliminato, selezionare **Elimina**. Quando viene richiesto di confermare, selezionare **Sì**. 
    
![Eliminare i dati di un cliente](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - La rimozione completa di dati dal sistema può richiedere fino a sette giorni. I moderatori devono informare i clienti di tale durata.
> - Se i clienti hanno modificato il relativo nome nelle impostazioni dell'account, molteplici elementi possono essere visualizzati nella ricerca. In questo caso, per eliminare completamente i dati del cliente, il moderatore deve selezionare **Elimina** per ogni elemento. 

## <a name="download-ratings-and-reviews-data"></a>Scaricare i dati di valutazioni e recensioni

Lo strumento di moderazione di valutazioni e recensioni consente ai moderatori di importare in blocco i dati di valutazioni e recensioni, di modo che possano analizzare le tendenze. Un modello di Power BI che include le metriche di base è disponibile. I moderatori possono utilizzare questo modello per collegare i dati importati in blocco e visualizzare un dashboard. Non devono creare un dashboard personalizzato. I moderatori possono inoltre personalizzare il modello di Power BI in base alle proprie esigenze. 

Per scaricare i dati di valutazioni e recensioni, effettuare le seguenti operazioni.

1. Andare a **Home \> Recensioni \> Report**.
1. Selezionare **Scarica dati di recensioni** per scaricare in blocco i dati di valutazioni e recensioni in formato CSV.

## <a name="view-ratings-and-reviews-trends"></a>Visualizzare le tendenze di valutazioni e recensioni

I moderatori possono scaricare il modello di Power BI in modo da poter visualizzare le tendenze in un dashboard.

Per visualizzare le tendenze di valutazioni e recensioni, effettuare le seguenti operazioni.

1. Andare a **Home \> Recensioni \> Report**.
1. Selezionare **Modello di PowerBI** per scaricare il modello.

    ![Scaricare il modello di Power BI](media/rnr-moderation-reports.png) 

1. Aprire il modello scaricato utilizzando l'app Power BI. Chiudere la finestra di dialogo **Accedi a contenuto Web** e il messaggio di errore "Aggiorna" visualizzati.
1. Andare a **Home**, selezionare **Modifica query** e quindi selezionare **Impostazioni origine dati**.
1. Nella finestra di dialogo **Impostazioni origine dati**, selezionare **Cambia origine**.
1. Nel campo **URL**, immettere il percorso dei dati delle recensioni scaricati nella procedura precedente (ad esempio **c:\\reviews\\ReviewsData.csv**).

    ![Campo URL nella finestra di dialogo Valori separati da virgola](media/rnr-powerbi-datasource-settings.png) 

1. Selezionare **OK** e quindi selezionare **Applica modifiche**. L'applicazione delle modifiche all'origine dati può durare fino a due minuti.
1. Selezionare **Foglio tendenze** per visualizzare le tendenze di valutazioni e recensioni.

    ![Tendenze di valutazioni e recensioni](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica valutazioni e recensioni](ratings-reviews-overview.md)

[Consentire l'utilizzo di valutazioni e recensioni](opt-in-ratings-reviews.md)

[Configurare valutazioni e recensioni](configure-ratings-reviews.md)

[Sincronizzare valutazioni sul prodotto in Dynamics 365 Retail](sync-product-ratings.md)
