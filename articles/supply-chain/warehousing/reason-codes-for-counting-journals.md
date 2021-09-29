---
title: Codici motivo conteggio scorte
description: In questo argomento viene descritto come impostare e applicare i codici motivo ai fini delle attività di conteggio
author: perlynne
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 4c178ddf342b13a0ef8fee8b8b958554a9a31069
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500592"
---
# <a name="reason-codes-for-inventory-counting"></a>Codici motivo conteggio scorte

[!include [banner](../includes/banner.md)]

I codici motivo consentono di analizzare i risultati di un processo di conteggio e le eventuali discrepanze che si verificano durante tale processo. È possibile specificare il motivo del conteggio, ad esempio un pallet rotto o una correzione dello scorte basata su campioni di inventario. Allo stesso tempo, puoi utilizzare la funzionalità di rettifica per registrare il valore delle rettifiche di scorte disponibili nel conto di contropartita appropriato, in base al motivo di ciascuna rettifica di scorte.

## <a name="recommendation"></a>Suggerimento

Prima di impostare il sistema, si consiglia di definire una strategia per la gestione dei codici motivo. Ad esempio, provare a rispondere alle domande seguenti:

- I codici motivo devono essere obbligatori nei magazzini?
- I codici motivo devono essere obbligatori o facoltativi per alcuni articoli?
- Quanti codici motivo sono necessari?
- Devi preselezionare un elenco limitato di codici motivo per le rettifiche?
- Come dovrebbero usare i codici di ragione gli utenti degli scanner di codici a barre? I codici motivo devono essere preselezionati, obbligatori o non modificabili?
- I lavoratori di magazzino richiedono un diverso comportamento del codice motivo sui lettori mobili? Se la risposta è sì, puoi creare più voci di menu e assegnarle a persone diverse.
- I codici motivo devono guidare la registrazione del conto di contropartita finanziaria?

## <a name="turn-on-reason-code-features-in-your-system"></a>Attivare le funzionalità del codice motivo nel sistema

Se non vedi tutte le funzionalità descritte in questo argomento nel tuo sistema, probabilmente devi attivare la funzionalità *Registrare le rettifiche delle scorte disponibili utilizzando codici motivo configurabili collegati ai conti di contropartita*. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Registrare le rettifiche delle scorte disponibili utilizzando codici motivo configurabili collegati ai conti di contropartita*

## <a name="set-up-reason-codes"></a>Imposta i codici causale

### <a name="set-up-reason-code-policies"></a>Impostare i criteri di codici motivo

È possibile creare più criteri del codice motivo per controllare quando e come vengono applicati i codici motivo di conteggio. Ogni criterio del codice motivo può avere uno dei due tipi di codice motivo di conteggio (*Facoltativo* oppure *Obbligatorio*). I criteri di codici motivo di conteggio possono essere utilizzati nel magazzino o a livello dell'articolo.

Per creare un criterio del codice motivo, attieniti alla seguente procedura.

1. Vai a **Gestione inventario** \> **Impostazioni** \> **Inventario** \> **Criteri codice motivo di conteggio**.
1. Nel riquadro azioni seleziona **Nuovo** per aggiungere un criterio alla griglia.
1. Imposta il campo **Nome** per il nuovo criterio.
1. Nel campo **Tipo di codice motivo conteggio** selezionare *Obbligatorio* o *Facoltativo* per specificare se la selezione di un codice motivo deve essere un'azione facoltativa o obbligatoria in uno dei seguenti processi di rettifica scorte:

    - Conteggio ciclo (dispositivo mobile)
    - Conteggio ciclo a campione (dispositivo mobile)
    - Conteggio soglia (dispositivo mobile)
    - Rettifica in entrata (dispositivo mobile)
    - Rettifica in uscita (dispositivo mobile)
    - Giornale di registrazione di conteggio (rich client)
    - Rettifica quantità/Conteggio online (rich client)

È inoltre possibile impostare i criteri di codici motivo per singoli magazzini e prodotti. L'impostazione del codice motivo per un prodotto può sostituire l'impostazione per il magazzino del prodotto.

> [!NOTE]
> Per i magazzini e gli articoli in cui il campo **Criteri codice motivo conteggio** è impostato su *Obbligatorio*, il giornale di registrazione di conteggio non può essere completato e chiuso finché non viene fornito un codice motivo. Per ulteriori informazioni, vedi la sezione successiva.

### <a name="assign-counting-reason-code-policies-to-warehouses"></a>Assegnare criteri codice motivo conteggio ai magazzini

Per assegnare un criterio di codice motivo di conteggio a un magazzino, segui questi passaggi.

1. Vai a **Gestione inventario** \> **Impostazioni** \> **Suddivisione scorte** \> **Magazzini**.
1. Seleziona un magazzino nel riquadro elenco.
1. Nel riquadro azioni della scheda **Magazzino**, nel gruppo **Imposta**, seleziona **Criteri codice motivo conteggio**. Poi, nella finestra a discesa **Assegna criterio codice motivo conteggio** segui uno di questi passaggi:

    - Per utilizzare l'impostazione dei criteri per ogni articolo per determinare se i giornali di registrazione di conteggio sono obbligatori, non immettere alcun valore (o elimina il valore esistente).
    - Per richiedere un codice motivo nei giornali di registrazione di conteggio per il magazzino, seleziona un criterio motivo in cui il campo **Tipo di codice motivo conteggio** è impostato su *Obbligatorio*.
    - Se un codice motivo è facoltativo nei giornali di registrazione di conteggio per il magazzino, seleziona un criterio motivo in cui il campo **Tipo di codice motivo conteggio** è impostato su *Facoltativo*.

### <a name="assign-counting-reason-code-policies-to-products"></a>Assegnare criteri codice motivo conteggio ai prodotti

Per assegnare un criterio di codice motivo di conteggio a un prodotto, segui questi passaggi.

1. Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.
1. Selezionare un prodotto nella griglia.
1. Nel riquadro azioni della scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Criteri codice motivo conteggio**. Poi, nella finestra a discesa **Assegna criterio codice motivo conteggio** segui uno di questi passaggi:

    - Per utilizzare l'impostazione dei criteri per il magazzino per determinare se i giornali di registrazione di conteggio sono obbligatori per il prodotto, non immettere alcun valore (o elimina il valore esistente).
    - Per richiedere un codice motivo nei giornali di registrazione di conteggio per il prodotto, seleziona un criterio motivo in cui il campo **Tipo di codice motivo conteggio** è impostato su *Obbligatorio*. Questa impostazione ha la priorità su qualsiasi impostazione di codici motivo a livello di magazzino.
    - Se un codice motivo è facoltativo nei giornali di registrazione di conteggio per il prodotto, seleziona un criterio motivo in cui il campo **Tipo di codice motivo conteggio** è impostato su *Facoltativo*. Questa impostazione ha la priorità su qualsiasi impostazione di codici motivo a livello di magazzino.

### <a name="set-up-counting-reason-codes"></a>Impostare i codici motivo di conteggio

Per impostare i codici motivo di conteggio, procedi come descritto di seguito.

1. Vai a **Gestione inventario** \> **Impostazioni** \> **Inventario** \> **Codici motivo di conteggio**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Imposta i campi **Codice motivo conteggio** e **Descrizione** per la nuova riga.
1. Per assegnare un conto di contropartita, immetti o seleziona un valore nel campo **Conto di contropartita**.

    > [!NOTE]
    > Se un conto di contropartita viene assegnato a un codice motivo di conteggio, quando registri un giornale di registrazione di conteggio che utilizza tale codice motivo di conteggio, il valore viene registrato rispetto al conto di contropartita assegnato anziché al conto del profilo di registrazione inventario predefinito.

### <a name="set-up-counting-reason-code-groups"></a><a name="reason-groups"></a>Impostare gruppi di codici motivo di conteggio

*Gruppi di codici motivo di conteggio* può essere utilizzato come parte delle voci di menu *Rettifica in entrata* e *Rettifica in uscita* nell'app per dispositivi mobili Warehouse Management per limitare l'elenco dei codici motivo di conteggio. (Per ulteriori informazioni sui gruppi di codici motivo di conteggio, vedi la sezione [Impostare le voci di menu del dispositivo mobile per la rettifica in entrata e in uscita](#setup-adjustment-in-out) più avanti in questo argomento.)

1. Vai a **Gestione inventario** \> **Impostazioni** \> **Inventario** \> **Gruppi di codici motivo di conteggio**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere un gruppo.
1. Imposta i campi **Gruppo motivi conteggio** e **Descrizione gruppo** per il nuovo gruppo.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella sezione **Dettagli** seleziona **Nuovo** sulla barra degli strumenti per aggiungere una riga alla griglia. Imposta il campo **Codice motivo conteggio** per la nuova riga. 
1. Ripeti il passaggio precedente per assegnare più codici secondo necessità. Se devi rimuovere un codice dal gruppo, selezionalo, quindi seleziona **Elimina** sulla barra degli strumenti.

### <a name="set-up-reason-codes-for-mobile-device-menu-items"></a>Impostare i codici motivo per le voci di menu del dispositivo mobile

È possibile configurare i codici motivo per i seguenti tipi di rettifica scorte disponibili:

- Conteggio ciclo
- Conteggio ciclo a campione
- Conteggio soglia
- Rettifica in entrata
- Rettifica in uscita

Nella maggior parte dei casi, è possibile definire le seguenti informazioni per ogni voce di menu del dispositivo mobile rilevante:

- Indica se il codice motivo viene mostrato al lavoratore con il dispositivo mobile durante il conteggio.
- Il codice motivo predefinito mostrato su una voce di menu del dispositivo mobile.
- Se l'utente può modificare il codice motivo.

#### <a name="set-up-mobile-device-menu-items-for-a-counting-process"></a>Impostare le voci di menu del dispositivo mobile per un processo di conteggio

Per configurare una voce di menu del dispositivo mobile per un processo di conteggio, segui questi passaggi.

1. Vai a **Warehouse Management** \> **Impostazioni** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile**.
1. Seleziona la voce di menu pertinente nel riquadro elenco o crea una nuova voce di menu.
1. Nel riquadro azioni, seleziona **Conteggio ciclo**.
1. Nel campo **Codice motivo conteggio predefinito** imposta il codice motivo predefinito che deve essere registrato quando la voce di menu del dispositivo mobile viene usata per eseguire il conteggio.
1. Nel campo **Visualizza codice motivo conteggio**, seleziona uno dei seguenti valori:

    - *Riga* – Mostra il codice motivo dopo che ogni variazione è stata registrata.
    - *Nascondi* – Non mostrare il codice motivo.

1. Imposta **Modifica codice motivo conteggio** su *Sì* per consentire al lavoratore di modificare il codice motivo quando viene visualizzato sul dispositivo mobile durante il conteggio. Impostalo su *No* per impedire al lavoratore di modificare il codice.

> [!NOTE]
> Il pulsante **Conteggio ciclo** può essere abilitato su qualsiasi voce di menu del dispositivo mobile in cui è possibile eseguire il conteggio. Gli esempi includono le voci di menu per i conteggi ciclo a campione, il lavoro diretto dall'utente e il lavoro diretto dal sistema.

#### <a name="set-up-mobile-device-menu-items-for-adjustment-in-and-adjustment-out"></a><a name="setup-adjustment-in-out"></a>Impostare le voci di menu del dispositivo mobile per la rettifica in entrata e in uscita

Per configurare una voce di menu del dispositivo mobile per la rettifica in entrata o in uscita, segui questi passaggi.

1. Vai a **Warehouse Management** \> **Impostazioni** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile**.
1. Nel riquadro azioni seleziona **Nuovo** per creare una voce di menu.
1. Imposta i campi **Nome voce mobile** e **Titolo** per la nuova voce di menu.
1. Imposta il campo **Modalità** su *Lavoro*.
1. Impostare l'opzione **Utilizza lavoro esistente** su *No*.
1. Nel campo **Processo di creazione lavoro** seleziona *Rettifica in entrata* o *Rettifica in uscita*.
1. Nella scheda dettaglio **Generale**, imposta i seguenti campi. (Tutti questi campi vengono aggiunti quando selezioni *Rettifica in entrata* o *Rettifica in uscita* nel campo **Processo di creazione lavoro**.)

    - **Usa guida processo** – Se stai creando un processo *Rettifica in uscita*, assicurati di impostare questa opzione su *Sì*. Se stai creando un processo *Rettifica in uscita* questa opzione è sempre impostata su *Sì*.
    - **Codice motivo conteggio predefinito** - Imposta il codice motivo predefinito che deve essere registrato quando la voce di menu del dispositivo mobile viene usata per eseguire il conteggio.
    - **Visualizza codice motivo conteggio** - Seleziona uno dei seguenti valori:

        - *Riga* – Mostra il codice motivo dopo che ogni variazione è stata registrata.
        - *Nascondi* – Non mostrare il codice motivo.

    - **Modifica codice motivo conteggio** - Imposta questa opzione su *Sì* per consentire al lavoratore di modificare il codice motivo quando viene visualizzato sul dispositivo mobile durante il conteggio. Impostalo su *No* per impedire al lavoratore di modificare il codice.
    - **Gruppo codici motivo conteggio** – Seleziona un gruppo di codici motivo se vuoi limitare l'elenco di opzioni presentato ai lavoratori. Per informazioni su come impostare i gruppi di codici motivo, vedi la sezione [Impostare gruppi di codici motivo di conteggio](#reason-groups) precedente in questo argomento. 

> [!NOTE]
> Quando assegni un gruppo di codici motivo di conteggio alle voci di menu *Rettifica in entrata* e *Rettifica in uscita* in cui l'opzione **Usa guida processo** è impostata su *Sì*, puoi ottenere un elenco limitato dei codici motivo di conteggio come parte dell'elaborazione nell'app per dispositivi mobili Warehouse Management.
>
> L'opzione **Usa guida processo** può anche aiutare a prevenire che si verifichino per errore grandi quantità di rettifiche. (Ad esempio, un lavoratore potrebbe accidentalmente scansionare un codice a barre di un numero di articolo invece di un valore di quantità.) Per impostare questa funzionalità, imposta l'opzione **Usa guida processo** su *Sì* per ogni voce di menu pertinente. Quindi vai a **Warehouse Management \> Impostazioni \> Lavoratore**, e imposta il campo **Limite quantità rettifiche** per ogni lavoratore del magazzino rilevante per specificare la quantità di rettifica massima che il lavoratore può registrare.

## <a name="processing-that-uses-counting-reason-codes"></a>Elaborazione che utilizza codici motivo di conteggio

Quando i lavoratori utilizzano l'app per dispositivi mobili Warehouse Management, vengono registrati i codici motivo. A meno che non sia stato definito un processo di approvazione del conteggio, i codici motivo registrati vengono utilizzati immediatamente come parte della registrazione del giornale di registrazione che segue.

### <a name="cycle-count-approvals"></a>Approvazioni del conteggio ciclo

Prima che un conteggio venga approvato, il lavoratore può modificare il codice motivo associato al conteggio. Quando il conteggio viene approvato, il codice motivo viene inserito nelle righe del giornale di registrazione di conteggio

#### <a name="modify-reason-codes-for-cycle-count-approvals"></a>Modificare i codici motivo per le approvazioni del conteggio ciclo

Segui questi passaggi per modificare l'approvazione di un conteggio ciclo.

1. Vai a **Warehouse Management** \> **Conteggio ciclo** \> **Lavoro conteggio ciclo con revisione in sospeso**.
1. Seleziona un conteggio ciclo nella griglia.
1. Nel riquadro Azioni, nella scheda **Lavoro**, seleziona **Conteggio ciclo**. Seleziona un nuovo codice motivo nel campo **Codice motivo**.

I codici motivo vengono aggiunti alle righe del giornale di registrazione nei i giornali di registrazione di conteggio di tipo *Giornale di registrazione di conteggio*.

1. Vai a **Gestione inventario** \> **Inserimenti nel giornale di registrazione** \> **Conteggio articoli** \> **Conteggio**.
2. Nei dettagli della riga del giornale di registrazione conteggio, nel campo **Codice motivo conteggio** seleziona il codice motivo che corrisponde alla tua situazione attuale.

### <a name="view-the-reason-codes-recorded-in-the-counting-history"></a>Visualizzare i codici motivo registrati nella cronologia di conteggio

Per visualizzare i codici motivo che sono stati registrati nella cronologia di conteggio, segui questi passaggi.

1. Vai a **Gestione inventario** \> **Richieste di informazioni e report** \> **Cronologia conteggio**.
1. Seleziona un record di conteggio articolo nel riquadro elenco.
1. Nel campo **Codice motivo conteggio** visualizza la cronologia di conteggio che è stata registrata tramite un codice motivo.

### <a name="use-reason-codes-for-quantity-adjustment-or-online-counting"></a>Utilizzare i codici motivo per la rettifica della quantità o il conteggio online

Per utilizzare un codice motivo per una rettifica di quantità o un conteggio online, attieniti alla seguente procedura.

1. Passare a **Gestione articoli \> Richieste di informazioni e report \> Scorte disponibili**.
1. Nel riquadro azioni, selezionare **Rettifica quantità**.
1. Seleziona **Rettifica quantità**, quindi nel campo **Codice motivo conteggio** seleziona un codice motivo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
