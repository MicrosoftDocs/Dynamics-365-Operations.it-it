---
title: Ancoraggio
description: Questo argomento spiega come abilitare e utilizzare l'ancoraggio.
author: GalynaFedorova
ms.date: 07/29/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-29
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a17574cccbdf6f26f0453bda67eabaa16d559cd3
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505580"
---
# <a name="anchoring"></a>Ancoraggio

[!include [banner](../includes/banner.md)]

Questo argomento fornisce dettagli sul processo di ancoraggio. Descrive la configurazione richiesta e la logica che viene eseguita quando un lavoratore di magazzino modifica l'ubicazione di gestione temporanea o l'ubicazione di carico.

La funzione di ancoraggio consente di ignorare la posizione di gestione temporanea o carico. Tutti gli stoccaggi aperti verranno quindi indirizzati alla nuova posizione di gestione temporanea o carico specificata.

Questa funzione può aiutare i lavoratori a essere più efficienti durante la spedizione delle merci. Di seguito sono riportati alcuni esempi.

- Un lavoratore deve inserire gli articoli per l'ordine 1 in un'ubicazione di gestione temporanea dalla banchina 1, ma non può completare l'operazione perché un carico precedente non ha cancellato l'ubicazione. Anziché attendere che diventi disponibile l'ubicazione gestione temporanea banchina 1, il lavoratore può scegliere di utilizzare l'ubicazione gestione temporanea per la banchina 2. In questo caso, il lavoratore ignora l'ubicazione gestione temporanea suggerita. L'ubicazione di stoccaggio per tutti gli articoli rimanenti del lavoro viene aggiornata impostando l'ubicazione di gestione temporanea della banchina 2.
- Un lavoratore che deve eseguire più prelievi per la stessa consegna può essere certo che tutti gli articoli stoccati siano assemblati nello stesso luogo. Pertanto, è necessario meno tempo per caricare gli articoli nel camion.

Configura l'ancoraggio per le voci di menu del dispositivo mobile utilizzando l'opzione **Ancora**. Se imposti questa opzione su *Sì* puoi usare il campo **Ancora per** per specificare se eseguire l'ancoraggio in base alla spedizione o al carico nel campo Ancora per. Se imposti il campo **Ancora per** su *Spedizione*, i successivi stoccaggi aperti verranno modificati sulla nuova posizione per quella spedizione. Se imposti il campo su *Carico*, i successivi stoccaggi aperti verranno modificati sulla nuova posizione per quel carico.

> [!IMPORTANT]
> La posizione per i successivi stoccaggi aperti verrà modificata solo sulle righe di lavoro generate dalla stessa riga del modello di lavoro. In altre parole il sistema ancorerà le righe di stoccaggio che hanno origine dalla stessa riga del modello di lavoro.

Questo argomento fornisce uno scenario che mostra come funziona l'ancoraggio. Durante lo scenario, creerai una serie di ordini cliente e rilascerai ogni serie nel magazzino. Quindi sovrascriverai la posizione di gestione temporanea suggerita e verificherai che tutto il lavoro di stoccaggio rimanente sia diretto alla nuova posizione.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Prerequisito dello scenario: rendere disponibili i dati demo

Lo scenario in questo argomento fa riferimento a valori e record inclusi nei dati demo standard forniti per Microsoft Dynamics 365 Supply Chain Management. Se desideri utilizzare i valori forniti qui durante l'esecuzione degli esercizi, assicurati di lavorare in un ambiente in cui sono installati i dati dimostrativi e imposta la persona giuridica su *USMF* prima di iniziare.

## <a name="scenario-setup"></a>Impostazione dello scenario

Prima di elaborare lo scenario di esempio, è necessario abilitare l'ancoraggio per la voce di menu pertinente del dispositivo mobile.

### <a name="set-up-a-mobile-device-menu-item-to-enable-anchoring"></a>Impostare una voce di menu del dispositivo mobile per abilitare l'ancoraggio

Segui questi passaggi per abilitare l'ancoraggio per una voce di menu di un dispositivo mobile.

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro dell'elenco, seleziona il record denominato *Prelievo vendite*. Se nessun record esistente ha questo nome, crealo. Conferma o imposta i seguenti valori per il record:

    - **Nome voce di menu:** *Prelievo vendite*
    - **Titolo:** *Prelievo vendite*
    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *Sì*
    - **Diretto da:** *Diretto dall'utente*
    - **Ancoraggio:** *Sì*

        Questa impostazione fa sì che il sistema ancori più righe dell'ordine di lavoro durante il prelievo delle vendite.

    - **Ancora per:** *Carico*

        Questa impostazione fa sì che il sistema ancori per carico.

    - **Ignora targa destinazione:** *Sì*
    - **Ignora targa durante inserimento:** *Sì*
    - **Mantieni il lavoro bloccato dall'utente:** *Sì*
    - **Consenti prelievo in eccesso:** *Sì*

### <a name="set-up-a-work-template-to-enable-staging"></a>Impostare un modello di lavoro per abilitare la gestione temporanea

Segui questi passaggi per configurare un modello di lavoro per abilitare la gestione temporanea. Questa configurazione supporterà lo scenario in cui un lavoratore stocca gli articoli per un ordine in un'ubicazione di gestione temporanea.

1. Accedi a **Gestione magazzino \> Impostazione \> Lavoro \> Modelli di lavoro**.
1. Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.
1. Nella griglia, selezionare il modello di lavoro **Fase ordine cliente 61**.
1. Nella sezione **Dettagli modello di lavoro** assicurati che le seguenti righe esistano e siano configurate come mostrato qui:

    - Riga 1:

        - **Tipo di lavoro:** *Prelevare*
        - **Obbligatorio:** Selezionato (= *Sì*)
        - **ID classe lavoro:** *Prelievo ordine cliente*

    - Riga 2:

        - **Tipo di lavoro:** *Inserire*
        - **Obbligatorio:** Selezionato (= *Sì*)
        - **Codice direttiva:** *Fase*
        - **ID classe lavoro:** *Prelievo ordine cliente*

    - Riga 3:

        - **Tipo di lavoro:** *Prelevare*
        - **Obbligatorio:** Selezionato (= *Sì*)
        - **Interrompi lavoro:** *Sì*
        - **ID classe lavoro:** *Carico ordine cliente*

    - Riga 4:

        - **Tipo di lavoro:** *Inserire*
        - **Obbligatorio:** Selezionato (= *Sì*)
        - **Codice direttiva:** *Portellone*
        - **ID classe lavoro:** *Carico ordine cliente*

1. Nel riquadro azioni, seleziona **Modifica query** per aprire l'editor di query.
1. Nella scheda **Intervallo**, verifica che sia presente la seguente riga:

    - **Tabella:** *Transazioni lavoro temporanee*
    - **Tabella derivata:** *Transazioni lavoro temporanee*
    - **Campo:** *Magazzino*
    - **Criteri:** *61*

1. Nella scheda **Ordinamento**, verifica che sia presente la seguente riga:

    - **Tabella:** *Transazioni lavoro temporanee*
    - **Tabella derivata:** *Transazioni lavoro temporanee*
    - **Campo:** *ID spedizione*
    - **Direzione di ricerca:** *Crescente*

1. Seleziona **OK** per applicare le impostazioni e chiudere l'editor di query. Accetta le modifiche se richiesto.
1. Nel riquadro azioni, selezionare **Suddivisioni intestazione lavoro**.
1. Nella riga in cui il campo **Nome campo** è impostato su *ID spedizione*, accertati che la casella di controllo **Raggruppa per questo campo** sia selezionata.

### <a name="set-up-license-plates-locations-and-inventory"></a>Impostare targhe, ubicazioni e inventario

Prima di creare ordini cliente e spedizioni, è necessario assicurarsi che esistano le ubicazioni, le targhe e l'inventario richiesti.

1. Vai a **Gestione magazzino \> Impostazione \> Magazzino \> Targhe** e crea due targhe:

    - Targa1
    - Targa2

1. Vai a **Gestione magazzino \> Impostazione \> Magazzino \> Ubicazioni** e crea le seguenti ubicazioni se non sono già presenti.

    | Magazzino | Posizione   | ID profilo ubicazione | ID zona   |
    |-----------|------------|---------------------|-----------|
    | 61        | 06A01R2S1B | PRELIEVO-06             | FLOOR     |
    | 61        | 06A01R3S1B | PRELIEVO-06             | FLOOR     |
    | 61        | FASE01    | FASE               | *(Vuoto)* |
    | 61        | FASE02    | FASE               | *(Vuoto)* |
    | 61        | FASE03    | FASE               | *(Vuoto)* |
    | 61        | FASE04    | FASE               | *(Vuoto)* |

1. Assicurati che sia disponibile il seguente inventario. Se è necessario regolare le scorte, puoi creare movimenti manuali, utilizza il rifornimento o utilizza qualsiasi altro flusso, come richiesto.

    | Numero articolo | Quantità | Magazzino | Posizione   | Targa |
    |-------------|----------|-----------|------------|---------------|
    | A0001       | 100      | 61        | 06A01R2S1B | Targa1         |
    | A0002       | 100      | 61        | 06A01R3S1B | Targa2         |

### <a name="create-demand"></a>Creare domanda

Prima di poter usare la funzionalità di ancoraggio è necessario creare una domanda. Per questo scenario, creerai tre ordini cliente per lo stesso cliente.

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Seleziona **Nuovo** per creare il primo ordine cliente.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-001*
    - **Magazzino:** *61*

1. Selezionare **OK**.
1. Viene aperto il nuovo ordine cliente. Include una riga vuota nella Scheda dettaglio **Righe ordine cliente**. Impostare i seguenti valori per questa riga:

    - **Numero articolo:** *A0001*
    - **Quantità:** *1*

1. Nella barra degli strumenti seleziona **Aggiungi riga** per aggiungere un secondo ordine clienti, quindi imposta i seguenti valori:

    - **Numero articolo:** *A0002*
    - **Quantità:** *1*

1. Ripeti questi passaggi per ciascuna riga di vendita nell'ordine per prenotare le relative scorte:

    1. Nella scheda dettaglio **Righe ordine cliente**, seleziona una riga dell'ordine cliente.
    1. Sulla barra degli strumenti, seleziona **Inventario \> Prenotazione**.
    1. Nella pagina **Prenotazione** selezionare **Prenota lotto** e chiudere la pagina.
    1. Nel riquadro azioni selezionare **Salva**.

1. Ripeti i passaggi da 2 a 6 per creare un secondo ordine cliente. Impostare i seguenti valori per questo record:

    - Nella finestra di dialogo **Crea ordine cliente**:

        - **Conto cliente:** *US-001*
        - **Magazzino:** *61*

    - Nella riga ordine cliente 1:

        - **Numero articolo:** *A0001*
        - **Quantità:** *2*

    - Nella riga ordine cliente 2:

        - **Numero articolo:** *A0002*
        - **Quantità:** *2*

1. Ripeti il passaggio 7 per prenotare ogni riga dell'ordine cliente 2.
1. Ripeti i passaggi da 2 a 6 per creare un terzo ordine cliente. Impostare i seguenti valori per questo record:

    - Nella finestra di dialogo **Crea ordine cliente**:

        - **Conto cliente:** *US-001*
        - **Magazzino:** *61*

    - Nella riga ordine cliente 1:

        - **Numero articolo:** *A0001*
        - **Quantità:** *3*

    - Nella riga ordine cliente 2:

        - **Numero articolo:** *A0002*
        - **Quantità:** *3*

1. Ripeti il passaggio 7 per prenotare ogni riga dell'ordine cliente 3.

### <a name="use-the-load-planning-workbench-to-create-a-load-and-release-it-to-the-warehouse"></a>Utilizza il workbench di pianificazione del carico per creare un carico e rilasciarlo nel magazzino

Segui questi passaggi per creare un carico per gli ordini creati per questo scenario e quindi rilascialo nel magazzino.

1. Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.
1. Nella scheda **Righe vendita** trova e seleziona tutte le righe per l'ordine cliente 1 e l'ordine cliente 2.
1. Nel riquadro azioni, nella scheda **Domanda e offerta**, nel gruppo **Aggiungi** seleziona **Al nuovo carico**.
1. Nella finestra di dialogo **Assegnazione modello di carico**, nel campo **ID modello carico**, seleziona un modello di caricamento, ad esempio *Modello di caricamento stnd*.
1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Nella sezione **Carichi**, trova e seleziona il carico che hai creato.
1. Nella barra degli strumenti seleziona **Rilascia \> Rilascia in magazzino**.
1. Nella finestra di dialogo **Rilascia carico in magazzino** seleziona **OK** per rilasciare il carico selezionato nel magazzino.
1. Passare a **Gestione magazzino \> Lavoro \> Tutti i lavori** per visualizzare tutti i lavori creati. Sono disponibili due nuovi ID lavoro, uno per ogni spedizione. Ciascun ID lavoro ha righe di prelievo e stoccaggio che portano l'inventario dalle ubicazioni di prelievo all'ubicazione di gestione temporanea e dall'ubicazione di gestione temporanea al portellone. Prendi nota del valore **ID lavoro** per la prima consegna, in modo da poterlo utilizzare nella procedura successiva.

### <a name="sales-order-picking-to-the-staging-location-for-the-first-shipment"></a>Prelievo dell'ordine cliente nell'ubicazione di gestione temporanea per la prima spedizione

1. Accedi all'app per dispositivi mobili Gestione magazzino come lavoratore nel magazzino *61*. (nei dati demo standard, è possibile accedere utilizzando _61_ come ID utente e _1_ come password).
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Prelievo vendite**.
1. Selezionare il campo **ID**, quindi immettere l'ID lavoro per la prima spedizione.
1. Conferma l'inserimento.
1. Nel campo **Targa** immetti un numero di targa per il primo articolo (*Targa1*).
1. Conferma l'inserimento.
1. Nel campo **Targa destinazione** inserisci un numero qualsiasi (la targa di destinazione non deve esistere già).

    Prelevi tutte le righe create dal cliclo elaborato sulla stessa targa di destinazione.

1. Conferma l'inserimento.
1. Nel campo **Targa** immetti un numero di targa per il secondo articolo (*Targa2*).
1. Conferma l'inserimento.

    Immagina che il lavoratore abbia ora ritirato l'ordine, ma quando arriva nell'ubicazione di gestione temporanea specificata nel lavoro, scopre che lo spazio è già occupato. Tuttavia, il lavoratore può vedere che un'altra ubicazione vicina (*FASE03*) è disponibile. Pertanto, chiede di cambiare l'ubicazione di gestione temporanea. Poiché la funzione di ancoraggio è abilitata, il sistema aggiornerà automaticamente l'ubicazione di gestione temporanea per questo e tutti i lavori correlati.

1. Seleziona **Sostituisci ubicazione** per sostituire l'ubicazione di gestione temporanea suggerita.
1. Nel campo **Eccezioni lavoro**, specifica *Corsia gestione temporanea cambiata*.
1. Nel campo **Ubicazione** immetti una nuova ubicazione di gestione temporanea (*FASE03*).
1. Conferma l'inserimento. Viene visualizzato il messaggio "Lavoro completato".
1. Vai a **Gestione magazzino \> Lavoro \> Tutti i lavori**.
1. Apri l'ID lavoro per la prima spedizione. Verifica che l'ubicazione di gestione temporanea sia stata aggiornata alla nuova posizione (*FASE03*) che è stata definita utilizzando il dispositivo mobile.
1. Apri l'ID lavoro per la seconda spedizione. Verifica che l'ubicazione di gestione temporanea sia stata aggiornata alla nuova ubicazione di gestione temporanea (*FASE03*) a causa della configurazione dell'ancoraggio.

> [!NOTE]
> L'ubicazione per tutte le righe di lavoro di stoccaggio aperte rimanenti che hanno la stessa ubicazione di gestione temporanea e che sono state generate dalla stessa riga del modello di lavoro verrà aggiornata alla nuova ubicazione.

### <a name="use-the-load-planning-workbench-to-add-the-new-sales-order-to-the-existing-load"></a>Utilizzare il workbench di pianificazione del carico per aggiungere il nuovo ordine cliente al carico esistente

Segui questi passaggi per aggiungere un ordine al carico e poi rilasciarlo al magazzino.

1. Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.
1. Nella scheda **Righe vendita** trova e seleziona tutte le righe per l'ordine cliente 3.
1. Nel riquadro azioni, nella scheda **Domanda e offerta** nel gruppo **Aggiungi** seleziona **A carico esistente** per aggiungere le righe ordine selezionate a un carico esistente.
1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Nella sezione **Carichi**, trova e seleziona il carico dai passaggi precedenti.
1. Seleziona **Rilascia \> Rilascia in magazzino**.
1. Nella finestra di dialogo **Rilascia carico in magazzino** seleziona **OK** per rilasciare il carico selezionato nel magazzino.
1. Passare a **Gestione magazzino \> Lavoro \> Tutti i lavori** per visualizzare tutti i lavori creati. Prendere nota del valore **ID lavoro**, in modo da poterlo utilizzare nella procedura successiva.

### <a name="sales-order-picking-to-the-staging-location-for-the-third-shipment"></a>Prelievo dell'ordine cliente nell'ubicazione di gestione temporanea per la terza spedizione

1. Accedere all'app per dispositivi mobili come lavoratore nel magazzino *61*.
1. Nel menu principale, selezionare **In uscita**.
1. Nel menu **In uscita**, selezionare **Prelievo vendite**.
1. Selezionare il campo **ID**, quindi immettere l'ID lavoro per la terza spedizione.
1. Conferma l'inserimento.
1. Nel campo **Targa** immetti un numero di targa per il primo articolo (*Targa1*).
1. Conferma l'inserimento.
1. Nel campo **Targa destinazione** inserisci un numero qualsiasi (la targa di destinazione non deve esistere già).
1. Conferma l'inserimento.
1. Nel campo **Targa** immetti un numero di targa per il secondo articolo (*Targa2*).
1. Conferma l'inserimento.

    Per quanto riguarda il primo carico, immagina che il lavoratore trovi che l'ubicazione di gestione temporanea specificata non è disponibile. Pertanto, desidera utilizzare un'ubicazione di gestione temporanea diversa (*FASE04*).

1. Seleziona **Sostituisci ubicazione** per sostituire l'ubicazione di gestione temporanea suggerita.
1. Nel campo **Eccezioni lavoro**, specifica *Corsia gestione temporanea cambiata*.
1. Nel campo **Ubicazione** immetti una nuova ubicazione di gestione temporanea (*STAGE04*).
1. Conferma l'inserimento. Viene visualizzato il messaggio "Lavoro completato".
1. Vai a **Gestione magazzino \> Lavoro \> Tutti i lavori**.
1. Apri l'ID lavoro per la prima spedizione. Verifica che l'ubicazione di gestione temporanea non sia stata aggiornata alla nuova ubicazione di gestione temporanea (*FASE04*) perché la riga di stoccaggio rimanente aperta non corrisponde alla riga del modello di lavoro della riga di stoccaggio completata.
1. Apri l'ID lavoro per la seconda spedizione. Verifica che l'ubicazione di gestione temporanea non sia stata aggiornata alla nuova ubicazione di gestione temporanea (*FASE04*) perché l'ubicazione di gestione temporanea non corrisponde all'ubicazione di gestione temporanea della riga di stoccaggio completata. In altre parole, la riga di lavoro di stoccaggio completata e la riga di lavoro aperta rimanente hanno diverse ubicazioni di gestione temporanea e, in questo caso, vengono aggiornate solo le righe che hanno le stesse ubicazioni di gestione temporanea.
1. Apri l'ID lavoro per la terza spedizione. Verifica che l'ubicazione di gestione temporanea sia stata aggiornata alla nuova ubicazione di gestione temporanea (*STAGE04*).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
