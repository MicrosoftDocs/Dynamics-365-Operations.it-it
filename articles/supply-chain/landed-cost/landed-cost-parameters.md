---
title: Impostazione dei parametri di costo sbarcato
description: In questo argomento viene descritto come definire impostazioni di configurazione e relative a informazioni utilizzate nel modulo Costo sbarcato per registrazione, aggiornamenti dello stato, sequenze numeriche e comportamento.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 489c0db50d52c1e58eab73ad19a73babf22b4de7
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500768"
---
# <a name="landed-cost-parameters-setup"></a>Impostazione dei parametri di costo sbarcato

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La pagina **Parametri di costo sbarcato** consente di definire impostazioni di configurazione e relative a informazioni utilizzate nel modulo **Costo sbarcato** per registrazione, aggiornamenti dello stato, sequenze numeriche e comportamento. L'impostazione dei parametri è condivisa tra persone giuridiche e può essere modificata da un amministratore.

## <a name="open-the-landed-cost-parameters-page"></a>Aprire la pagina Parametri di costo sbarcato

Per utilizzare i parametri, selezionare **Costo sbarcato \> Impostazioni \> Parametri di costo sbarcato**, quindi impostare i campi come descritto nelle sottosezioni seguenti.

![Pagina Parametri di costo sbarcato](media/landed-cost-parameters.png "Pagina Parametri di costo sbarcato")

## <a name="general-tab"></a>Scheda Generale

### <a name="general-fasttab"></a>Scheda dettaglio Generale

La tabella seguente descrive i campi disponibili nella Scheda dettaglio **Generale** della scheda **Generale** nella pagina **Parametri di costo sbarcato**.

| Impostazione | Descrizione |
|---|---|
| Usa tasso spedizione | Un tasso di spedizione viene impostata per un periodo definito e viene utilizzata per i costi stimati delle merci che utilizzano più valute. Impostare questa opzione su *Sì* per utilizzare un tasso di spedizione. |
| Tipo di tasso di cambio | La raccolta predefinita di tassi di cambio utilizzata per i calcoli con più valute relativi a un viaggio e ai costi di viaggio. |
| Aggiorna quantità ordine fornitore | Selezionare ciò che deve verificarsi se un utente modifica la quantità in una riga dell'ordine fornitore:<ul><li>**Accetta** - La quantità di viaggio viene rettificata automaticamente.</li><li>**Avviso** - Se la riga è collegata a un viaggio, viene visualizzato un avviso, ma la quantità del viaggio viene aggiornata.</li><li>**Errore** - Se la riga è collegata a un viaggio, viene visualizzato un messaggio di errore e l'ordine fornitore non può essere aggiornato. Pertanto, la riga dell'ordine deve essere prima rimossa dal viaggio.</li></ul> |
| Aggiorna automaticamente il numero di cartoni | Quando questa opzione è impostata su *Sì*, tutti i cartoni vengono sommati e visualizzati a livello di viaggio e di contenitore. Quando è impostata su *No*, il numero di cartoni è inizialmente impostato su 0 (zero) e può essere modificato manualmente come necessario. |

### <a name="costing-fasttab"></a>Scheda dettaglio Determinazione costi

La tabella seguente descrive i campi disponibili nella Scheda dettaglio **Determinazione costi** della scheda **Generale** nella pagina **Parametri di costo sbarcato**.

| Impostazione | Descrizione |
|---|---|
| Specifica di registrazione | Selezionare la rettifica del valore nel libro mastro:<ul><li>**Totale** - Una cifra totale viene registrata nel libro mastro.</li><li>**Gruppo di articoli** - La rettifica viene specificata per gruppo di articoli.</li><li>**Numero articolo** - La rettifica viene specificata per articolo. Questo valore fornisce il maggior numero di dettagli.</li></ul> |
| Consenti costi zero | Impostare questa opzione su *No* per visualizzare un errore se un utente tenta di registrare una stima dei costi per una fattura di viaggio o un ordine fornitore che non include un valore per il costo di viaggio previsto. Il messaggio di errore indica che non è possibile allocare un costo pari a 0 (zero) e la registrazione della fattura non riuscirà. In questo caso, l'utente può aggiornare manualmente la stima (o riconfigurare il costo automatico), quindi inserire il valore aggiornato o eliminare il costo se non è applicabile.<p>Imposta questa opzione su *Sì* per lasciare vuoto il costo di viaggio. In questo caso, verrà allocato un prezzo pari a 0 (zero) in base all'area di costo. Una fattura dei costi del fornitore può quindi essere elaborata a fronte del costo a prezzo zero al ricevimento del viaggio.</p><p>Si consiglia di configurare la stima nel record del costo automatico per evitare che venga visualizzato un costo a prezzo zero. Sebbene questa stima non sia completamente accurata, dovrebbe comunque essere più accurata di un presunto costo zero.</p> |
| Data di registrazione rettifica | Quando si registra una fattura costo di viaggio della contabilità fornitori, viene aggiornata anche la tabella delle liquidazioni (rettifiche inventario). Selezionare la data impostata per impostazione predefinita nella pagina **Selezionare costi di viaggio** nel giornale di registrazione fatture:<ul><li>**Data transazione**: utilizzare la data del giornale di registrazione (data della registrazione).</li><li>**Data fattura ordine fornitore** - Utilizzare la data di registrazione finanziaria della fattura delle scorte (ordine fornitore).</li><li>**Data selezionata** - L'utente può specificare una data di registrazione. Sebbene il campo della data possa essere lasciato vuoto, se è ancora vuoto quando viene registrata la fattura dei costi, l'utente vedrà un messaggio di errore.</li></ul> |
| Usa giustificativo fattura acquisto | Quando questa opzione è impostata su *Sì*, le transazioni dei ratei dei costi utilizzeranno lo stesso numero di giustificativo utilizzato per la fattura di acquisto. Quando è impostata su *No*, il sistema utilizzerà il numero disponibile successivo della sequenza numerica di **Giustificativo ratei dei costi** impostata nella scheda **Sequenze numeriche** della pagina **Parametri di costo sbarcato**.<p>Questa opzione ha effetto solo quando l'opzione **Registra nel conto di addebito nella contabilità generale** è impostata su *Sì* nella scheda **Fattura** della pagina **Parametri contabilità fornitori**.</p> |
| Blocca registrazione manuale nel conto di compensazione | Impostare questa opzione su *Sì* per impedire la registrazione nei conti di compensazione in cui la transazione non è stata collegata a un viaggio selezionando **Funzioni \> Selezionare costi di viaggio** nel riquadro Azioni del giornale di registrazione fatture fornitore. È consigliabile impostare questa opzione su *Sì*, in modo che il conto di viaggio e di compensazione possa essere saldato correttamente. |
| Usa conto ratei di addebito del tipo di costo | Quando questa opzione è impostata su *Sì*, il conto ratei di addebito configurato per il codice di tipo di costo pertinente nella pagina **Codici di tipo di costo** verrà utilizzata per attribuire costi come spese.<p>Questa opzione ha effetto solo quando l'opzione **Registra nel conto di addebito nella contabilità generale** è impostata su *Sì* nella scheda **Fattura** della pagina **Parametri contabilità fornitori**. |
| Registra rettifiche come scostamento | Quando questa opzione è impostata su *Sì*, sostituisce la funzionalità standard e forza la registrazione delle transazioni di rettifica scorte correlate agli scostamenti tra costi stimati e costi effettivi in un conto scostamento.<p>Quando questa opzione è impostata su *No*, le transazioni di rettifica scorte correlate agli scostamenti vengono gestite in base alla configurazione del metodo di determinazione dei costi e del codice di tipo di costo. Per il costo standard, gli scostamenti verranno comunque registrati nel conto scostamento. Per la media ponderata mobile (WMA), gli scostamenti verranno registrati nel conto scostamento o nell'inventario.</p><p>Questa opzione ha effetto solo quando l'opzione **Registra nel conto di addebito nella contabilità generale** è impostata su *Sì* nella scheda **Fattura** della pagina **Parametri contabilità fornitori**.</p> |

### <a name="validation-fasttab"></a>Scheda dettaglio Convalida

La tabella seguente descrive i campi disponibili nella Scheda dettaglio **Convalida** della scheda **Generale** nella pagina **Parametri di costo sbarcato**.

| Impostazione | Descrizione |
|---|---|
| Più fatture di costi | Selezionare cosa deve verificarsi se più di una fattura viene elaborata per un viaggio, una registrazione o un contenitore per le stesse spese varie.<ul><li>**Accetta** - Il sistema consente più fatture di costi.</li><li>**Avviso** - Viene visualizzato un avviso.</li><li>**Errore** - Viene visualizzato un messaggio di errore.</li></ul> |
| Più fornitori per registrazione | Selezionare cosa deve verificarsi se a una registrazione vengono aggiunti più ordini fornitore di un fornitore.<ul><li>**Accetta** - Il sistema deve consentire l'azione.</li><li>**Avviso** - Viene visualizzato un avviso, ma l'azione può ancora essere eseguita.</li><li>**Errore** - Viene visualizzato un messaggio di errore e l'azione viene impedita.</li></ul><p>Il broker doganale o le leggi locali potrebbero imporre un valore specifico per questo campo.</p> |
| Tolleranza più modalità di consegna | Selezionare cosa deve verificarsi se le merci di un ordine fornitore che utilizza una modalità di consegna diversa da quella del viaggio vengono aggiunte a quel viaggio.<ul><li>**Accetta** - Il sistema deve consentire l'azione.</li><li>**Avviso** - Viene visualizzato un avviso, ma l'azione può ancora essere eseguita.</li><li>**Errore** - Viene visualizzato un messaggio di errore e l'azione viene impedita.</li></ul> |
| Tolleranza più magazzini | Selezionare cosa deve verificarsi se un viaggio include più righe ordine che devono essere consegnate a diversi magazzini. Queste righe ordine potrebbero estendersi su uno o più ordini fornitore.<ul><li>**Accetta** - Il sistema deve consentire l'azione.</li><li>**Avviso** - Viene visualizzato un avviso.</li><li>**Errore** - Viene visualizzato un messaggio di errore.</li></ul> |
| Volume mancante | Selezionare cosa deve verificarsi se un utente aggiunge un articolo senza volume a un viaggio.<ul><li>**Accetta** - Il sistema deve accettare l'articolo.</li><li>**Avviso** - Viene visualizzato un avviso.</li><li>**Errore** - Viene visualizzato un messaggio di errore.</li></ul><p>Se i volumi vengono utilizzati per calcolare e ripartire i costi, si consiglia di selezionare *Avviso* o *Errore*.</p> |
| Provider di servizi senza costo di viaggio | Selezionare cosa deve verificarsi se un utente tenta di elaborare una fattura per un provider di servizi che non è stato collegato a un viaggio. <ul><li>**Accetta** - Il sistema deve consentire l'azione.</li><li>**Avviso** - Viene visualizzato un avviso.</li><li>**Errore** - Viene visualizzato un messaggio di errore.</li></ul><p>È consigliabile selezionare *Avviso*.</p> |

### <a name="defaults-fasttab"></a>Scheda dettaglio Impostazioni predefiniti

La tabella seguente descrive i campi disponibili nella Scheda dettaglio **Impostazioni predefinite** della scheda **Generale** nella pagina **Parametri di costo sbarcato**.

| Impostazione | Descrizione |
|---|---|
| Nome giornale di registrazione | Selezionare il giornale di registrazione predefinito che la funzione *Crea giornale di registrazione arrivi* deve usare. |
| Stato viaggio | Selezionare lo stato che un viaggio deve avere prima che gli utenti possano impostare un contenitore di spedizione a noleggio nel sistema. Questa azione si verifica in genere quando le merci sono in transito o al molo. |
| Modello di percorso | Selezionare il modello di percorso predefinito da utilizzare per nuovi contenitori di spedizione a noleggio. In genere si selezionerà un modello di percorso che include i costi di noleggio. |
| Movimento | Se la quantità in eccesso/in difetto per una consegna rientra nella tolleranza definita, verrà elaborato automaticamente un giornale di registrazione movimenti. Selezionare il giornale di registrazione movimenti da utilizzare. Il campo **Conto di contropartita** per il nome del giornale di registrazione movimenti selezionato deve avere un valore. |
| Trasferito | Quando viene elaborata una consegna in difetto, la quantità di ricevimento ridotta verrà trasferita a un magazzino di consegna in difetto. Selezionare il giornale di registrazione trasferimento scorte predefinito da utilizzare. |
| Disabilita ordini fornitore diversi da viaggio | Disattivare la funzionalità di consegna in eccesso/in difetto di Costo sbarcato per gli ordini fornitore non associati a un viaggio. |
| Disabilita ordini fornitore diversi da merci in transito | Disattivare la funzionalità di consegna in eccesso/in difetto di Costo sbarcato per gli ordini fornitore che non utilizzano la funzionalità Merci in transito. |
| Periodo di tolleranza entrata in eccesso merci in transito | Specificare il numero di giorni dopo la prima entrata di un contenitore di spedizione per cui è ancora possibile completare ulteriori entrate in eccesso per quel contenitore di spedizione. |

## <a name="status-updates-tab"></a>Scheda Aggiornamenti stato

Il sistema utilizza valori di stato per indicare lo stato di ogni viaggio. I valori di stato del viaggio possono essere applicati automaticamente ai viaggi tramite processi di batch periodici o tracciabilità del viaggio. In alternativa, è possibile applicarli manualmente aprendo il viaggio e selezionando uno stato nel gruppo **Aggiornamento viaggio** della scheda **Gestisci** del riquadro Azioni. 

È possibile creare un numero illimitato di valori di stato del viaggio. Tuttavia, è necessario definire quattro di questi come utilizzati per uno scopo speciale nella scheda **Aggiornamenti di stato** della pagina **Parametri di costo sbarcato**. Nella seguente tabella vengono descritti i campi disponibili.

| Impostazione | Descrizione |
|---|---|
| Preventivato | Selezionare lo stato di viaggio che identifica che un viaggio è stato finalizzato. |
| In transito | Selezionare lo stato di viaggio che identifica che un viaggio è in transito. |
| Pronto per determinazione costi | Selezionare lo stato di viaggio che identifica che un viaggio è pronto per la determinazione costi. Questo stato viene utilizzato quando tutte le fatture acquisto scorte e le fatture costo di viaggio in cui il campo **Credito sul costo di viaggio** è impostato su *Fornitore* sono state elaborate per il viaggio. I viaggi per le quali il processo preventivato non riesce avranno lo stato *Pronto per determinazione costi*.|
| Preventivo in preparazione | Selezionare lo stato di viaggio che identifica che il preventivo di un viaggio è in preparazione. Questo stato viene utilizzato quando una nuova transazione di costo viene aggiunta a un viaggio dopo che è già stato preventivato. Nuove transazioni di costo potrebbero essere aggiunte a un viaggio precedentemente preventivato quando viene ricevuta una seconda fattura di trasporto o un addebito imprevisto per controstallia. Questo stato viene applicato automaticamente quando un nuovo costo di viaggio viene aggiunto a un viaggio preventivato. |

## <a name="voyage-creator-tab"></a>Scheda Creatore viaggio

La tabella seguente descrive le sezioni della scheda **Creatore viaggio** della pagina **Parametri di costo sbarcato**.

| Sezione | Descrizione |
|---|---|
| Tolleranze | I campi **Tolleranza volume esterno** e **Tolleranza peso esterno** definiscono le soglie al di sopra delle quali le merci sono considerate sovraccarico e sovrappeso. Quando un utente aggiunge merci alla pagina **Editor viaggio**, se il volume o il peso supera il valore impostato qui, il sistema mostra un avviso. Il valore di ogni campo è espresso come percentuale del volume o del peso massimo impostato per il tipo di contenitore di spedizione pertinente. Si consiglia un valore tra il 5 e il 10 percento del volume o del peso massimo. |
| Impostazione creazione registrazione | Il sistema può creare più registrazioni durante il processo di creazione del viaggio. Utilizzare questa sezione per definire quando si deve creare una nuova registrazione. Per ogni riga in questa sezione, il sistema controllerà la tabella e il campo specificati e creerà una registrazione per ogni valore di campo univoco. |

## <a name="cost-estimates-tab"></a>Scheda Stime dei costi

La scheda **Stime dei costi** nella pagina **Parametri di costo sbarcato** include un solo campo: **Versione di determinazione dei costi predefinita**. Questo campo si applica solo quando il metodo di determinazione dei costi è *Determinazione costi standard*. Selezionare la versione di determinazione costi predefinita da utilizzare per l'attività periodica *Aggiornamento prezzo di costo articoli*. Potrebbe essere necessario modificare questa impostazione ogni volta che inizia un nuovo anno finanziario.

## <a name="inventory-dimensions-tab"></a>Scheda Dimensioni inventariali

La scheda **Dimensioni inventariali** della pagina **Parametri di costo sbarcato** consente di controllare quali dimensioni inventariali disponibili devono essere visualizzate per impostazione predefinita in ciascuna pagina di Costo sbarcato in cui vengono utilizzate le dimensioni.

Selezionare una dimensione, quindi impostare le opzioni **Righe di viaggio**, **Merci in transito** e/o **Stime dei costi** su *Sì* per ogni pagina in cui quella dimensione deve essere visualizzata per impostazione predefinita. Ripetere questo passaggio per altre dimensioni, come necessario.

Le impostazioni in questa scheda stabiliscono le dimensioni predefinite per ciascuna pagina designata per le persone giuridiche. Tuttavia, gli utenti che stanno lavorando su una delle pagine designate possono sostituire le dimensioni predefinite selezionando **Inventario \> Visualizza dimensioni** nel riquadro Azioni.

## <a name="number-sequences-tab"></a>Scheda Sequenze numeriche

La scheda **Sequenze numeriche** della pagina **Parametri di costo sbarcato** elenca ogni tipo di sequenza numerica di riferimento che Costo sbarcato necessita, ma che non è condivisa tra persone giuridiche. Per ogni riferimento nell'elenco, selezionare un codice di sequenza numerica.

> [!NOTE]
> In una configurazione per più società, è necessario creare sequenze numeriche diverse per ciascuna società (persona giuridica).

## <a name="shared-number-sequences-tab"></a>Scheda Sequenze numeriche condivise

La scheda **Sequenze numeriche condivise** della pagina **Parametri di costo sbarcato** elenca ogni tipo di sequenza numerica di riferimento che è condivisa tra persone giuridiche per Costo sbarcato. Attualmente, nell'elenco è presente una sola sequenza numerica. Questa sequenza numerica viene utilizzata per l'ID viaggio.

Nella pagina **Tutti i viaggi**, gli utenti possono visualizzare tutti i viaggi di tutte le persone giuridiche. Tuttavia, per modificare ed elaborare un viaggio, gli utenti devono essere nella persona giuridica del record selezionato.

## <a name="feature-visibility-tab"></a>Scheda Visibilità funzionalità

Costo sbarcato aggiunge funzionalità (campi e funzioni) a diverse pagine utilizzate di frequente in Microsoft Dynamics 365 Supply Chain Management. Queste pagine includono pagine correlate a dati master di fornitore, prodotti rilasciati, ordini fornitore, ordini di trasferimento e configurazione di magazzino. Se si utilizza Costo sbarcato, è necessario rendere tali funzionalità visibili ovunque per poterle utilizzare. Se non si utilizza Costo sbarcato, è possibile nascondere queste funzionalità.

Nella scheda **Visibilità funzionalità** della pagina **Parametri di costo sbarcato**, impostare l'opzione **Attiva** su *Sì* per rendere visibili le funzionalità di Costo sbarcato ovunque siano disponibili. Impostarla su *No* per nascondere le funzionalità nelle pagine comuni esterne a Costo sbarcato. Tuttavia, anche quando l'opzione è impostata su *No*, il modulo stesso, inclusa la pagina **Parametri di costo sbarcato**, rimarrà disponibile per gli utenti che dispongono delle autorizzazioni corrette per accedervi.
