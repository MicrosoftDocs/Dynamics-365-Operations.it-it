---
title: Configurare le deviazioni per i passaggi nelle voci di menu del dispositivo mobile
description: Questo articolo descrive come configurare le deviazioni per le voci di menu in modo che i lavoratori possano sospendere l'attività corrente, eseguire un'altra attività e quindi tornare all'attività originale senza perdere alcuna informazione.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 50f899cd7f28a4b7fd23db5f049de02896e8d8e9
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336127"
---
# <a name="configure-detours-for-steps-in-mobile-device-menu-items"></a>Configurare le deviazioni per i passaggi nelle voci di menu del dispositivo mobile

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Le caratteristiche che sono descritte in questo articolo si applicano solo alla nuova applicazione mobile Warehouse Management. Non riguardano la vecchia app del magazzino, che ora è deprecata.

Questo articolo descrive come configurare le deviazioni per le voci di menu in modo che i lavoratori possano "sospendere" l'attività corrente, eseguire un'altra attività e quindi tornare all'attività originale senza perdere alcuna informazione.

Una deviazione è una voce di menu separata che può essere aperta da un passaggio in un'attività principale. Al termine della deviazione, il lavoratore torna nel luogo in cui ha lasciato l'attività principale. Durante la configurazione, specifichi la voce di menu che deve fungere da deviazione. Puoi anche selezionare quali valori di campo dell'attività principale devono essere automaticamente inoltrati (copiati) alla deviazione e inseriti. Pertanto, è necessario comprendere in quale punto del flusso di attività vuoi che la deviazione sia disponibile per i lavoratori. È inoltre necessario assicurarsi che le informazioni da copiare nella deviazione siano disponibili per quel passaggio del flusso di attività.

## <a name="enable-detours-in-your-system"></a>Abilitare le deviazioni nel tuo sistema

Prima di poter configurare le deviazioni per i passaggi nelle voci di menu del dispositivo mobile, è necessario completare la procedura seguente per abilitare le funzionalità richieste e generare i nomi dei campi richiesti nell'app per dispositivi mobili Warehouse Management.

1. Vai a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Assicurati che la funzionalità *Istruzioni per i passaggi dell'app di magazzino* sia attivata per il tuo sistema. A partire dalla versione 10.0.29 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. Per ulteriori informazioni sulla funzionalità *Istruzioni per i passaggi dell'app di magazzino*, vedi [Personalizzare i titoli dei passi e le istruzioni per l'applicazione mobile Warehouse Management](mobile-app-titles-instructions.md). Questa funzione è un prerequisito per la funzionalità *Deviazioni dell'app Warehouse Management*.
1. Attiva la funzionalità *Deviazioni dell'app Warehouse Management*. Questa funzionalità è descritta in questo articolo. A partire dalla versione 10.0.29 di Supply Chain Management, è attivata per impostazione predefinita.
1. Se la funzionalità *Deviazioni dell'app Warehouse Management* non è attivata, aggiorna i nomi dei campi nell'app per dispositivi mobili Warehouse Management andando a **Warehouse Management \> Impostazioni \> Dispositivo mobile \> Nomi campo app magazzino** e selezionando **Crea impostazione predefinita**. Ripeti questo passaggio per ogni persona giuridica (società) in cui utilizzi l'app per dispositivi mobili Warehouse Management. Per ulteriori informazioni, vedi [Configurare i campi per l'app per dispositivi mobili Gestione magazzino](configure-app-field-names-priorities-warehouse.md).

## <a name="configure-a-detour-from-a-menu-specific-override"></a>Configurare una deviazione da un override specifico del menu

Utilizza la procedura seguente per impostare una deviazione da un override specifico del menu.

1. Crea un override specifico del menu per il menu pertinente e procedi come descritto in [Personalizzare i titoli dei passaggi e le istruzioni per l'app per dispositivi mobili Warehouse Management](mobile-app-titles-instructions.md).
1. Trova la combinazione di valori **ID passo** e **Nome voce di menu** che vuoi modificare e quindi seleziona il valore nella colonna **ID passo** .
1. Nella pagina che appare, nella scheda dettaglio **Deviazioni disponibili (voci di menu)** puoi specificare la voce di menu che deve fungere da deviazione. Puoi anche selezionare quali valori di campo dell'attività principale devono essere automaticamente inoltrati alla e dalla deviazione. Per esempi che mostrano come usare queste impostazioni, vedi gli scenari più avanti in questo articolo.

## <a name="sample-scenario-1-sales-picking-where-a-location-inquiry-acts-as-a-detour"></a>Scenario di esempio 1: prelievo vendite in cui una richiesta di posizione funge da deviazione

Questo scenario mostra come configurare una richiesta di posizione come una deviazione in un flusso di attività di prelievo vendite diretto dal lavoratore. Questa deviazione consentirà ai lavoratori di cercare tutte le targhe nella posizione da cui stanno prelevando e scegliere la targa che desiderano utilizzare per completare il prelievo. Questo tipo di deviazione può essere utile se il codice a barre è danneggiato e quindi illeggibile dal dispositivo scanner. In alternativa, può essere utile se un lavoratore deve sapere ciò che è effettivamente disponibile nel sistema. Tieni presente che questo scenario funziona solo se scegli da ubicazioni controllate da targa.

### <a name="enable-sample-data"></a>Abilitare dati di esempio

Per usare i record e i valori di esempio specificati in questo scenario, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-1"></a>Creare un override specifico del menu e configurare la deviazione per lo scenario 1

In questa procedura, configurerai una deviazione per la voce di menu **Prelievo vendite** nel passaggio targa.

1. Vai alla **gestione del magazzino \> Impostazione \> Dispositivo mobile \> Passi per il dispositivo mobile**.
1. Trova e seleziona l'ID del passaggio denominato *LicensePlateId*.
1. Nel riquadro delle azioni, seleziona **Aggiungi configurazione del passo**.
1. Nella finestra di dialogo a discesa, utilizza il campo **Voce di menu** per trovare e selezionare *Prelievo vendite*.
1. Selezionare **OK**.
1. Viene visualizzata la pagina dei dettagli per l'override appena creato. Nella scheda dettaglio **Deviazioni disponibili (voci di menu)** seleziona **Aggiungi** sulla barra degli strumenti.
1. Nella finestra di dialogo **Aggiungi deviazione** seleziona **Richiesta di ubicazione** come la deviazione che sarà resa disponibile nell'app per dispositivi mobili Warehouse Management.
1. Selezionare **OK**.
1. Nella Scheda dettaglio **Deviazioni disponibili (voci di menu)**, seleziona la deviazione appena aggiunta, quindi seleziona **Seleziona i campi da inviare** sulla barra degli strumenti.
1. Nella finestra di dialogo **Seleziona i campi da inviare** specifica le informazioni che devono essere inviate da e verso la deviazione. In questo scenario, consenti ai lavoratori di utilizzare l'ubicazione da cui devono scegliere come input per la deviazione della richiesta di ubicazione. Pertanto, nella sezione **Invia da prelievo vendite** seleziona **Aggiungi** sulla barra degli strumenti per aggiungere una riga alla griglia. Quindi imposta i seguenti valori per la nuova riga:

    - **Copia da prelievo vendite:** *Ubicazione*
    - **Incolla in richiesta ubicazione:** *Ubicazione*

1. Poiché la deviazione in questo scenario è configurata sul passaggio targa, sarà utile se i lavoratori possono riportare la targa dalla richiesta al flusso principale. Pertanto, nella sezione **Restituisci da richiesta ubicazione** seleziona **Aggiungi** sulla barra degli strumenti per aggiungere una riga alla griglia. Quindi imposta i seguenti valori per la nuova riga:

    - **Copia da richiesta ubicazione:** *Targa*
    - **Incolla in prelievo vendite:** *Targa*

1. Selezionare **OK**.

La deviazione è ora completamente configurata. Un pulsante per avviare la deviazione **Richiesta ubicazioine** apparirà ora sul passaggio targa per la voce di menu **Prelievo vendite**.

### <a name="complete-a-sales-pick-on-a-mobile-device-and-use-the-detour"></a>Completare un prelievo vendite su un dispositivo mobile e usa la deviazione

In questa procedura, completerai un prelievo vendite utilizzando l'app per dispositivi mobili Warehouse Management. Utilizzerai la deviazione appena configurata per trovare la targa che utilizzerai per completare il passaggio prelievo.

1. In Microsoft Dynamics 365 Supply Chain Management, crea un ordine cliente che richiederà un passaggio di prelievo per prelevare da un'ubicazione in cui è tracciata la targa. Rilascia quindi l'ordine cliente al magazzino. Prendi nota dell'ID lavoro generato.
1. Apri l'app per dispositivi mobili Warehouse Management e accedi al magazzino 24. (Nei dati demo standard, accedere utilizzando *24* come ID utente e *1* come password.)
1. Seleziona il menu **Uscita** quindi seleziona la voce di menu **Prelievo vendite**.
1. Seguire le istruzioni per l'immissione dei dati sullo schermo per inserire l'ID lavoro generato nel passaggio 1.
1. Nel passaggio che contiene il testo **Scansiona una targa**, apri il menu delle azioni. Dovresti vedere un nuovo pulsante etichettato **Richiesta ubicazione**. Una freccia nell'angolo in alto a sinistra indica che il pulsante avvierà una deviazione. Seleziona **Richiesta ubicazione**.
1. La deviazione è iniziata. Nella pagina successiva, conferma l'ubicazione che è stata copiata dal flusso principale.
1. Nell'elenco delle targhe disponibili nell'ubicazione, tocca la targa che desideri copiare di nuovo nel flusso principale. Quindi seleziona il pulsante **Restituisci**.
1. Sei tornato al flusso principale di prelievo vendite e la targa è stata copiata dalla deviazione. Conferma il valore per proseguire con il passaggio successivo.
1. È ora possibile completare il resto del flusso standard immettendo le istruzioni di inserimento dati richieste.

Il lavoro di magazzino è ora completato. L'operatore ha aperto una deviazione per eseguire un'attività secondaria (richiesta ubicazione) senza perdere il punto nell'attività principale e ha restituito le informazioni necessarie per completare l'attività principale.

## <a name="sample-scenario-2-item-inquiry-with-movement-and-adjustment-detours"></a>Scenario di esempio 2: Richiesta di articolo con deviazioni di movimento e rettifica

Questo scenario mostra come configurare il movimento e le rettifiche come deviazioni multiple nel flusso di attività di richiesta di ubicazione. Questa capacità può essere utile in situazioni in cui un lavoratore arriva in un'ubicazione, rileva che l'inventario nell'ubicazione è diverso da quello registrato nel sistema e deve quindi rettificare o spostare le merci.

Puoi sostituire la richiesta di ubicazione con una richiesta di targa o una richiesta di articolo come necessario.

### <a name="enable-sample-data"></a>Abilitare dati di esempio

Per usare i record e i valori di esempio specificati in questo scenario, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/fin-ops/get-started/demo-data.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-2"></a>Creare un override specifico del menu e configurare la deviazione per lo scenario 2

In questa procedura, configurerai una deviazione per la voce di menu **Prelievo vendite** nel passaggio targa.

1. Vai alla **gestione del magazzino \> Impostazione \> Dispositivo mobile \> Passi per il dispositivo mobile**.
1. Trova e seleziona l'ID del passaggio denominato *LocationInquiryList*.

    > [!NOTE]
    > Per utilizzare una richiesta di articolo invece di una richiesta di ubicazione, seleziona una riga in cui è denominato l'ID del passaggio *ItemInquiryList*. Per utilizzare una richiesta di targa, seleziona una riga in cui è denominato l'ID del passaggio *LPInquiryList*.

1. Nel riquadro delle azioni, seleziona **Aggiungi configurazione del passo**.
1. Nella finestra di dialogo a discesa, utilizza il campo **Voce di menu** per trovare e selezionare *Richiesta ubicazione*.
1. Selezionare **OK**.
1. Viene visualizzata la pagina dei dettagli per l'override appena creato. Nella scheda dettaglio **Deviazioni disponibili (voci di menu)** seleziona **Aggiungi** sulla barra degli strumenti.
1. Nella finestra di dialogo **Aggiungi deviazione** seleziona **Movimento** come la deviazione che sarà resa disponibile nell'app per dispositivi mobili Warehouse Management.
1. Selezionare **OK**.
1. Nella Scheda dettaglio **Deviazioni disponibili (voci di menu)**, seleziona la deviazione appena aggiunta, quindi seleziona **Seleziona i campi da inviare** sulla barra degli strumenti.
1. Nella finestra di dialogo **Seleziona i campi da inviare** specifica le informazioni che devono essere inviate da e verso la deviazione. In questo scenario, ti aspetti che i lavoratori cerchino ubicazioni controllate dalle targhe. Pertanto, sarà utile copiare la targa dalla richiesta nella deviazione **Movimento**. Nella sezione **Invia da prelievo vendite** seleziona **Aggiungi** sulla barra degli strumenti per aggiungere una riga alla griglia. Quindi imposta i seguenti valori per la nuova riga:

    - **Copia da richiesta ubicazione:** *Ubicazione*
    - **Incolla in movimento:** *Loc / LP*

    In questa deviazione, non ti aspetti che le informazioni vengano ricopiate, perché il flusso principale era una richiesta in cui non sono necessari passaggi aggiuntivi.

1. Selezionare **OK**.

La deviazione è ora completamente configurata. Un pulsante per avviare la deviazione **Movimento** apparirà ora sul passaggio targa per la voce di menu **Richiesta ubicazione**.

### <a name="do-a-location-inquiry-on-a-mobile-device-and-use-the-detour"></a>Eseguire una richiesta ubicazione su un dispositivo mobile e usa la deviazione

In questa procedura, esegui una richiesta ubicazione utilizzando l'app per dispositivi mobili Warehouse Management. Utilizzerai quindi la deviazione per completare un movimento di merci.

1. Apri l'app per dispositivi mobili Warehouse Management e accedi al magazzino 24. (Nei dati demo standard, accedere utilizzando *24* come ID utente e *1* come password.)
1. Seleziona il menu **Inventario** quindi seleziona la voce di menu **Richiesta ubicazione**.
1. Inserisci un'ubicazione per cui chiedere informazioni, ad esempio *FL-001*.
1. Quando viene visualizzato l'elenco, tocca e tieni premuta una delle schede per mostrare le deviazioni disponibili.
1. Seleziona **Movimento**.
1. Nota che la targa è stata copiata dalla scheda selezionata. Conferma il valore.
1. Ora puoi seguire il flusso di attività standard per completare il movimento. Al termine del lavoro, apri il menu delle azioni e seleziona **Annulla**.
1. Torni alla pagina **Richiesta ubicazione**. Nota che i valori non vengono aggiornati automaticamente. Pertanto, è necessario aggiornare manualmente la pagina per visualizzare le modifiche della deviazione del movimento.
