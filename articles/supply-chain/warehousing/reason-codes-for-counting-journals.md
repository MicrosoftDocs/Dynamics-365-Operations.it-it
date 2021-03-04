---
title: Codici motivo conteggio scorte
description: In questo argomento viene descritto come impostare e applicare i codici motivo ai fini delle attività di conteggio
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 1025dd00db2e8b87e3c76e3047a7cf470a2d6641
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430943"
---
# <a name="reason-codes-for-inventory-counting"></a>Codici motivo conteggio scorte

[!include [banner](../includes/banner.md)]

I codici motivo consentono di analizzare i risultati di un processo di conteggio e le eventuali discrepanze che si verificano durante tale processo. È possibile specificare il motivo del conteggio, ad esempio un pallet rotto o una correzione dello scorte basata su campioni di inventario.

## <a name="recommendation"></a>Suggerimento

Prima di impostare il sistema, si consiglia di definire una strategia per la gestione dei codici motivo. Ad esempio, provare a rispondere alle domande seguenti:

- I codici motivo devono essere obbligatori nei magazzini?
- I codici motivo devono essere obbligatori o facoltativi per alcuni articoli?
- Quanti codici motivo sono necessari?
- In che modo dei lettori di codici a barre devono utilizzare codici motivo? I codici motivo devono essere preselezionati, obbligatori o non modificabili?
- I lavoratori di magazzino richiedono un diverso comportamento del codice motivo sui lettori mobili? Se la risposta è sì, puoi creare più voci di menu e assegnarle a persone diverse.

## <a name="where-reason-codes-apply"></a>Dove si applicano i codici motivo

È possibile creare più criteri di codici motivo e ogni criterio di codice motivo può avere due criteri di codice motivo di conteggio. I criteri di conteggio di codici motivo possono essere utilizzati nel magazzino o a livello dell'articolo.

## <a name="set-up-reason-code-policies"></a>Impostare i criteri di codici motivo

1. Selezionare **Gestione inventario** \> **Impostazione** \> **Magazzino** \> **Criteri codice motivo conteggio** e creare nuovi criteri del codice motivo.
2. Nel campo **Tipo di codice motivo conteggio** selezionare **Obbligatorio** o **Facoltativo** per specificare se la selezione di un codice motivo deve essere un'azione facoltativa o obbligatoria in uno dei seguenti giornali di registrazione di conteggio:

    - Conteggio ciclo (dispositivo mobile)
    - Conteggio ciclo a campione (dispositivo mobile)
    - Conteggio soglia (dispositivo mobile)
    - Rettifica in entrata (dispositivo mobile)
    - Rettifica in uscita (dispositivo mobile)
    - Giornale di registrazione di conteggio (rich client)

È inoltre possibile impostare codici motivo per singoli magazzini e prodotti. L'impostazione di codici motivo per i prodotti può ignorare le impostazioni per i magazzini.

## <a name="mandatory-reason-codes"></a>Codici motivo obbligatori

Se il parametro **Obbligatorio** è impostato nella configurazione dei codici motivo per magazzini o articoli, il giornale di registrazione di conteggio non può essere completato e chiuso finché non viene fornito un codice motivo.

### <a name="set-up-reason-codes-for-warehouses"></a>Imposta codici motivo per i magazzini

1. Selezionare **Gestione articoli** \> **Impostazioni** \> **Suddivisione scorte** \> **Magazzini**.
2. Nella scheda **Magazzino**, nel campo **Criteri codice motivo conteggio** selezionare una delle seguenti opzioni:

    - **Vuoto**: il parametro impostato per l'articolo viene utilizzato per determinare se i giornali di registrazione di conteggio sono obbligatori per il prodotto.
    - **Obbligatorio**: il codice motivo è sempre obbligatorio per i giornali di registrazione di conteggio per il magazzino.
    - **Facoltativo**: il codice motivo non è obbligatorio per i giornali di registrazione di conteggio per il magazzino.

### <a name="set-up-reason-codes-for-products"></a>Imposta codici motivo per i prodotti

1. Selezionare **Gestione informazioni sul prodotto** \> **Prodotti** \> **Prodotti rilasciati**.
2. Nella scheda **Prodotto** selezionare **Criteri codice motivo conteggio** e quindi una delle seguenti opzioni:

    - **Vuoto**: il parametro impostato per il magazzino viene utilizzato per determinare se i giornali di registrazione di conteggio sono obbligatori per il prodotto.
    - **Obbligatorio**: il codice motivo è sempre obbligatorio per i giornali di registrazione di conteggio per il prodotto. Questa impostazione ha la priorità su qualsiasi impostazione di codici motivo a livello di magazzino.
    - **Facoltativo**: il codice motivo non è obbligatorio per i giornali di registrazione di conteggio per il prodotto. Questa impostazione ha la priorità su qualsiasi impostazione di codici motivo a livello di magazzino.

### <a name="use-reason-codes-in-counting-journals"></a>Utilizzare i codici motivo nei giornali di registrazione di conteggio

In un giornale di registrazione, è possibile aggiungere i codici motivo per i conteggi dei seguenti tipi:

- Conteggio ciclo
- Conteggio ciclo a campione
- Conteggio soglia
- Rettifica in entrata
- Rettifica in uscita

I codici motivo vengono aggiunti alle righe del giornale di registrazione nei i giornali di registrazione di conteggio di tipo **Giornale di registrazione di conteggio**.

1. Selezionare **Gestione inventario** \> **Inserimenti nel giornale di registrazione** \> **Conteggio articoli** \> **Conteggio**.
2. In dettaglio i dettagli riga del giornale di registrazione di conteggio, nel campo **Codice motivo conteggio** selezionare un'opzione.

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a>Visualizzare la cronologia del conteggio così come è registrata dai codici motivo

- Selezionare **Gestione inventario** \> **Richieste di informazioni e report** \> **Storico conteggio**, quindi nel campo **Codice motivo conteggio**, visualizzare lo storico di conteggio registrato tramite un codice motivo.

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a>Utilizzare un codice motivo per rettifica della quantità

1. Nella pagina **Scorte disponibili**, selezionare **Rettifica quantità**. È possibile aprire la pagina **Scorte disponibili** in diversi metodi. Ad esempio, selezionando **Gestione inventario** \> **Richieste di informazioni e report** \> **Scorte disponibili**.
2. Selezionare **Rettifica quantità**, quindi nel campo **Codice motivo conteggio** selezionare un codice motivo.

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a>Configurare i codici motivo per le voci di menu del dispositivo mobile

È possibile configurare i codici motivo per qualsiasi tipo di conteggio su una voce di menu del dispositivo mobile. La configurazione della voce di menu del dispositivo mobile include le seguenti informazioni:

- Indica se il codice motivo viene mostrato al lavoratore con il dispositivo mobile durante il conteggio.
- Il codice motivo predefinito mostrato su una voce di menu del dispositivo mobile.
- Se l'utente può modificare il codice motivo.

### <a name="set-up-reason-codes-on-a-mobile-device"></a>Impostare i codici motivo su un dispositivo mobile

1. Selezionare **Gestione magazzino** \> **Impostazioni** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile**.
2. Nella scheda **Conteggio ciclo**, scegliere **Conteggio ciclo**.
3. Nel campo **Codice motivo conteggio predefinito** impostare il codice motivo predefinito che deve essere registrato quando il conteggio viene eseguito utilizzando la voce di menu del dispositivo mobile.
4. Nel campo **Visualizza codice motivo conteggio** selezionare **Riga** per visualizzare il codice motivo dopo ogni scostamento viene registrato. In alternativa, selezionare **Nascondi** se il codice motivo non deve essere mostrato.
5. Impostare l'opzione **Modifica codice motivo conteggio** su **Sì** o **No**. Se si imposta questa opzione su **Sì**, il lavoratore può modificare il codice motivo quando viene visualizzato sul dispositivo mobile durante il conteggio.

> [!NOTE]
> Il pulsante **Conteggio ciclo** può essere abilitato su qualsiasi voce di menu del dispositivo mobile in cui è possibile eseguire il conteggio. L'esempio include le voci di menu per i conteggi ciclo a campione, il lavoro diretto dall'utente e il lavoro diretto dal sistema.

## <a name="cycle-count-approvals"></a>Approvazioni del conteggio ciclo

Prima che un conteggio venga approvato, l'utente può modificare il codice motivo associato al conteggio. Quando il conteggio viene approvato, il codice motivo viene inserito nelle righe del giornale di registrazione di conteggio

### <a name="modify-cycle-count-approvals"></a>Modifica delle approvazioni del conteggio ciclo

1. Selezionare **Gestione magazzino** \> **Conteggio ciclo** \> **Lavoro conteggio ciclo con revisione in sospeso**.
2. Selezionare **Conteggio ciclo**, quindi nel campo **Codice motivo** selezionare un nuovo codice motivo.

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a>Modificare la voce di menu del dispositivo mobile per Rettifica e Rettifica in uscita

1. Selezionare **Gestione magazzino** \> **Impostazione** \> **Dispositivo mobile** \> **Voci di menu del dispositivo mobile** e quindi **Rettifica in entrata e in uscita**.
2. Impostare l'opzione **Utilizza lavoro esistente** su **No**.
3. Nel campo **Processo di creazione lavoro** selezionare **Rettifica in entrata**.

I seguenti campi verranno aggiunti alla voce di menu del dispositivo mobile quando si seleziona **Rettifica in entrata** o **Rettifica in uscita** durante il processo di creazione del lavoro:

- Codice motivo conteggio predefinito
- Visualizza codice motivo conteggio
- Modifica codice motivo conteggio


[!INCLUDE[footer-include](../../includes/footer-banner.md)]