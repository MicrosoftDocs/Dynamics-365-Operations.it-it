---
title: Incorporare app di terze parti
description: In questo argomento viene spiegato come incorporare app di terze parti per aumentare la funzionalità del prodotto.
author: jasongre
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, UserWorkspaceAdd, UserWorkspaceConfigureWebsite
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2021-04-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d348683e0a2ed35f26830a6ce05c0bf9ca5970bd
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944842"
---
# <a name="embed-third-party-apps"></a>Incorporare app di terze parti

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Molti clienti utilizzano una vasta gamma di applicazioni per gestire la propria attività. Alcune di queste applicazioni sono app Web di terze parti che funzionano insieme alle app Finance and Operations. Per fornire un'esperienza utente più integrata, puoi utilizzare la funzionalità **(Anteprima) App a tutta pagina** per incorporare quelle app di terze parti direttamente nelle app Finance and Operations (a condizione che le app di terze parti consentano di essere incorporate). In questo modo, gli utenti possono accedere ai siti Web e alle app di cui hanno bisogno senza dover cambiare scheda o finestra.

Prima di poter incorporare app di terze parti nel prodotto, è necessario attivare la funzionalità **(Anteprima) App a tutta pagina** in Gestione funzionalità. È quindi possibile utilizzare uno dei seguenti metodi per incorporare un'app o un sito Web di terze parti. Questi metodi sono analoghi ai metodi utilizzati per incorporare app canvas da Microsoft Power Apps in app Finance and Operations.

- Incorpora l'app o il sito Web in una pagina esistente come nuova scheda (scheda pivot, scheda dettaglio, pannello o sezione dell'area di lavoro).
- Crea una nuova esperienza a tutta pagina per l'app o il sito Web dal dashboard.

## <a name="embed-a-website-on-an-existing-page"></a>Incorporare un sito web in una pagina esistente

Utilizzare questa procedura se si desidera integrare una pagina esistente nel sistema con un'app incorporata.

1. Apri la pagina in cui vuoi incorporare l'app.
2. Aprire il riquadro **Aggiungi un'app**:

    1. Aprire la barra degli strumenti **Personalizzazione** selezionando **Impostazioni**, quindi **Personalizza**.
    2. Selezionare **Di più \> Aggiungi un'app**.

3. Selezionare l'area della pagina in cui si desidera aggiungere l'app. Quest'area deve essere un *contenitore di schede* per una scheda pivot, una scheda dettaglio, un pannello o una sezione dell'area di lavoro.
4. Selezionare **Sito web**.
5. Configurare l'app incorporata:

    - **Nome** - Immettere il testo da visualizzare per la scheda che contiene l'app incorporata. Spesso, vorrai che questo testo sia il nome dell'app.
    - **URL** – Specifica il percorso dell'app.

    > [!IMPORTANT]
    > - Per motivi di sicurezza, l'URL deve utilizzare HTTPS (Hypertext Transfer Protocol Secure).
    > - L'app o il sito Web devono essere configurati per consentire a se stessi di essere incorporati.

6. Selezionare **Salva** per incorporare l'app nella pagina. L'app viene aggiunta come ultima scheda o sezione nel gruppo.
7. Verifica che l'app venga visualizzata come previsto. Se non viene eseguito il rendering dell'app, vedere la sezione [Risoluzione dei problemi](#troubleshooting) più avanti in questo argomento.
8. Apri il selettore di visualizzazione e seleziona **Salva** (se l'app deve essere associata alla visualizzazione corrente) o **Salva con nome** (per salvare l'app in una visualizzazione diversa).

    Se la pagina non dispone di un selettore di visualizzazioni (ad esempio, se la pagina è una finestra di dialogo o un'area di lavoro), puoi saltare questo passaggio.

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a>Incorporare un sito Web come esperienza a tutta pagina dal dashboard

Utilizzare questa procedura se l'app che si desidera incorporare non è correlata a una pagina esistente o se si desidera solo un'esperienza a tutta pagina per l'app all'interno dell'app Finance and Operations.

1. Aprire il dashboard.
2. Seleziona e tieni premuta la pagina (o fai clic con il pulsante destro del mouse), seleziona **Personalizza** e quindi seleziona **Aggiungi una pagina**.
3. Nel riquadro **Aggiungi una pagina** fare clic su **Sito Web**.
4. Configurare l'app incorporata:

    - **Nome** - Immettere il testo che deve essere visualizzato nel riquadro aggiunto per l'app incorporata nel dashboard. Spesso, vorrai che questo testo sia il nome dell'app.
    - **URL** – Specifica il percorso dell'app.

    > [!IMPORTANT]
    > - Per motivi di sicurezza, l'URL deve utilizzare HTTPS.
    > - L'app o il sito Web devono essere configurati per consentire a se stessi di essere incorporati.

5. Selezionare **Salva** per aggiungere l'app al dashboard come nuovo riquadro.
6. Seleziona il nuovo riquadro nella dashboard e conferma che l'app viene visualizzata come previsto. Se non viene eseguito il rendering dell'app, vedere la sezione [Risoluzione dei problemi](#troubleshooting) più avanti in questo argomento.

## <a name="sharing-embedded-apps"></a>Condivisione di app incorporate

Dopo aver incorporato un'app utilizzando uno dei metodi descritti nelle sezioni precedenti, potresti voler condividere la visualizzazione con altri utenti nel sistema. Per condividere un'app incorporata, utilizza uno dei seguenti metodi:

- **Pubblica la visualizzazione (consigliato):** Se l'app incorporata è stata salvata in una visualizzazione, il modo consigliato e preferito per condividerla è pubblicare la visualizzazione per gli utenti che dispongono dei ruoli di sicurezza appropriati. Quindi tutti gli utenti che dispongono dei ruoli di sicurezza individuati dalla visualizzazione pubblicata vedranno l'app nelle app Finance and Operations. Per ulteriori informazioni su come pubblicare una visualizzazione, vedere [Pubblicazione di visualizzazioni](saved-views.md#publishing-views).

    Puoi anche pubblicare un'app che è stata incorporata come esperienza a tutta pagina dal dashboard. Nel dashboard, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il riquadro associato all'app, seleziona **Personalizza** e quindi seleziona **Pubblica pagina**. Attualmente è possibile pubblicare solo nei ruoli di sicurezza. Tuttavia, la capacità di pubblicare per le persone giuridiche verrà aggiunta prima che la funzionalità diventi generalmente disponibile.

- **Copia la personalizzazione:** Per le pagine che non supportano le visualizzazioni (ad esempio, finestre di dialogo o aree di lavoro) o per l'esperienza dell'app a tutta pagina, puoi copiare la personalizzazione per gli utenti appropriati. Per ulteriori informazioni, vedere [Condividere le personalizzazioni](personalize-user-experience.md#sharing-personalizations).

## <a name="viewing-embedded-apps"></a>Visualizzazione di app incorporate

Per visualizzare un'app incorporata in una pagina nelle app Finance and Operations, apri la pagina che include l'app incorporata. Ricorda che in alcune pagine è possibile accedere alle app utilizzando il pulsante **Power Apps** nel riquadro azioni standard. In alternativa, possono apparire direttamente in una pagina come nuova scheda, Scheda dettaglio o sezione in un'area di lavoro.

## <a name="editing-or-removing-embedded-apps"></a>Modifica o rimozione di app incorporate

Dopo che un'app è stata incorporata in una pagina, potrebbe essere necessario modificarne la configurazione (ad esempio, cambiando l'etichetta della sezione o l'URL). In alternativa, potresti doverla rimuovere dalla pagina. Utilizzare una delle seguenti procedure per modificare la configurazione di un'app incorporata o rimuoverla completamente.

### <a name="apps-that-are-embedded-on-existing-pages"></a>App incorporate in pagine esistenti

1. Apri la pagina in cui l'app è incorporata.
2. Aprire la barra degli strumenti **Personalizzazione** selezionando **Impostazioni**, quindi **Personalizza**.
3. Seleziona lo strumento **Seleziona**, quindi seleziona l'app incorporata.
4. Per modificare l'app, apportare le modifiche richieste alla sua configurazione, quindi selezionare **Salva**.

    In alternativa, per rimuovere l'app, seleziona **Elimina**.

5. Salvare nuovamente o ripubblicare la visualizzazione. Tieni presente che se esci dalla pagina senza salvare esplicitamente la visualizzazione, nessuna delle azioni che hai eseguito nel riquadro **Modifica sito Web** verrà mantenuto.

### <a name="apps-that-are-embedded-from-the-dashboard"></a>App incorporate dalla dashboard

1. Aprire il dashboard.
2. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il riquadro associato all'app incorporata, quindi seleziona **Personalizza**.
3. Per modificare l'app, seleziona **Modifica pagina**. Nel riquadro **Modifica sito Web**, apporta le modifiche richieste alla configurazione dell'app, quindi selezionare **Salva**.

    In alternativa, per rimuovere l'app, seleziona **Rimuovi pagina**.

## <a name="appendix"></a>Appendice

### <a name="troubleshooting"></a>Risoluzione dei problemi

Se il rendering di un sito Web non viene eseguito correttamente dopo essere stato incorporato in un'app Finance and Operation o se viene visualizzato un messaggio di errore che indica che all'URL è stata negata una connessione, il sito Web è probabilmente configurato per impedire a se stesso di essere incorporato in un iFrame. Segui questi passaggi per determinare se il sito web può essere incorporato.

1. Apri gli strumenti di sviluppo del browser che stai utilizzando.
2. Nella scheda **Rete**, trova e seleziona la risposta dal sito incorporato.
3. Nella scheda **Intestazioni**, sotto **Intestazioni di risposta**, cercare **x-frame-options**. Se **x-frame-options** esiste nelle intestazioni della risposta e ha un valore di **DENY** o **SAMEORIGIN**, al momento il sito web non può essere incorporato. Dovrai collaborare con il proprietario dell'app per consentirne l'incorporazione in modo sicuro.

### <a name="developer-modeling-a-website-on-a-form"></a>[Sviluppatore] Modellazione di un sito Web su un modulo

Sebbene questo argomento sia incentrato sull'incorporamento di app o siti Web di terze parti tramite la personalizzazione, gli sviluppatori possono anche incorporarli in un modulo utilizzando l' esperienza di sviluppo di Visual Studio. Basta aggiungere un controllo **WebsiteHostControl** al modulo. Le proprietà dei metadati disponibili per il controllo forniscono le stesse funzionalità dell'esperienza di personalizzazione.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
