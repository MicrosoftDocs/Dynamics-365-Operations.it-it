---
title: Transazioni della gestione degli sconti
description: In questo argomento viene descritto come creare le transazioni di gestione degli sconti. Le transazioni vengono utilizzate per controllare diversi metodi e basi per il calcolo di sconti e royalty. Includono regole per inclusioni ed esclusioni.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 5b8a1beae80ad63f26cd1b532d1d6026a5b38a8701c9c1d0aadfee5da8965477
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716494"
---
# <a name="rebate-management-deals"></a>Transazioni della gestione degli sconti

[!include [banner](../includes/banner.md)]

Le transazioni di gestione degli sconti vengono utilizzate per controllare diversi metodi e basi per il calcolo di sconti e royalty. Includono regole per inclusioni ed esclusioni. Esistono tre tipi di transazioni di gestione degli sconti: sconti per i clienti, royalty per i clienti e sconti per i fornitori. Tutti e tre i tipi utilizzano impostazioni simili. Questo argomento evidenzia le differenze dove presenti.

## <a name="create-a-deal"></a>Creare una transazione

1. Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Tutti le transazioni di gestione degli sconti**. Nella pagina elenco **Tutte le transazioni di gestione degli sconti** puoi creare e lavorare con transazioni di tutti e tre i tipi.

    In alternativa, segui uno dei passaggi seguenti. In ogni caso, la pagina elenco che appare fornisce tutte le stesse impostazioni della pagina elenco **Tutte le transazioni di gestione degli sconti** ma è filtrata per mostrare transazioni di un solo tipo.

    - Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Transazioni di sconti per clienti** per creare solo transazioni di sconti per i clienti.
    - Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Transazioni di royalty per clienti** per creare solo transazioni di royalty per i clienti.
    - Vai a **Gestione degli sconti \> Transazioni di gestione degli sconti \> Transazioni di sconti per fornitori** per creare solo transazioni di sconti per i fornitori.

1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea nuova transazione**, imposta i seguenti campi:

    - **Transazione di gestione degli sconti** - Se hai [impostato una sequenza numerica](rebate-management-parameters.md) per le transazioni di sconti, questo campo viene impostato automaticamente su un ID univoco generato dal sistema. In caso contrario, immetti un ID univoco.
    - **Descrizione** - Immetti una descrizione della transazione.
    - **Modulo** - Seleziona il tipo di partner a cui si applica la transazione (*Cliente* o *Fornitore*). A seconda della pagina da cui sei partito, questo campo potrebbe essere impostato automaticamente in base al tipo di transazione selezionata. In questo caso il campo è in sola lettura.
    - **Tipo** - Seleziona il tipo di transazione (*Sconto* o *Royalty*). A seconda della pagina da cui sei partito, questo campo potrebbe essere impostato automaticamente in base al tipo di transazione selezionata. In questo caso il campo è in sola lettura.
    - **Riconcilia per** - Seleziona la modalità di calcolo e riconciliazione della transazione:

        - *Transazione* - Deve essere elaborato un unico sconto per tutti gli sconti e le detrazioni della transazione.
        - *Riga* - Gli sconti devono essere elaborati per ogni riga in una transazione.

    - **Profilo di registrazione** - Seleziona il [profilo di registrazione](rebate-management-posting.md) da utilizzare per le transazioni in cui si applica la transazione. Questo campo è disponibile solo quando il campo **Riconcilia per** è impostato su *Transazione*. Se è impostato su *Riga*, assegnerai il profilo in un secondo momento, per ogni riga che aggiungi alla transazione.
    - **Profilo di registrazione per garanzia** - Seleziona il [profilo di registrazione](rebate-management-posting.md) da utilizzare per le transazioni di garanzia. I profili di registrazione sono necessari per le transazioni di garanzia solo se la garanzia si applica a una royalty. In caso contrario, sebbene un profilo di registrazione non sia obbligatorio, se non viene specificato alcun profilo di registrazione, verrà visualizzato un errore quando vengono registrate le garanzie. Questo campo è disponibile solo quando il campo **Tipo** è impostato su *Royalty*. 
    - **Output sconto** - Seleziona la modalità di pagamento dello sconto o della royalty:

        - *Dati finanziari* - Genera una nota di credito a testo libero o una nota di addebito della contabilità fornitori, in modo che il denaro possa essere pagato o ricevuto in seguito. Tieni presente che gli accantonamenti **possono** essere utilizzati con gli sconti in cui questa opzione è selezionata. Questa opzione è l'unica disponibile quando il campo **Tipo** è impostato su *Royalty*.
        - *Articolo* - Genera un ordine di vendita cliente per gli articoli in base all'impostazione della transazione. In questo ordine cliente, a ogni articolo viene assegnato un prezzo pari a 0 (zero). Tieni presente che gli accantonamenti **non possono** essere utilizzati con gli sconti in cui questa opzione è selezionata.

    - **Valuta di sconto** - Seleziona la valuta da utilizzare quando viene pagato lo sconto, la detrazione o la royalty.
    - **Note del documento** - Inserisci le note sulla transazione, come richiesto.
    - **Garanzia cumulativa** - Puoi impostare questa opzione su *Sì* solo se il campo **Tipo** è impostato su *Royalty*. Questa opzione influisce sul calcolo dei pagamenti con detrazione garantita. Ecco un esempio:

        - La garanzia della transazione è vendere un valore che comporterà un pagamento di $10.000 a trimestre.
        - L'organizzazione che vende la merce vende un valore che causa una detrazione del pagamento di $12.000 nel trimestre 1. Il risultato è una royalty $12.000 pagata, meno la garanzia $10.000.
        - Se l'opzione **Garanzia cumulativa** è impostata su *Sì*, i $2.000 aggiuntivi delle royalty pagate nel trimestre 1 si applicano al trimestre 2. Pertanto, al cliente viene garantito $8.000 (la garanzia $10.000 meno il pagamento aggiuntivo $2.000).
        - Nel secondo trimestre, registri le vendite che attivano una royalty $5.000.
        - Il sistema identifica un pagamento di $3.000 (la garanzia $8.000 meno i $5.000 delle royalty pagate).
        - Se l'opzione **Garanzia cumulativa** è impostata su *No*, tutti i $10.000 sono garantiti ogni trimestre. Questa garanzia corrisponde a un pagamento suggerito di $5.000 nel trimestre 2 (la garanzia $10.000 meno i $5.000 delle royalty pagate).

1. Seleziona **OK** per creare la transazione e chiudere la finestra di dialogo.

Questa procedura crea il livello di intestazione della nuova transazione. Successivamente, aggiungerai delle righe alla transazione.

## <a name="add-lines-to-a-deal"></a>Aggiungere righe a una transazione

Dopo aver creato una transazione come descritto nella sezione precedente, puoi aprirla dalla pagina elenco. È quindi possibile aggiungere righe per identificare clienti o fornitori, articoli, intervalli di tempo, una base e metodi di calcolo per la transazione. Una transazione può avere una o più righe. Se una transazione ha più righe, generalmente sono tutte dello stesso tipo o ad esse sono associati gli stessi parametri. Fino a quando non aggiungi righe a una transazione, la transazione in realtà non farà nulla.

1. Apri la pagina elenco delle transazioni di sconti appropriata, come descritto nella sezione precedente.
1. Trova e apri la transazione su cui vuoi lavorare.
1. Nella Scheda dettaglio **Gestione degli sconti** seleziona uno dei seguenti pulsanti per aggiungere una linea di transazione alla griglia:

    - **Aggiungi riga** - Aggiungi una nuova riga di transazione vuota.
    - **Copia riga** - Se una riga di transazione esistente è simile alla riga di transazione che vuoi aggiungere, è possibile selezionare questo pulsante per copiarla e aggiungerne una copia. La nuova riga della transazione includerà tutte le impostazioni dai dettagli relativi alla gestione dello sconto. È quindi possibile modificare le impostazioni. Ad esempio, in genere si aggiorna la relazione dell'articolo e la percentuale di sconto.

1. Nella nuova riga transazione, impostare i seguenti campi:

    - **Numero di gestione degli sconti** - Se hai [impostato una sequenza numerica](rebate-management-parameters.md) per i numeri di gestione degli sconti, questo campo viene impostato automaticamente su un ID univoco generato dal sistema. In caso contrario, immetti un ID univoco.
    - **Tipo** - Il tipo di transazione a cui si applica la riga (*Sconto* o *Royalty*). Il valore viene copiato dall'intestazione e non può essere modificato.
    - **Descrizione** - Immetti una descrizione della riga di transazione.
    - **Società** - Seleziona la società (persona giuridica) a cui si applica la riga di transazione. Durante l'elaborazione, gli utenti possono elaborare solo le righe di transazione assegnate alla società che stanno attualmente utilizzando. La pagina elenco **Transazioni di sconti clienti** fornisce una visualizzazione globale dell'azienda, basata sull'accesso di sicurezza dell'utente. Tuttavia, puoi modificare ed elaborare gli sconti solo per la società che stai attualmente utilizzando.
    - **Codice conto** - Seleziona l'ambito di clienti o fornitori a cui si applica la riga di transazione:

        - *Tabella* - La riga di transazione si applica a un cliente o fornitore specifico.
        - *Gruppo* - La riga di transazione si applica a un gruppo di clienti o fornitori. Per ulteriori informazioni su come impostare i gruppi, vedi [Gruppi di gestione degli sconti](rebate-management-groups.md).
        - *Tutti* - La riga di transazione si applica a tutti i clienti o i fornitori.

    - **Relazione conto** – Se è stato selezionato *Tabella* nel campo **Codice conto**, seleziona il cliente o il fornitore a cui si applica la transazione. Se selezioni *Gruppo*, seleziona il gruppo di clienti o fornitori. Se selezioni *Tutti*, questo campo non è disponibile.
    - **Codice articolo** - Seleziona l'ambito di articoli a cui si applica la riga di transazione:

        - *Tabella* - La riga di transazione si applica a un articolo specifico.
        - *Gruppo* - La riga di transazione si applica a un gruppo di articoli. Per ulteriori informazioni su come impostare i gruppi, vedi [Gruppi di gestione degli sconti](rebate-management-groups.md).
        - *Tutti* - La riga di transazione si applica a tutti gli articoli.

    - **Relazione articolo** – Se è stato selezionato *Tabella* nel campo **Codice articolo**, seleziona l'articolo a cui si applica la riga di transazione. Se selezioni *Gruppo*, seleziona il gruppo di articoli. Se selezioni *Tutti*, questo campo non è disponibile.
    - **Tipo di unità** – Seleziona il tipo di unità che si applica alla riga di transazione (*Unità di magazzino* o *Unità peso variabile*). Tieni presente che questo campo potrebbe essere vuoto per i record più vecchi. In questo caso, il valore *Unità di magazzino* viene usato.
    - **(Parametri di gestione dell'inventario)** - Nei restanti campi della riga di transazione specifica i valori per i parametri di gestione dell'inventario che verranno utilizzati per definire gli articoli inclusi nella transazione (come la dimensione dell'articolo, il colore, lo stile, il sito e il magazzino). Per aggiungere o rimuovere le dimensioni, seleziona **Visualizza dimensioni** nel riquadro azioni.

1. Nel riquadro azioni selezionare **Salva**.
1. Se desideri limitare ulteriormente il set di articoli a cui si applica una riga di transazione, seleziona la riga, quindi, nella scheda dettaglio **Gestione degli sconti** seleziona **Filtro** per aprire una finestra di dialogo standard **Richiesta informazioni**.
1. Per ogni riga di transazione aggiunta, imposta i dettagli del calcolo e altri dettagli nella scheda dettaglio **Dettagli gestione degli sconti**, come descritto nella sezione successiva.

## <a name="add-rebate-management-details-to-a-deal-line"></a>Aggiungere i dettagli di gestione degli sconti a una riga di transazione

Per ogni riga della tua transazione, devi impostare i dettagli nella scheda dettaglio **Dettagli gestione degli sconti**. Per prima cosa seleziona la riga di transazione nella Scheda dettaglio **Gestione degli sconti**. Quindi imposta i valori per quella linea di transazione utilizzando le varie schede della scheda dettaglio **Dettagli gestione degli sconti**. Nelle sezioni seguenti viene descritto come utilizzare ciascuna scheda.

### <a name="settings-on-the-general-tab"></a>Impostazioni nella scheda Generale

La scheda **Generale** della scheda dettaglio **Dettagli gestione degli sconti** consente di impostare il metodo di calcolo e la base per la riga di transazione selezionata. Questa impostazione controlla se è richiesto un acquisto minimo, i profili di registrazione associati alla riga di transazione e i dettagli del calcolo. Nella seguente tabella vengono illustrati i campi disponibili.

| Campo | descrizione |
|---|---|
| Metodo di calcolo | Seleziona il metodo da utilizzare quando la riga di transazione selezionata è combinata con altre righe di transazione (*Graduale*, *Cumulativo*, *Rolling*, o *Totale*). Il valore di questo campo può influire notevolmente sul risultato dei calcoli degli sconti. Per una descrizione completa di ogni metodo e degli esempi che mostrano come influisce sul calcolo degli sconti vedi [Metodi di calcolo per le righe di transazione](#calc-methods) più avanti in questo argomento. |
| Base | Seleziona se lo sconto viene applicato in base alla quantità (ovvero il numero totale di unità acquistate o vendute) o al valore (ovvero, il prezzo totale delle merci acquistate o vendute). |
| Tipo di transazione | <p>Seleziona il punto del processo in cui deve avvenire il calcolo:</p><ul><li>*Ordine* - Utilizza la quantità o il valore ordinato come base per il calcolo.</li><li>*Consegnato* - Utilizza la quantità o il valore consegnato come base per il calcolo.</li><li>*Fattura* - Utilizza la quantità o il valore fatturato come base per il calcolo.</li></ul> |
| Unità | Se hai selezionato *Quantità* nel campo **Base** seleziona l'unità in cui deve essere specificata la quantità. |
| Importo minimo | Inserisci l'importo minimo che deve essere pagato per periodo. Puoi immettere un valore negativo per consentire importi di sconto negativi se le note di credito superano le vendite per il periodo. |
| Principio di riduzione degli sconti | Seleziona il [principio di riduzione degli sconti](rebate-reduction-principle.md) che si applica alla riga di transazione. |
| Numero variante | Se la riga di transazione si applica a un articolo che ha varianti, seleziona la variante a cui si applica la riga di transazione. |
| Base per lo sconto fornitore | <p>Questo campo viene visualizzato solo per gli sconti fornitore (ovvero, le transazioni in cui il campo **Modulo** è impostato su *Fornitore*). Seleziona la base per lo sconto fornitore:</p><ul><li>*Ordinazione fornitore* - Lo sconto ricevuto dal fornitore si basa sulla quantità o sul valore dell'ordine fornitore.</li><li>*Ordine cliente* - Il fornitore riceve uno sconto solo dopo che la merce è stata venduta. Lo sconto si basa sulla quantità o sul valore dell'ordine cliente.</li></ul> |
| Base di prezzo | <p>Questo campo viene visualizzato solo per gli sconti fornitore (le transazioni in cui il campo **Modulo** è impostato su *Fornitore*). Se hai selezionato *Ordine cliente* nel campo **Base per lo sconto fornitore** seleziona la base di prezzo applicabile:</p><ul><li><p>*FIFO* - L'attività periodica **Calcola il prezzo di acquisto FIFO** deve essere eseguita per calcolare lo sconto. (Per eseguire l'attività, vai a **Gestione degli sconti \> Attività periodiche \> Calcola il prezzo di acquisto FIFO**.) Una regola FIFO (first in, first out) verrà utilizzata per calcolare il valore delle scorte vendute. Questo valore verrà quindi utilizzato per calcolare gli sconti del fornitore. Ecco un esempio:</p><ul><li>**Scorte vendute:** 1.000 unità a $3,00 ciascuna = $3.000</li><li>**Prezzo di acquisto corrente, basato su FIFO:** $2,00</li><li>**Calcolo di lavoro:** *Unità vendute* × *Prezzo di acquisto corrente* = 1.000 × $2,00 = $2.000</li></ul></li><li><p>*Ultimo prezzo di acquisto* - Il valore dell'ultima transazione di acquisto verrà utilizzato per calcolare gli sconti del fornitore. Ecco un esempio:</p><ul><li>**Scorte vendute:** 1.000 unità a $3,00 ciascuna = $3.000</li><li>**Ultimo prezzo di acquisto:** $2,00</li><li>**Calcolo di lavoro:** *Unità vendute* × *Ultimo prezzo di acquisto* = 1.000 × $2,00 = $2.000</li></ul></li><li><p>*Prezzo medio di acquisto* - Il valore medio ponderato degli ultimi *X* mesi verrà utilizzato per calcolare gli sconti del fornitore. Se selezioni questa opzione, devi inserire il numero di mesi nel campo **Numero di mesi** (che è disponibile solo quando il campo **Base del prezzo** è impostato su *Prezzo medio di acquisto*). Ecco un esempio:</p><ul><li>**Scorte vendute:** 1.000 unità a $3,00 ciascuna = $3.000</li><li>**Prezzo medio di acquisto:** $2,00</li><li>**Calcolo di lavoro:** *Unità vendute* × *Prezzo medio di acquisto* = 1.000 × $2,00 = $2.000</li></ul></li><li><p>*Prezzo di vendita* - Il prezzo di vendita verrà utilizzato per calcolare gli sconti del fornitore. Ecco un esempio:</p><ul><li>**Scorte vendute:** 1.000 unità a $3,00 ciascuna = $3.000</li><li>**Prezzo medio di acquisto:** $2,00</li><li>**Calcolo di lavoro:** *Unità vendute* × *Prezzo di vendita* = 1.000 × $3,00 = $3.000</li></ul></li></ul> |
| Numero di mesi | Questo campo viene visualizzato solo per gli sconti fornitore (le transazioni in cui il campo **Modulo** è impostato su *Fornitore*). Se hai selezionato *Prezzo medio di acquisto* nel campo **Base del prezzo** immetti il numero di mesi da utilizzare. |
| Profilo registrazione | Seleziona il [profilo di registrazione](rebate-management-posting.md) che si applica alla riga di transazione selezionata. Questo profilo viene utilizzato solo quando il campo **Riconcilia per** nell'intestazione della transazione è impostato su *Riga*. Se il campo **Riconcilia per** è impostato su *Transazione*, viene sempre utilizzato il profilo di registrazione impostato nell'intestazione della transazione. Se nessun profilo di registrazione è impostato nella riga di transazione, viene utilizzato il profilo di registrazione impostato nell'intestazione della transazione. |
| Profilo di registrazione per garanzia | Questo campo funziona come il campo **Profilo di registrazione** ma si applica solo alle royalty. |
| Tipo di pagamento | Il tipo di pagamento per il profilo di registrazione selezionato per la transazione. |
| IVA inclusa | Seleziona se la transazione è comprensiva di imposte. L'inclusione delle imposte è rilevante solo quando il campo **Base** è impostato su *Valore*. L'importo della fattura verrà utilizzato come importo comprensivo di imposte. Se il calcolo dello sconto si basa su una percentuale, il sistema moltiplicherà la percentuale dello sconto per l'importo comprensivo di imposte. Tieni presente che il calcolo utilizza il valore dell'IVA dalla riga di transazione. |
| Includi note di accredito | <p>Imposta questa opzione su *Sì* per includere note di credito nel calcolo degli sconti.</p><p>Se imposti questa opzione su *Sì*, l'effetto varia a seconda del valore del campo **Tipo di transazione**:</p><ul><li>Se il campo **Tipo di transazione** è impostato su *Fattura*, il calcolo terrà conto delle note di credito. Questa è la configurazione normale.</li><li>Se il campo **Tipo di transazione** è impostato su *Ordine*, il calcolo terrà conto sia degli ordini cliente che hanno valori negativi sia degli ordini di reso aperti.</li></ul> |
| Importo scontato | Imposta questa opzione su *Sì* per basare il calcolo sull'importo scontato dell'articolo o degli articoli nei casi in cui vengono concessi sconti sulla riga di transazione. |
| Solo fatture pagate | Imposta questa opzione su *Sì* se il calcolo deve considerare solo fatture interamente pagate. (In altre parole, gli sconti non verranno calcolati per le fatture parzialmente pagate.) Questa opzione è disponibile solo quando il campo **Tipo di transazione** è impostato su *Fattura*. |
| Includi testo libero | Imposta questa opzione su *Sì* per includere le fatture a testo libero nel calcolo. Le fatture a testo libero possono essere incluse solo per le righe di transazione in cui il campo **Codice articolo** è impostato su *Tutti*. |
| Includi sconto di liquidazione | Imposta questa opzione su *Sì* per ridurre lo sconto del primo sconto di liquidazione. Si presume che l'organizzazione accetterà il primo sconto di liquidazione. Imposta questa opzione su *No* per consentire l'utilizzo successivo dello sconto di liquidazione. |
| Note documenti | Immetti le note da utilizzare come testo della transazione nelle righe del giornale di registrazione delle transazioni di sconti. |

### <a name="settings-on-the-dates-tab"></a>Impostazioni della scheda Date

Le impostazioni nella scheda **Date** della scheda dettaglio **Dettagli gestione degli sconti** definiscono la frequenza e la tempistica dei calcoli specificati nella scheda **Generale**. Determinano come vengono eseguiti i calcoli al momento dell'elaborazione.

Questa scheda consente di specificare l'intervallo di date per cui è valida la riga di transazione selezionata e la frequenza di calcolo. È inoltre possibile specificare se la garanzia deve essere registrata e quando.

Puoi utilizzare i pulsanti sulla barra degli strumenti per aggiungere righe di data alla griglia o per rimuoverle. Se esistono più righe di data, gli intervalli di date validi non devono sovrapporsi. In caso contrario, riceverai un messaggio di errore quando proverai a salvare la transazione.

Nella seguente tabella vengono descritti i campi disponibili per ogni riga di data.

| Campo | descrizione |
|---|---|
| Data iniziale | Immetti la prima data a cui si applica la riga di data. Se le date di "inizio" e "fine" sono specificate nell'intestazione della transazione, vengono utilizzate come valori predefiniti per ogni nuova riga di data. |
| Data finale | Immetti l'ultima data a cui si applica la riga di data. Se le date di "inizio" e "fine" sono specificate nell'intestazione della transazione, vengono utilizzate come valori predefiniti per ogni nuova riga di data. |
| Per | Specifica la frequenza con cui deve essere calcolata la linea di transazione. Immetti un numero intero qui, quindi seleziona un'unità nel campo **Cumula per**. Ad esempio, per calcolare ogni due settimane, imposta il campo **Per** su *2* e il campo **Cumula per** su *Settimane*. |
| Cumula per | Seleziona l'unità che si applica all'impostazione **Per**. Seleziona *Durata* per calcolare sull'intera durata della riga di transazione. Seleziona *Periodo personalizzato* per selezionare un periodo definito nella contabilità generale. In questo caso, è necessario impostare anche il campo **Tipo di periodo**. |
| Tipo di periodo | Questo campo è disponibile solo quando il campo **Cumula per** è impostato su *Periodo personalizzato*. I valori disponibili per la selezione provengono dai tipi di periodo definiti nella contabilità generale. |
| Primo giorno della settimana | Specifica come vengono identificate le settimane per il periodo. Questo campo è disponibile solo quando il campo **Cumula per** è impostato su *Settimane*. |
| Richiedi per | Specifica la frequenza con cui è possibile richiedere lo sconto in denaro per la riga di transazione. Immetti un numero intero qui, quindi seleziona un'unità nel campo **Richiedi da**. |
| Richiedi da | Seleziona l'unità che si applica all'impostazione **Richiedi per**. Seleziona *Durata* per consentire le richieste solo una volta durante l'intera durata della riga di transazione. Seleziona *Periodo personalizzato* per selezionare un periodo definito nella contabilità generale. In questo caso, è necessario impostare anche il campo **Tipo di periodo richiesta**. |
| Tipo di periodo richiesta | Questo campo è disponibile solo quando il campo **Richiedi da** è impostato su *Periodo personalizzato*. I valori disponibili per la selezione provengono dai tipi di periodo definiti nella contabilità generale. |
| Elabora alla registrazione | Selezionare questa casella di controllo se la riga della richiesta deve essere elaborata al momento della registrazione. Questa opzione è disponibile solo per le righe di transazione in cui il campo **Tipo di transazione** nella scheda **Generale** è impostato su *Consegnato* o *Fattura*. Per gli accantonamenti, l'accantonamento verrà registrato quando viene generata la bolla di consegna o la fattura. |
| Garanzia per | Questo campo si applica solo alle transazioni di royalty. Specifica la frequenza con cui deve essere calcolata la garanzia della royalty durante il periodo definito dall'impostazione **Cumula per**. Immetti un numero intero qui, quindi seleziona un'ora di pagamento nel campo **Garanzia pagata**. |
| Garanzia pagata | <p>Questo campo si applica solo alle transazioni di royalty. Funziona insieme al campo **Garanzia per** per definire la frequenza del calcolo della garanzia. Selezionare uno dei seguenti valori:</p><ul><li><p>*Inizio periodo* - La garanzia viene pagata all'inizio del periodo di contratto definito per la riga della data. La garanzia completa viene elaborata per prima. Viene contabilizzato come royalty solo il valore delle royalty che eccedono l'importo garantito. Ecco un esempio:</p><ul><li>**Minimo di garanzia:** $10.000 in due mesi.</li><li>**Mese 1:** $10.000 sono stati pubblicati come garanzia e $0 in royalty.</li><li>**Mese 2:** $2.000 sono stati pubblicati come royalty e $0 in garanzia.</li><li>**Calcolo di lavoro:** *Garanzia rimanente* - *Royalty registrate* = $0 - $2.000 = - $ 2.000.</li></ul><p>Poiché è richiesto il pagamento delle royalty di $2.000, viene creato un giornale di registrazione per $2.000.</p><p>**Nota:** La garanzia deve essere calcolata e registrata insieme all'accantonamento per le detrazioni del primo periodo.</p></li><li><p>*Fine del periodo* - La garanzia non viene pagata fino alla fine del contratto di detrazione, come definito nella riga della data. Ecco un esempio:</p><ul><li>**Minimo di garanzia:** $10.000 in due mesi.</li><li>**Mese 1:** $5.000 sono stati registrati come royalty ed è stato creato un giornale di registrazione.</li><li>**Mese 2:** $7.000 sono stati registrati come royalty ed è stato creato un giornale di registrazione.</li><li>**Calcolo di lavoro:** Poiché le royalty superano l'importo della garanzia, $0 vengono registrati nella garanzia.</li></ul><p>**Nota:** La garanzia deve essere calcolata e registrata solo insieme all'accantonamento per le detrazioni e la transazione degli sconti del periodo finale.</p></li></ul> |
| Minimo di garanzia | Questo campo si applica solo alle transazioni di royalty. Immetti l'importo minimo della garanzia per una royalty, nella valuta definita nell'intestazione della transazione. |

### <a name="settings-on-the-lines-tab"></a>Impostazioni della scheda Righe

La scheda **Righe** della scheda dettaglio **Dettagli gestione degli sconti** consente di definire le righe di calcolo per la riga di transazione selezionata. Ogni riga di calcolo stabilisce una quantità o una soglia di valore e un importo di retribuzione o gli articoli correlati. Il campo **Base** nella scheda **Generale** specifica se ogni riga di calcolo è basata su una quantità o un valore.

Puoi utilizzare i pulsanti sulla barra degli strumenti per aggiungere righe di calcolo alla griglia o per rimuoverle. Puoi avere un numero qualsiasi di righe di calcolo. Tuttavia, se esistono più righe di calcolo, gli intervalli di quantità o valori di "inizio" e "fine" non devono sovrapporsi.

Nella seguente tabella vengono descritti i campi disponibili per ogni riga di calcolo.

| Campo | descrizione |
|---|---|
| Qtà/valore iniziale | Immettere la quantità o il valore minimo a cui si applica la riga di calcolo. |
| Qtà/valore finale | Immettere la quantità o il valore massimo a cui si applica la riga di calcolo. |
| Metodo di gestione degli sconti | <p>Questo campo è disponibile solo per le transazioni in cui il campo **Output sconto** nell'intestazione è impostato su *Dati finanziari*. Seleziona il metodo da utilizzare per calcolare lo sconto:</p><ul><li>*Fisso* - Per la riga viene utilizzato un importo di prezzo fisso.</li><li>*Percentuale* - Viene utilizzata una percentuale dell'importo della vendita.</li><li>*Tasso* - Viene utilizzato un importo di prezzo fisso per ordine.</li></ul><p>**Importante:** si consiglia vivamente di utilizzare lo stesso metodo per ogni riga di calcolo nella scheda **Righe**. Se è necessario un nuovo metodo, crea una nuova riga di transazione. Ricorda che puoi usare il pulsante **Copia riga** della scheda dettaglio **Gestione degli sconti** per creare una nuova riga di transazione da una riga di transazione esistente.</p><p>**Nota:** se il campo **Output sconto** è impostato su *Articolo*, questo campo è sempre impostato su *Fisso*. Per ulteriori informazioni su come specificare gli articoli vedi il testo che segue questa tabella. |
| Importo di gestione degli sconti | Questo campo è disponibile solo per le transazioni in cui **Output sconto** nell'intestazione è impostato su *Dati finanziari*. Immetti l'importo da utilizzare per calcolare lo sconto, in base al metodo selezionato nel campo **Metodo di gestione degli sconti**. |

Come accennato per la tabella precedente, per le transazioni in cui il campo **Output sconto** nell'intestazione è impostato su *Articolo*, è necessario specificare gli articoli che verranno forniti per ogni riga di calcolo nella scheda **Righe**. Per specificare gli articoli, segui questi passaggi.

1. Sulla scheda **Righe** crea la riga di calcolo richiesta se non esiste e selezionala.
1. Se la transazione non è stata salvata da quando hai creato la riga di calcolo, seleziona **Salva** nel riquadro azioni.
1. Nella scheda **Righe**, seleziona **Articoli**.
1. Nella pagina **Articoli** utilizza i pulsanti nel riquadro azioni per aggiungere o rimuovere articoli alla griglia secondo le necessità. Per ciascuna riga, imposta i seguenti campi:

    - **Numero articolo** - Seleziona l'articolo che verrà fornito.
    - **(Altre dimensioni)** - Se è necessario utilizzare più dimensioni per definire l'articolo (ad esempio, configurazione articolo, dimensione, colore, stile, sito o magazzino), specificale. Per aggiungere o rimuovere le dimensioni disponibili, seleziona **Visualizza dimensioni** nel riquadro azioni.
    - **Quantità** - Immetti la quantità che verrà fornita una volta raggiunta la soglia per la riga di calcolo selezionata.
    - **Unità** - Seleziona l'unità in cui viene specificato il valore **Quantità**.
    - **Multiplo** – Questo campo viene utilizzato con il campo **Quantità**. Ad esempio, in una riga di articolo, imposti il campo **Quantità** su *2* e il campo **Multiplo** di *100*. Se hai quindi una quantità totale dell'ordine di vendita pari a 150, due degli articoli saranno gratuiti (due per 100).

### <a name="settings-on-the-inventory-dimensions-tab"></a>Impostazioni della scheda Dimensioni inventariali

La scheda **Dimensioni inventariali** della scheda dettagli **Dettagli gestione degli sconti** mostra tutti i valori di dimensione disponibili per il prodotto specificato per la riga di transazione selezionata. Include le dimensioni che non sono mostrate nella scheda dettaglio **Gestione degli sconti**. Puoi modificare i valori solo per quelle dimensioni che si applicano al prodotto selezionato.

Puoi aggiungere più dimensioni alla griglia nella scheda dettaglio **Gestione degli sconti** selezionando **Visualizza dimensioni** nel riquadro azioni.

## <a name="calculation-methods-for-deal-lines"></a><a name="calc-methods"></a>Metodi di calcolo per le righe di transazione

Ogni volta che imposti i dettagli per una delle righe di transazione come descritto nella sezione precedente, è necessario selezionare il metodo di calcolo per quella riga. Questa sezione spiega ogni metodo di calcolo e fornisce esempi che mostrano come ogni metodo calcola lo sconto totale per ordini e righe di transazione. In questi esempi, gli ordini e le righe di transazione sono identici. Differiscono solo i metodi di calcolo.

### <a name="stepped-calculation-method"></a>Metodo di calcolo graduale

Il metodo di calcolo graduale esegue il calcolo passo dopo passo, in cui ciascuna riga di transazione contribuisce in modo incrementale allo sconto fino a quando non viene raggiunta la quantità o il valore delle vendite. I passaggi possono essere basati sulla quantità o sul valore delle merci vendute, a seconda dell'impostazione del campo **Base** nella scheda **Generale** della scheda dettaglio **Dettagli gestione degli sconti**.

Ad esempio, una riga di transazione viene impostata in modo che il campo **Metodo di calcolo** è impostato su *Graduale* e il campo **Base** è impostato su *Valore*. Include righe di calcolo che forniscono i seguenti sconti:

- **Riga A:** 10 percento fino a $1.000
- **Riga B:** 25 percento fino a $2.500

Se il valore della merce acquistata o venduta è $2.000, lo sconto risultante di $350 viene calcolato nel modo seguente:

- **Sconto (A):** *Soglia (A)* × *Percentuale (A)* = $1.000 × 10 percento = $100
- **Sconto (B):** (*Valore venduto* - *Soglia (A)*) × *Percentuale (B)* = ($ 2.000 - $1.000) × 25 percento = $250
- **Sconto totale:** *Sconto (A)* + *Sconto (B)* = $100 + $250 = $350

Se il campo **Base** è impostato su *Quantità* invece di *Valore*, il metodo di calcolo graduale funziona in modo simile. Il primo passaggio viene utilizzato per la quantità identificata fino a quando non viene raggiunto il secondo passaggio. Il secondo passaggio viene utilizzato per tutta la quantità oltre il primo passaggio fino a quando non viene raggiunto il terzo passaggio. Questo processo continua quindi attraverso tutti i passaggi successivi.

### <a name="cumulative-calculation-method"></a>Metodo di calcolo cumulativo

Il metodo di calcolo cumulativo utilizza una sola riga di calcolo per calcolare lo sconto. Se sono disponibili più righe di calcolo per la riga di transazione, la riga di calcolo del valore più alto o della quantità più alta raggiunta viene utilizzata per l'intera quantità o valore. Come gli altri metodi di calcolo, il metodo cumulativo utilizza l'impostazione del campo **Base** della scheda **Generale** della scheda dettaglio **Dettagli gestione degli sconti** per determinare se la quantità di vendita o il valore di vendita viene utilizzato per calcolare gli sconti.

Ad esempio, una riga di transazione viene impostata in modo che il campo **Metodo di calcolo** è impostato su *Cumulativo* e il campo **Base** è impostato su *Valore*. Include righe di calcolo che forniscono i seguenti sconti:

- **Riga A:** 10 percento fino a $1.000
- **Riga B:** 25 percento fino a $2.500

Se il valore della merce acquistata o venduta è $2.000, il calcolo utilizza solo la riga B. Lo sconto risultante di $500 viene calcolato nel modo seguente:

- **Sconto totale:** *Valore venduto* × *Sconto (B)* = $2.000 × 25 percento = $500

### <a name="rolling-calculation-method"></a>Metodo di calcolo rolling

Il metodo di calcolo rolling calcola tutte le possibili righe di calcolo per la transazione. Se sono presenti più righe di calcolo e ne viene raggiunta più di una, verranno utilizzate tutte le righe di calcolo raggiunte, ma a ciascuna percentuale si applicano soglie superiori. Come gli altri metodi di calcolo, il metodo rolling utilizza l'impostazione del campo **Base** della scheda **Generale** della scheda dettaglio **Dettagli gestione degli sconti** per determinare se la quantità di vendita o il valore di vendita viene utilizzato per calcolare gli sconti.

Ad esempio, una riga di transazione viene impostata in modo che il campo **Metodo di calcolo** è impostato su *Rolling* e il campo **Base** è impostato su *Valore*. Include righe di calcolo che forniscono i seguenti sconti:

- **Riga A:** 10 percento fino a $1.000
- **Riga B:** 25 percento fino a $2.500

Se il valore della merce acquistata o venduta è $2.000, lo sconto risultante di $600 viene calcolato nel modo seguente:

- **Sconto (A):** *Soglia (A)* × *Percentuale (A)* = $1.000 × 10 percento = $100
- **Sconto (B):** *Valore venduto* × *Percentuale (B)* = $2.000 × 25 percento = $500
- **Sconto totale:** *Sconto (A)* + *Sconto (B)* = $100 + $500 = $600

### <a name="total-calculation-method"></a>Metodo di calcolo totale

Il metodo di calcolo totale utilizza tutte le righe di calcolo per calcolare lo sconto. Applica la quantità totale per calcolare lo sconto per ciascuna riga di calcolo raggiunta e ciascuna riga di calcolo applica la propria percentuale all'intero importo. Come gli altri metodi di calcolo, il metodo totale utilizza l'impostazione del campo **Base** della scheda **Generale** della scheda dettaglio **Dettagli gestione degli sconti** per determinare se la quantità di vendita o il valore di vendita viene utilizzato per calcolare gli sconti.

Ad esempio, una riga di transazione viene impostata in modo che il campo **Metodo di calcolo** è impostato su *Totale* e il campo **Base** è impostato su *Valore*. Include righe di calcolo che forniscono i seguenti sconti:

- **Riga A:** 10 percento fino a $1.000
- **Riga B:** 25 percento fino a $2.500

Se il valore della merce acquistata o venduta è $2.000, lo sconto risultante di $700 viene calcolato nel modo seguente:

- **Sconto (A):** *Valore venduto* × *Percentuale (A)* = $2.000 × 10 percento = $200
- **Sconto (B):** *Valore venduto* × *Percentuale (B)* = $2.000 × 25 percento = $500
- **Sconto totale:** *Sconto (A)* + *Sconto (B)* = $200 + $500 = $700
