---
title: Simulazioni di contabilità generale (Italia)
description: Questo argomento fornisce informazioni sulla registrazione delle transazioni di contabilità generale come simulazioni del giornale di registrazione generale e quindi sulla verifica dei report che includono le transazioni simulate.
author: anasyash
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: b03e75d72d1d0b45e53141f08a8bbb47c6b24334
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408110"
---
# <a name="general-ledger-simulations"></a>Simulazioni di contabilità generale

[!include [banner](../includes/banner.md)]

Le simulazioni di contabilità generale consentono di registrare transazioni di contabilità generale simulate del giornale di registrazione generale e quindi di esaminare i report che includono le transazioni simulate.

Questa funzionalità è disponibile solo per le persone giuridiche con un indirizzo principale in Italia. 

È possibile registrare transazioni di simulazione solo per le righe del giornale di registrazione dove **Tipo di account** e **Tipo di conto di contropartita** sono uguali a **Contabilità generale**.
È possibile eliminare le transazioni di contabilità generale simulate, modificarle e spostarle nelle transazioni di contabilità generale registrate reali.
È possibile esaminare le transazioni di contabilità generale di simulazione registrate nei report **Bilancio di verifica** e **Rendiconto dimensioni con simulazione**.


## <a name="prerequisites"></a>Prerequisiti

Per poter utilizzare le simulazioni di contabilità generale, è necessario soddisfare i seguenti prerequisiti:

- L'indirizzo principale della persona giuridica è in italia.
- Abilitare la funzionalità **Simulazioni di contabilità generale** nell'area di lavoro **Gestione funzionalità**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="setup"></a>Impostazione 

### <a name="create-a-number-sequence-for-the-simulated-general-journal-transfer"></a>Creare una sequenza numerica per il trasferimento del giornale di registrazione simulato

1.  Selezionare **Contabilità generale** > **Impostazione contabilità generale** > **Parametri di contabilità generale**.
2.  Nella scheda **Sequenze numeriche**, impostare la sequenza su **Trasferimento giornale di registrazione generale di simulazione**.

### <a name="create-a-simulation-journal"></a>Creare un giornale di registrazione di simulazione

1. Selezionare **Contabilità generale** > **Impostazione giornale di registrazione** > **Nome giornale di registrazione** e creare un nuovo giornale di registrazione denominato "Simulazione".
2. Impostare **Tipo di giornale di registrazione** su **Giornaliero**.
3. Nel campo **Simulazione**, selezionare **Sì**.
4. Nel campo **Giornale di registrazione di simulazione**, impostare **Richiede convalida** su **Sì** per indicare che il giornale di registrazione deve essere convalidato prima dell'esecuzione della registrazione simulata.


## <a name="operations"></a>Operations

### <a name="create-and-post-simulation-transaction"></a>Creare e registrare transazioni di simulazione

1. Selezionare **Contabilità generale** > **Inserimenti nel giornale di registrazione** > **Giornali di registrazione di simulazione**.
2. Creare righe del giornale di registrazione come **Contabilità generale - Contabilità generale** nel modo standard, quindi selezionare **Registra** > **Registra simulazione** per registrare le transazioni di simulazione. Ciò rende la transazione effettiva per i calcoli di simulazione e il giornale di registrazione diventa *simulazione registrata*.
3. Selezionare **Registra** > **Riapri** per rendere modificabile la transazione di simulazione registrata.
4. Selezionare **Registra** > **Registra** per spostare la transazione di simulazione registrata nella contabilità generale ordinaria.

> [!IMPORTANT]
> La funzione che chiude un periodo fiscale o un anno fiscale verifica che le transazioni di simulazione siano state registrate come transazioni tipiche o siano state eliminate. Se vi sono transazioni di contabilità generale simulate in sospeso per il periodo, viene visualizzato un messaggio di errore.


## <a name="periodic-operations"></a>Operazioni periodiche

### <a name="post-all-simulation-transactions"></a>Registrare tutte le transazioni di simulazione 

- Per registrare transazioni di simulazione per tutti i giornali di registrazione di simulazione, selezionare **Attività periodiche** > **Simulazioni** > **Registra giornali di registrazione di simulazione**.

Le transazioni non includeranno più le transazioni di simulazione dopo la registrazione di tutti i giornali di registrazione.

### <a name="reopen-all-simulation-journals"></a>Riaprire tutti i giornali di registrazione di simulazione 

- Per riaprire tutti i giornali di registrazione di simulazione, selezionare **Attività periodiche** > **Simulazioni** > **Riapri giornali di registrazione di simulazione**.

Tutti i giornali di registrazione di simulazione registrati vengono riaperti. È possibile modificare i giornali di registrazione di simulazione e registrare nuovamente la simulazione.

### <a name="delete-all-simulation-journals"></a>Eliminare tutti i giornali di registrazione di simulazione 

- Per eliminare tutti i giornali di registrazione di simulazione aperti, selezionare **Attività periodiche** > **Simulazioni** > **Elimina giornali di registrazione di simulazione**. 

## <a name="review-simulation-transactions-in-reports"></a>Esaminare le transazioni di simulazione nei report

Le transazioni di simulazione possono essere esaminare in diversi report di contabilità generale.

> [!NOTE] 
> Le transazioni di simulazione non compaiono nel giornale di registrazione fiscale italiano fino a quando non diventano transazioni reali.

### <a name="create-a-simulation-journal-name-group"></a>Creare un gruppo di giornali di registrazione di simulazione 

1. Selezionare **Contabilità generale** > **Impostazione giornale di registrazione** > **Simulazioni** > **Gruppo di giornali di registrazione di simulazione**.
2. Creare un gruppo di giornali di registrazione di simulazione. 
3. Nella scheda **Giornali di registrazione di simulazione**, selezionare i giornali da includere nel gruppo dall'elenco dei giornali di registrazione di simulazione disponibili. 

### <a name="trial-balance"></a>Bilancio di verifica

1. Selezionare **Contabilità generale** > **Richieste di informazioni e report** > **Bilancio di verifica**.
2. Nella scheda dettaglio **Parametri** dell'intestazione del report **Bilancio di verifica**, selezionare un valore nel campo **Gruppo di giornali di registrazione di simulazione**.
3. Immettere altri parametri e calcolare i bilanci.
4. Verificare che il report contenga colonne che prendano in considerazione le transazioni di simulazione, tra cui:

-   **Dare (simulazione)**
-   **Avere (simulazione)**
-   **Saldo di chiusura (con simulazioni)** - Questo è il totale dei valori nelle colonne **Saldo di chiusura**, **Dare (simulazione)** e **Avere (simulazione)**.

### <a name="dimension-statement-with-simulation"></a>Rendiconto dimensioni con simulazione

1. Selezionare **Contabilità generale** > **Richieste di informazioni e report** > **Report di contabilità generale** > **Rendiconto dimensioni con simulazione**.
2. Impostare **Transazioni giornale di registrazione di simulazione** su **Sì** nella finestra di dialogo **Rendiconto per dimensioni**.
3. Selezionare un valore nel campo **Gruppo di giornali di registrazione di simulazione** e selezionare **OK**.
4. Verificare che il report contenga transazioni di simulazione registrate e transazioni di contabilità generale standard.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]