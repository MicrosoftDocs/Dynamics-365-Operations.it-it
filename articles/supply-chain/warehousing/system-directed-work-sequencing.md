---
title: Sequenza lavori gestiti dal sistema
description: Questo argomento fornisce informazioni sulla sequenza di lavori gestiti dal sistema. Questa funzionalità consente di ordinare e filtrare gli ordini di lavoro che il sistema presenta agli utenti per l'esecuzione. È utile in scenari in cui sono richiesti criteri aggiuntivi per guidare il processo di prelievo di magazzino.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 2884c480d20090266f7cffb5e7d0aca58c1174f0
ms.sourcegitcommit: edb46dce498df42b09e8f5ad6de00f86c8022dfa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2020
ms.locfileid: "3534852"
---
# <a name="system-directed-work-sequencing"></a>Sequenza lavori gestiti dal sistema

[!include [banner](../includes/banner.md)]

Sequenza lavori gestiti dal sistema consente di ordinare e filtrare gli ordini di lavoro che il sistema presenta agli utenti per l'esecuzione. È utile in scenari in cui sono richiesti criteri aggiuntivi (come il tempo di spedizione, la zona di prelievo, il profilo di ubicazione o una combinazione di vari criteri) per guidare il processo di prelievo in magazzino.

Questa funzionalità estende l'attuale funzionalità di selezione diretta dal sistema aggiungendo un ordine di query diretto dal sistema, in cui gli utenti possono impostare una sequenza e una o più query che valuteranno tutti gli ordini di lavoro creati. Verranno acquisiti e presentati solo gli ordini di lavoro che soddisfano i criteri specificati nell'impostazione della voce di menu del dispositivo mobile.

Pertanto, questa funzionalità consente un'ulteriore ottimizzazione dei processi di prelievo in magazzino in quanto identifica gli ordini di lavoro che soddisfano i criteri specificati, li assegna alla voce di menu del dispositivo mobile corretta e li presenta a un lavoratore, in base a un set di competenze, attrezzature di prelievo o altri requisiti specifici.

> [!NOTE]
> Se sono necessari criteri diversi, è necessario utilizzare più voci di menu del dispositivo mobile.

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a>Attivare la funzionalità di sequenza lavoro gestiti dal sistema a livello di organizzazione

Prima di poter utilizzare la sequenza lavori gestita dal sistema, tale funzionalità deve essere attivata nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzione:** *Sequenza del lavoro diretto al sistema a livello di organizzazione*

## <a name="setup"></a>Attrezzaggio

### <a name="make-demo-data-available"></a>Rendi disponibili i dati dimostrativi

Per elaborare lo scenario utilizzando i record e i valori di esempio presentati in questo argomento, devi utilizzare un sistema in cui sono installati i dati dimostrativi standard. Inoltre, è necessario selezionare la persona giuridica **USMF**. Lo scenario utilizza il magazzino *51* dai dati demo.

> [!IMPORTANT]
> Prima di rilasciare gli ordini al magazzino, devi assicurarti che le posizioni di prelievo dispongano di scorte sufficienti per tutti gli articoli degli ordini.
>
> I dati USMF predefiniti dovrebbero supportare questo scenario. Se non stai utilizzando dati dimostrativi, rivedi Rivedere l'impostazione **Direttiva ubicazione** per apprendere quali ubicazioni di prelievo vengono utilizzate per il prelievo dell'ordine cliente. Se è necessario regolare le scorte, puoi creare movimenti manuali, utilizza il rifornimento o utilizza qualsiasi altro flusso, come richiesto.

### <a name="set-up-a-mobile-device-menu-item"></a>Configurare una voce di menu per dispositivo mobile

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nell'elenco delle voci di menu del dispositivo mobile, seleziona **Selezione vendite - Sistema**. La voce di menu richiesta dovrebbe già esistere. 
1. Verificare le seguenti impostazioni:

    - Nella Scheda dettaglio **Generale**, il campo **Diretto da** deve essere impostato su *Diretto dal sistema*.
    - la Scheda dettaglio **Classi di lavoro** dovrebbe mostrare le seguenti impostazioni.

        | ID classe lavoro | Tipo ordine di lavoro |
        |---|---|
        | Sales | Gestione ordini cliente |
        | Prelievo SO | Gestione ordini cliente |

1. Nel riquadro azioni seleziona **Query della sequenza di lavoro diretta dal sistema**.
1. Selezionare **Modifica**.
1. Elimina la riga esistente, quindi conferma l'azione selezionando **Sì**.
1. Nel riquadro azioni seleziona **Nuova** per creare una riga.
1. Nella nuova riga, imposta i seguenti valori:

    - **Numero progressivo:** *1*
    - **Campo descrizione:** *Quantità di lavoro inferiore a 20 e decrescente*

1. Selezionare **Salva**.
1. Nel riquadro azioni, seleziona **Modifica query**.
1. Nella scheda **Join**, espandi la gerarchia di join per mostrare la tabella **Righe di lavoro**.
1. Seleziona il join della tabella **Righe di lavoro**.
1. Seleziona **Aggiungi tabella join**.
1. Nell'elenco che appare, trova e seleziona la riga con le seguenti impostazioni:

    - **Modalità join:** *n:1*
    - **Relazione:** *Ubicazioni (ubicazione)*

1. Selezionare **Select**.

    Le ubicazioni vengono aggiunte al join della tabella.

1. Sulla scheda **Ordinamento**, seleziona e **Aggiungi** per aggiungere una riga.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *Quantità di lavoro* (nella finestra di messaggio che appare, seleziona **Sì** per aggiungere l'ordinamento a questo campo).
    - **Direzione di ricerca:** *Decrescente*

1. Seleziona la scheda **Intervallo**.

    Se nella sequenza devono essere inclusi solo criteri di lavoro specifici, è possibile specificarli nella scheda **Intervallo**. In questo esempio, è consigliabile includere solo lavori in cui la quantità è inferiore a 20 ea (l'unità di misura più bassa).

    Nota che alcune righe sono già incluse. Tali righe non devono essere rimosse.

1. Seleziona **Aggiungi** per aggiungere una riga.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *Quantità inventario lavoro*
    - **Criteri:** *\<20* (meno di 20)

1. Seleziona **Aggiungi** per aggiungere un'altra riga.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Righe di lavoro*
    - **Tabella derivata:** *Righe di lavoro*
    - **Campo:** *Tipo di lavoro*
    - **Criteri:** *Prelievo*

1. Seleziona **Aggiungi** per aggiungere un'altra riga.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tabella:** *Ubicazioni*
    - **Tabella derivata:** *Ubicazioni*
    - **Campo:** *ID profilo ubicazione*
    - **Criteri:** *!STAGE*

        > [!IMPORTANT]
        > Assicurati di includere il punto esclamativo (*!*) di fronte a *STAGE*.

1. Seleziona **OK** per salvare e chiudere la query.
1. Selezionare **Salva**.
1. Chiudi la pagina per tornare alla pagina **Voci di menu del dispositivo mobile**.

> [!NOTE]
> Questa configurazione definisce i criteri che verranno utilizzati per inserire il lavoro idoneo alla voce di menu del dispositivo mobile. Se aggiungi più righe di criteri alla query, il sistema utilizzerà prima la riga della query con il numero di sequenza più basso. In altre parole, tutti i lavori idonei per la sequenza numero 1 verranno prima presentati all'utente per primi, seguiti da tutti i lavori per la sequenza numero 2. Pertanto, se un intervallo e un ordinamento specifici devono essere utilizzati insieme, devono essere specificati nella stessa query della sequenza di lavoro diretta dal sistema.
>
> Questa configurazione acquisirà qualsiasi lavoro che abbia almeno una riga in cui la quantità è inferiore a 20 ea. Pertanto, se il lavoro ha una riga in cui la quantità è esattamente di 20 ea o più di 20 ea, sarà valida, a condizione che abbia anche almeno una riga in cui la quantità è inferiore a 20 ea.

### <a name="location-directives"></a>Direttive ubicazione

Se si utilizzano i dati Contoso predefiniti, la query per l'azione della direttiva ubicazione non richiederà modifiche. Tuttavia, per assicurarsi che le direttive di ubicazione acquisiscano gli articoli negli ordini cliente quando si applica la funzionalità in un ambiente non Contoso, crea una nuova direttiva di ubicazione. Per verificare le impostazioni nell'ambiente demo, attieniti alla seguente procedura.

1. Andare a **Gestione magazzino** \> **Impostazioni** \> **Direttive ubicazione**.
1. Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.
1. Seleziona la direttiva ubicazione denominata *Prelievo 51*.
1. Nella Scheda dettaglio **Azioni direttiva ubicazione**, seleziona la riga per l'azione **Prelievo**.
1. Seleziona **Modifica query** sopra la griglia.
1. Rivedi la query **Intervallo**.

    1. Trova la riga in cui il campo **Campo** è impostato su *Ubicazione*.
    2. Verifica che il campo **Criteri** sia vuoto (ovvero non ci sono restrizioni).

## <a name="scenario"></a>Scenario

### <a name="create-sales-order-picking-work"></a>Creare lavoro di prelievo ordini di vendita

Prima di eseguire il prelievo diretto dal sistema, è necessario creare alcuni lavori in uscita. Per questo scenario, verranno creati quattro ordini cliente basati sulle query della sequenza di lavoro diretta dal sistema specificate.

Prenoterai le quantità di scorte per ciascun ordine cliente. Pertanto, le scorte prenotate non possono quindi essere prelevate dal magazzino per altri ordini, a meno che la prenotazione o parte di questa non venga annullata.

Rilascerai quindi ciascun ordine cliente nel magazzino per creare il lavoro in uscita.

#### <a name="sales-order-1"></a>Ordine cliente 1

1. Selezionare **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**.
1. Nel riquadro azioni seleziona **Nuovo** per creare l'ordine cliente 1.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - Nella sezione **Cliente**, imposta il campo **Conto cliente** su *US-004*.
    - Nella sezione **Generale** imposta il campo **Magazzino** su *51*.

1. Selezionare **OK** per chiudere la finestra di dialogo. Prendi nota del numero di ordine cliente.
1. Aggiungi una riga al nuovo ordine cliente e imposta i seguenti valori:

    - **Numero articolo:** *M9200*
    - **Quantità:** *20*

1. Nel menu **Scorte** sopra la griglia, seleziona **Prenotazione**.
1. Nella pagina **Prenotazione**, seleziona **Prenota lotto** per prenotare le scorte.
1. Chiudi la pagina **Prenotazione**.
1. Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino** per creare lavoro per il magazzino.

    Ricevi messaggi informativi che mostrano l'ID ondata e gli ID spedizione creati per l'ordine cliente.

#### <a name="sales-order-2"></a>Ordine cliente 2

1. Nel riquadro azioni seleziona **Nuovo** per creare l'ordine cliente 2.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-007*
    - **Magazzino:** *51*

1. Selezionare **OK** per chiudere la finestra di dialogo. Prendi nota del numero di ordine cliente.
1. Aggiungi una riga al nuovo ordine cliente e imposta i seguenti valori:

    - **Numero articolo:** *M9200*
    - **Quantità:** *5*

1. Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:

    - **Numero articolo:** *M9201*
    - **Quantità:** *1*

1. Prenota scorte per entrambe le righe.
1. Rilascia l'ordine ordini al magazzino.

#### <a name="sales-order-3"></a>Ordine cliente 3

1. Nel riquadro azioni seleziona **Nuovo** per creare l'ordine cliente 3.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-009*
    - **Magazzino:** *51*

1. Selezionare **OK** per chiudere la finestra di dialogo. Prendi nota del numero di ordine cliente.
1. Aggiungi una riga al nuovo ordine cliente e imposta i seguenti valori:

    - **Numero articolo:** *M9200*
    - **Quantità:** *7*

1. Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:

    - **Numero articolo:** *M9202*
    - **Quantità:** *8*

1. Prenota scorte per entrambe le righe.
1. Rilascia l'ordine ordini al magazzino.

#### <a name="sales-order-4"></a>Ordine cliente 4

1. Nel riquadro azioni seleziona **Nuovo** per creare l'ordine cliente 4.
1. Nella finestra di dialogo **Crea ordine cliente**, imposta i seguenti valori:

    - **Conto cliente:** *US-010*
    - **Magazzino:** *51*

1. Selezionare **OK** per chiudere la finestra di dialogo. Prendi nota del numero di ordine cliente.
1. Aggiungi una riga al nuovo ordine cliente e imposta i seguenti valori:

    - **Numero articolo:** *M9200*
    - **Quantità:** *25*

1. Seleziona **Aggiungi riga** per aggiungere una seconda riga, quindi imposta i seguenti valori:

    - **Numero articolo:** *M9202*
    - **Quantità:** *10*

1. Prenota scorte per entrambe le righe.
1. Rilascia l'ordine ordini al magazzino.

### <a name="get-work-ids-for-the-work-that-was-created"></a>Ottenere gli ID lavoro per il lavoro che è stato creato

1. Vai a **Gestione magazzino \> Lavoro \> Dettagli lavoro**.
1. Filtra il campo **Magazzino** in modo che il lavoro venga mostrato solo per il magazzino *51*.
1. Dovrebbero essere stati creati quattro ID lavoro. Prendi nota dell'ID di lavoro per ciascun ordine cliente.

    | ID ordine cliente | ID lavoro | Quantità lavoro |
    |---|---|---|
    | Ordine cliente 1 | ID lavoro 1 | 20 ea |
    | Ordine cliente 2 | ID lavoro 2 | 6 ea (somma di entrambe le righe) |
    | Ordine cliente 3 | ID lavoro 3 | 15 ea (somma di entrambe le righe) |
    | Ordine cliente 4 | ID lavoro 4 | 35 ea (somma di entrambe le righe) |

Prima di eseguire il flusso sul dispositivo mobile, verifica che solo il lavoro appena creato sia nello stato *Aperto* per il magazzino *51* e il tipo di ordine di lavoro *Ordine cliente*. Altrimenti, i risultati del test potrebbero variare, poiché il prelievo diretto dal sistema includerà tutto il lavoro idoneo.

1. Vai a **Gestione magazzino \> Lavoro \> In uscita \> Lavoro acquisti aperto**.
1. Nella griglia **Lavoro acquisti aperto**, filtra il campo **Magazzino** in modo che il lavoro venga mostrato solo per il magazzino *51*.
1. Conferma che vengono visualizzati solo i quattro ID lavoro creati in precedenza.
1. Chiudi la pagina **Lavoro**.

### <a name="mobile-device-flow-execution"></a>Esecuzione dei flussi su dispositivo mobile

In base alla configurazione, il sistema inserirà il lavoro dell'utente che viene ordinato dalla quantità più elevata della riga di lavoro alla più bassa. La quantità su ogni riga sarà inferiore a 20 ea.

Ricorda che questa configurazione acquisirà qualsiasi lavoro che abbia almeno una riga in cui la quantità è inferiore a 20 ea. Pertanto, se il lavoro ha un'altra riga in cui la quantità è esattamente 20 ea o più di 20 ea, anche questa sarà valida.

#### <a name="mobile-app"></a>App per dispositivi mobili

1. Accedi all'app di magazzino come utente nel magazzino *51*.
1. Vai a **In uscita \> Selezione vendite - Sistema**.

    Viene presentato il passaggio di prelievo per l'ID lavoro *4*. Questo ID lavoro viene presentato per primo a causa dell'impostazione dell'ordine di query diretto dal sistema, in cui è stato specificato che la sequenza del lavoro deve corrispondere alla quantità della riga di lavoro decrescente.

1. Completa il prelievo richiesto e chiudi l'ID lavoro.

    Quindi, viene presentato l'ID lavoro *3*. Una delle sue righe di lavoro è la seguente nella sequenza, in base alla quantità delle righe di lavoro.

1. Completa il prelievo e chiudi l'ID lavoro.

    Quindi, viene presentato l'ID lavoro *2*. La riga di prelievo di questo lavoro è la prossima nella sequenza.

1. Completa il prelievo e chiudi l'ID lavoro.

    Nessun ulteriore lavoro dovrebbe essere presentato. L'ID lavoro *1* non è idoneo per questa voce di menu del dispositivo mobile, poiché la query specifica che le intestazioni di lavoro sono considerate solo se la quantità sulle righe di lavoro è inferiore a 20 ea.

## <a name="tips"></a>Suggerimenti

Le query della sequenza di lavoro dirette dal sistema sono *inclusive*. È importante ricordare questo fatto per alcune configurazioni. Ad esempio, vuoi che una voce di menu specifica elabori il lavoro solo dove si trova l'unità di lavoro *ea* e specifichi tale limitazione nella scheda **Intervallo** della query. In questo caso, tutto il lavoro in cui almeno una riga di lavoro ha l'unità di lavoro impostata su *ea* sarà inserita sul lavoratore. Pertanto, questo lavoro potrebbe includere anche lavori in cui le righe di lavoro hanno un'unità di lavoro diversa da *ea* (ad esempio *scatola* o *pallet*). La query esclude il lavoro solo dove nessuna riga di lavoro ha l'unità di lavoro impostata su *ea*.

Pertanto, nell'esempio di questo scenario, l'ID lavoro *4* è stato anche acquisito dalla query. Quando è stato creato, sono state aggiunte due righe: una per 25 ea e una per 10 ea. Il lavoro è stato ancora presentato all'utente, poiché almeno una riga di lavoro ha una quantità inferiore a 20 ea.

A seconda dello scenario, è possibile impedire questo comportamento utilizzando le suddivisioni del lavoro.
