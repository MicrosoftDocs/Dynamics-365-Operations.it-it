---
title: Eseguire query sui dati usando le deviazioni dell'app per dispositivi mobili Warehouse Management
description: Questo articolo descrive come configurare voci di menu di dispositivo mobile per richieste di dati e usarle come parte delle deviazioni.
author: perlynne
ms.date: 08/01/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c3ea53379badb3cb2ed71b7f102956d71c3f047a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220540"
---
# <a name="query-data-using-warehouse-management-mobile-app-detours"></a>Eseguire query sui dati usando le deviazioni dell'app per dispositivi mobili Warehouse Management

[!include [banner](../includes/banner.md)]

## <a name="feature-introduction"></a>Introduzione alla funzionalità

Fornendo funzionalità di scansione di codici a barre, l'app per dispositivi mobili Warehouse Management ti offre un modo semplice e preciso di acquisire dati nell'ambito dei processi di magazzino. Tuttavia, i codici a barre a volte vengono danneggiati e diventano illeggibili oppure le informazioni sui dati necessarie potrebbero non esistere in forma di codice a barre nei flussi del processo aziendale. In questi casi, l'immissione manuale dei dati può richiedere molto tempo e può anche comportare l'acquisizione di dati errati. Il risultato può essere un'efficacia ridotta e un livello di servizio inferiore.

Utilizzando un processo di richiesta di dati flessibile, i lavoratori possono cercare facilmente le informazioni necessarie come parte dei flussi dell'app per dispositivi mobili Warehouse Management incorporata e applicare opzioni di filtro di modo che vengano mostrati solo i dati pertinenti. Pertanto, la selezione manuale risulta più rapida e precisa.

Ad esempio, nel flusso di entrata dell'ordine fornitore, un numero di ordine fornitore è necessario per l'inventario in arrivo. Come parte di questo processo, puoi facilmente configurare voci di menu per fornire una visualizzazione elenco con schede dei numeri di ordine fornitore pertinenti. In questo modo, puoi continuare il flusso di entrata utilizzando un approccio rapido. Questo articolo fornisce scenari di esempio, ma la funzionalità può essere usata anche in tutti i flussi dell'app per dispositivi mobili Warehouse Management.

## <a name="turn-on-the-data-inquiry-flow-feature-and-its-prerequisites"></a>Attivare la funzionalità del flusso di richiesta di dati e i relativi prerequisiti

Prima di poter utilizzare la funzionalità descritta in questo articolo, devi completare la procedura seguente per attivare le funzionalità necessarie.

1. Vai a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**. Per ulteriori informazioni su come utilizzare l'area di lavoro **Gestione funzionalità**, vedi [Panoramica di Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Attiva la funzionalità elencata nel modo seguente:

    - **Modulo:** *Gestione Magazzino*
    - **Nome funzionalità:** *Istruzioni per i passaggi dell'app di magazzino*

    Questa funzione è un prerequisito della funzionalità *Flusso di richiesta di dati dell'app Warehouse Management*. Per ulteriori informazioni sulla funzionalità *Istruzioni per i passaggi dell'app di magazzino*, vedi [Personalizzare i titoli dei passi e le istruzioni per l'applicazione mobile Warehouse Management](mobile-app-titles-instructions.md).

1. Attiva la funzionalità elencata nel modo seguente:

    - **Modulo:** *Gestione Magazzino*
    - **Nome funzione:** *Deviazioni dell'app Warehouse Management*

    Questa funzione è un prerequisito della funzionalità *Flusso di richiesta di dati dell'app Warehouse Management*. Per ulteriori informazioni sulla funzionalità *Deviazioni dell'app Warehouse Management*, vedi [Configurare le deviazioni per i passaggi nelle voci di menu del dispositivo mobile](warehouse-app-detours.md).

1. Se la funzionalità *Deviazioni dell'app Warehouse Management* non è attivata, aggiorna i nomi dei campi nell'app per dispositivi mobili Warehouse Management andando a **Warehouse Management \> Impostazioni \> Dispositivo mobile \> Nomi campo app magazzino** e selezionando **Crea impostazione predefinita**. Ripeti questo passaggio per ogni persona giuridica (società) in cui utilizzi l'app per dispositivi mobili Warehouse Management. Per ulteriori informazioni, vedi [Configurare i campi per l'app per dispositivi mobili Gestione magazzino](configure-app-field-names-priorities-warehouse.md).
1. Attiva la funzionalità elencata nel modo seguente:

    - **Modulo:** *Gestione Magazzino*
    - **Nome funzionalità**: *Flusso di richiesta di dati dell'app Warehouse Management*

    Questa funzionalità è descritta in questo articolo.

## <a name="example-scenarios"></a>Scenari di esempio

In questo articolo vengono utilizzati scenari di esempio per mostrare come è possibile utilizzare la funzionalità *Flusso di richiesta di dati dell'app Warehouse Management* per migliorare il flusso di entrata degli acquisti. Gli scenari utilizzano i dati di esempio standard, che includono un flusso denominato *Entrata acquisti*. All'inizio del flusso viene chiesto ai lavoratori di identificare un numero di ordine fornitore. Per aiutare i lavoratori a identificare più facilmente l'ordine fornitore, migliorerai la prima pagina del flusso aggiungendo le seguenti nuove opzioni di query come [deviazioni](warehouse-app-detours.md):

- **Cerca ordini fornitore per fornitore**: apre una pagina che richiede ai lavoratori di immettere un nome di fornitore o parte di un nome fornitore. È possibile utilizzare caratteri jolly. Ad esempio, se un lavoratore prevede una consegna in entrata in giornata da un fornitore il cui nome include *Tailspin*, può immettere **Tail\*** per visualizzare un set di schede per ordini fornitore aperti che includono tale termine. Ogni scheda presenta vari campi che forniscono informazioni su ciascun ordine fornitore. Oltre al nome del fornitore, puoi progettare le schede di modo che mostrino il numero di conto del fornitore, la data di consegna e lo stato del documento.
- **Cerca ordini fornitore per oggi**: apre una pagina che non richiede ai lavoratori di immettere dati ma che include filtri preconfigurati (come la data odierna). La pagina mostra quindi un set di schede che corrispondono al filtro. I lavoratori procedono selezionando una scheda per l'ordine fornitore da utilizzare per registrare gli articoli di magazzino.
- **Cerca ordini fornitore per articolo**: apre una pagina che richiede ai lavoratori di eseguire la scansione del codice a barre di qualsiasi articolo nell'inventario arrivato. Il flusso elenca quindi tutti gli ordine fornitore aperti che contengono righe per il numero di articolo scansionato. Per le situazioni in cui non è possibile leggere un codice a barre, puoi aggiungere un'altra ricerca di deviazione a questa pagina che consenta ai lavoratori di cercare numeri di articolo in un ordine fornitore specifico.

In ogni caso, il lavoratore identifica un ordine fornitore selezionando una scheda e viene quindi visualizzata di nuovo la prima pagina, che mostra il numero dell'ordine fornitore selezionato. Il lavoratore può quindi continuare il flusso di registrazione degli articoli di magazzino in entrata.

## <a name="enable-sample-data"></a>Abilitare dati di esempio

Per elaborare gli scenari di esempio descritti in questo articolo, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. Inoltre, devi selezionare la persona giuridica *USMF* (società) prima di iniziare.

## <a name="configure-the-mobile-device-menu-items"></a>Configurare le voci di menu di dispositivo mobile

Per creare ognuna delle nuove opzioni di query che devi aggiungere alla prima pagina del flusso, devi configurarla come voce di menu di dispositivo mobile. Successivamente, renderai disponibili le opzioni di query come deviazioni al flusso *Entrata acquisti*.

### <a name="create-the-look-up-pos-by-vendor-menu-item"></a>Creare la voce di menu "Cerca ordini fornitore per fornitore"

Crea la voce di menu **Cerca ordini fornitore per fornitore** procedendo come segue.

1. Passa a **Gestione magazzino \> Impostazioni \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro Azioni, seleziona **Nuovo** per aggiungere una voce di menu di dispositivo mobile.
1. Imposta i seguenti valori per la nuova voce di menu:

    - **Nome voce di menu**: *Cerca ordini fornitore per fornitore*
    - **Titolo**: *Cerca ordini fornitore per fornitore*
    - **Modalità:** *Indiretta*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Codice attività**: *Richiesta di dati*
    - **Utilizza guida processo**: *Sì* (questo valore viene selezionato automaticamente).
    - **Nome tabella**: *PurchTable* (vuoi cercare numeri di ordine fornitore in questa tabella).

1. Nel riquadro Azioni seleziona **Modifica query** per definire una query basata sulla tabella di base selezionata (in questo caso, la tabella degli ordini fornitore).
1. Nell'editor di query, nella scheda **Intervallo**, aggiungi le seguenti righe alla griglia:

    | Tabella | Tabella derivata | Campo | Criteri |
    |---|---|---|---|
    | Ordine fornitore | Ordine fornitore | Stato ordine fornitore | Ordine aperto |
    | Ordine fornitore | Ordine fornitore | Data di consegna | (dayRange(-10,10)) |
    | Ordine fornitore | Ordine fornitore | Nome fornitore | |

1. Seleziona **OK**.

    In questo esempio, la nuova voce di menu è configurata per trovare ordini fornitore aperti che dovrebbero arrivare in qualsiasi momento tra 10 giorni nel passato e 10 giorni nel futuro.

    Nella query, la colonna **Criteri** per *Nome fornitore* è stata lasciata vuota. Pertanto, i lavoratori potranno specificare questo valore mentre utilizzano l'app per dispositivi mobili Warehouse Management.

    Se vuoi specificare come verrà ordinato l'elenco, puoi impostare l'ordinamento nella scheda **Ordinamento**.

1. Oltre a definire la query, devi selezionare quali campi verranno visualizzati nelle schede della pagina di elenco delle richieste. A questo proposito, nel riquadro Azioni, seleziona **Elenco campi**.
1. Nella pagina **Elenco campi**, imposta i seguenti valori:

    - **Campo di visualizzazione 1**: *PurchId* (questo campo verrà mostrato come intestazione di ogni scheda).
    - **Campo di visualizzazione 2:** *PurchStatus*
    - **Campo di visualizzazione 3:** *PurchName*
    - **Campo di visualizzazione 4:** *OrderAccount*
    - **Campo di visualizzazione 5:** *DeliveryDate*
    - **Campo di visualizzazione 6:** *displayDocumentStatus()* (questo valore è un metodo di visualizzazione, come indica "()" alla fine).

1. Nel riquadro azioni selezionare **Salva**. Quindi, chiudere la pagina.

### <a name="create-the-look-up-pos-for-today-menu-item"></a>Creare la voce di menu "Cerca ordini fornitore per oggi"

Crea la voce di menu **Cerca ordini fornitore per oggi** procedendo come segue.

1. Passa a **Gestione magazzino \> Impostazioni \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro Azioni, seleziona **Nuovo** per aggiungere una voce di menu di dispositivo mobile.
1. Imposta i seguenti valori per la nuova voce:

    - **Nome voce di menu**: *Cerca ordini fornitore per oggi*
    - **Titolo:** *Cerca ordini fornitore per oggi*
    - **Modalità:** *Indiretta*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Codice attività**: *Richiesta di dati*
    - **Utilizza guida processo**: *Sì* (questo valore viene selezionato automaticamente).
    - **Nome tabella**: *PurchTable* (vuoi cercare numeri di ordine fornitore in questa tabella).

1. Nel riquadro Azioni seleziona **Modifica query** per definire una query basata sulla tabella di base selezionata (in questo caso, la tabella degli ordini fornitore).
1. Nell'editor di query, nella scheda **Intervallo**, aggiungi le seguenti righe alla griglia:

    | Tabella | Tabella derivata | Campo | Criteri |
    |---|---|---|---|
    | Ordine fornitore | Ordine fornitore | Stato ordine fornitore | Ordine aperto |
    | Ordine fornitore | Ordine fornitore | Data di consegna | (Day(0)) |

1. Seleziona **OK**.

    In questo esempio, la nuova voce di menu è configurata per trovare ordini fornitore aperti che dovrebbero arrivare oggi.

    Se vuoi specificare come verrà ordinato l'elenco, puoi impostare l'ordinamento nella scheda **Ordinamento**.

1. Oltre a definire la query, devi selezionare quali campi verranno visualizzati nelle schede della pagina di elenco delle richieste. A questo proposito, nel riquadro Azioni, seleziona **Elenco campi**.
1. Nella pagina **Elenco campi**, imposta i seguenti valori:

    - **Campo di visualizzazione 1:** *PurchName* (questo campo verrà mostrato come intestazione di ogni scheda).
    - **Campo di visualizzazione 2:** *PurchId*
    - **Campo di visualizzazione 3:** *PurchStatus*
    - **Campo di visualizzazione 4:** *DlvMode*
    - **Campo di visualizzazione 5:** *DlvTerm*
    - **Campo di visualizzazione 6:** *OrderAccount*
    - **Campo di visualizzazione 7:** *VendorName()* (questo valore è un metodo di visualizzazione, come indica "()" alla fine).

1. Nel riquadro azioni selezionare **Salva**. Quindi, chiudere la pagina.

### <a name="create-the-look-up-pos-by-item-menu-item"></a>Creare la voce di menu "Cerca ordini fornitore per articolo"

Crea la voce di menu **Cerca ordini fornitore per articolo** procedendo come segue.

1. Passa a **Gestione magazzino \> Impostazioni \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro Azioni, seleziona **Nuovo** per aggiungere una voce di menu di dispositivo mobile.
1. Imposta i seguenti valori per la nuova voce:

    - **Nome voce di menu:** *Cerca ordini fornitore per articolo*
    - **Titolo:** *Cerca ordini fornitore per articolo*
    - **Modalità:** *Indiretta*

1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Codice attività**: *Richiesta di dati*
    - **Utilizza guida processo**: *Sì* (questo valore viene selezionato automaticamente).
    - **Nome tabella:** *PurchLine* (vuoi cercare numeri di ordine fornitore in base al numero di articolo tramite i dati della riga.)

1. Nel riquadro Azioni seleziona **Modifica query** per definire una query basata sulla tabella di base selezionata (in questo caso, la tabella delle righe dell'ordine fornitore, ma puoi utilizzare qualsiasi valore correlato all'intestazione unendo *PurchTable*).
1. Nell'editor di query, nella scheda **Intervallo**, aggiungi le seguenti righe alla griglia:

    | Tabella | Tabella derivata | Campo | Criteri |
    |---|---|---|---|
    | Righe ordine fornitore | Righe ordine fornitore | Stato riga | Ordine aperto |
    | Righe ordine fornitore | Righe ordine fornitore | Data di consegna | (dayRange(-10,10)) |
    | Righe ordine fornitore | Righe ordine fornitore | Numero articolo | |

1. Seleziona **OK**.

    In questo esempio, la nuova voce di menu è configurata per trovare righe di ordini fornitore aperti che dovrebbero arrivare in qualsiasi momento tra 10 giorni nel passato e 10 giorni nel futuro.

    Nella query, la colonna **Criteri** per *Numero articolo* è stata lasciata vuota. Pertanto, i lavoratori potranno specificare questo valore mentre utilizzano l'app per dispositivi mobili Warehouse Management.

    Se vuoi specificare come verrà ordinato l'elenco, puoi impostare l'ordinamento nella scheda **Ordinamento**.

1. Oltre a definire la query, devi selezionare quali campi verranno visualizzati nelle schede della pagina di elenco delle richieste. A questo proposito, nel riquadro Azioni, seleziona **Elenco campi**.
1. Nella pagina **Elenco campi**, imposta i seguenti valori:

    - **Campo di visualizzazione 1:** *PurchId* (questo valore di campo verrà usato come intestazione di ogni scheda).
    - **Campo di visualizzazione 2:** *VendAccount*
    - **Campo di visualizzazione 3:** *PurchQty*
    - **Campo di visualizzazione 4:** *PurchUnit*
    - **Campo di visualizzazione 5:** *PurchStatus*

1. Nel riquadro azioni selezionare **Salva**. Quindi, chiudere la pagina.

## <a name="add-the-new-mobile-device-menu-items-to-a-menu"></a>Aggiungere le nuove voci di menu di dispositivo mobile a un menu

Le tre nuove voci di menu di dispositivo mobile sono ora pronte per essere aggiunte al menu del dispositivo mobile. Questa attività deve essere completata affinché le voci di menu possano essere utilizzate come parte di un processo di deviazione. In questo esempio, creerai un nuovo sottomenu e vi aggiungerai le nuove voci di menu.

1. Accedi a **Gestione magazzino \> Impostazioni \> Dispositivo mobile \> Menu del dispositivo mobile**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Imposta i seguenti valori nell'intestazione del nuovo record:

    - **Nome:** *Richiedi informazioni*
    - **Descrizione:** *Richiesta di informazioni*

1. Nell'elenco **Menu e voci di menu disponibili**, seleziona la prima voce di menu di dispositivo mobile appena creata. Quindi seleziona il pulsante freccia DESTRA per spostare quella voce di menu nell'elenco **Struttura menu**.
1. Ripeti il passaggio precedente per le altre due nuove voci di menu.
1. Nel riquadro elenco a sinistra, seleziona il menu **Principale**.
1. Nell'elenco **Menu e voci di menu disponibili**, scorri verso il basso fino alla sezione **Menu** e seleziona il nuovo menu **Richiedi informazioni**. Quindi seleziona il pulsante freccia DESTRA per spostare quella voce di menu nell'elenco **Struttura menu**.

## <a name="configure-detours-in-your-mobile-device-steps"></a>Configurare deviazioni nei passaggi per dispositivo mobile

Per completare la configurazione, ora devi utilizzare la configurazione delle deviazioni nella pagina **Passaggi per dispositivi mobili** per aggiungere le tre nuove voci di menu di dispositivo mobile al passaggio di identificazione di ordini fornitore esistente nel flusso *Entrata acquisti*.

1. Vai a **Gestione magazzino \> Impostazioni > Dispositivo mobile \> Passaggi per dispositivo mobile**.
1. Nel campo **Filtro**, immetti *PONum*. Quindi seleziona *ID passaggio: "PONum"* nell'elenco a discesa.
1. Con il record trovato selezionato nella griglia, seleziona **Aggiungi configurazione passaggio** nel riquadro Azioni. Nella finestra di dialogo a discesa visualizzata, imposta il campo **Voce di menu** su *Entrata acquisti*. Quindi seleziona **OK** per chiudere la finestra di dialogo.
1. Nella pagina dei dettagli per la nuova configurazione di passaggi (**Entrata acquisti : PONum**), nella Scheda dettaglio **Deviazioni disponibili (voci di menu)**, seleziona **Aggiungi** nella barra degli strumenti.
1. Nella finestra di dialogo **Aggiungi deviazione**, trova e seleziona la voce di menu **Cerca ordini fornitore per fornitore** creata in precedenza.
1. Seleziona **OK** per chiudere la finestra di dialogo e aggiungere la voce di menu selezionata all'elenco delle deviazioni.
1. Seleziona la nuova deviazione, quindi seleziona **Seleziona i campi da inviare** nella barra degli strumenti.
1. Nella finestra di dialogo **Seleziona i campi da inviare**, non aggiungere nulla alla sezione **Invia da entrata acquisti** in quanto non vuoi passare alcun valore alla voce di menu della deviazione. Tuttavia, nella sezione **Ripristina da Cerca ordini fornitore per fornitore**, imposta il seguente valore per la riga vuota che è già stata aggiunta lì:

    - **Copia da Cerca ordini fornitore per fornitore:** *Ordine fornitore*
    - **Incolla in Entrata acquisti:** *Ordine fornitore*

1. Selezionare **OK** per chiudere la finestra di dialogo.
1. Ripeti i passaggi da 4 a 9 per le altre due nuove voci di menu (**Cerca ordini fornitore per oggi** e **Cerca ordini fornitore per articolo**). Per quanto riguarda la voce di menu **Cerca ordini fornitore per fornitore**, non vuoi inviare dati a tali deviazioni, ma restituire un numero di ordine fornitore.
1. Chiudi la pagina.

## <a name="try-a-purchase-receiving-flow-that-has-a-data-inquiry-as-part-of-a-detour"></a>Provare un flusso di entrata acquisti che include una richiesta di dati come parte di una deviazione

Segui questi passaggi per testare la nuova configurazione dell'app per dispositivi mobili.

1. Crea vari ordini fornitore che includono righe per il magazzino 51.
1. Passare a un dispositivo mobile o un emulatore che esegue l'app per dispositivi mobili Gestione magazzino e accedere al magazzino 51 utilizzando *51* come ID utente e *1* come password.
1. Nel menu dell'app per dispositivi mobili, seleziona **In entrata** e quindi **Entrata acquisti**.

    Dovresti vedere la pagina seguente, che include le tre nuove voci di menu.

    ![Entrata acquisti che utilizza il numero di ordine fornitore.](media/wma-purchase-receive-po-num-with-detours.png "Entrata acquisti che utilizza il numero di ordine fornitore")

1. Prova le differenti funzionalità e tieni presente che puoi restituire un numero di ordine fornitore selezionando una delle schede nell'elenco.

    ![Entrata acquisti che utilizza la ricerca di ordini fornitore per fornitore, esempio 1.](media/wma-purchase-receive-lookup-po-vendor-keyin-detours.png "Entrata acquisti che utilizza la ricerca di ordini fornitore per fornitore, esempio 1")

    ![Entrata acquisti che utilizza la ricerca di ordini fornitore per fornitore, esempio 2.](media/wma-purchase-receive-lookup-po-vendor-detours.png "Entrata acquisti che utilizza la ricerca di ordini fornitore per fornitore, esempio 2")

> [!TIP]
> Anziché eseguire il flusso di entrata eseguendo una ricerca dalla voce di menu **Entrata acquisti**, puoi iniziare da un flusso di richiesta (**Principale \> Richiedi informazioni \> Cerca ordini fornitore per fornitore**) e invocare una deviazione per eseguire il flusso desiderato selezionando una delle schede nell'elenco. Per utilizzare questo approccio, puoi definire una deviazione nella pagina **Passaggi per dispositivo mobile** per il passaggio il cui **ID passaggio** è *GenericDataInquiryList*. Poiché questo flusso è un flusso di deviazione, non puoi richiamare più deviazioni dallo stesso. Pertanto, quando arrivi alla schermata di immissione del numero di articolo, ad esempio, la ricerca non sarà disponibile poiché il sistema attualmente supporta un solo livello di deviazioni.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
