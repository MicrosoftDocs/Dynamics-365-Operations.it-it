---
title: Elaborazione merci in transito
description: In questo argomento viene descritto come utilizzare gli ordini merci in transito. Quando un ordine o un viaggio viene configurato per utilizzare l'elaborazione merci in transito, le merci possono essere fatturate prima di essere ricevute nel magazzino per l'utilizzo.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DeliveryTerms, InventLocation, InventPosting, ITMGoodsInTransitOrder, ITMTableListPage, ITMTable, ITMContainersListPage, ITMContainers, ITMFolioTableListPage, ITMFolioTable, ITMGoodsInTransitOrderEditLines, SysOperationTemplateForm, WHSRFMenuItem, WHSLocDirTable, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: af7ac416053a90766138f999ce69d9993ee2ff6c
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500281"
---
# <a name="goods-in-transit-processing"></a>Elaborazione merci in transito

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come utilizzare gli ordini merci in transito. Questo tipo di ordine viene utilizzato solo nel modulo **Costo sbarcato**. Quando un ordine o un viaggio viene configurato per utilizzare l'elaborazione merci in transito, non è necessario attendere il ricevimento delle merci per fatturarle. Le merci vengono invece fatturate quando lasciano il magazzino o il porto di origine del fornitore e i costi finanziari vengono riconosciuti quando ha inizio il viaggio. Questa funzionalità consente di assumere correttamente la proprietà delle merci in quanto queste spesso diventano di proprietà della propria organizzazione quando lasciano il porto di spedizione.

Quando vengono utilizzati ordini merci in transito, gli articoli aggiornati finanziariamente vengono ricevuti in un magazzino provvisorio noto come magazzino merci in transito. Le merci rimangono quindi in questo magazzino fino a quando non possono essere ricevute nel magazzino di destinazione finale (ovvero il magazzino definito nella riga di acquisto). Non possono essere rimosse manualmente.

Fino a che gli articoli sono in transito, non sono disponibili nell'inventario e non possono essere prelevati per una consegna. Tuttavia, è possibile visualizzare l'inventario merci in transito. È anche possibile utilizzare le merci per la pianificazione generale. In questo caso, utilizzare la data di consegna confermata nella riga di ordine fornitore come data prevista in cui le merci in magazzino saranno disponibili per il consumo.

Le sezioni seguenti descrivono la configurazione necessaria per elaborare l'inventario e i viaggi utilizzando il concetto e la funzionalità merci in transito.

## <a name="terms-of-delivery"></a>Termini di consegna

Quando si abilita il modulo **Costo sbarcato**, l'entità *termini di consegna* standard viene migliorata per supportare la funzionalità merci in transito.

Quando l'opzione **Gestione merci in transito** è impostata su *Sì* per i termini di consegna applicabili, le merci vengono integrate nel magazzino merci in transito. Questa azione viene attivata solo se l'entrata in magazzino non viene elaborata prima dell'elaborazione di una fattura. Quando i termini di consegna di un ordine sono impostati per utilizzare le merci in transito, gli utenti non possono più registrare un'entrata prodotti per l'ordine fornitore. Se ci provano, si verifica un errore. Il messaggio di errore indica che devono utilizzare la funzionalità merci in transito per procedere.

Per utilizzare le informazioni sui termini di consegna per le merci in transito, selezionare **Approvvigionamento \> Impostazioni \> Distribuzione \> Termini di consegna**. La tabella seguente descrive i campi che il modulo **Costo sbarcato** aggiunge alla pagina **Termini di consegna** per supportare la funzionalità merci in transito. Entrambi i campi sono nella Scheda dettaglio **Generale**. Per ulteriori informazioni sugli altri campi in questa pagina, vedere [Termini di consegna (modulo)](/dynamicsax-2012//terms-of-delivery-form).

| Campo | Descrizione |
|---|---|
| Porto di spedizione obbligatorio | Impostare questa opzione su *Sì* se un porto di spedizione è obbligatorio quando si applicano i termini di consegna. |
| Gestione merci in transito | Impostare questa opzione su *Sì* per utilizzare la gestione delle merci in transito quando si applicano i termini di consegna. |

## <a name="warehouses-for-goods-in-transit-and-under-delivery"></a>Magazzini per merci in transito e consegna in difetto

Quando si abilita il modulo **Costo sbarcato**, l'entità *magazzini* standard viene migliorata per abilitare la fatturazione degli ordini fornitore quando le merci si trovano in un magazzino merci in transito.

Il modulo Costo sbarcato aggiunge due nuovi tipi di magazzino: *merci in transito* e *consegna in difetto*. I magazzini di entrambi i tipi possono essere selezionati come magazzini predefiniti. Per un'elaborazione corretta degli ordini merci in transito, sia il magazzino merci in transito che il magazzino consegna in difetto devono essere configurati nella pagina **Magazzini**. Quindi, per ogni magazzino predefinito che verrà utilizzato con Costo sbarcato e merci in transito, è necessario selezionare il magazzino merci in transito e il magazzino consegna in difetto per i magazzini disponibili di ciascun tipo.

Il tipo di magazzino *merci in transito* verrà associato al magazzino merci in transito e tale magazzino verrà utilizzato per elaborare le merci negli ordini merci in transito prima che vengano ricevute nel magazzino di destinazione finale. In generale, un magazzino merci in transito è sufficiente per ogni sito se Sito e Magazzino sono le uniche dimensioni inventariali utilizzate per la gestione degli articoli. Se viene utilizzata anche la dimensione inventariale Ubicazione, è necessario impostare un magazzino merci in transito per ciascuna combinazione di sito e magazzino, in modo da poter specificare anche l'ubicazione predefinita.

Per utilizzare le impostazioni relative alle merci in transito per i magazzini in uso, selezionare **Gestione articoli \> Impostazioni \> Suddivisione scorte \> Magazzini**. La tabella seguente descrive i campi che il modulo **Costo sbarcato** aggiunge alla pagina **Magazzini** per supportare la funzionalità merci in transito. Entrambi i campi sono visualizzati nella Scheda dettaglio **Generale**. Per informazioni sugli altri campi nella pagina, vedere [Magazzini (modulo)](/dynamicsax-2012//warehouses-form).

| Campo | Descrizione |
|---|---|
| Magazzino merci in transito | Consente di identificare il magazzino merci in transito correlato al magazzino principale. |
| Magazzino consegna in difetto | Consente di identificare il magazzino consegna in difetto correlato al magazzino principale. |

## <a name="posting-rules-for-landed-cost"></a>Regole di registrazione per costo sbarcato

Costo sbarcato aggiunge due nuove regole di registrazione che è possibile configurare. Queste regole di registrazione sono utilizzate per registrare finanziariamente gli importi diretti della fattura di ordine fornitore per identificare la proprietà delle merci quando lasciano il punto di origine. Questo processo sostituisce il concetto di *merce ricevuta non fatturata* poiché le merci vengono fatturate prima di essere ricevute. <!-- KFM: Add a link to the related scenario when available. -->

Per utilizzare i profili di registrazione, selezionare **Gestione articoli \> Impostazioni \> Registrazione \> Registrazione**. Nella scheda **Ordine fornitore**, sono disponibili le seguenti nuove regole di registrazione:

- **Costo sbarcato, merci in transito** - Specificare le regole di registrazione per la gestione merci in transito.
- **Costo sbarcato, rateo addebito costi** - Specificare le regole di registrazione per il rateo del conto di addebito.

## <a name="goods-in-transit-orders"></a>Ordini merci in transito

È possibile esaminare e gestire ordini merci in transito direttamente nel modulo **Costo sbarcato**. È possibile elaborare ordini merci in transito direttamente dalla pagina **Ordini merci in transito**. In alternativa, è possibile accedere al viaggio associato agli ordini merci in transito ed elaborare l'intero viaggio, contenitore di spedizione o registrazione. Quando si fattura un viaggio e si creano ordini merci in transito, viene creato un nuovo ordine merci in transito per ogni combinazione di inventario e dimensioni inventariali associata alla riga di ordine fornitore.

Per gestire merci in transito, Costo sbarcato utilizza una procedura in due fasi:

1. Un articolo viene ricevuto quando viene elaborata una fattura delle scorte e le viene assegnato lo stato *In transito*.
1. L'ordine merci in transito viene elaborato nella pagina **Ordini merci in transito** e viene quindi ricevuto nel magazzino specificato nell'ordine fornitore. A quel punto, lo stato diventa *Ricevuto*.

Per utilizzare gli ordini merci in transito, selezionare **Costo sbarcato \> Attività periodiche \> Ordini merci in transito**.

## <a name="receiving-stock-from-the-goods-in-transit-warehouse"></a>Ricevimento delle scorte dal magazzino merci in transito

È possibile ricevere merci da un ordine merci in transito in molti modi, a seconda della configurazione del sistema.

### <a name="in-transit-receiving"></a>Ricevimento in transito

È possibile eseguire un ricevimento in transito in una qualsiasi delle seguenti pagine:

- Nella pagina **Ordini merci in transito**, selezionare la riga e quindi, nel riquadro Azioni, selezionare **Ricevi**.
- Nella pagina **Tutti i viaggi**, selezionare o aprire un viaggio. Quindi, nel riquadro Azioni, nella scheda **Gestisci**, nel gruppo **Merci in transito**, selezionare **Ricevi merci in transito**.
- Nella pagina **Tutti i contenitori di spedizione**, selezionare o aprire un contenitore di spedizione. Quindi, nel riquadro Azioni, nella scheda **Gestisci**, nel gruppo **Merci in transito**, selezionare **Ricevi merci in transito**.
- Nella pagina **Tutte le registrazioni**, selezionare o aprire una registrazione. Quindi, nel riquadro Azioni, nella scheda **Gestisci**, nel gruppo **Merci in transito**, selezionare **Ricevi merci in transito**.

> [!NOTE]
> La ricezione in transito viene generalmente utilizzata in situazioni in cui le ubicazioni e la tracciabilità seriale/batch non sono utilizzate.

### <a name="arrival-journal"></a>Giornale di registrazione arrivi

È anche possibile ricevere merci creando un giornale di registrazione arrivi. È possibile creare un giornale di registrazione arrivi direttamente dalla pagina del viaggio. Le procedure consigliate stabilite dall'organizzazione determinano se il giornale di registrazione arrivi viene utilizzato per ricevere le merci.

1. Aprire il viaggio, il contenitore o la registrazione.
1. Nel riquadro azioni della scheda **Gestisci** del gruppo **Funzioni**, selezionare **Crea giornale di registrazione arrivi**.
1. Nella finestra di dialogo **Crea giornale di registrazione arrivi**, impostare i seguenti valori:

    - **Inizializza quantità** - Impostare questa opzione su *Sì* per impostare la quantità in base alla quantità in transito. Se questa opzione è impostata su *No*, non viene impostata alcuna quantità predefinita in base alle righe merci in transito.
    - **Crea da merci in transito** - Impostare questa opzione su *Sì* per prelevare quantità dalle righe in transito selezionate per il viaggio, il contenitore o il folio selezionato.
    - **Crea da righe ordine** - Impostare questa opzione su *Sì* per impostare la quantità predefinita nel giornale di registrazione arrivi in base alle righe di ordine fornitore. La quantità predefinita nel giornale di registrazione arrivi può essere impostata in questo modo solo se la quantità nella riga di ordine fornitore corrisponde alla quantità nell'ordine merci in transito.

1. Elaborare il giornale di registrazione arrivi come descritto in [Registrare le entrate articoli con un giornale di registrazione arrivi articoli](/dynamicsax-2012/appuser-itpro/register-item-receipts-with-an-item-arrival-journal).

> [!NOTE]
> Il giornale di registrazione arrivi è generalmente utilizzato in situazioni in cui vengono utilizzate ubicazioni e tracciabilità batch/seriale, ma non la gestione del magazzino.
>
> Le ubicazioni di ricevimento predefinite non devono essere specificate nelle righe ordine se verrà specificata un'ubicazione di stoccaggio nel giornale di registrazione arrivi.

## <a name="warehouse-management"></a>Gestione magazzino

Quando si abilita il modulo **Costo sbarcato**, diverse pagine nel modulo **Gestione magazzino** vengono modificate di modo che l'elaborazione degli ordini (in particolare, l'elaborazione merci in transito) possa essere eseguita tramite il modulo **Costo sbarcato**. Questa sezione descrive i campi e i processi aggiunti nel modulo **Gestione magazzino**.

### <a name="mobile-device-menu-items"></a>Voci di menu del dispositivo mobile

Le merci possono essere ricevute utilizzando un dispositivo mobile, a condizione che il menu del dispositivo mobile e il modulo **Gestione magazzino** siano stati impostati per ricevere merci su un ordine merci in transito. Questa sezione descrive l'impostazione associata al ricevimento merci in transito.

Per configurare i dispositivi mobili per l'elaborazione merci in transito, selezionare **Gestione magazzino \> Impostazioni \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.

Costo sbarcato aggiunge i seguenti processi di creazione di lavoro alle voci di menu del dispositivo mobile per supportare l'elaborazione merci in transito:

- Ricevimento articoli merci in transito
- Ricevimento e stoccaggio articoli merci in transito

Le impostazioni di configurazione per questi processi sono simili alle impostazioni per i [processi di creazione lavoro: ricevimento e stoccaggio ordine fornitore](/dynamicsax-2012/appuser-itpro/configure-mobile-devices-for-warehouse-work). Tuttavia, il processo *Ricevimento e stoccaggio articoli merci in transito* aggiunge anche il seguente campo.

- **Abilita contenitore di spedizione completo** - Se questa opzione è impostata su *Sì*, quando il lavoro di stoccaggio è completato, l'app per dispositivi mobili Gestione magazzino fornirà un'opzione aggiuntiva denominata **Contenitore di spedizione completo**. Quando questa opzione è selezionata, al lavoratore verrà chiesto di confermare che il contenitore è completo. A quel punto, tutte le entrate incomplete verranno elaborate come transazione in difetto.

### <a name="location-directives"></a>Direttive ubicazione

Costo sbarcato aggiunge un nuovo tipo di ordine di lavoro denominato *Merci in transito* alla pagina **Direttive ubicazione**. Questo tipo di ordine di lavoro deve essere configurato allo stesso modo dei [tipi di ordine di lavoro di ordine fornitore](/dynamicsax-2012/appuser-itpro/create-a-work-template).

### <a name="work-templates"></a>Modelli di lavoro

Questa sezione descrive le funzioni che il modulo **Costo di spedizione** aggiunge ai modelli di lavoro.

#### <a name="goods-in-transit-work-order-type"></a>Tipo di ordine di lavoro Merce in transito

Costo sbarcato aggiunge un nuovo tipo di ordine di lavoro denominato *Merci in transito* alla pagina **Modelli di lavoro**. Questo tipo di ordine di lavoro deve essere configurato allo stesso modo dei [modelli di lavoro di ordine fornitore](/dynamicsax-2012/appuser-itpro/create-a-work-template).

#### <a name="work-header-breaks"></a>Interruzioni intestazione lavoro

I modelli di lavoro che hanno un tipo di ordine di lavoro di *Merce in transito* possono essere configurati per dividere le intestazioni di lavoro. Nella pagina **Modelli di lavoro**, effettua una delle seguenti operazioni:

- Nella scheda **Generale** per il modello, imposta i valori massimi dell'intestazione di lavoro. Questi valori massimi funzionano nello stesso modo in cui funzionano per i modelli di lavoro degli ordini fornitore. Per ulteriori informazioni, vedi [modelli di lavoro ordine fornitore](/dynamicsax-2012/appuser-itpro/create-a-work-template).
- Utilizza il pulsante **Suddivisioni intestazione lavoro** per definire il momento in cui il sistema deve creare nuove intestazioni di lavoro, in base ai campi usati per l'ordinamento. Ad esempio, per creare un'intestazione di lavoro per ogni ID contenitore, seleziona **Modifica query** nel riquadro azioni e quindi aggiungere il campo **ID contenitore** alla scheda **Ordinamento** dell'editor di query. I campi aggiunti alla scheda **Ordinamento** sono disponibili per la selezione come *campi di raggruppamento*. Per impostare i campi di raggruppamento, seleziona **Suddivisioni intestazione lavoro** nel riquadro azioni e quindi, per ogni campo da utilizzare come campo di raggruppamento, seleziona la casella di controllo nella colonna **Raggruppa per questo campo**.

Il costo di spedizione [crea una transazione in eccesso](over-under-transactions.md) se la quantità registrata supera la quantità dell'ordine originale. Quando un'intestazione di lavoro è completata, il sistema aggiorna lo stato delle transazioni di inventario per la quantità dell'ordine entità. Tuttavia, aggiorna prima la quantità collegata alla transazione in eccesso dopo che l'entità è stata completamente acquistata.

Se annulli un'intestazione di lavoro per una transazione in eccesso che è già stata registrata, la transazione in eccesso viene prima ridotta della quantità annullata. Dopo che la transazione in eccesso viene ridotta a una quantità pari a 0 (zero), il record viene rimosso e qualsiasi quantità aggiuntiva viene annullata rispetto alla quantità dell'ordine entità.
