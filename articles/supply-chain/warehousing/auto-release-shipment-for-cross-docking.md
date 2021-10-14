---
title: Rilascio automatico della spedizione della versione per cross-docking
description: In questo argomento viene descritta una strategia di cross-docking che consente di rilasciare automaticamente un ordine di domanda nel magazzino quando l'ordine di produzione che fornisce la quantità della domanda viene dichiarato finito, in modo che la quantità viene spostata direttamente dall'ubicazione di uscita della produzione nell'ubicazione in uscita.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 1315bda1fd284eb326d4f08bf36bfea59074fde3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577938"
---
# <a name="auto-release-shipment-for-cross-docking"></a>Rilascio automatico della spedizione della versione per cross-docking

[!include [banner](../includes/banner.md)]

In questo argomento viene descritta una strategia di cross-docking che consente di rilasciare automaticamente un ordine di domanda nel magazzino quando l'ordine di produzione che fornisce la quantità della domanda viene dichiarato finito. In questo modo, la quantità necessaria per l'esecuzione dell'ordine di domanda viene spostata direttamente dall'ubicazione di uscita della produzione nell'ubicazione in uscita.

Il cross-docking è un magazzino che gestisce il flusso in cui la quantità necessaria per soddisfare un ordine in uscita viene eseguita nella banchina di uscita o nell'area di transito dell'ordine dall'ubicazione in cui l'ordine in entrata è stato ricevuto. L'ordine in entrata può essere un ordine fornitore, un ordine di trasferimento o di produzione. Benché che la funzionalità avanzata di cross-docking supporta tutti gli ordini di offerta e domanda e richiede che la domanda in uscita sia rilasciata prima che l'opportunità di cross-dock venga identificata, la funzionalità di rilascio automatico della spedizione ha le seguenti caratteristiche:

- Supporta solo gli ordini di produzione come fornitura e solo gli ordini cliente e gli ordini di trasferimento come domanda.
- L'operazione di cross-docking può essere avviata anche se l'ordine di domanda non è stato rilasciato al magazzino prima della registrazione del ricevimento della fornitura, ovvero prima che la produzione venga dichiarata finita.

Questa funzionalità di cross-docking ha due vantaggi:

- Le operazioni di magazzino possono ignorare il passaggio dello stoccaggio di prodotti finiti nell'area di immagazzinamento regolare se tali quantità verranno prelevate ancora per evadere l'ordine di uscita. In questo caso, le quantità possono essere spostate una volta, dall'ubicazione di uscita a un'ubicazione di spedizione/imballaggio. In questo modo, le funzionalità consente di ridurre il numero di volte che le scorte vengono gestite e, infine, massimizzare il risparmio di tempo e spazio nello shop floor del magazzino.
- Le operazioni di magazzino possono posticipare il rilascio degli ordini cliente e degli ordini di trasferimento nel magazzino fino a quando l'uscita dei prodotti finiti per l'ordine di produzione associato viene dichiarata come finita. Il vantaggio può risultare particolarmente importante negli ambienti di produzione su ordine, in cui i lead time di produzione tendono a essere più lunghi dei lead time negli ambienti di produzione per magazzino.

## <a name="prerequisites"></a>Prerequisiti

| Prerequisito | Descrizione |
|---|---|
| Elemento | Gli articoli devono essere abilitati per i processi di gestione magazzino.<p>**Nota:** gli articoli abilitati per il peso variabile non possono essere inclusi nei processi di cross-docking.</p> |
| Magazzino | Il magazzino deve essere abilitato per i processi di gestione magazzino. |
| Modelli di cross-docking | Almeno un modello di cross-docking che utilizza i criteri di rilascio della domanda **Al ricevimento della fornitura** deve essere impostato per un magazzino specifico. |
| Classe lavoro | L'ID della classe di lavoro di cross-docking deve essere creato per il tipo di ordine di lavoro **Cross-docking**. |
| Modelli di lavoro | I modelli di tipo di ordine di lavoro **Cross-docking** sono necessari per creare il lavoro di prelievo e stoccaggio di cross-docking. |
| Direttive ubicazione | Le direttive ubicazione del tipo di ordine di lavoro **Cross-docking** sono necessarie per facilitare il lavoro di stoccaggio nelle ubicazioni in cui le quantità degli ordini cliente vengono imballate e spedite. |
| Contrassegno tra un ordine di domanda e un ordine di produzione | Il sistema di gestione magazzino può attivare il rilascio automatico della spedizione dell'ordine di uscita e creare un lavoro cross-docking dall'ubicazione di uscita all'azione di dichiarazione di finito solo se gli ordini cliente e gli ordini di trasferimento vengono prenotati e contrassegnati per un ordine di produzione. |

## <a name="example-cross-docking-flow"></a>Flusso di cross-docking di esempio

Un flusso tipico di cross-docking è costituito dalle seguenti operazioni principali.

1. Un incaricato dell'ordine cliente crea un ordine cliente per un prodotto di tipo produzione su ordine. In genere, la quantità richiesta non è disponibile e deve prima essere prodotta.
2. L'incaricato dell'ordine cliente crea un ordine di produzione direttamente dalla riga ordine cliente. In questo modo, l''incaricato dell'ordine cliente prenota e contrassegna la quantità dell'ordine cliente rispetto alla quantità dell'ordine di produzione. 

    In alternativa, un pianificazione di produzione indica che il contrassegno deve essere aggiornato quando gli ordini pianificati vengono stabilizzati.

3. L'ordine di produzione comporta l'esecuzione delle seguenti operazioni:

    1. Una pianificazione della produzione stima e rilascia l'ordine di produzione. La stima include la prenotazione di materie prime e il rilascio include l'uscita in un magazzino.
    2. Un addetto magazzino avvia e completa il prelievo di materie prime dall'ubicazione di immagazzinamento all'ubicazione di entrata della produzione, in base al lavoro di prelievo di produzione.
    3. Un operatore dello shop floor avvia l'ordine di produzione.
    4. Nell'ultima operazione, un operatore utilizza il dispositivo mobile per dichiarare finito l'ordine di produzione.

4. Il sistema utilizza l'impostazione per identificare l'evento di cross-docking per i due ordini collegati, quindi completa le seguenti attività:

    1. Rilasciare automaticamente l'ordine cliente collegato a un magazzino per creare una spedizione.
    2. Creare automaticamente il lavoro di cross-docking con le istruzioni per il prelievo dei prodotti finiti dall'ubicazione di uscita e spostarli nell'ubicazione in uscita che le direttive di ubicazione di cross-docking hanno assegnato all'ordine cliente.
    3. Richiedere a un operatore di completare il lavoro di cross-docking subito dopo che l'ordine di produzione viene dichiarato finito.

5. Dopo che il lavoro di cross-docking è completato e le quantità vengono caricate nel veicolo, un addetto alla pianificazione del magazzino conferma la spedizione di vendita.

## <a name="example-scenario"></a>Scenario di esempio

Per questo scenario, i dati dimostrativi devono essere installati ed è necessario utilizzare la società di dati dimostrativi **USMF**.

### <a name="set-up-cross-docking-that-uses-the-auto-release-shipment-feature"></a>Impostare il cross-docking che utilizza la funzionalità di spedizione con rilascio automatico

#### <a name="cross-docking-template"></a>Modello di cross-docking

1. Andare a **Gestione magazzino** \> **Impostazione** \> **Lavoro** \> **Modelli di cross-docking**.
2. Selezionare **Nuovo**.
3. Nel campo **Numero progressivo** immettere **1**.
4. Nel campo **ID modello di cross-docking**, immettere un nome, ad esempio **XDock\_RAF**.
5. Nel campo **Criteri di rilascio della domanda** selezionare **Al ricevimento della fornitura**.
6. Nel campo **Magazzino**, immettere il numero del magazzino in cui si desidera impostare il processo di cross-docking. Per questo esempio, selezionare **51**.

    > [!NOTE]
    > Non appena si seleziona **Al ricevimento della fornitura** come criteri del rilascio della domanda per il modello, tutti gli altri campi presenti nella pagina diventano non disponibili. Inoltre, non è possibile definire le origini della fornitura. Questo comportamento si verifica perché il cross-docking che utilizza la funzionalità di spedizione con rilascio automatico supporta solo gli ordini di produzione come origini della fornitura e richiede che esista un contrassegno tra gli ordini cliente e gli ordini di produzione. Se si seleziona **Prima del ricevimento della fornitura** come criteri di rilascio della domanda, i campi delle schede **Progettazione** e **Origini di fornitura** sono disponibili e possono essere modificati.

#### <a name="work-classes"></a>Classi lavoro

1. Andare a **Gestione magazzino** \> **Impostazioni** \> **Lavoro** \> **Classi di lavoro**.
2. Selezionare **Nuovo**.
3. Nel campo **ID classe di lavoro**, immettere un nome, ad esempio **CrossDock**.
4. Nel campo **Tipo ordine di lavoro** selezionare **Cross-docking**.

Per limitare i tipi di ubicazione per lo stoccaggio dei prodotti finiti con cross-docking, è possibile specificare uno o più tipi di ubicazione validi.

#### <a name="work-templates"></a>Modelli di lavoro

1. Andare a **Gestione magazzino** \> **Impostazioni** \> **Lavoro** \> **Modelli di lavoro**.
2. Nel campo **Tipo ordine di lavoro** selezionare **Cross-docking**.
3. Selezionare **Nuovo**.
4. Nel campo **Numero progressivo** immettere **1**.
5. Nel campo **Modello di lavoro**, immettere un nome, ad esempio **CrossDock\_51**.
6. Selezionare **Salva**.
7. Nella sezione **Dettagli modello di lavoro**, selezionare **Nuovo**.
8. Per la nuova riga, nel campo **Tipo di lavoro**, selezionare **Prelievo**. Nel campo **ID classe lavoro** selezionare **CrossDock**.
9. Selezionare **Nuovo**.
10. Per la nuova riga, nel campo **Tipo di lavoro**, selezionare **Stoccaggio**. Nel campo **ID classe lavoro** selezionare **CrossDock**.

#### <a name="location-directives"></a>Direttive ubicazione

Un processo di stoccaggio standard per i prodotti finiti richiede una direttiva di ubicazione **Stoccaggio** per guidare lo spostamento delle quantità di produzione prelevate verso uno spazio di stoccaggio regolare. Inoltre, è necessario impostare una direttiva di ubicazione **Stoccaggio** di cross-docking per indicare al lavoro di stoccare la quantità finita in un'ubicazione di uscita designata che serve la spedizione dell'ordine cliente collegato.

Per il cross-docking, come per il normale stoccaggio dei prodotti finiti, non è necessario creare una direttiva di ubicazione per l'azione di prelievo perché viene fornita l'ubicazione di uscita. Inoltre, si prevede che questa ubicazione di uscita sia impostata come ubicazione di uscita predefinita per uno dei record relativi alle risorse (vale a dire, la risorsa, la relazione del gruppo di risorse o il gruppo di risorse) o come ubicazione predefinita dei prodotti finiti di produzione per un magazzino.

1. Andare a **Gestione magazzino** \> **Impostazioni** \> **Direttive ubicazione**.
2. Nel campo **Tipo ordine di lavoro** selezionare **Cross-docking**.
3. Selezionare **Nuovo**.
4. Nel campo **Numero progressivo** immettere **1**.
5. Nel campo **Nome**, immettere un nome, ad esempio **Baydoor**.
6. Nel campo **Tipo di lavoro** selezionare **Inserisci**.
7. Nel campo **Sito** selezionare **5**.
8. Nel campo **Magazzino** selezionare **51**.
9. Nella scheda dettaglio **Righe**, selezionare **Nuovo**.
10. Nel campo **A quantità**, immettere la quantità massima dell'intervallo, ad esempio **1000000**.
11. Selezionare **Salva**.
12. Nella scheda dettaglio **Azioni delle direttive di ubicazione**, selezionare **Nuovo**.
13. Nel campo **Nome**, immettere un nome, ad esempio **Baydoor**.
14. Selezionare **Salva**.
15. È possibile utilizzare la funzione di query standard per limitare le ubicazioni di stoccaggio a una o più ubicazioni specifiche. Selezionare **Modifica query** e selezionare **51** con criterio per il campo **Magazzino** nella tabella **Ubicazioni**.

### <a name="cross-dock-finished-goods-to-the-outbound-location"></a>Prodotti finiti di cross-docking nell'ubicazione in uscita

Per eseguire il cross-dock della quantità di prodotti finiti nell'ubicazione in uscita dell'ordine cliente associato, attenersi alla seguente procedura.

1. Andare a **Vendite e marketing** \> **Ordini cliente** \> **Tutti gli ordini cliente**.
2. Selezionare **Nuovo**.
3. Per l'intestazione dell'ordine cliente, selezionare l'account **US-001** e un magazzino impostato per il cross-docking che utilizza la funzionalità di spedizione con rilascio automatico.
4. Aggiungere una riga per un prodotto finito e immettere **10** come quantità.
5. Nella sezione **Righe ordine cliente**, selezionare **Prodotto e fornitura** \> **Ordine di produzione**.
6. Nella finestra di dialogo **Crea ordine di produzione**, esaminare i valori predefiniti e quindi selezionare **Crea**. Un nuovo ordine di produzione viene creato e associato all'ordine cliente, ovvero viene riservato e contrassegnato.
7. Facoltativo: modificare il valore del campo **Quantità** in modo che sia superiore al valore necessario per evadere l'ordine cliente. Quando la quantità di produzione viene dichiarata finita, il sistema crea le operazioni di cross-docking per la quantità contrassegnata e il lavoro di stoccaggio per la quantità rimanente, in base alla normale procedura per la gestione dello stoccaggio dei prodotti finiti.

    Come indicato in precedenza, un contrassegno deve esistere tra l'ordine cliente e l'ordine di produzione. In caso contrario, il cross-docking non verrà eseguito. Un contrassegno può essere creato in diversi modi:

    - Il sistema crea automaticamente il contrassegno nelle seguenti situazioni:

        - L'ordine di produzione viene creato manualmente direttamente dalla riga ordine cliente (vedere il passaggio 6).
        - Gli ordini di produzione pianificati vengono stabilizzati e il campo **Aggiorna contrassegno** è impostato su **Standard**.

    - L'utente può creare manualmente il contrassegno aprendo la pagina **Contrassegno** dalla riga dell'ordine di domanda.

    > [!NOTE]
    > Un contrassegno non può essere creato manualmente per gli articoli impostati per l'utilizzo della media ponderata e standard come modelli inventariali.

8. Nella pagina **Ordine di produzione**, nel riquadro azioni, nella scheda **Ordine di produzione**, nel gruppo **Processo** selezionare **Stima** e quindi **OK**. L'ordine viene stimato e la quantità di materie prime viene prenotata per la produzione.
9. Nel riquadro azioni, nella scheda **Ordine di produzione**, nel gruppo **Processo** selezionare **Rilascio** e quindi **OK**. Il lavoro di prelievo di magazzino viene creato per le materie prime.
10. Aprire ed esaminare il lavoro. Nella scheda **Magazzino** del riquadro azioni, nel gruppo **Generale**, selezionare **Dettagli lavoro**. Prendere nota dell'ID lavoro.
11. Accedi all'app per dispositivi mobili Gestione magazzino per eseguire il lavoro nel magazzino 51.
12. Andare a **Produzione** \> **Prelievo di produzione**.
13. Immettere l'ID lavoro per avviare e completare il prelievo delle materie prime. 

    Dopo che il lavoro è dichiarato finito, la quantità delle materie prime è disponibile nell'ubicazione di entrata produzione (**005** nei dati dimostrativi di USMF) e l'esecuzione dell'ordine di produzione può iniziare.

14. Nella pagina **Ordine di produzione**, nel riquadro azioni, nella scheda **Ordine di produzione**, nel gruppo **Processo** selezionare **Avvia** e quindi **OK**.
15. Nel'app, andare a **Produzione** \> **Dichiarata finita e stoccaggio**.
16. Nel campo **ID produzione**, immettere il numero dell'ordine di produzione e altri dettagli obbligatori, quindi selezionare **OK**.

Si verificano i seguenti eventi:

- Il rilascio a un magazzino viene attivato per l'ordine cliente associato.
- In base al rilascio, viene creato il lavoro di spedizione e cross-docking. Questo lavoro indica all'operatore del magazzino di prelevare le quantità richieste per soddisfare la riga ordine cliente e metterle nell'ubicazione in uscita specificata nella direttiva di ubicazione di cross-docking.
- Se la quantità dell'ordine di produzione è maggiore della quantità richiesta dall'ordine cliente, viene creato il lavoro di stoccaggio regolare. Questo lavoro indica all'operatore del magazzino di prelevare la quantità di prodotti finiti rimanente dopo cross-docking e spostarla nell'ubicazione normale, a seconda della direttiva di ubicazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]