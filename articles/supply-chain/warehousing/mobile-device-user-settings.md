---
title: Impostazioni utente dispositivo mobile
description: In questo argomento viene descritto come gestire le impostazioni utente del dispositivo mobile per gli addetti al magazzino.
author: MarkusFogelberg
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppDeviceBrand,WHSMobileAppUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: mafoge
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 51c530fd0043a4ec5a82660af72c001be25b7e62
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647487"
---
# <a name="mobile-device-user-settings"></a>Impostazioni utente dispositivo mobile

[!include [banner](../../includes/banner.md)]

La nuova app per dispositivi mobili Gestione magazzino include una serie di impostazioni specifiche dell'app che consentono di personalizzare l'esperienza dell'utente. Poiché l'app può essere utilizzata su dispositivi con schermi di dimensioni e configurazioni diverse (come tablet o telefoni), può essere utile per gestire centralmente queste impostazioni in Microsoft Dynamics 365 Supply Chain Management.

La funzionalità *Impostazioni utente dispositivo mobile* consente di definire le impostazioni utente globali che verranno utilizzate in tutti i dispositivi. È anche possibile definire impostazioni utente più granulari per singoli marchi di dispositivo, modelli di dispositivo e/o lavoratori. Quando un lavoratore accede all'app per dispositivi mobili Gestione magazzino, l'app recupera e applica il profilo delle impostazioni più specifico archiviato in Supply Chain Management per l'ID marchio, dispositivo e/o utente corrispondenti.

Questa funzionalità può aiutare gli addetti a iniziare a utilizzare più rapidamente un nuovo dispositivo. Di seguito sono riportati alcuni esempi.

- Gli amministratori possono stabilire un insieme standard di preferenze che funzionano meglio per i dispositivi di uno specifico produttore e/o per specifici modelli di dispositivo. Pertanto, gli addetti possono iniziare a utilizzare un nuovo dispositivo senza dover necessariamente modificare le impostazioni.
- Se la società dispone di un pool di dispositivi identici condivisi tra i lavoratori, questi vedranno la loro configurazione preferita ogni volta che eseguono l'accesso, anche se non hanno mai utilizzato il dispositivo fisico specifico selezionato in un dato giorno.
- In Supply Chain Management, gli amministratori possono visualizzare e modificare tutte le impostazioni archiviate, anche per i singoli lavoratori. Questa funzionalità può aiutarli a risolvere i problemi o a ottimizzare nuove funzionalità.

> [!IMPORTANT]
> La funzionalità *Impostazioni utente dispositivo mobile* si applica solo alla nuova app per dispositivi mobili Gestione magazzino. Non è utilizzabile con la vecchia app di magazzino.

## <a name="turn-on-the-mobile-device-user-settings-feature"></a>Attivare la funzionalità Impostazioni utente dispositivo mobile

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione magazzino*
- **Nome funzionalità:** *Impostazioni utente, icone e titoli dei passaggi per la nuova app di magazzino*

## <a name="create-and-manage-user-settings"></a>Creare e gestire impostazioni utente

Usare la pagina **Impostazioni utente dispositivo mobile** per creare, visualizzare e gestire profili di impostazioni a tutti i livelli di granularità. La prima volta che un lavoratore modifica le proprie impostazioni utente su un nuovo dispositivo, un nuovo profilo viene aggiunto automaticamente in questa pagina, se non esiste già. Tale profilo viene quindi aggiornato ogni volta che il lavoratore apporta una modifica.

È anche possibile definire un profilo di impostazioni da applicare a tutti i marchi di dispositivo, modelli di dispositivo e/o lavoratori. È quindi possibile aumentare la granularità applicando impostazioni più specifiche per singoli marchi, modelli e/o lavoratori.

Seguire questi passaggi per creare e gestire impostazioni utente per i dispositivi mobili.

1. Selezionare **Warehouse Management \> Impostazione \> Dispositivo mobile \> Impostazioni utente dispositivo mobile**.
1. Selezionare un profilo di impostazioni utente esistente nel riquadro elenco per aprire il relativo record. In alternativa, selezionare **Nuovo** nel riquadro Azioni per creare un nuovo profilo.

    Ogni profilo nel riquadro elenco è etichettato per indicare l'ID marchio, modello e/o utente a cui si applica il profilo. I profili più generali hanno il valore *Tutti* per alcune o tutte queste caratteristiche.

1. Nella sezione dell'intestazione del record per il profilo di impostazioni nuovo o selezionato, impostare i seguenti campi:

    - **Nome marchio dispositivo** - Selezionare il nome del marchio del dispositivo a cui deve essere applicato il profilo. Se il profilo deve essere applicato a tutti i marchi, lasciare vuoto questo campo. L'elenco dei valori include tutti i marchi che sono stati definiti nel sistema. Per informazioni su come definire l'elenco dei marchi, vedere la sezione successiva.
    - **ID modello dispositivo** - Selezionare il modello del dispositivo a cui deve essere applicato il profilo. Se il profilo deve essere applicato a tutti i modelli del marchio selezionato, lasciare vuoto questo campo. L'elenco dei valori include tutti i modelli che sono stati definiti per il marchio selezionato nel campo **Nome marchio dispositivo**. Per informazioni su come definire l'elenco dei modelli di ogni marchio, vedere la sezione successiva.
    - **ID utente** - Selezionare l'ID utente dell'addetto al magazzino a cui deve essere applicato il profilo di impostazioni. Se il profilo deve essere applicato a tutti i lavoratori, lasciare vuoto questo campo.

1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Posizione pulsanti** - Selezionare il modo in cui posizionare i pulsanti sul dispositivo. Gli elementi nell'app verranno spostati per adattarsi meglio alle preferenze o alla manualità del lavoratore. Le opzioni disponibili sono *In basso a destra (predefinito)*, *In basso a sinistra*, *In alto a destra* e *In alto a sinistra*.
    - **Orientamento schermo** - Selezionare l'orientamento dello schermo che deve essere applicato per impostazione predefinita nell'app.
    - **Scansione con fotocamera** - Impostare questa opzione su *Sì* per utilizzare la fotocamera del dispositivo per eseguire la scansione dei campi di input in cui la modalità di input preferita è impostata su *Scansione*. Se il dispositivo in uso ha uno scanner integrato, impostare questa opzione su *No* per utilizzare lo scanner.
    - **Mostra foto del prodotto** - Selezionare se le foto del prodotto rilasciato devono essere visualizzate se sono disponibili. Per ulteriori informazioni su come aggiungere immagini del prodotto, vedere [Aggiungere un'immagine a un prodotto](../pim/tasks/add-image-product.md).
    - **Visualizza tema di colori** - Selezionare un tema di colori per il dispositivo.
    - **Livello audio** - Selezionare il livello audio del dispositivo. Selezionare un valore tra 0 (zero) e 10. Con il valore *0*, il volume è azzerato mentre il valore *10* rappresenta il volume massimo. Il valore predefinito è *4*.
    - **Livello vibrazione** - Selezionare il livello di vibrazione del dispositivo. Selezionare un valore tra 0 (zero) e 5. Con il valore *0*, la vibrazione è azzerata mentre il valore *5* rappresenta la vibrazione massima. Il valore predefinito è *1*.
    - **Percentuale scalabilità testo** - Specificare la dimensione del testo come percentuale della dimensione standard. Immettere un valore tra 70 e 400. Il valore *70* rappresenta la scalabilità del testo più piccola e il valore *400* rappresenta la scalabilità del testo più grande. Il valore predefinito è *100*.
    - **Percentuale scalabilità pulsanti** - Specificare la dimensione dei pulsanti come percentuale della dimensione standard. Immettere un valore tra 50 e 200. Il valore *50* rappresenta la scalabilità dei pulsanti più piccola e il valore *200* rappresenta la scalabilità dei pulsanti più grande. Il valore predefinito è *100*.

## <a name="create-and-manage-mobile-device-brands"></a>Creare e gestire marchi di dispositivi mobili

Utilizzare la pagina **Marchi di dispositivi mobili** per visualizzare, creare e gestire i marchi e i modelli di dispositivi che possono essere utilizzati con i profili di impostazioni. L'app per dispositivi mobili recupera e invia automaticamente il nome di marchio locale e l'ID modello la prima volta che un lavoratore modifica le proprie impostazioni in un determinato dispositivo. Pertanto, la maggior parte di questi record verrà generalmente generata automaticamente. Tuttavia, è anche possibile gestire tutti i record in questa pagina. Ad esempio, è possibile fornire descrizioni più utili di ciascun marchio e modello per distinguere ID modello simili o criptici.

Seguire questi passaggi per creare e gestire marchi e modelli di dispositivi mobili.

1. Vai a **Warehouse Management \> Impostazione \> Dispositivo mobile \> Marchi di dispositivi mobili**.
1. Nel riquadro elenco, selezionare una marchio di dispositivo mobile per aprirne il record. In alternativa, selezionare **Nuovo** nel riquadro Azioni per creare un nuovo marchio.
1. Nella sezione dell'intestazione del record per il marchio di dispositivo nuovo o selezionato, impostare i seguenti campi:

    - **Nome marchio dispositivo** - Il nome del marchio del dispositivo, ad esempio *Microsoft Corporation*.
    - **Descrizione** - È possibile inserire una descrizione per distinguere i nomi dei marchi.

1. La Scheda dettaglio **Modelli di dispositivi mobili** mostra tutti i modelli per il marchio di dispositivo selezionato. Utilizzare i pulsanti nella barra degli strumenti per aggiungere righe alla griglia o rimuoverle. Per ogni riga, è possibile impostare i seguenti campi:

    - **ID modello dispositivo** - L'ID modello di dispositivo, ad esempio *Surface Book 2*.
    - **Descrizione** - È possibile inserire una descrizione per distinguere gli ID modello.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Installare e connettere l'app per dispositivi mobili Gestione magazzino](install-configure-warehouse-management-app.md)
- [Assegnare icone e titoli dei passaggi per l'app per dispositivi mobili Warehouse Management](step-icons-titles.md)