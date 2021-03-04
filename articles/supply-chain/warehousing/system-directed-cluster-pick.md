---
title: Prelievo cluster diretto dal sistema
description: In questo argomento viene fornita una panoramica del prelievi cluster diretto dal sistema in Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkCluster, WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0838405bcb5ee0d8e582093fbbd69553228cb2b6
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431539"
---
# <a name="system-directed-cluster-picking"></a>Prelievo cluster diretto dal sistema

[!include [banner](../includes/banner.md)]

Il prelievo cluster è un processo di prelievo dei pezzi che consente di prelevare gli articoli per più ordini contemporaneamente raggruppandoli in cluster di prelievo. Pertanto è necessario visitare il luogo di prelievo solo una volta. In genere, questa funzionalità viene utilizzata con prelievi di ordini di piccole dimensioni o quantità inferiori alle quantità del caso.

Quando viene configurato il prelievo cluster diretto dal sistema, è possibile prelevare in cluster le intestazioni di lavoro in base a un cluster generato dal sistema. Il sistema preleva in cluster gli ordini fino al numero di ubicazioni specificato nel profilo del cluster. Pertanto, è possibile prelevare più ordini contemporaneamente senza dover creare manualmente un cluster.

Il prelievo cluster diretto dal sistema offre un'alternativa alla creazione manuale dei cluster, in cui un profilo cluster viene utilizzato per creare un cluster. Diverse righe relative alla configurazione devono essere definite nel profilo del cluster prima di essere utilizzate:

- **Numero di posizioni** corrisponde al numero di ordini che verranno inseriti in un cluster. Pertanto, corrisponde al numero di totali.
- **Suddividi cluster** determina in che modo il cluster deve essere suddiviso.
- **Genera ID cluster** controlla se l'ID cluster verrà generato dal sistema o immesso dall'utente.
- **Ordina tipo di verifica** determina se la verifica della posizione è obbligatoria.

Una nuova voce di menu del dispositivo mobile viene utilizzata per il prelievo cluster diretto dal sistema. L'**ID profilo cluster** deve essere specificato per l'opzione **Diretto da** selezionata. Inoltre, le query della sequenza di lavoro diretta dal sistema possono raggruppare gli ordini in base a criteri specifici dell'azienda. Pertanto, è possibile ottimizzare ulteriormente l'assegnazione degli ordini di lavoro specificando criteri di ordinamento che utilizzano le query della sequenza di lavoro diretta dal sistema.

Quando il prelievo cluster diretto dal sistema viene abilitato, ai magazzinieri viene presentato un cluster in cui gli ordini di prelievo sono stati preassegnati alle posizioni del cluster. Pertanto, gli addetti possono iniziare a prelevare un articolo per più ordini di lavoro visitando la posizione di prelievo una sola volta. Il processo di prelievo per il prelievo cluster diretto dal sistema è uguale al processo di prelievo cluster diretto dall'utente.

## <a name="enable-the-system-directed-cluster-picking-feature"></a>Abilitare la funzionalità di prelievo cluster diretto dal sistema

Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema. Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario. La funzione viene elencata come:

- **Modulo**: Gestione magazzino
- **Nome funzione**: Prelievo cluster diretto dal sistema

Questa funzionlità richiede anche l'abilitazione di una funzionalità dipendente. La funzionalità dipendente è:

- **Modulo**: Gestione magazzino
- **Nome funzione**: Sequenza del lavoro diretto al sistema a livello di organizzazione

## <a name="set-up-system-directed-cluster-picking"></a>Configurare il prelievo cluster diretto dal sistema

### <a name="create-cluster-profiles"></a>Creare profili cluster

I profili cluster controllano il modo in cui il sistema crea ciascun cluster. Se sono richiesti cluster diversi, è necessario creare un profilo cluster diverso per ciascuna voce di menu del dispositivo mobile.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Profili cluster**.
2. Selezionare **Nuovo**.
3. Nel campo **ID profilo cluster**, immetti **2 posizioni**.
4. Nel campo **Nome** immettere **2 posizioni**.
5. Nella scheda dettaglio **Generale** immettere le seguenti informazioni:

    - **Genera ID cluster**: selezionare **Sì**. Questa opzione determina se l'ID cluster viene creato automaticamente dal sistema o se l'utente lo creerà all'inizio del prelievo. 
    - **Attiva posizioni:** selezionare **Sì**. Questa opzione determina se i nomi delle posizioni vengono generati automaticamente in base all'impostazione del nome della posizione. Se l'opzione è impostata su **No**, viene utilizzato l'ID della targa per la posizione.
    - **Numero di posizioni:** selezionare **2**. Questo campo determina il numero massimo di posizioni che il cluster può avere (ovvero il numero massimo di caselle, totali e così via).
    - **Nome posizione:** selezionare **Numerico**, in modo che le posizioni vengano denominate utilizzando numeri continui. Se si seleziona **Alfabetico**, le posizioni sono denominate in ordine alfabetico.
    - **Suddividi cluster a:** selezionare **Inserisci**. Questo campo determina quando il cluster viene suddiviso. 
    - **Ordina tipo di verifica:** selezionare **Scansione di posizione**. Questo campo determina se il passaggio di inserimento in posizione è verificato.
        
6. Nella scheda dettagli **Ordinamento cluster**, è possibile definire i criteri di ordinamento creando una nuova riga e immettendo le nformazioni seguenti:

    - **Sequenza numerica**: selezionare **1**. Questo campo determina la sequenza in base alla quale il sistema esegue l'ordinamento. Un valore viene inserito automaticamente, ma è possibile modificarlo se necessario.
    - **Nome campo:** immettere **WMSLocationId**. Questo campo determina il campo utilizzato dalla riga per i criteri di ordinamento.
    - **Ordinamento:** selezionare **Crescente**. Questo campo definisce se l'ordinamento viene eseguito in ordine crescente o decrescente.

### <a name="create-a-mobile-device-menu-item"></a>Creare una voce di menu per dispositivo mobile

Per creare una nuova voce di menu del dispositivo mobile per il prelievo cluster diretto dal sistema e collegare l'ID profilo del cluster alla voce di menu del dispositivo mobile, attenersi alla seguente procedura.

1. Andare a **Gestione magazzino > Impostazioni > Dispositivo mobile > Voci di menu del dispositivo mobile**.
1. Selezionare **Nuovo**.
1. Nella sezione dell'intestazione immettere le informazioni seguenti:
    - **Nome voce di menu**: Cluster SD
    - **Titolo**: Cluster SD
    - **Modalità**: Lavoro
    - **Utilizza lavoro esistente**: Sì

1. Nella scheda dettaglio **Generale** immettere le seguenti informazioni:
    - **Diretto da**: Prelievo cluster diretto dal sistema
    - **Genera targa**: Sì
    - **ID profilo cluster**: 2 posizioni

1. Nella Scheda dettaglio **Classi di lavoro**, impostare la classe di lavoro valida per questa voce di menu del dispositivo mobile impostando i seguenti campi:
    - **ID classe lavoro**: Vendita
    - **Tipo di ordine di lavoro**: Ordini di vendita

1. Nel riquadro azioni **Voci di menu del dispositivo mobile**, selezionare **Query della sequenza di lavoro diretta dal sistema** e seguire questi passaggi per specificare una nuova query della sequenza di lavoro diretta dal sistema:
    - Nel riquadro azioni selezionare **Nuovo**.
    - **Sequenza numerica**: 1
    - **Descrizione**: - Priorità lavoro - ID lavoro

1. Nel riquadro azioni, selezionare **Modifica query**.
1. Selezionare la scheda **Ordinamento**.
1. Selezionare **Aggiungi** per aggiungere una nuova riga, quindi immettere quanto segue:
    - **Tabella**: - Lavoro
    - **Tabella derivata**: Lavoro
    - **Campo**: Priorità lavoro
    - **Direzione di ricerca**: Crescente
1. Selezionare **Aggiungi** per aggiungere una seconda riga, quindi immettere quanto segue:
    - **Tabella**: - Lavoro
    - **Tabella derivata**: Lavoro
    - **Campo**: ID lavoro
    - **Direzione di ricerca**: Crescente

1. Il sistema ordinerà ora gli ID lavoro nel cluster, prima per priorità di lavoro e poi per ID lavoro.

### <a name="set-up-a-mobile-device-menu"></a>Configurare un menu per dispositivo mobile

1. Andare a **Gestione magazzino > Impostazioni > Dispositivo mobile > Menu del dispositivo mobile**.
1. Aggiungere la voce di menu **Cluster SD** appena creata al menu del dispositivo mobile.
1. Selezionare il menu **In uscita**.
1. Nel riquadro azioni, selezionare **Modifica**.
1. Scorrere fino a trovare **Cluster SD**.
1. Selezionare **Cluster SD**; la freccia che punta all'elenco **Struttura menu** verrà abilitata.
1. Selezionare il pulsante **freccia** per spostare la voce di menu **Cluster SD** nella struttura di menu **In uscita**.
1. Selezionare **Cluster SD** dall'elenco **Struttura menu**, quindi selezionare la freccia **SU** o **GIÙ** per spostare la voce di menu nella posizione desiderata nel menu del dispositivo mobile.

## <a name="scenario"></a>Scenario

### <a name="create-picking-work"></a>Creare il lavoro di prelievo

Prima di poter impostare il prelievo cluster diretto al sistema, è necessario creare del lavoro in uscita idoneo. Il profilo cluster creato in precedenza specifica due posizioni cluster. Pertanto, è necessario creare almeno due ID lavoro. In questo scenario, verranno creati due ordini cliente, si prenoteranno le scorte, si rilasceranno gli ordini cliente al magazzino e quindi si elaborerà l'onda manualmente.

1. Andare a **Vendite e marketing > Ordini cliente > Tutti gli ordini cliente**.
1. Per creare il primo ordine cliente, nel Riquadro azioni, selezionare **Nuovo**.
    - Si apre il menu **Crea ordine cliente**; inserire le seguenti informazioni:
        - Nella Scheda dettaglio **Cliente**, immettere **Conto cliente** - **US-004**.
        - Nella Scheda dettaglio **Generale**, immettere **Magazzino** - **62**.
        - Selezionare **OK** per chiudere il menu e creare l'ordine cliente.
    - Nella Scheda rapida **Righe ordine cliente**, selezionare **Aggiungi riga** se una nuova riga non viene aggiunta automaticamente e immettere quanto segue:
        - **Numero articolo**: A0001
        - **Quantità**: 1
        - Selezionare **Aggiungi riga** per aggiungere una seconda riga.
        - **Numero articolo**: A0002
        - **Quantità**: 3
    - Prenotare le scorte per entrambe le righe appena create.
        - Selezionare **Riga 1**.
        - Nella scheda dettaglio **Righe ordine cliente** selezionare **Scorte** e quindi selezionare **Prenotazione** nell'elenco.
        - Nel modulo **Prenotazione**, selezionare **Prenota lotto** per prenotare le scorte.
        - Chiudere il modulo **Prenotazione** al termine della prenotazione.
        - Ripetere questi passaggi per prenotare le scorte per **Riga 2**.
1. Per creare il secondo ordine cliente, nel Riquadro azioni, selezionare **Nuovo**.
    - Si apre il menu **Crea ordine cliente**; inserire le seguenti informazioni:
        - Nella Scheda dettaglio **Cliente**, immettere **Conto cliente** - **US-005**.
        - Nella Scheda dettaglio **Generale**, immettere **Magazzino** - **62**.
        - Selezionare **OK** per chiudere il menu e creare l'ordine cliente.
    - Nella Scheda rapida **Righe ordine cliente**, selezionare **Aggiungi riga** se una nuova riga non viene aggiunta automaticamente e immettere quanto segue:
        - **Numero articolo**: A0001
        - **Quantità**: 4
        - Selezionare **Aggiungi riga** per aggiungere una seconda riga.
        - **Numero articolo**: A0002
        - **Quantità**: 2
    - Prenotare le scorte per entrambe le righe appena create.
        - Selezionare **Riga 1**.
        - Nella scheda dettaglio **Righe ordine cliente** selezionare **Scorte** e quindi selezionare **Prenotazione** nell'elenco.
        - Nel modulo **Prenotazione**, selezionare **Prenota lotto** per prenotare le scorte.
        - Chiudere il modulo **Prenotazione** al termine della prenotazione.
        - Ripetere questi passaggi per prenotare le scorte per **Riga 2**.
    - Chiudere l'ordine cliente e ritornare alla pagina elenco **Tutti gli ordini clienti**.
1. Trovare i due ordini cliente appena creati (è possibile che sia necessario aggiornare la pagina). Nella tabella selezionare entrambi gli ordini cliente utilizzando il segno di spunta della sezione.
    - Nel riquadro azioni **Tutti gli ordini cliente**, selezionare la scheda **Magazzino**.
    - Nel gruppo **Azioni**, selezionare **Rilascia in magazzino** per rilasciare entrambi gli ordini cliente al magazzino.
1. Una volta completato il processo di rilascio in magazzino, verrà visualizzato un messaggio informativo.
    - Le spedizioni verranno create per ciascun ordine cliente.
    - Verrà creata un'onda ed entrambe le spedizioni verranno assegnate all'onda. Prendere nota dell'**ID onda**.
1. Selezionare **Gestione magazzino > Ondate in uscita > Ondate spedizione > Tutte le ondate**.
    - Nell'elenco **Tutte le onde** trovare e selezionare l'**ID onda** creato nel passaggio precedente.
    - Selezionare la scheda **Onda** nel riquadro azioni.
    - Nel gruppo **Onda**, selezionare **Elabora** per elaborare l'onda e creare **Lavoro**.
    - Al termine dell'elaborazione verranno generati messaggi informativi per indicare che il lavoro è stato creato e che l'onda è stata pubblicata.
1. **Facoltativo**: andare a **Gestione magazzino > Lavoro> Dettagli lavoro** per visualizzare il lavoro creato. Vengono creati due diversi ID lavoro. Ogni ID lavoro ha due righe di prelievo.

### <a name="run-the-mobile-device-flow"></a>Eseguire il flussi del dispositivo mobile

1. Accedere al dispositivo mobile di un utente in magazzino **62**.
1. Nel **Menu principale**, selezionare **In uscita**.
1. Nel menu menu **In uscita**, selezionare **Cluster SD** per avviare il prelievo.
    - Viene creato un cluster a cui vengono associati i due ID lavoro creati in precedenza. Se sono stati creati più di due ID lavoro, solo i primi due vengono aggiunti al cluster. Si noti che gli ID lavoro vengono aggiunti al cluster in ordine crescente, come specificato nell'impostazione della query.

    > [!NOTE]
    > Il nuovo cluster viene creato automaticamente solo se in precedenza sono stati creati abbastanza ID lavoro aggiuntivi. In caso contrario, viene visualizzato il seguente messaggio: "Impossibile trovare lavoro sufficiente per il cluster".

    - Dopo aver selezionato il menu, viene visualizzata la prima schermata di prelievo. Il sistema aggrega tutte le righe di prelievo corrispondenti dai due ID lavoro e suggerisce di visitare una volta il luogo di prelievo, in modo da poter soddisfare entrambi gli ordini utilizzando un solo prelievo. Questo processo viene eseguito allo stesso modo del processo per il prelievo cluster diretto dall'utente.

1. Confermare la prima posizione di prelievo e l'articolo selezionando **OK**.
    - La quantità del prelievo sarà il totale dell'articolo visualizzato negli ordini cliente nel cluster.
1. Immettere il nome della posizione (numerico o alfabetico) per confermare che la quantità dell'articolo prelevata per la posizione è stata inserita nella posizione corretta.
1. Ripetere questo processo fino a quando tutte le quantità dell'articolo siano state prelevate e inserite nella posizione corretta.
1. L'ultimo passaggio sul dispositivo mobile consiste nell'**inserire** il cluster nella posizione finale. Selezionare **OK**.
    - Quando l'operazione di inserimento viene confermata, il cluster viene chiuso e suddiviso, in base al valore impostato per il campo **Suddividi il cluster a** nel profilo cluster. Anche gli ID lavoro vengono chiusi.
1. Sul dispositivo mobile viene visualizzato il messaggio "Cluster completato".


[!INCLUDE[footer-include](../../includes/footer-banner.md)]