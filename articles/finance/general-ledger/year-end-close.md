---
title: Chiusura di fine anno
description: In questo articolo viene descritto la configurazione e la procedura richieste per l'esecuzione del processo di chiusura di fine anno della contabilità generale.
author: kweekley
ms.date: 11/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e1c7722b560246fb597f0b7f91a70afecf69e22
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779745"
---
# <a name="year-end-close"></a>Chiusura di fine anno

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto la configurazione e la procedura richieste per l'esecuzione del processo di chiusura di fine anno della contabilità generale.

Alla fine di un anno fiscale,è necessario eseguire il processo di chiusura di fine anno per trasferire i saldi iniziali al nuovo anno. La maggior parte delle organizzazioni eseguirà il processo di chiusura di fine anno più volte. La prima esecuzione sposta i saldi nel nuovo anno fiscale. Il processo può quindi essere nuovamente eseguito, il numero di volte necessario, per spostare i saldi dalle voci di rettifica nel nuovo anno fiscale.

Durante la chiusura di fine anno, sono creati due tipi possibili di transazioni. Una transazione di apertura sempre viene generata e viene utilizzata per creare i saldi iniziali nel nuovo anno fiscale. La transazione di apertura mostra i saldi dei conti CoGe dello stato patrimoniale nel nuovo anno fiscale e i saldi dai conti CoGe profitti e perdite nel conto CoGe per gli utili non distribuiti nel nuovo anno fiscale. La transazione di chiusura facoltativamente viene creata per riportare a zero i saldi dei conti profitti e perdite nell'anno fiscale che viene chiuso.

## <a name="prepare-to-run-the-year-end-close"></a>Prepararsi alla chiusura di fine anno

Prima di eseguire la chiusura di fine anno, convalidare le impostazioni per i seguenti elementi:

Nella pagina **Conto principale**:

- Verifica che il campo **Tipo di conto principale** sia impostato correttamente per ogni conto principale. Il tipo di conto principale determina se il saldo del conto principale verrà riportato come saldo iniziale o verrà chiuso negli utili non distribuiti nella transazioni di apertura.
- Il saldo del conto principale può essere trarsferito in un nuovo conto principale durante la chiusura di fine anno. Immetti il nuovo conto principale nel campo **Conto di apertura**. Questo campo viene in genere utilizzato per i conti principali dello stato patrimoniale quando il conto principale viene disattivato e un nuovo conto principale utilizzato per il nuovo anno fiscale.

Nella pagina **Parametri di contabilità generale** in **Chiusura anno fiscale**:

- L'opzione **Elimina le voci di fine anno esistenti quando si richiude l'anno** viene usata per specificare se la transazione di apertura generata dal sistema da una precedente chiusura di fine anno deve essere eliminata quando la chiusura di fine anno viene nuovamente eseguita. Se l'opzione è impostata su **Sì**, le transazioni di apertura e facoltativamente chiusura precedenti verranno eliminate e una nuova transazione di apertura o chiusura viene creata in base ai saldi correnti. Se l'opzione è impostata su **No**, le precedenti transazioni di apertura e facoltativamente chiusura rimangono e una transazione di apertura o chiusura aggiuntiva viene creata per spostare i saldi in avanti dalle transazioni di rettifica registrate dopo la precedente chiusura di fine anno.
- L'opzione **Crea transazioni di chiusura durante il trasferimento** viene utilizzata per creare le transazioni di chiusura dell'anno fiscale in chiusura per riportare i saldi di tutti i conti principali a 0 (zero). Se l'opzione è impostata su **Sì**, la transazione di apertura e di chiusura vengono entrambe create. Se l'opzione è impostata su **No**, soltanto la transazione di apertura viene creata nell'anno fiscale successivo per trasferire i saldi. I saldi dei conti principali rimangono alla fine dell'anno fiscale.
- L'opzione **Imposta stato anno fiscale su chiuso in modo permanente** viene utilizzata per impostare un anno fiscale definitivamente allo stato chiuso. Utilizza questa opzione con attenzione, perché i periodi con stato di chiusura permanente non possono essere riaperti. Pertanto, le rettifiche non possono essere registrate nell'anno fiscale. È consigliabile impostare questa opzione su **No**.
- L'opzione **un numero di giustificativo deve essere completato durante la chiusura di fine anno** è stata rimossa. Ora è necessario un giustificativo quando viene eseguito il processo di chiusura di fine anno. A quel punto, il numero di giustificativo viene inserito manualmente.

Nella pagina **Calendario fiscale**:

- L'anno fiscale successivo deve essere già presente prima di eseguire la chiusura di fine anno. In caso contrario, i saldi iniziali non possono essere creati nel periodo di apertura.

Nella pagina **Calendario contabilità generale**:

- Facoltativo: ogni periodo fiscale per l'anno fiscale che viene chiuso può essere impostato su **In attesa** per impedire nuove transazioni inserite. Quando le voci di rettifica vengono identificate, i periodi in attesa possono essere riaperti per registrare le voci di rettifica, anche se la chiusura di fine anno è già stato eseguito.

Nella pagina **Configurazione del modello di chiusura di fine anno**:

- Quando la funzionalità **Miglioramenti di fine anno della contabilità generale** è attivata, il processo di impostazione del modello di chiusura di fine anno è separato dal processo di esecuzione della chiusura di fine anno. Il modello può essere definito nella pagina **Configurazione del modello di chiusura di fine anno** (**Contabilità generale \> Impostazione contabilità generale \> Configurazione del modello di chiusura di fine anno**), oppure puoi accedervi dal processo di chiusura di fine anno.

## <a name="define-year-end-close-templates"></a>Definire i modelli di chiusura di fine anno

Una volta completata la configurazione, è possibile eseguire il processo di chiusura di fine anno. Nella pagina **Configurazione del modello di chiusura di fine anno**, un modello può essere definito per il gruppo di persone giuridiche per cui il processo di chiusura di fine anno verrà eseguito. Il modello verrà riutilizzato a ogni chiusura di fine anno, ma può essere modificato se l'organizzazione viene modificata.

Innanzitutto, imposta il campo **Nome gruppo** del modello e seleziona il calendario fiscale. Il nome del gruppo deve identificare il gruppo di persone giuridiche incluse. Quando determini i gruppi di persone giuridiche, ricorda che le persone giuridiche possono essere incluse nello stesso gruppo solo se per esse è selezionato lo stesso calendario fiscale. Ad esempio, i modelli possono essere impostati in base alla posizione geografica, con gruppi distinti creati per le persone giuridiche nordamericane, le persone giuridiche Europa, Medio Oriente o Africa (EMEA) e le persone giuridiche Asia Pacifico (APAC).

A questo punto, le persone giuridiche possono essere aggiunti al modello. Le persone giuridiche possono essere aggiunti selezionando una gerarchia organizzativa o le persone giuridiche. Se una gerarchia organizzativa è selezionata, solo le persone giuridiche nella gerarchia che adottano il calendario fiscale selezionato verranno aggiunti al modello. Se si utilizzano le persone giuridiche da aggiungere al modello, soltanto le persone giuridiche con lo stesso calendario fiscale possono essere aggiunte. Lo stesso calendario fiscale è necessario perché la chiusura di fine anno viene eseguita selezionando un anno fiscale, che può variare dal calendario al calendario.

Dopo che le persone giuridiche vengono aggiunti, definire i conti principali di utili non distribuiti per ogni persona giuridica.

La scheda **Dimensione finanziaria** consente di definire le dimensioni finanziarie da utilizzare nella transazione di apertura. Tieni presente che le impostazioni in questa scheda si applicano solo alla persona giuridica selezionata nella griglia **Persone giuridiche**. Devi ripetere l'impostazione per ogni persona giuridica nella griglia.

L'opzione **Trasferisci dimensioni di conto patrimoniale** viene utilizzata per specificare se le dimensioni finanziarie nelle transazioni registrate nei conti dello stato patrimoniale devono essere mantenute nella transazione di apertura. È consigliabile impostare questa opzione su **Sì**. L'impostazione delle dimensioni di conto patrimoniale non influisce sui saldi esistenti nei conti CoGe utili non distribuiti. Tali saldi sono determinati dalle dimensioni di profitti e perdite definite nella sezione successiva. Ad esempio, l'anno fiscale 2019 è stato il primo anno chiuso e l'opzione **Chiudi tutto** è stata utilizzata per selezionare le dimensioni **Reparto** e **Centro di costo** per la chiusura. In questo caso, è stato creato un conto degli utili non distribuiti separato per ogni combinazione di un reparto e un centro di costo. Quando si esegue la chiusura di fine anno per l'anno fiscale 2020, gli utili non distribuiti dell'anno precedente rimangono esattamente come sono stati registrati, anche se **Trasferisci dimensioni di conto patrimoniale** è impostato su **No**. I saldi registrati negli utili non distribuiti dalle precedenti chiusure di fine anno non vengono mai modificati.

La sezione **Trasferisci dimensioni di profitti e perdite** viene utilizzata per specificare qualie dimensioni finanziarie nelle transazioni registrate nei conti profitti e perdite verranno trasferite nel conto principale utili non distribuiti. Innanzitutto, identifica le dimensioni finanziarie pertinenti alla persona giuridica selezionata. Queste dimensioni finanziarie includono tutte le dimensioni finanziarie usate per la registrazione durante l'anno, anche se la dimensione finanziaria non fa parte di una struttura dei conti attiva. Quindi, definire ogni dimensione come **Chiudi singolo** o **Chiudi tutte**. L'opzione predefinita è **Chiudi tutto**. Questa opzione mantiene i valori di dimensione finanziaria originali delle transazioni registrate e li utilizza per creare i saldi iniziali per il conto utili non distribuiti. I saldi iniziali distinti per gli utili distribuiti verranno creati per ogni combinazione specifica di valori di dimensione finanziaria. Se **Chiudi singolo** è selezionata, tutte le transazioni registrate con quella dimensione finanziaria verranno riepilogate in un saldo iniziale utili non distribuiti per il valore di dimensione immesso nel campo dopo **Chiudi singolo**. Ad esempio, supponi che tutte le transazioni per l'anno fiscale sono state registrate con la struttura dei conti del **conto principale - Reparto**. Nella dimensione finanziaria **Reparto** nel modello, **Chiudi singolo** è selezionato e **100** è il valore di dimensione immesso. Se il ricavo totale di tutte le transazioni registrate per i reparti 200, 300 e 400 è $ 100.000, un saldo iniziale verrà creati per gli **utili non distribuiti - 100**. Se selezioni **Chiudi singolo** ma lasci vuoto il valore della dimensione finanziaria, tutte le transazioni verranno registrate a utili non distribuiti con tale valore di dimensione vuoto.

## <a name="run-the-year-end-close-process"></a>Eseguire il processo di chiusura di fine anno

Dopo aver creato i modelli di chiusura di fine anno, è possibile avviare il processo di chiusura di fine anno nella pagina **Chiusura di fine anno** (**Contabilità generale \> Chiusura periodo \> Chiusura di fine anno**). Prima di eseguire la chiusura di fine anno, puoi aggiungere nuovi modelli di chiusura di fine anno o modificare i modelli esistenti selezionando **Configurazione del modello di chiusura di fine anno** per aprire la pagina di configurazione dei modelli.

Seleziona il modello di chiusura di fine anno, quindi, nel riquadro azioni, seleziona **Esegui chiusura di fine anno**. Seleziona tutte o un sottoinsieme di persone giuridiche dal modello per cui esegui la chiusura di fine anno. Durante l'esecuzione della chiusura di fine anno per la prima volta in un anno fiscale, probabilmente scegli tutte le persone giuridiche per creare i saldi iniziali per tutte le persone giuridiche. Se in precedenza hai eseguito la chiusura di fine anno, potresti voler eseguire il processo di nuovo solo per le persone giuridiche per cui voci di rettifica sono state registrate.

Seleziona l'anno fiscale di cui vuoi eseguire la chiusura di fine anno. Se per l'ultimo periodo dell'anno fiscale esiste più di un periodo di chiusura, il campo **Nome periodo** diventa disponibile. Puoi quindi selezionare il periodo di chiusura da utilizzare per registrare la transazione di chiusura, se l'impostazione è definita per creare la transazione di chiusura.

Quindi immetti il numero di giustificativo. Lo stesso numero di giustificativo verrà utilizzato per tutte le persone giuridiche selezionate per la chiusura di fine anno. Il numero di giustificativo non viene generato usando una sequenza numerica.

La chiusura di fine anno viene eseguita in modalità batch, per impostazione predefinita. Pertanto, dopo averla avviata, puoi tornare ad altre attività.

Poiché le strutture dei conti possono cambiare nel corso di un anno fiscale, non è sempre possibile identificare la struttura dei conti pertinente. Pertanto il processo di chiusura di fine anno non corrisponde alle strutture dei conti. Quando vengono create transazioni di apertura, i saldi vengono riportati con le dimensioni finanziarie definite nel modello di chiusura di fine anno. Le voci dei saldi iniziali possono includere dimensioni finanziarie non più nella corrente struttura dei conti e combinazioni di segmenti non più valide nella struttura dei conti corrente. Se l'organizzazione desidera escludere una dimensione finanziaria per il saldo iniziale utili non distribuiti, imposta la dimensione finanziaria su **Chiudi singolo** e lasciare il valore di dimensione vuoto.

Al termine del processo, viene creato un record per ogni combinazione di persona giuridica e anno fiscale. Vedrai i record solo per le persone giuridiche a cui hai accesso. Ogni record include la data e l'ora di sistema in cui è stato eseguito il processo e un collegamento diretto ai giustificativi creati per la chiusura di fine anno.

[![Record creati nella scheda dettaglio Cronologia di chiusura di fine anno della pagina di chiusura di fine anno](./media/run-yr-end-close.png)](./media/run-yr-end-close.png)

Se esegui nuovamente la chiusura di fine anno, verranno visualizzati uno o più record per ciascuna combinazione di persona giuridica e anno fiscale, a seconda dell'impostazione dell'opzione **Elimina le voci di fine anno esistenti quando si richiude l'anno** nella pagina **Parametri di contabilità generale**.

- Se l'opzione è impostata su **Sì**, il giustificativo per la chiusura di fine anno precedente viene eliminato. Il record è contrassegnato come **Stornato** e timbrato con la data e l'ora in cui è stato eseguito lo storno. Inoltre, viene rimosso il collegamento al numero del giustificativo. Al termine della chiusura di fine anno, verrà creato un nuovo record per il nuovo giustificativo creato.
- Se l'opzione è impostata su **No**, il record per la chiusura di fine anno precedente resta, unitamente al collegamento al giustificativo. Ogni volta che si ripete la chiusura di fine anno, verrà creato un nuovo record, insieme a un collegamento ai nuovi giustificativi.

## <a name="reverse-the-year-end-close-process"></a>Stornare il processo di chiusura di fine anno

Nella pagina **Chiusura di fine anno** puoi stornare una chiusura di fine anno. Selezionare il record per la combinazione di persona giuridica e anno fiscale che deve essere stornato, quindi seleziona **Storna chiusura di fine anno**. Il processo di storno elimina tutti i giustificativi di apertura e chiusura creati per l'anno fiscale. Il record è contrassegnato come **Stornato** e timbrato con la data e l'ora in cui è stato eseguito lo storno. Inoltre, viene rimosso il collegamento al numero del giustificativo. Come per il processo di chiusura di fine anno, lo storno viene eseguito in modalità batch.

Una casella di controllo **Mostra stornato** disponibile sopra la griglia ti consente di nascondere o mostrare i record per i processi di chiusura di fine anno stornati. Dopo aver eseguito il processo **Storna chiusura di fine anno** potrebbe essere necessario selezionare la casella di controllo **Mostra stornato** per vedere il record. Puoi impostare filtri aggiuntivi per visualizzare altre informazioni.

[![Utilizzo della casella di controllo Mostra stornato per visualizzare i record per i processi di chiusura di fine anno stornati nella pagina di chiusura di fine anno](./media/rvrs-yr-end-close.png)](./media/rvrs-yr-end-close.png)

Per ulteriori informazioni, vedere [Chiudere la contabilità generale a fine periodo](close-general-ledger-at-period-end.md) e [Chiudere l'anno fiscale](tasks/close-fiscal-year.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
