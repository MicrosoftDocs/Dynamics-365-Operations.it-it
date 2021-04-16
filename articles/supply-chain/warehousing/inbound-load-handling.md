---
title: Gestione magazzino dei carichi in entrata per gli ordini fornitore
description: Questo argomento descrive il processo di gestione del magazzino per i carichi in entrata per gli ordini fornitore.
author: omulvad
ms.date: 03/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-21
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 095ef3bb9fff26915bf4fbeb7e240ae9175e315c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835632"
---
# <a name="warehouse-handling-of-inbound-loads-for-purchase-orders"></a>Gestione magazzino dei carichi in entrata per gli ordini fornitore

Questo argomento descrive il processo di gestione del magazzino per i carichi in entrata per gli ordini fornitore.

Per ciascun carico in entrata, il sistema deve già includere un ordine cliente correlato e può contenere anche una specifica del carico e/o un piano di trasporto correlati. Per ulteriori informazioni su come creare e gestire i carichi in entrata, vedere [Processo aziendale: pianificazione del trasporto per carichi in entrata](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/business-process-planning-transportation-for-inbound-loads).

## <a name="overview-how-inbound-loads-are-created-registered-and-received"></a>Panoramica: come vengono creati, registrati e ricevuti i carichi in entrata

La seguente illustrazione mostra il flusso tipico per la gestione di carichi in entrata, che hanno quantità di ordini fornitore quando arrivano al magazzino.

![Il processo di gestione del carico in entrata](media/inbound-process.png "Il processo di gestione del carico in entrata")

1. **Il fornitore conferma l'ordine fornitore.**

    Il processo inizia quando un ordine fornitore viene inserito nel sistema e quindi consegnato a un fornitore, che conferma l'ordine. L'ordine fornitore deve esistere prima di poter creare un record di carico in entrata. Tuttavia, è possibile creare il carico in entrata anche se l'ordine non è stato confermato. Per ulteriori informazioni, vedere [Approvare e confermare gli ordini fornitore](../procurement/purchase-order-approval-confirmation.md).

1. **Viene creato un record di carico in entrata per pianificare l'arrivo e il suo contenuto.**

    Il record di carico in entrata rappresenta una spedizione fornitore di uno o più ordini fornitore. Il carico arriva al magazzino come unità di trasporto fisica (ad esempio un camion). Il record di carico in entrata viene utilizzato a fini della pianificazione e consente al coordinatore della logistica di tenere traccia dell'avanzamento del carico dal fornitore. Viene anche utilizzato per registrare le quantità della riga ordine e gestire i progressi attraverso le operazioni di magazzino, come i lavori di arrivo e di stoccaggio. I carichi possono essere creati automaticamente o manualmente e possono essere basati su un ordine fornitore o un avviso di spedizione avanzato (ASN) dal fornitore. Per ulteriori informazioni, vedere [Creare o modificare un carico in entrata](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/create-or-modify-an-inbound-load).

1. **Il fornitore conferma la spedizione del carico.**

    Quando il fornitore spedisce il carico, il coordinatore della logistica presso il magazzino ricevente conferma la spedizione del carico. Se la società ricevente utilizza il modulo **Gestione trasporto** la conferma della spedizione in entrata attiverà altri processi di gestione dei carichi associati ai carichi in entrata. Per ulteriori informazioni, vedere [Confermare un carico per la spedizione](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/confirm-a-load-for-shipping).

1. **Il carico arriva al magazzino e i lavoratori registrano le quantità.**

    Quando un camion arriva alla banchina di entrata del magazzino, i magazzinieri registrano le quantità di carico. Quando viene utilizzato il modulo **Gestione magazzino** i lavoratori eseguono la registrazione utilizzando i dispositivi mobili. Per ulteriori informazioni, vedere [Entrata prodotti e ordini fornitore - registrazione](../procurement/product-receipt-against-purchase-orders.md#registration) e la sezione [Registrare le quantità degli articoli che arrivano su un carico in entrata](#register-item-quantities-arriving).

1. **Le quantità di carico registrate vengono registrate rispetto agli ordini fornitore.**

    Dopo che le quantità di carico sono state registrate all'arrivo, tali quantità devono essere registrate all'entrata prodotti nella contabilità generale inventario dell'azienda per registrare l'aumento fisico delle scorte. Per ulteriori informazioni, vedere [Entrata prodotti e ordini fornitore - entrata del prodotto](../procurement/product-receipt-against-purchase-orders.md#product-receipt) e [Registrare le quantità di prodotti registrati rispetto agli ordini fornitore](#post-registered-quantities).

## <a name="register-item-quantities-that-arrive-on-an-inbound-load"></a><a name="register-item-quantities-arriving"></a>Registrare le quantità degli articoli che arrivano su un carico in entrata

Microsoft Dynamics 365 Supply Chain Management supporta diversi approcci operativi per la registrazione dell'arrivo dei prodotti ordinati. Pertanto, è possibile configurare il sistema in modo che corrisponda ai requisiti aziendali specifici. Questa sezione descrive come registrare le quantità di articoli in entrata utilizzando un dispositivo mobile quando nel sistema è attivata la gestione avanzata del magazzino. Tuttavia, esiste un flusso alternativo basato sull'utilizzo del giornale di registrazione arrivi articoli anziché di un dispositivo mobile. Per ulteriori informazioni riguardo questo flusso, vedere [Registrare articoli per un articolo abilitato a immagazzinaggio avanzato tramite un giornale di registrazione arrivi articoli](tasks/register-items-advanced-warehousing.md).

Quando un carico in entrata arriva per la prima volta in magazzino, gli addetti al magazzino devono registrare le quantità degli articoli incluse nella spedizione. In genere, è preferibile utilizzare scanner portatili. Questo flusso di lavoro è disponibile solo se nel sistema sono presenti i seguenti elementi:

- **Un record di carico in entrata che descrive le quantità di articoli previste nella spedizione**

    In genere, il fornitore conferma il record di carico in entrata prima che la spedizione arrivi al magazzino. Pertanto, il carico ha lo stato _Spedito_. Tuttavia, gli addetti al magazzino possono anche registrare le quantità degli articoli per carichi con lo stato _Aperto_ o _Ricevuto_.

- **Un menu del dispositivo mobile configurato per supportare la ricezione del carico**

    L'[app per dispositivi mobili Gestione magazzino](../warehousing/install-configure-warehouse-management-app.md) per dispositivi mobili supporta i seguenti processi di creazione del lavoro:

    - Ricezione articoli di carico
    - Ricevimento e stoccaggio articoli di carico
    - Ricevimento targa mista, in cui il campo **Metodo di identificazione riga del documento di origine** per la voce di menu del dispositivo mobile è impostato su _Ricezione articoli di carico_. Per ulteriori informazioni, vedere [Ricevimento targa mista](mixed-license-plate-receiving.md).
    - Ricevimento targa mista e stoccaggio, in cui il campo **Metodo di identificazione riga del documento di origine** per la voce di menu del dispositivo mobile è impostato su _Ricezione articoli di carico_. Per ulteriori informazioni, vedere [Ricevimento targa mista](mixed-license-plate-receiving.md).

    > [!NOTE]
    > Indipendentemente dal processo, il sistema genererà lavoro per prelevare quantità registrate nell'ubicazione di ricevimento e stoccarle nella normale ubicazione di magazzino. Quando il processo _Ricevimento e stoccaggio articoli di carico_ o _Ricevimento e stoccaggio targa mista_ viene utilizzato, al lavoratore che ha registrato la quantità di carico verrà inoltre richiesto dal dispositivo di eseguire il lavoro di stoccaggio come parte dell'attività di registrazione. Di contro, per i processi, _Ricezione articoli di carico_ e _Ricevimento targa mista_ il presupposto è che il lavoro di stoccaggio verrà svolto separatamente dall'attività di registrazione.

- **Un modello di lavoro che definisce il lavoro di prelievo e stoccaggio per i carichi in entrata**

    Questo articolo è correlato agli articoli precedenti. È necessario avere almeno un modello per il tipo di ordine di lavoro _Ordine fornitore_ contenente un insieme di tipi di lavoro prelievo/stoccaggio.

Il dispositivo mobile guida l'addetto al ricevimento del magazzino attraverso il flusso per la registrazione della quantità di carico. È necessario che almeno, questo flusso include i seguenti passaggi per ciascun ID carico:

1. Inserire l'ID carico.
2. Immettere il numero dell'articolo per un articolo ricevuto.
3. Immettere la quantità del numero di articolo ricevuto.
4. Immettere il numero di targa per la posizione iniziale dell'articolo, se il sistema non è impostato per generare automaticamente questo numero.
5. Toccare **OK**.

Dopo che il lavoratore ha completato questi passaggi, il sistema effettua i seguenti aggiornamenti sulle entità appropriate, a condizione che la quantità della riga ordine fornitore sia arrivata su un carico e tutte le quantità di carico siano state registrate:

| Entità | Aggiornamenti | Nota |
|---|---|---|
| Caricamento | Il campo **Quantità di lavoro creata** nella riga di carico viene aggiornato per mostrare la quantità registrata. | Il valore **Stato del carico** rimane _Spedito_ o _Aperto_ se non è stata eseguita alcuna conferma di spedizione per il carico. Se è stata avviata almeno una riga di lavoro di stoccaggio, viene impostata su _In corso_. |
| Transazione di magazzino di un ordine fornitore per cui sono state registrate le quantità di carico associate |<p>I campi seguenti sono aggiornati:</p><ul><li>Il campo <b>Entrata</b> è impostato su <i>Registrato.</i></li><li>Il campo <b>Ubicazione</b> viene aggiornato con il codice di posizione della banchina di entrata. (Questo codice è specificato nel campo <b>Ubicazione predefinita entrata</b> per ogni magazzino.)</li><li>Il campo <b>Targa</b> viene aggiornato con il numero di targa immesso o generato durante la registrazione.</li><li>Il campo <b>ID carico</b> viene aggiornato con il numero del carico rispetto al quale è stata registrata la quantità. (Vedere la nota.)</li></ul> | La possibilità di collegarsi tra la transazione di inventario dell'ordine fornitore e le quantità registrate rispetto al carico è stata introdotta nella versione 10.0.9 come funzionalità opzionale denominata _Associa transazioni di inventario dell'ordine fornitore al carico_. Questa funzione è particolarmente utile per i flussi operativi in cui un singolo ordine di beni acquistati viene consegnato come carichi multipli o quando un carico contiene quantità per più ordini fornitore. |
| Magazzino stoccaggio | Il lavoro viene creato in base a un modello di lavoro, per indicare al lavoratore di spostare le quantità registrate dall'ubicazione di ricevimento a una ubicazione di magazzino normale. | La scelta dell'ubicazione di magazzino è controllata dalla direttiva di ubicazione stoccaggio. Se non è stata definita alcuna direttiva sull'ubicazione, l'ubicazione di stoccaggio sul lavoro risulterà vuota. |

Si noti che gli addetti al magazzino possono registrare l'entrata di un ordine fornitore con uno o più carichi associati senza utilizzare il processo _Ricezione articoli di carico_. Sono disponibili i seguenti metodi:

- **Sul dispositivo mobile:** Utilizzare i processi _Ricevimento riga ordine acquisto_ e _Ricevimento e stoccaggio riga ordine acquisto_. (Se esiste più di un carico per la quantità della riga ordine fornitore, il lavoratore non può utilizzare il processo _Ricevimento riga ordine fornitore_. Al lavoratore verrà invece richiesto di utilizzare l'azione del dispositivo associata al processo _Ricezione articoli di carico_.)
- **Nel client:** utilizzare il giornale di registrazione arrivi articoli.
- **Nel client:** Utilizzare l'azione di **Registrazione** a cui è possibile accedere dalla riga ordine fornitore.

> [!NOTE]
> Se l'entrata dell'ordine fornitore viene registrata utilizzando uno dei metodi precedenti, non viene creato alcun collegamento tra la transazione di inventario dell'ordine fornitore e il carico, anche quando la funzione _Associa transazioni di inventario dell'ordine fornitore al carico_ è attivata. Un'eccezione a questa regola è quando si utilizza l'opzione **Ricezione riga ordine fornitore** e solo un carico ha uno stato diverso da _Ricevuto_ per la riga ordine.

### <a name="handle-discrepancies-during-registration-of-inbound-load-quantities"></a>Gestire le discrepanze durante la registrazione delle quantità di carico in entrata

Gli addetti al magazzino possono effettuare una registrazione dell'entrata della quantità di carico parziale. Ogni entrata della quantità di carico parziale crea quindi una transazione di magazzino separata con lo stato dell'entrata _Registrato_ per la quantità registrata e l'ID lotto si riferisce alla riga dell'ordine fornitore di origine.

#### <a name="load-under-receiving"></a>Ricezione del carico in difetto

Quando arriva un carico, se le quantità degli articoli sono inferiori alle quantità indicate nel record di carico, il personale addetto al ricevimento in magazzino può lavorare direttamente nel client per riconoscere questa discrepanza riducendo la quantità sulla riga di carico in modo che corrisponda alla quantità effettiva che è arrivata ed è stata registrata.

#### <a name="load-over-receiving"></a><a name="load-over-receiving"></a>Ricezione del carico in eccesso

La ricezione in eccesso si verifica quando all'arrivo di un carico le quantità degli articoli superano la quantità prevista della riga di carico. È possibile controllare se e fino a che punto è consentita la ricezione in eccesso durante la registrazione del carico.

Utilizzare il campo **Ricezione carico in eccesso** per le voci di menu del dispositivo mobile in questione per controllare cosa succede quando un addetto al magazzino tenta di registrare una consegna in eccesso. Questo campo è disponibile per le voci di menu dei dispositivi mobili che utilizzano i seguenti tipi di processi di creazione del lavoro:

- Ricezione articoli di carico
- Ricevimento e stoccaggio articoli di carico
- Ricezione di targhe miste, (quando il campo **Metodo di identificazione riga del documento di origine** è impostato su _Ricezione articoli di carico_)
- Ricezione di targhe miste e stoccaggio (quando il campo **Metodo di identificazione riga del documento di origine** è impostato su _Ricezione articoli di carico_)

Nella seguente tabella vengono illustrate le opzioni disponibili per il campo **Ricezione carico in eccesso**.

| Valore | Descrizione |
|---|---|
| Consenti | I lavoratori possono registrare la ricezione di quantità che superano la quantità non registrata rimanente per un carico selezionato, ma solo se la quantità totale registrata non supera la quantità della riga dell'ordine fornitore associata al carico (dopo la correzione per la percentuale di consegna in eccesso). |
| Blocca | <p>I lavoratori non possono registrare la ricezione di quantità che superano la quantità non registrata rimanente per un carico selezionato (dopo la correzione per la percentuale di consegna in eccesso). Un lavoratore che tenta di registrare le entrate riceverà un errore e non sarà in grado di continuare fino a quando non registra una quantità uguale o inferiore alla quantità di carico non registrata rimanente.</p><p>Per impostazione predefinita, il valore della percentuale di consegna in eccesso su una riga di carico viene copiato dalla riga dell'ordine fornitore associata. Quando il campo <b>Ricezione carico in eccesso</b> è impostato su <i>Blocca</i>, il sistema utilizza il valore percentuale di consegna in eccesso per calcolare la quantità totale che può essere registrata per una riga di carico. Tuttavia, tale valore può essere sovrascritto per singoli carichi, se necessario. Questo comportamento diventa rilevante durante la ricezione di flussi in cui una parte o tutta la quantità in eccesso che rappresenta la percentuale di consegna in eccesso della riga ordine viene distribuita in modo sproporzionato su più carichi. Ecco uno scenario di esempio:</p><ul><li>Esistono più carichi per una riga ordine fornitore.</li><li>La riga dell'ordine fornitore ha una percentuale di consegna in eccesso superiore a 0 (zero).</li><li>Le quantità sono già state registrate rispetto a uno o più carichi senza tenere conto della percentuale di consegna in eccesso.</li><li>La quantità di consegna in eccesso arriva all'ultimo carico.</li></ul><p>In questo scenario, un dispositivo mobile può essere utilizzato per registrare la quantità in eccesso per l'ultimo carico solo se il supervisore del magazzino aumenta la percentuale di consegna in eccesso per la relativa riga di carico dal valore predefinito a un valore sufficientemente grande da consentire la registrazione della consegna in eccesso completa con il carico finale.</p> |
| Blocca solo per carichi chiusi | I lavoratori possono ricevere quantità eccessive di righe di carico per carichi aperti, ma non per carichi con lo stato _Ricevuto_. |

> [!NOTE]
> Il valore predefinito del campo **Ricezione carico in eccesso** è _Consenti_. Quando viene utilizzato questo valore, il comportamento corrisponde al comportamento standard disponibile prima dell'introduzione della funzione _Entrata eccessiva delle quantità di carico_ nella versione 10.0.11.

### <a name="put-away-the-registered-quantities"></a>Stoccare le quantità registrate

Quando la registrazione è completata sul dispositivo mobile, l'azione _Registrazione entrata quantità_ aggiorna i record di inventario e magazzino per indicare che le quantità sono ora nella posizione della banchina di entrata e disponibili per la prenotazione. Tuttavia, le operazioni di magazzino di una società richiedono in genere che le quantità vengano spostate dalla banchina di entrata al magazzino normale, in modo che possano verificarsi i successivi processi di prelievo. Le istruzioni per lo stoccaggio vengono acquisite nell'attività di stoccaggio che viene generata automaticamente quando il carico in entrata viene registrato come ricevuto.

Quando il lavoratore del magazzino ha completato il lavoro di stoccaggio, il sistema registra e tiene traccia del risultato aggiornando le diverse entità, come riepilogato nella tabella seguente.

| Entità | Aggiornamenti | Nota |
|---|---|---|
| Caricamento | <p>I campi seguenti sono aggiornati:</p><ul><li>Il valore <b>Stato del carico</b> è cambiato in <i>In corso</i>.</li><li>Il valore <b>Stato del lavoro</b> è cambiato in <i>100,00% del lavoro completato</i>.</li></ul> | Il valore **Stato del carico** è cambiato in _In corso_ quando il lavoratore avvia l'attività di stoccaggio per almeno una riga di lavoro di stoccaggio. |
| Le transazioni di magazzino del lavoro per cui sono state stoccate le quantità associate | Il campo **Entrata** e **Ubicazione** e altri campi pertinenti, vengono aggiornati per riflettere lo spostamento dall'ubicazione di ricevimento all'ubicazione di magazzino. | Il valore dello **Stato dell'entrata** della transazione di inventario dell'ordine fornitore rimane _Registrato_. |
| Magazzino stoccaggio | Il valore **Stato del lavoro** è cambiato in _Chiuso_. | |

## <a name="post-registered-product-quantities-against-purchase-orders"></a><a name="post-registered-quantities"></a>Registrare le quantità di prodotti registrati rispetto agli ordini fornitore

Dopo che le quantità di prodotti in entrata sono state registrate nel sistema, diventano disponibili per la prenotazione in relazione alle vendite e ad altre operazioni in uscita e interne. Tuttavia, il sistema non aggiorna ancora i conti di magazzino (intermedi). Questo aggiornamento può verificarsi solo quando il team operativo registra le entrate del prodotto registrate.

Per aprire una pagina in cui è possibile registrare un'entrata del prodotto, i membri del team operativo possono seguirne _uno_ qualsiasi di questi passaggi:

- Aprire il record di carico pertinente, quindi selezionare l'azione **Entrata prodotti**.
- Andare a **Gestione magazzino \> Attività periodiche \> Aggiorna entrate prodotti** e quindi nel campo **ID carico** , specificare il carico da registrare.
- Aprire l'ordine fornitore pertinente, quindi selezionare l'azione **Entrata prodotti**.
- Andare a **Approvvigionamento \> Ordini fornitore \> Ricezione dei prodotti \> Registrazione del processo di ricezione del prodotto**.

L'azione **Entrata prodotti** disponibile nella pagina **Carico** (e nella pagina equivalente per il processo di aggiornamento, la pagina **Aggiorna entrate prodotti**) può aggiornare le quantità di ricevute del prodotto solo sulle quantità di ordini fornitore che hanno lo stato _Registrato_. Tuttavia, l'azione **Entrata prodotti** disponibile sulla pagina **Ordini fornitore** può includere quantità in entrambi gli stati di elaborazione (_Ordinato_ e _Registrato_). Può anche controllare l'ambito della registrazione dell'entrata del prodotto attraverso parametri aggiuntivi, come ad esempio _Quantità in Ricevi ora_ e _Quantità registrata e servizi_.

Solo gli ordini con lo stato _Confermato_ possono essere registrati all'entrata prodotti. Per gli ordini fornitore non confermati, l'azione **Entrata prodotti** apparirà come non disponibile.

### <a name="post-registered-quantities-from-the-load-page"></a>Registrare le quantità registrate dalla pagina Carico

Per registrare all'entrata prodotti le quantità registrate dalla pagina **Carico** devono essere presenti i seguenti prerequisiti:

- Il carico deve avere almeno un'unità di quantità con lo stato _Registrato_.
- Lo stato del carico deve essere _Spedito_.
- L'ordine fornitore associato al carico deve avere lo stato _Confermato_.

> [!NOTE]
> Se lo stato del carico non è stato impostato su _Spedito_, il sistema confermerà automaticamente il carico prima di eseguire l'aggiornamento dell'entrata del prodotto. (Lo stato del carico è impostato su _Spedito_ quando un utente registra la spedizione in entrata del carico.)

Per registrare all'entrata prodotti le registrazioni di arrivo associate a un carico selezionato, il lavoratore seleziona l'azione **Entrata prodotti** nella pagina **Carico**. La pagina che viene visualizzata contiene i seguenti dettagli chiave:

- Il campo **Quantità** nella sezione **Parametri** della scheda **Impostazioni** mostra la _quantità registrata_. Non sono disponibili ulteriori opzioni.
- La griglia nella scheda dettaglio **Panoramica** elenca tutti gli ordini fornitore inclusi nel carico selezionato.
- La griglia nella scheda dettaglio **Righe** elenca tutte le righe ordine con una quantità registrata.

> [!NOTE]
> Le quantità per le righe ordine presenti nella scheda **Riga** vengono calcolate in modo diverso, a seconda se la funzione _Consenti l'entrata di più prodotti per carico_ sia disponibile e attivata nella versione di Supply Chain Management.
>
> | Versione | Calcolo |
> |---|---|
> | Versioni precedenti alla versione 10.0.10 e versioni più recenti in cui la funzione _Consenti l'entrata di più prodotti per carico_ non è attivata | La quantità della riga è il totale di tutte le quantità registrate _per quella riga ordine fornitore_, indipendentemente dal fatto che la registrazione sia stata effettuata su più carichi, separatamente dal carico, da un dispositivo mobile o dal client. |
> | Versioni 10.0.10 e versioni successive in cui la funzione _Consenti l'entrata di più prodotti per carico_ è attivata | La quantità della riga è il totale di tutte le quantità registrate _per il record di carico_ da cui è stata avviata l'azione **Registrazione entrata prodotto**. |

Quando l'utente seleziona **OK** per confermare la registrazione dell'entrata del prodotto, il sistema esegue i seguenti aggiornamenti chiave sulle entità appropriate.

| Entità | Aggiornamenti |
|---|---|
| Transazione di magazzino dell'ordine fornitore per cui le quantità di riga sono state incluse nell'ambito di registrazione | <p>I seguenti campi vengono aggiornati (ma si noti che sono disponibili anche altri aggiornamenti):</p><ul><li>Il campo <b>Entrata</b> è impostato su <i>Ricevuto</i>.</li><li>Il campo <b>Data effettiva</b> viene aggiornato con la data di registrazione.</li></ul> |
| Carico da cui l'utente ha registrato l'entrata del prodotto | Gli aggiornamenti ai carichi dipenderanno dalla versione utilizzata e dall'impostazione del campo **Consenti l'entrata di più prodotti per carico**. Le regole sono descritte nella tabella riportata più avanti in questa sezione. |

Il campo **Consenti l'entrata di più prodotti per carico** consente alle società di scegliere criteri di ricezione del carico in entrata. A seconda dei flussi operativi, le aziende possono scegliere di consentire o negare più registrazioni di entrate di prodotti per lo stesso carico. Consigliamo al responsabile della logistica di impostare il campo **Consenti l'entrata di più prodotti per carico** su uno dei seguenti valori:

- **No** - Selezionare questo valore se gli addetti al ricevimento del magazzino registrano sempre tutte le quantità degli ordini che arrivano con ciascun carico entro un periodo di tempo designato. Se le quantità di carico non sono registrate, il sistema presume che non siano arrivate o che non fossero presenti nel carico e pertanto non considerate come parte del carico. La registrazione dell'entrata del prodotto eseguita da un carico utilizza lo stesso presupposto. Oltre all'entrata del prodotto, che aggiorna tutte le quantità registrate (la funzione principale), dichiara il carico completo e chiuso per ulteriore elaborazione. In questo caso, tutte le quantità delle righe di carico vengono automaticamente aggiornate alle quantità registrate, le righe di carico che non hanno quantità registrate vengono eliminate e lo stato del carico viene modificato in _Ricevuto_. 
- **Sì** - Selezionare questo valore se gli addetti al ricevimento del magazzino richiedono più tempo per registrare tutte le quantità sul carico che è arrivato, ma nel frattempo devono registrare all'entrata prodotti le quantità che sono già state registrate. In questo caso, il responsabile della logistica vorrà mantenere il carico aperto anche dopo l'esecuzione del processo di registrazione dell'entrata del prodotto, in modo tale che le quantità di carico rimanenti possano essere registrate e che l'entrata del prodotto venga aggiornata nel registro su base continuativa.
- **Richiesta** - Selezionare questo valore se le procedure di ricezione del carico sono miste ed è necessaria una decisione ogni volta che viene eseguita la registrazione dell'entrata del prodotto.

Nella tabella seguente sono riepilogati gli effetti dell'impostazione **Consenti l'entrata di più prodotti per carico**.

| Consenti l'entrata di più prodotti per carico | Quantità di carico | Stato carico | Nota |
|---|---|---|---|
| Quando questo campo non è disponibile (versioni precedenti a 10.0.10) | <p>La quantità di carico è impostata in modo che sia uguale alla quantità registrata.</p><p>Se la quantità di carico viene aggiornata su 0 (zero), ossia non è stata effettuata alcuna registrazione, la riga di carico viene eliminata.</p><p>Se non ci sono righe di carico sul carico, il carico viene eliminato.</p> | _Ricevuti_ | Se esistono più carichi per la quantità registrata della riga ordine, solo lo stato del carico da cui è stata registrata l'entrata viene aggiornato su _Ricevuto_. |
| Nessuna | <p>La quantità di carico è impostata in modo che sia uguale alla quantità registrata associata all'ID carico.</p><p>Se non viene registrato alcun ID carico per la transazione di inventario, il comportamento corrisponde a quello delle versioni precedenti alla 10.0.10.</p> | _Ricevuti_ | |
| Sì | Nessun aggiornamento | _Ricevuto_, se la quantità di carico totale registrata è uguale o superiore alla quantità di carico | |
| Sì | Nessun aggiornamento | _Spedito_ o _In corso_, se la quantità di carico totale registrata è minore della quantità di carico | |

Una volta che il campo **Stato del carico** è impostato su _Ricevuto_, non è più possibile effettuare registrazioni di entrate del prodotto per quel carico. Tuttavia, il lavoratore può registrare la quantità di ordine rimanente rispetto al carico ricevuto nelle seguenti condizioni. (Per ulteriori informazioni, vedere la sezione [Ricezione del carico in eccesso](#load-over-receiving) descritta precedentemente in questo argomento.)

- La versione di Supply Chain Management è precedente alla versione 10.0.11.
- La funzione _Entrata eccessiva delle quantità di carico_ è attivata e il campo **Entrata eccessiva quantità riga di carico** sulla voce di menu del dispositivo mobile per l'azione di ricezione articoli di carico è impostato su _Consenti_.

Per registrare all'entrata prodotti ulteriori quantità di carico registrate rispetto a un carico con stato _Ricevuto_, l'utente deve eseguire l'azione di registrazione dall'ordine fornitore associato.

### <a name="post-registered-quantities-from-the-purchase-order-page"></a>Registrare le quantità registrate dalla pagina Ordine fornitore

Per registrare all'entrata prodotti le quantità dalla pagina **Ordine fornitore** , l'utente completa le seguenti attività prima di selezionare l'azione **Entrata prodotti**:

- Impostare il campo **Quantità** nella sezione **Parametri** nella scheda **Impostazioni** su _Quantità registrata_.
- Nel campo **Entrata prodotti**, inserire i numeri degli ordini fornitore inclusi nella registrazione.

> [!NOTE]
> La quantità di riga che verrà inclusa nell'ambito di registrazione è il totale di tutte le quantità registrate per la riga ordine, indipendentemente dal fatto che la registrazione della quantità sia stata effettuata su più carichi, separatamente dal carico, da un dispositivo mobile o dal client. La stessa regola si applica quando la registrazione dell'entrata del prodotto viene eseguita da un carico, se viene eseguita laddove il campo **Consenti l'entrata di più prodotti per carico** non è disponibile o non è abilitato.

Quando l'utente seleziona **OK** per confermare la registrazione dell'entrata del prodotto, il sistema esegue i seguenti aggiornamenti chiave sulle entità appropriate.

| Entità | Aggiornamenti |
|---|---|
| Transazione di magazzino dell'ordine fornitore per cui le quantità di riga sono state incluse nell'ambito di registrazione | <p>I seguenti campi vengono aggiornati (ma si noti che sono disponibili anche altri aggiornamenti):</p><ul><li>Il campo <b>Entrata</b> è impostato su <i>Ricevuto</i>.</li><li>Il campo <b>Data effettiva</b> viene aggiornato con la data di azione di registrazione dell'entrata del prodotto.</li></ul> |
| Caricamento | Gli aggiornamenti ai carichi dipendono dal fatto che il campo **Consenti l'entrata di più prodotti per carico** sia disponibile e abilitato. Le regole vengono descritte nella seguente tabella. |

Nella tabella seguente sono riepilogati gli effetti dell'impostazione **Consenti l'entrata di più prodotti per carico**.

| Consenti più entrate prodotti per carico | Quantità di carico | Stato carico | Nota |
|---|---|---|---|
| Quando questo campo è disabilitato o non disponibile (nelle versioni precedenti a 10.0.10) | Nessun aggiornamento | Non sono stati eseguiti aggiornamenti. (Lo stato rimane _Aperto_, _Spedito_ o _In corso_.) | Poiché la registrazione dell'entrata del prodotto è iniziata da un ordine fornitore, la logica di aggiornamento non contiene informazioni sull'associazione tra le quantità registrate nel suo ambito e i carichi rispetto ai quali è stata registrata la registrazione. Pertanto, non è possibile selezionare il carico per l'aggiornamento dello stato. |
| Abilitate | Nessun aggiornamento | <p>Si verifica una delle seguenti azioni:</p><ul><li>Lo stato viene cambiato in <i>Ricevuto</i> se le quantità totali ricevute e acquistate delle transazioni di inventario dell'ordine fornitore sono maggiori o uguali alla quantità del carico a cui sono associate.</li><li>Lo stato rimane <i>Aperto</i>, <i>Spedito</i> o <i>In corso</i> se la condizione precedente non viene soddisfatta per tutte le righe nel carico.</li></ul> | |

### <a name="select-the-appropriate-product-receipt-posting-option-for-your-logistics-operations"></a>Selezionare l'opzione di registrazione dell'entrata del prodotto appropriata per le operazioni logistiche

Come precedentemente descritto, il sistema offre due opzioni di registrazione dell'entrata del prodotto. È possibile accedere alle opzioni nei seguenti punti:

- Sulla pagina **Carico** o dal menu **Gestione magazzino \> Attività periodiche** come processo di aggiornamento
- Sulla pagina **Ordine fornitore** o dal menu **Approvvigionamento \> Ordini fornitore \> Ricezione di prodotti** come processo di aggiornamento

Le aziende che utilizzano i carichi per pianificare e gestire il trasporto e la movimentazione del magazzino dei propri ordini in entrata sono invitati a utilizzare le seguenti funzioni, progettate per funzionare con i carichi:

- Azioni **Ricezione articoli di carico** sui dispositivi mobili del magazzino, per registrare l'arrivo della quantità di prodotto rispetto al carico
- Azioni **Registrazione entrata prodotto** avviate da un carico per aggiornare la contabilità generale inventario

> [!NOTE]
> Altre funzioni di registrazione della quantità e di registrazione dell'entrata del prodotto possono essere utilizzate per supportare i corrispondenti processi operativi in entrata. Tuttavia, se li si utilizza in modo intercambiabile o al posto delle funzioni dedicate attivate sul carico, è possibile compromettere l'accuratezza dei dati dei record di carico e quindi la fluidità dei flussi di gestione del carico.

## <a name="example-scenarios"></a>Scenari di esempio

### <a name="prepare-your-system-to-run-the-sample-scenarios"></a>Preparare il sistema per eseguire gli scenari di esempio

Per eseguire gli scenari di esempio descritti in questa sezione, è necessario innanzitutto assicurarsi che tutte le funzionalità richieste siano attivate nel sistema. I dati dimostrativi richiesti devono anche essere disponibili nel sistema.

#### <a name="turn-on-the-required-features"></a>Attivare le funzionalità richieste

Questi scenari richiedono la funzionalità _Registrazioni entrata di più prodotti per carico_ e la sua caratteristica prerequisito. Gli amministratori possono attivare tali funzionalità procedendo come segue.

1. Aprire l'area di lavoro **Gestione funzionalità**. (Per i dettagli completi su come trovare e utilizzare questo spazio di lavoro, vedere [Panoramica sulla gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)

1. Attivare la funzionalità _Associa transazioni di inventario dell'ordine fornitore al carico_, elencata nel modo seguente:

    - **Modulo:** _Gestione magazzino_
    - **Nome della funzione:** _Associa transazioni di inventario dell'ordine fornitore al carico_

1. Attivare la funzionalità _Registrazioni entrata di più prodotti per carico_, elencata nel modo seguente:

    - **Modulo:** _Gestione magazzino_
    - **Nome della funzione:** _Registrazioni entrata di più prodotti per carico_

#### <a name="enable-sample-data"></a>Abilitare dati di esempio

Per elaborare questi scenari utilizzando i record e i valori di esempio specificati, è necessario utilizzare un sistema in cui sono installati i dati demo standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

#### <a name="add-a-menu-item-for-receiving-load-items-when-a-mobile-device-is-used"></a>Aggiungere una voce al menu per ricevere articoli di carico quando viene utilizzato un dispositivo mobile

Prima che gli addetti al ricevimento del magazzino possano utilizzare un dispositivo mobile per registrare l'inventario in entrata collegato a un carico, è necessario creare una voce di menu del dispositivo mobile a tale scopo.

In questa sezione, si crea una voce di menu del dispositivo mobile e la si aggiunge a un menu esistente. Un addetto al magazzino può quindi selezionare la voce di menu nell'app per dispositivi mobili Gestione magazzino.

1. Andare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile** e verificare che il menu del dispositivo mobile includa una voce di menu con le seguenti impostazioni:

    - **Modalità:** _Lavoro_
    - **Processo di creazione del lavoro:** _Ricezione articoli di carico_
    - **Genera targa:** _Sì_

    È possibile lasciare tutte le altre impostazioni sui loro valori predefiniti.

    ![Impostazioni delle voci di menu del dispositivo mobile](media/inbound-mobile-menu-items.png "Impostazioni delle voci di menu del dispositivo mobile")

    Per ulteriori informazioni su come configurare il menu dei dispositivi mobili, vedere [Configurare i dispositivi mobili per il lavoro di magazzino](configure-mobile-devices-warehouse.md).

2. Dopo aver completato la configurazione della voce di menu, andare su **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Menu dispositivo mobile** e aggiungerlo alla struttura del menu per i dispositivi mobili.

### <a name="example-scenario-1-register-a-load-where-some-items-are-missing"></a>Scenario di esempio 1: registrare un carico in cui mancano alcuni articoli

Questo scenario mostra come registrare le quantità per un carico in entrata in cui non sono presenti tutte le quantità previste. Quindi, illustra come registrare l'entrata del prodotto per l'ordine fornitore.

#### <a name="create-a-load-to-plan-receipt-of-a-purchase-order"></a>Creare un carico per pianificare la ricezione di un ordine fornitore

In questa procedura, verrà creato manualmente un ordine fornitore e un carico associato. In questo modo sarà possibile aggiornare il carico per simulare che è stato spedito dal fornitore (il quale aggiorna lo stato del carico). I pianificatori del magazzino possono quindi filtrare i carichi tramite **Stato del carico** per trovare i carichi in entrata previsti.

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine fornitore**, impostare il campo **Conto fornitore** su _1001_.
1. Scegliere **OK** per chiudere la finestra di dialogo e creare l'ordine fornitore.
1. Il nuovo ordine fornitore include già una riga sotto **Righe ordine fornitore**. Impostare i seguenti valori per questa riga:

    - **Numero articolo:** _A0001_
    - **Magazzino:** _24_
    - **Quantità:** _10_

1. Nel riquadro azioni, nella scheda **Acquisto** , selezionare **Azioni \> Conferma**. Lo stato dell'ordine è ora _Confermato_.
1. Nel riquadro azioni, nella scheda **Magazzino** , selezionare **Azioni \> Conferma**.
1. Nella pagina **Workbench pianificazione carico**, nel riquadro azioni, nella scheda **Domanda e offerta** , selezionare **Aggiungi \> Al nuovo carico**.
1. Nella finestra di dialogo **Assegnazione modello di carico**, impostare il campo **ID modello di carico** su _Contenitore 20'_.
1. Scegliere **OK** per chiudere la finestra di dialogo e tornare al workbench.
1. Nella sezione **Carichi**, selezionare **ID carico** per aprire il carico appena creato.
1. Esaminare l'intestazione del carico e i dettagli della riga e osservare i seguenti punti:

    - Nella scheda dettaglio **Carica**, il campo **Stato del carico** è impostato su _Aperto_.
    - Nella sezione **Righe di carico**, c'è una sola riga in cui il campo **Quantità** è impostato su _10_ e il campo **Quantità di lavoro creata** è impostato su _0_ (zero).

    ![Dettagli carico](media/inbound-load-details.png "Dettagli carico")

1. Nel riquadro azioni, nella scheda **Spedizione e ricezione** selezionare **Conferma \> Spedizione in entrata**. Si noti che lo **Stato del carico** è cambiato in _Spedito_.
1. Prendere nota del valore **ID carico**, in modo da poterlo utilizzare nella procedura successiva.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-load"></a>Registrare l'entrata delle quantità arrivate sul carico

Quando il carico arriva alla banchina di entrata del magazzino, un addetto al ricevimento registra le quantità di carico su un dispositivo mobile.

1. Utilizzare il dispositivo mobile per accedere al magazzino 24. (Nei dati demo standard, accedere utilizzando _24_ come ID utente e _1_ come password.)
1. Selezionare la voce di menu _Ricezione articoli di carico_ creata per questo scenario.
1. Seguire le istruzioni per l'immissione dei dati sullo schermo per inserire i seguenti valori. (L'ordine potrebbe variare, a seconda del dispositivo mobile o dell'emulatore che si sta utilizzando.)

    - **Carico** - Immettere l'ID carico creato nella procedura precedente.
    - **Articolo** - Immettere _A0001_, che corrisponde all'articolo previsto per questo carico.
    - **Quantità** - Immettere _9_ come quantità effettiva presente sul carico. Si noti che questa quantità è inferiore alla quantità prevista.

1. Si continui a scorrere il flusso di lavoro, lasciando tutti gli altri campi vuoti o impostati sui valori predefiniti, fino a quando il dispositivo non informa che il lavoro è completato.

L'attività di ricezione del carico è ora completata e l'addetto al ricevimento può passare all'attività successiva. Tuttavia, il personale addetto al ricevimento in magazzino esaminerà il record di carico e sarà in grado di vedere che la quantità entrata era inferiore alla quantità prevista. Completerà quindi la seguente procedura utilizzando il client Web.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Nell'elenco, fare riferimento al carico appena ricevuto. (Potrebbe essere necessario selezionare la casella di controllo **Mostra chiuso** per includere i carichi in entrata che hanno lo stato carico di _Spedito_). Quindi selezionare il collegamento nella colonna **ID carico** per aprire il carico.
1. Nel record di carico, si noti che il valore **Stato del carico** rimane _Spedito_, ma il valore **Quantità di lavoro creata** sulla riga di carico è cambiato in _9_.
1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Nell'elenco, trovare l'acquisto appena ricevuto, quindi selezionare il collegamento nella colonna **Ordine fornitore** per aprire l'ordine.
\
1. Nella scheda dettaglio **Righe ordine fornitore**, selezionare **Magazzino \> Visualizza \> Transazioni**.
1. Rivedere i dettagli delle due transazioni dell'ordine fornitore. (Potrebbe essere necessario personalizzare la pagina **Transazioni di magazzino** per vedere il campo **ID carico** sulla griglia). Sono presenti due transazioni:

    - La transazione con un'entrata nello stato _Registrato_ rappresenta la quantità di registrazione di _9_ eseguita su un carico specifico utilizzando il dispositivo mobile. L'**ID carico** è associato alla transazione in questione.
    - La transazione con un'entrata nello stato _Ordinato_ rappresenta la quantità rimanente di riga ordine non registrata di _1_.

#### <a name="product-receiptpost-the-registered-load-quantities-against-purchase-orders"></a>Registrare all'entrata prodotti le quantità di carico rispetto agli ordini fornitore

In questa procedura, si registra all'entrata prodotti l'inventario registrato per un carico. Di conseguenza, l'inventario ricevuto e i relativi costi verranno aggiunti alla contabilità generale dell'azienda.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Nell'elenco, trovare il carico appena ricevuto. (Potrebbe essere necessario selezionare la casella di controllo **Mostra chiuso** per includere i carichi in entrata che hanno lo stato carico di _Spedito_). Quindi selezionare il collegamento nella colonna **ID carico** per aprire il carico.
1. Nel riquadro azioni, nella scheda **Spedizione e ricezione** selezionare **Ricezione \> Entrata prodotti**. Se viene richiesto di confermare la selezione, fare clic su **Sì**.
1. Nella finestra di dialogo **Registrazione dell'entrata del prodotto**, nella scheda dettaglio **Righe**, analizzare la griglia. È visualizzata la riga dell'ordine fornitore per la quale la quantità è stata registrata rispetto al carico selezionato.

    > [!NOTE]
    > Nelle versioni in cui la funzione _Registrazioni entrata di più prodotti per carico_ non è disponibile o non è abilitata, la quantità predefinita visualizzata nella griglia **Righe di carico** sarà la quantità totale che è stata registrata su tutti i carichi associati alla riga ordine fornitore.

1. Nella scheda dettaglio **Panoramica** , esaminare il campo **Entrata prodotti** nella griglia. Si noti che deve essere impostato su un numero che include l'ID carico selezionato.
1. Selezionare **OK** per registrare l'entrata del prodotto e chiudere la finestra di dialogo **Registrazione dell'entrata del prodotto**.
1. Si viene reindirizzati ai dettagli di carico. Notare i punti seguenti:

    - Il campo **Stato del carico** è ora impostato su _Ricevuto_.
    - Sulla riga di carico, il valore **Quantità** per il carico è cambiato da _10_ a _9_ pezzi per corrispondere la quantità registrata, ma il valore **Quantità di lavoro creata** rimane _9_.

Se il team acquisti non si aspetta che il fornitore consegni la quantità dell'ordine rimanente pari a 1, può chiudere l'ordine aggiornando il resto della consegna della riga a _0_. Tuttavia, se si realizza che il pezzo mancante è arrivato sul carico originale, il personale del magazzino può eseguire una delle seguenti azioni:

- Registrare la quantità sullo stesso carico. In questo caso, il campo **Stato del carico** verrà reimpostato su _Spedito_ e il valore **Quantità di lavoro creata** verrà aggiornato a _10_. Questa scelta risulta essere disponibile nelle situazioni riportate di seguito:

    - La funzione _Entrata eccessiva delle quantità di carico_ non è disponibile o non è abilitata.
    - La funzione _Entrata eccessiva delle quantità di carico_ è disponibile e abilitata, il campo **Entrata eccessiva quantità riga di carico** è impostato su _Consenti_.

- Aggiungere la quantità a un carico nuovo o esistente ed elaborarlo come di consueto.
- Registrare e/o ricevere la quantità in modo da non comportare la gestione del carico.

### <a name="example-scenario-2-register-quantities-that-arrive-on-multiple-inbound-loads-where-some-items-are-missing"></a>Scenario di esempio 2: registrare le quantità che arrivano su più carichi in entrata in cui mancano diversi articoli

In questo scenario, una spedizione in entrata correlata a una singola riga ordine fornitore verrà suddivisa in due carichi. Ad esempio, una riga ordine fornitore potrebbe essere suddivisa in più carichi a causa di vincoli di carico fisici per peso e/o volume.

Questo scenario mostra anche come elaborare simultaneamente registrazioni di entrate di prodotti per lo stesso carico. Verranno registrate le quantità che arrivano su più carichi in entrata, ma le quantità non corrisponderanno alle quantità previste. Gli aggiornamenti dei costi che si verificano tramite la registrazione dell'entrata del prodotto verranno eseguiti più volte per lo stesso carico.

#### <a name="set-up-load-receiving-policies"></a>Impostare i criteri di ricezione del carico

In questa procedura, sarà possibile abilitare più registrazioni di entrata del prodotto dallo stesso carico.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Sulla scheda **Carichi**, impostare il campo **Consenti l'entrata di più prodotti per carico** su _Sì_.

#### <a name="create-two-loads-to-plan-receipt-of-a-purchase-order"></a>Creare due carichi per pianificare la ricezione di un ordine fornitore

In questa procedura, verrà creato manualmente un ordine fornitore e due carichi . In questo modo sarà possibile aggiornare manualmente ogni carico per simulare che è stato spedito dal fornitore (il quale aggiorna lo stato del carico). I pianificatori del magazzino possono quindi filtrare i carichi tramite **Stato del carico** per trovare i carichi in entrata previsti.

Inoltre viene anche illustrato come impostare la riga dell'ordine fornitore in modo da poter ricevere una quantità superiore del 20 percento rispetto alla quantità specificata per la riga.

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Selezionare **Nuovo**.
1. Nella scheda dettaglio **Fornitore**, impostare il campo **Conto fornitore** su _1001_, quindi selezionare **OK**.
1. Il nuovo ordine fornitore viene aperto e include una riga vuota nella griglia **Righe ordine fornitore**. Impostare i seguenti valori per questa riga ordine:

    - **Numero articolo:** _A0001_
    - **Magazzino:** _24_
    - **Quantità:** _10_

1. Nella scheda dettaglio **Dettagli riga**, nella scheda **Consegna**, impostare il campo **Limite massimo di fornitura** su _20_.
1. Nel riquadro azioni, nella scheda **Acquisto** , selezionare **Azioni \> Conferma**. Lo stato dell'ordine è ora _Confermato_.
1. Nel riquadro azioni, nella scheda **Magazzino** , selezionare **Azioni \> Conferma**.
1. Nella pagina **Workbench pianificazione carico**, nel riquadro azioni, nella scheda **Domanda e offerta** , selezionare **Aggiungi \> Al nuovo carico**.
1. Nella finestra di dialogo **Assegnazione modello di carico**, impostare il campo **ID modello di carico** su _Contenitore 20'_. Nella scheda **Dettagli**, modificare il valore **Quantità** da _10_ a _5_ per aggiungere parzialmente la quantità della riga dell'ordine fornitore.
1. Selezionare **OK** per applicare le impostazioni e chiudere la finestra di dialogo.
1. Ripetere i passaggi da 8 a 10 per creare un secondo carico. Questa volta, il campo **Quantità** è già impostato su _5_.
1. Nella pagina **Workbench di pianificazione carico**, nella griglia **Carichi**, selezionare il valore **ID carico** per il primo carico creato. Verrà visualizzata la pagina **Dettagli carico** con il carico selezionato. Eseguire i passaggi indicati di seguito:

    1. Nel riquadro azioni, nella scheda **Spedizione e ricezione** selezionare **Conferma \> Spedizione in entrata**.
    1. Si noti che lo **Stato del carico** è cambiato in _Spedito_.
    1. Selezionare il pulsante di chiusura per tornare alla pagina **Workbench di pianificazione del carico**.

1. Ripetere il passaggio precedente per il secondo carico creato.
1. Prendere nota dei due valori **ID carico** che compaiono nella griglia **Carichi**.

#### <a name="register-partial-receipt-of-the-quantities-that-arrived-on-the-first-load-and-post-the-registered-load-quantities"></a>Registrare l'entrata parziale delle quantità arrivate al primo carico e registrare le quantità di carico registrate

Quando il carico arriva alla banchina di entrata del magazzino, un addetto al ricevimento registra le quantità di carico su un dispositivo mobile. L'inventario registrato collegato a un carico viene quindi aggiornato in base al carico nella contabilità generale della società registrando l'entrata del prodotto dell'ordine fornitore, in base al carico.

Questa procedura mostra come un addetto al ricevimento carichi registrerà le quantità di carico su un dispositivo mobile.

1. Utilizzare il dispositivo mobile per accedere al magazzino 24. (Nei dati demo standard, accedere utilizzando _24_ come ID utente e _1_ come password.)
1. Selezionare la voce di menu _Ricezione articoli di carico_ creata per questo scenario.
1. Seguire le istruzioni per l'immissione dei dati sullo schermo per inserire i seguenti valori. (L'ordine potrebbe variare, a seconda del dispositivo mobile o dell'emulatore che si sta utilizzando.)

    - **Carico** - Immettere il primo ID carico creato nella procedura precedente.
    - **Articolo** - Immettere _A0001_, che corrisponde all'articolo previsto per questo carico.
    - **Quantità** - Immettere _3_. Si noti che questa quantità è inferiore alla quantità prevista. Per questo scenario, si supponga di essere un addetto al ricevimento che non abbia il tempo di registrare tutte le quantità per questo carico. Più avanti in questa procedura, sarà necessario registrare i pezzi rimanenti ripetendo questo passaggio e impostando il campo **Quantità** su _2_.

1. Si continui a scorrere il flusso di lavoro, lasciando tutti gli altri campi vuoti o impostati sui valori predefiniti, fino a quando il dispositivo non informa che il lavoro è completato.
1. Nel client Web, passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Nell'elenco, trovare il carico appena ricevuto e selezionare il valore **ID carico** per aprire il carico. Si noti che il valore **Stato del carico** rimane _Spedito_, ma il valore **Quantità di lavoro creata** nella riga di carico è cambiato in _3_.
1. Nel riquadro azioni, nella scheda **Spedizione e ricezione** selezionare **Ricezione \> Entrata prodotti**. Se viene richiesto di confermare la selezione, fare clic su **Sì**.
1. Nella finestra di dialogo **Registrazione dell'entrata del prodotto**, rivedere ma non modificare i valori visualizzati, quindi selezionare **OK**.
1. Si viene reindirizzati alla pagina **Dettagli carico** per il carico selezionato. Notare i punti seguenti:

    - Il campo **Stato del carico** rimane impostato su _Spedito_.
    - Sulla riga di carico, il valore **Quantità** per il carico rimane _5_ pezzi, che è la quantità di carico originale, e il valore **Quantità di lavoro creata** rimane _3_.

1. Completare la registrazione della quantità rimanente su questo carico ripetendo questa procedura. Tuttavia, nel passaggio 3, impostare il campo **Quantità** su _2_.

L'attività di ricezione per il primo carico è ora completata. Sono stati creati due giornali di registrazione entrata prodotti, uno per ciascuno dei due aggiornamenti di entrata del prodotto eseguiti.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-second-load-and-account-for-the-overdelivered-quantity"></a>Registrare l'entrata delle quantità arrivate al secondo carico e tenere conto della quantità consegnata in eccesso

Per questo scenario, l'addetto al ricevimento registrerà in entrata una quantità che supera la quantità esistente nel carico. La ricezione eccessiva sarà consentita perché il sistema è impostato per consentire la consegna in eccesso.

1. Utilizzare il dispositivo mobile per accedere al magazzino 24. (Nei dati demo standard, accedere utilizzando _24_ come ID utente e _1_ come password.)
1. Selezionare la voce di menu _Ricezione articoli di carico_ creata per questo scenario.
1. Seguire le istruzioni per l'immissione dei dati sullo schermo per inserire i seguenti valori. (L'ordine potrebbe variare, a seconda del dispositivo mobile o dell'emulatore che si sta utilizzando.)

    - **Carico** - Immettere il secondo ID carico creato in precedenza.
    - **Articolo** - Immettere _A0001_, che corrisponde all'articolo previsto per questo carico.
    - **Quantità** - Immettere _7_, che è la quantità rimanente che il fornitore è autorizzato a consegnare come parte della quantità totale dell'ordine fornitore di 12 (dove 10 è la quantità dell'ordine originale e 2 è la quantità di consegna in eccesso consentita del 20 percento). Tenere a mente che 5 pezzi sono già stati registrati rispetto al primo carico.

Il secondo carico è stato ora aggiornato con la quantità di 7 e può essere aggiornato all'entrata del prodotto in base a questa quantità.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]