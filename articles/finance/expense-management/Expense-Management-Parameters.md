---
title: Parametri di gestione spese
description: I parametri seguenti controllano il comportamento in Gestione spese.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c1bc754b92e647f0fdac6799564273fb6ea6fb20
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178472"
---
# <a name="expense-management-parameters"></a>Parametri di gestione spese

[!include [banner](../includes/banner.md)]

-----------------------------

I parametri seguenti controllano il comportamento generale in Gestione spese.

### <a name="general"></a>Generale

| **Campo**                                                | **Descrizione**                                                 |
|----------------------------------------------------------|---------------------------------------------------------------------|
| **Tariffa standard chilometraggio**                             | Immettere la tariffa di rimborso delle spese di chilometraggio. La tariffa verrà moltiplicata in base al chilometraggio immesso nella spesa per calcolare l'importo rimborsato per le spese di viaggio.                       |
|**Spese personali pagate da**                             | Selezionare l'utente responsabile del pagamento di tutti gli importi di transazioni con carta di credito classificati come personali.                                                                                                     |
|**Visualizza intera nota spese in drill-back**               | Selezionare questa opzione per visualizzare tutte le spese per una nota spese durante la visualizzazione dei dettagli del documento originale per un giustificativo specifico generato con la registrazione della nota spese.              |
|**La preautorizzazione del viaggio è obbligatoria**                 | Selezionare questa opzione per richiedere che una richiesta di viaggio venga inoltrata e approvata prima dell'invio di una nota spese da parte di un dipendente.                                                                    |
|**Consenti modifica delle distribuzioni prima della registrazione**            | Selezionare se le distribuzioni di una nota spese possono essere modificate prima della registrazione.                                                                                                                 |
|**Valuta criteri di gestione spese**                     | Selezionare quando le spese vengono valutate per determinare se sono stati violati eventuali criteri di spesa. È possibile controllare eventuali violazioni quando si immette e si salva la voce di spesa o quando si inoltra la spesa per l'approvazione. Le regole dei criteri per le ricevute richieste verranno controllate quando viene salvata la riga di spesa.                   |
|**Consenti righe spese interaziendali**                         | Selezionare se consentire l'immissione di spese per altre persone giuridiche in una nota spese.                                                                                                          |
|**Consenti la modifica del tasso di cambio per le spese con carta di credito** | Selezionare questa opzione per consentire all'utente di modificare il tasso di cambio per le spese con carta di credito importate.                                                                        |
|**Campi della gerarchia multilivello da visualizzare**                  | Selezionare i campi dell'approvatore da visualizzare quando il tipo di assegnazione del flusso di lavoro della nota spese è impostato sulla gerarchia e la selezione della gerarchia è impostata in modo da utilizzare la gerarchia di approvazione multilivello delle spese. Quando la gerarchia di approvazione multilivello viene utilizzata per il flusso di lavoro, i campi selezionati vengono visualizzati nella nota spese e sono modificabili. |
|**Immettere il numero di carta di credito del dipendente (aggiornamento luglio 2017)**     | Selezionare se nel campo **ID carta** della pagina **Carte di credito** di un dipendente è possibile immettere e salvare un numero costituito da 15 o 16 caratteri.                                                                          |

### <a name="financial"></a>Finanziario

| **Campo**                                                            | **Descrizione**     |
|----------------------------------------------------------------------|------------------------------------|
|**Nome giornale di registrazione contabile**                                         | Selezionare il nome del giornale di registrazione contabile in cui vengono registrate le note spese approvate.            |
|**Attiva recupero imposte da spese**                                  | Selezionare questa opzione per consentire il recupero imposte di spesa per le spese idonee. Questa opzione non può essere attivata se sono attivate le regole sull'IVA e sulle imposte di utilizzo degli Stati Uniti.      |
|**Registra anticipo contanti immediatamente**                                     | Selezionare questa opzione per registrare un anticipo contanti approvato al completamento del processo Paga e trasferisci. Se l'opzione non è selezionata, il processo Paga e trasferisci genererà un giornale di registrazione generale non registrato. |
|**Correggi data di registrazione durante la registrazione**                             | Selezionare questa opzione per aggiornare la data di registrazione quando si registrano le spese se il periodo corrente è in attesa o chiuso. La data di registrazione verrà impostata sul successivo periodo aperto.   |
|**Consenti raggruppamento di transazioni in base al conto di contropartita specificato nel metodo di pagamento**      | Selezionare questa opzione per riepilogare le transazioni di spesa per una nota spese, in base al conto di contropartita specificato nel metodo di pagamento delle spese.   
|**Tasse incluse**                                                   | Selezionare questa opzione per includere l'IVA nell'importo di spesa per impostazione predefinita.             |
|**Rilascia impegni di spesa alla chiusura delle richieste di viaggio**            | Selezionare questa opzione per rilasciare fondi impegnati alla chiusura di una richiesta di viaggio approvata.                                                                                   |
|**Consenti inoltro richiesta di viaggio in caso di sovraccarico di budget per registro di budget e budget di progetto** | Selezionare questa opzione per consentire ai dipendenti di inviare per l'approvazione richieste di viaggio che superano il budget consentito indicato nel registro di budget oppure che superano il budget consentito per un progetto.            |
|**Consenti inoltro nota spese in caso di sovraccarico di budget per registro di budget e budget di progetto**    | Selezionare questa opzione per consentire ai dipendenti di inviare per l'approvazione note spese che superano il budget consentito indicato nel registro di budget oppure che superano il budget consentito per un progetto.                |
|**Consenti approvazione nota spese in caso di sovraccarico di budget solo per registro di budget**                | Selezionare questa opzione per consentire agli approvatori di approvare note spese che superano il budget consentito indicato nel registro di budget.                                                                       |

### <a name="per-diem"></a>Trasferta giornaliera

| **Campo**                             | **Descrizione**             |
|---------------------------------------|--------------------------------------------------------------------------------------|
|**Minimo ore per trasferta giornaliera**           | Immettere il numero minimo di ore predefinito che un dipendente deve lavorare al giorno per essere idoneo a essere rimborsato delle spese di viaggio per una trasferta giornaliera.  Questo valore viene utilizzato solo come valore predefinito per il campo Minimo ore nei livelli di tariffe giornaliere.                                                                                      |
|**Percentuale vitto**                          | Immettere la percentuale predefinita della trasferta giornaliera per il vitto utilizzata per il primo e l'ultimo giorno di spesa di viaggio quando il campo **Calcola riduzione per vitto per** è impostato su **Tipo di pasto al giorno** o **Numero di pasti al giorno**. Poiché la giornata lavorativa per il primo e l'ultimo giorno può essere più breve rispetto a un giorno lavorativo standard, l'ammontare della trasferta giornaliera in tali giorni può essere diversa dall'importo standard. Se la percentuale è impostata su 0, le detrazioni del primo e dell'ultimo giorno saranno pari a 0,00. |
|**Percentuale hotel**                        | Immettere la percentuale predefinita della trasferta giornaliera per le spese di hotel utilizzata il primo e l'ultimo giorno della spesa di viaggio. Poiché la giornata lavorativa per il primo e l'ultimo giorno può essere più breve rispetto a un giorno lavorativo standard, l'ammontare della trasferta giornaliera in tali giorni può essere diversa dall'importo standard. Se la percentuale è impostata su 0, le detrazioni del primo e dell'ultimo giorno saranno pari a 0,00.                                              |
|**Altra percentuale**                        | Immettere la percentuale predefinita della trasferta giornaliera per spese varie utilizzata il primo e l'ultimo giorno della spesa di viaggio. Poiché la giornata lavorativa per il primo e l'ultimo giorno può essere più breve rispetto a un giorno lavorativo standard, l'ammontare della trasferta giornaliera in tali giorni può essere diversa dall'importo standard. Se la percentuale è impostata su 0, le detrazioni del primo e dell'ultimo giorno saranno pari a 0,00.                                                                                                     |
|**Percentuale di riduzione per colazione** | Immettere la riduzione dell'importo di una trasferta giornaliera per la colazione. Se ad esempio a un dipendente viene offerta una colazione gratuita, è possibile ridurre l'importo della trasferta giornaliera del 10%.                               |
|**Percentuale di riduzione per pranzo**    | Immettere la riduzione dell'importo di una trasferta giornaliera per il pranzo. Se ad esempio a un dipendente viene offerto un pranzo gratuito, è possibile ridurre l'importo della trasferta giornaliera del 15%.                                       |
|**Percentuale di riduzione per cena**   | Immettere la riduzione dell'importo di una trasferta giornaliera per la cena. Se ad esempio a un dipendente viene offerta una cena gratuita, è possibile ridurre l'importo della trasferta giornaliera del 25%.                                     |
|**Calcola riduzione per vitto per**         | Selezionare la modalità con cui il sistema deve calcolare la riduzione di trasferta giornaliera per il vitto selezionando se la riduzione dipende dal tipo di vitto per viaggio o al giorno, o se la riduzione è basata sul numero di pasti consentiti al giorno.|
|**Arrotondamento trasferta giornaliera**                  | Selezionare il tipo di arrotondamento utilizzato per le spese di trasferta giornaliera. Se si seleziona un arrotondamento normale, le spese di trasferta giornaliera con un importo pari a 0,50 vengono arrotondate per eccesso a 1,00, mentre le spese con un importo inferiore a 0,50 vengono arrotondate per difetto a 0,00.                                                                                              |
|**Base per il calcolo della trasferta giornaliera**         | Selezionare se l'importo per la trasferta giornaliera si basa su un giorno di calendario o su un periodo di 24 ore.       |

### <a name="fax-cover-pages"></a>Copertine fax

| **Campo**                      | **Descrizione**            |
|--------------------------------|-----------------------------------------------------------------------------|
| **Istruzioni**                   | Immettere le istruzioni che i dipendenti devono rispettare quando creano una copertina fax utilizzata per inviare le ricevute correlate alla nota spese. Fare clic sul pulsante **Traduzioni** per immettere il testo in lingua che sarà visualizzato in base alla lingua dell'utente. |
|**ID utente (informazioni relative ai codici a barre)** | Selezionare questa opzione per memorizzare un identificatore univoco del dipendente nel codice a barre utilizzato sulla copertina fax.                 |
|**Codice a barre**                      | Selezionare il codice a barre da utilizzare sulla copertina fax. I codici a barre 39 e 128 sono supportati con Gestione spese.               |

### <a name="anti-corruption"></a>Anticorruzione

|                 <strong>Campo</strong>                 |                                                                                                                                                                                            <strong>Descrizione</strong>                                                                                                                                                                                             |
|--------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Visualizza attestazione anticorruzione</strong>  | Selezionare questa opzione per visualizzare il testo anticorruzione quando si crea una nuova nota spese. È quindi possibile attivare categorie di spesa specifiche per le quali sia richiesta la selezione dell'attestazione anticorruzione nella nota spese. Ad esempio, una categoria di regali correlata a una spesa per un funzionario statale può richiedere che il dipendente confermi l'idoneità della spesa rispetto ai criteri aziendali correlati ai funzionari statali. |
| <strong>Messaggio anticorruzione per autore dell'invio</strong> |                                                                                             Immettere il testo che verrà visualizzato al dipendente durante la creazione di una nuova nota spese. Fare clic sul pulsante <strong>Traduzioni</strong> per immettere il testo in lingua che sarà visualizzato in base alla lingua dell'utente.                                                                                             |
| <strong>Messaggio anticorruzione per approvatore</strong>  |                                                                                             Immettere il testo che verrà visualizzato all'approvatore durante la creazione di una nuova nota spese. Fare clic sul pulsante <strong>Traduzioni</strong> per immettere il testo in lingua che sarà visualizzato in base alla lingua dell'utente.                                                                                             |

