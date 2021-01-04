---
title: Criteri di lavoro
description: In questo argomento viene spiegato come configurare i criteri di lavoro.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 08c04caeace7b8ced40915ace1561d817426cba3
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431559"
---
# <a name="work-policies"></a>Criteri di lavoro

[!include [banner](../includes/banner.md)]

Questo argomento spiega come configurare il sistema e l'app del magazzino in modo che supportino i criteri di lavoro. È possibile utilizzare questa funzionalità per registrare rapidamente l'inventario senza creare lavori di stoccaggio quando si ricevono ordini fornitore o di trasferimento o quando si completano i processi di produzione. In questo argomento vengono fornite informazioni generali. Per informazioni dettagliate relative alla ricezione della targa, vedere [Ricezione della targa tramite l'app di magazzino](warehousing-mobile-device-app-license-plate-receiving.md).

Un criterio di lavoro controlla se il lavoro di magazzino viene creato quando un articolo prodotto viene segnalato come finito o quando le merci vengono ricevute utilizzando l'app di magazzino. È possibile impostare ogni criterio di lavoro definendo le condizioni in cui si applica: i tipi e i processi dell'ordine di lavoro, l'ubicazione dell'inventario e (facoltativamente) i prodotti. Ad esempio, un ordine fornitore per il prodotto *A0001* deve essere ricevuto nell'ubicazione *RECV* del magazzino *24*. Successivamente, il prodotto viene utilizzato in un altro processo presso l'ubicazione *RECV*. In questo caso, è possibile configurare un criterio di lavoro per impedire la creazione di lavori di stoccaggio quando un lavoratore segnala un prodotto *A0001* come ricevuto nell'ubicazione *RECV*.

> [!NOTE]
> - Affinché un criterio di lavoro sia attivo, è necessario definire almeno un'ubicazione per esso nella Scheda dettaglio **Ubicazioni di magazzino** della pagina **Criteri di lavoro**. 
> - Non è possibile specificare la stessa ubicazione per molteplici criteri di lavoro.
> - L'opzione **Stampa etichetta** per le voci di menu di dispositivi mobili non stampa un'etichetta di targa senza creazione di lavoro.

## <a name="activate-the-features-in-your-system"></a>Attivare le funzionalità nel sistema

Per rendere disponibili nel sistema tutte le funzionalità descritte in questo argomento, attivare le seguenti due funzionalità in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Miglioramenti ricevimento targa
- Miglioramenti dei criteri di lavoro per il lavoro in entrata

## <a name="the-work-policies-page"></a>Pagina Criteri di lavoro

Per configurare i criteri di lavoro, passare a **Gestione magazzino \> Imposta \> Lavoro \> Criteri di lavoro**. Quindi, su ogni Scheda dettaglio, impostare i campi come descritto nelle sottosezioni seguenti.

### <a name="the-work-order-types-fasttab"></a>Scheda dettaglio Tipi di ordine di lavoro

Nella Scheda dettaglio **Tipi di ordine di lavoro**, aggiungere tutti i tipi di ordini di lavoro e i relativi processi di lavoro a cui si applica il criterio di lavoro. I seguenti tipi di ordini di lavoro e i relativi processi di lavoro sono supportati per i criteri di lavoro.

| Tipo ordine di lavoro | Processo di lavoro |
|---|---|
| Prelievo materie prime| Tutti i processi correlati |
| Stoccaggio co-prodotti e sottoprodotti | Tutti i processi correlati |
| Stoccaggio prodotti finiti | Tutti i processi correlati |
| Entrata trasferimento | Ricevimento (e stoccaggio) targa |
| Ordine fornitore | <ul><li>Ricevimento (e stoccaggio) targa</li><li>Ricevimento (e stoccaggio) articoli di carico</li><li>Ricevimento (e stoccaggio) riga ordine acquisto</li><li>Ricevimento (e stoccaggio) articolo ordine acquisto</li></ul> |

Per configurare un criterio di lavoro in modo che si applichi a più processi di lavoro dello stesso tipo di ordine di lavoro, aggiungere una riga separata per ciascun processo di lavoro sulla griglia.

Per ogni riga della griglia, impostare il campo **Metodo di creazione lavoro** su uno dei seguenti valori:

- **Mai**: i criteri di lavoro impediranno la creazione di lavoro di magazzino per il tipo di ordine di lavoro selezionato e il relativo processo di lavoro.
- **Cross-docking**: i criteri di lacoro creeranno lavoro di cross-docking utilizzando i criteri selezionati nel campo **Nome criteri di cross-docking**.

### <a name="the-inventory-locations-fasttab"></a>Scheda dettaglio Ubicazioni di magazzino

Nella Scheda dettaglio **Ubicazioni di magazzino**, aggiungere tutte le ubicazioni in cui applicare questi criteri di lavoro. Se non si specifica una ubicazione associata ai criteri di lavoro, i criteri di lavoro non verranno applicati ad alcun processo.

Non è possibile specificare la stessa ubicazione per molteplici criteri di lavoro.

È possibile utilizzare un'ubicazione di magazzino assegnata a un profilo di ubicazione in cui l'opzione **Usa rilevamento targa** non è attivata. In questo caso, gli addetti registreranno direttamente le scorte disponibili.

### <a name="the-products-fasttab"></a>Scheda dettaglio Prodotti

Nella scheda **Prodotti**, impostare il campo **Selezione prodotto** per controllare a quali prodotti i criteri devono applicarsi:

- **Tutti**: i criteri dovrebbero applicarsi a tutti i prodotti.
- **Selezionati**: i crtieri dovrebbero applicarsi solo ai prodotti elencati nella griglia. Utilizzare la barra degli strumenti nella Scheda dettaglio **Prodotti** per aggiungere prodotti alla griglia o rimuoverli dalla griglia.

## <a name="default-and-custom-to-locations"></a>Ubicazioni di destinazione predefinite e personalizzate

> [!NOTE]
> Per rendere disponibili nel sistema le funzionalità descritte in questa sezione, è necessario attivare le funzionalità *Miglioramenti del ricevimento della targa* e *Miglioramenti dei criteri di lavoro per il lavoro in ingresso* in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

In precedenza, il sistema supportava il ricevimento solo nell'ubicazione predefinita definita per ciascun magazzino. Tuttavia, le voci di menu dei dispositivi mobili che utilizzano i seguenti processi di creazione del lavoro ora forniscono l'opzione **Utilizza dati predefiniti**. Questa opzione consente di assegnare un'ubicazione di destinazione personalizzata a una o più voci di menu. Questa opzione era già disponibile per alcuni altri tipi di voci di menu.

- Ricevimento (e stoccaggio) targa
- Ricevimento (e stoccaggio) articoli di carico
- Ricevimento (e stoccaggio) riga ordine acquisto
- Ricevimento (e stoccaggio) articolo ordine acquisto

L'impostazione **Ubicazione destinazione** per una voce di menu sostituisce l'ubicazione di ricezione predefinita per il magazzino, per tutti gli ordini elaborati utilizzando quella voce di menu.

Per configurare una voce di menu del dispositivo mobile in modo da supportare la ricezione in un'ubicazione personalizzata, attenersi alla seguente procedura.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Selezionare o creare una voce di menu che utilizza uno dei processi di creazione del lavoro elencati in precedenza in questa sezione.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Utilizza dati predefiniti** su **Sì**.
1. Nel riquadro azioni selezionare **Dati predefiniti**.
1. Nella pagina **Dati predefiniti**, impostare i seguenti valori:

    - **Campo Dati predefiniti:** impostare questo campo su *Ubicazione destinazione*.
    - **Magazzino:** selezionare il magazzino di destinazione da utilizzare con questa voce di menu.
    - **Ubicazione:** questo campo elenca tutti gli ID ubicazione disponibili per il magazzino selezionato. Tuttavia, l'impostazione di questo campo non ha alcun effetto. Pertanto, non è possibile non specificare tale valore. Tuttavia, è possibile utilizzare l'elenco per confermare l'ID che è necessario immettere nel campo **Valore codificato**.
    - **Valore codificato:** immettere l'ID ubicazione per l'ubicazione di ricezione applicabile a questa voce di menu.

> [!TIP]
> Un criterio di lavoro può essere applicato solo se tutte le ubicazioni di ricezione sono elencate nella relativa configurazione dei criteri di lavoro. Questo requisito si applica indipendentemente dal fatto che si stia utilizzando l'ubicazione di ricezione del magazzino predefinita o un'ubicazione destinazione personalizzata.

## <a name="example-scenario-warehouse-receiving"></a>Scenario di esempio: ricezione magazzino

Tutti i prodotti che vengono ricevuti dal processo *Ricevimento (e stoccaggio) articolo ordine acquisto* devono essere registrato nell'ubicazione *FL-001* e devono essere disponibili nel magazzino *24*. Tuttavia, il lavoro non dovrebbe essere creato. I prodotti che vengono ricevuti da qualsiasi altro processo (ovvero utilizzando altre voci di menu del dispositivo mobile) devono essere registrati nell'ubicazione di ricezione del magazzino predefinita (*RECV*) e il lavoro dovrebbe essere creato come al solito. (Questo scenario non mostra la configurazione di ricezione predefinita).

Questo scenario richiede i seguenti elementi:

- Un criterio di lavoro per il processo *Ricevimento (e stoccaggio) articolo ordine acquisto* nell'ubicazione *FL-001*, per tutti i prodotti
- Una voce di menu del dispositivo mobile con dati predefiniti e che imposta il campo **Ubicazione destinazione** su *FL-001*

### <a name="prerequisites"></a>Prerequisiti

Per rendere disponibili nel sistema le funzionalità descritte in questo scenario, è necessario attivare le funzionalità *Miglioramenti del ricevimento della targa* e *Miglioramenti dei criteri di lavoro per il lavoro in ingresso* in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Questo scenario utilizza i dati dimostrativi standard. Pertanto, se si desidera elaborarlo utilizzando i valori specificati qui, è necessario utilizzare un sistema in cui sono installati i dati dimostrativi standard. Inoltre, è necessario selezionare la persona giuridica **USMF**.

### <a name="set-up-a-work-policy"></a>Impostare un criterio di magazzino

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Criteri di lavoro**.
1. Selezionare **Nuovo**.
1. Nel campo **Nome criteri di lavoro**, immetti *Nessun lavoro di stoccaggio per l'articolo d'acquisto*.
1. Selezionare **Salva**.
1. Nella scheda dettaglio **Tipi di ordine di lavoro**, selezionare **Agggiungi** per aggiungere una riga alla griglia e quindi impostare i seguenti valori per la nuova riga:

    - **Tipo di ordine di lavoro:** *Ordini fornitore*
    - **Processo di lavoro:** *Ricevimento (e stoccaggio) articolo ordine acquisto*
    - **Metodo di creazione del lavoro:** *Mai*
    - **Nome criteri di cross-docking:** Lasciare vuoto questo campo.

1. Nella scheda dettaglio **Ubicazioni di magazzino**, selezionare **Aggiungi** per aggiungere una riga alla griglia e quindi impostare i seguenti valori per la nuova riga:

    - **Magazzino:** *24*
    - **Ubicazione:** *FL-001*

1. Nella Scheda dettaglio **Prodotti**, impostare il campo **Selezione prodotto** su *Tutti*.
1. Selezionare **Salva**.

### <a name="set-up-a-mobile-device-menu-item-to-change-the-receiving-location"></a>Impostare una voce di menu del dispositivo mobile in modo da modificare l'ubicazione di ricezione

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Nel riquadro sinistro, selezionare la voce di menu **Entrata acquisto** esistente.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Utilizza dati predefiniti** su *Sì*.
1. Selezionare **Salva**.
1. Nel riquadro azioni selezionare **Dati predefiniti**.
1. Nella riquadro azioni della pagina **Dati predefiniti**, selezionare **Nuovo** per aggiungere una riga alla griglia e quindi impostare i seguenti valori per la nuova riga:

    - **Campo Dati predefiniti:** *Ubicazione destinazione*
    - **Magazzino:** *24*
    - **Ubicazione:** lasciare vuoto questo campo.
    - **Valore codificato:** *FL-001*

1. Selezionare **Salva**.

### <a name="receive-a-purchase-order-without-creating-work"></a>Ricevere un ordine fornitore senza creare lavoro

L'esempio in questa sezione mostra come ricevere un articolo dell'ordine fornitore, ma senza creare lavoro, in una ubicazione diversa dall'ubicazione di ricezione predefinita configurata per il magazzino. In questo esempio vengono utilizzati i criteri di lavoro e la voce del dispositivo mobile creati in precedenza in questo scenario.

#### <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Andare ad **Approvvigionamento \> Ordini fornitore \> Tutti gli ordini fornitore**.
1. Selezionare **Nuovo**.
1. Nella finestra di dialogo **Crea ordine fornitore**, imposta i seguenti valori:

    - **Conto fornitore:** *US-101*
    - **Sito:** *2*
    - **Magazzino:** *24*

1. Scegliere **OK** per chiudere la finestra di dialogo e aprire il nuovo ordine fornitore.
1. Nella Scheda dettaglio **Righe ordine fornitore**, imposta i seguenti valori per la riga vuota:

    - **Numero articolo:** *A0001*
    - **Quantità:** *1*

1. Selezionare **Salva**.
1. Prendere nota del numero di ordine fornitore.

#### <a name="receive-a-purchase-order"></a>Ricevere un ordine fornitore

1. Sul dispositivo mobile, accedere al magazzino *24* utilizzando *24* come ID utente e *1* come password.
1. Selezionare **In ingresso**.
1. Selezionare **Entrata acquisto**. Il campo **Ubicazione** deve essere impostato su *FL-001*.
1. Immettere il numero dell'ordine fornitore per l'ordine fornitore creato nella procedura precedente.
1. Nel campo **Numero articolo** immettere *A0001*.
1. Selezionare **OK**.
1. Nel campo **Quantità** immettere *1*
1. Selezionare **OK**.

L'ordine fornitore è ora ricevuto, ma nessun lavoro è associato ad esso. Le scorte disponibili sono state aggiornate e una quantità di *1* dell'articolo *A0001* è ora disponibile nell'ubicazione *FL-001*.

## <a name="example-scenario-manufacturing"></a>Scenario di esempio: produzione

Nel seguente esempio, sono presenti due ordini di produzione, *PRD-001* e *PRD-002*. L'ordine di produzione *PRD-001* ha un'operazione denominata *Assemblaggio*, in cui il prodotto *SC1* viene dichiarato finito nell'ubicazione *001*. L'ordine di produzione *PRD-002* ha un'operazione denominata *Verniciatura* e utilizza il prodotto *SC1* dall'ubicazione *001*. L'ordine di produzione *PRD-002* utilizza anche le materie prime *RM1* dall'ubicazione *001*. Le materie prime *RM1* sono immagazzinate nell'ubicazione *BULK-001* e verranno prelevate nell'ubicazione *001* dal lavoro di magazzino per il prelievo di materie prime. Il lavoro di prelievo viene generato quando l'ordine di produzione *PRD-002* viene rilasciato.

[![Criteri di lavoro magazzino](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)

Quando si pianifica di configurazione dei criteri di lavoro di magazzino per questo scenario, valutare i seguenti punti:

- Il lavoro di magazzino per lo stoccaggio di articoli finiti non è richiesto quando si dichiara *SC1* come finito dall'ordine di produzione *PRD-001* nell'ubicazione *001*. Questo perché l'operazione *Verniciatura* per l'ordine di produzione *PRD-002* utilizza il prodotto *SC1* nella stessa ubicazione.
- Il lavoro di magazzino per il prelievo di materie prime è necessario per spostare le materie prime *RM1* dall'ubicazione di magazzino *BULK-001* all'ubicazione *001*.

Di seguito è riportato un esempio dei criteri di lavoro che è possibile impostare, in base a queste considerazioni:

- **Nome criteri di lavoro:** *Nessun lavoro di stoccaggio*
- **Tipi di ordini di lavoro:** *Stoccaggio prodotti finiti* e *Stoccaggio co-prodotti e sottoprodotti*
- **Ubicazioni di magazzino:** magazzino *51* e ubicazione *001*
- **Prodotti:** *SC1*

Nello scenario di esempio riportato di seguito vengono fornite istruzioni dettagliate sull'impostazione dei criteri di lavoro di magazzino per questo scenario.

## <a name="example-scenario-report-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Scenario di esempio: dichiarare un ordine di produzione finito in un'ubicazione non controllata da targhe

Questo scenario mostra un esempio di dichiarazione come finito di un ordine di produzione in un'ubicazione non controllata da targhe viene anche descritta.

Questo scenario utilizza i dati dimostrativi standard. Pertanto, se si desidera elaborarlo utilizzando i valori specificati qui, è necessario utilizzare un sistema in cui sono installati i dati dimostrativi standard. Inoltre, è necessario selezionare la persona giuridica **USMF**.

### <a name="set-up-a-warehouse-work-policy"></a>Impostare criteri di lavoro magazzino

I processi del magazzino non includono sempre il lavoro in magazzino. Definendo i criteri di lavoro, è possibile impedire la creazione di lavoro per il prelievo delle materie prime e lo stoccaggio di prodotti finiti per un set di prodotti in ubicazioni specifiche.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoro \> Criteri di lavoro**.
1. Selezionare **Nuovo**.
1. Nel campo **Nome criteri di lavoro**, immetti *Nessun lavoro di stoccaggio*.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella scheda dettaglio **Tipi di ordine di lavoro**, selezionare **Agggiungi** per aggiungere una riga alla griglia e quindi impostare i seguenti valori per la nuova riga:

    - **Tipo di ordine di lavoro:** *Stoccaggio dei prodotti finiti*
    - **Processo di lavoro:** *Tutti i processi di lavoro correlati*
    - **Metodo di creazione del lavoro:** *Mai*
    - **Nome criteri di cross-docking:** Lasciare vuoto questo campo.

1. Selezionare **Aggiungi** nuovamente per aggiungere una seconda riga alla griglia e quindi impostare i seguenti valori per la nuova riga:

    - **Tipo di ordine di lavoro:** *Stoccaggio co-prodotti e sottoprodotti*
    - **Processo di lavoro:** *Tutti i processi di lavoro correlati*
    - **Metodo di creazione del lavoro:** *Mai*
    - **Nome criteri di cross-docking:** Lasciare vuoto questo campo.

1. Nella scheda dettaglio **Ubicazioni di magazzino**, selezionare **Aggiungi** per aggiungere una riga alla griglia e quindi impostare i seguenti valori per la nuova riga:

    - **Magazzino:** *51*
    - **Ubicazione:** *001*

1. Nella Scheda dettaglio **Prodotti**, impostare il campo **Selezione prodotto** su *Selezionati*.
1. Nella Scheda dettaglio **Prodotti**, selezionare **Aggiungi** per aggiungere una riga alla griglia.
1. Nella nuova riga, impostare il campo **Numero articolo** su *L0101*.
1. Nel riquadro azioni selezionare **Salva**.

### <a name="set-up-an-output-location"></a>Impostare un'ubicazione di output

1. Passare a **Amministrazione organizzazione \> Risorse \> Gruppi di risorse**.
1. Nel riquadro sinistro, selezionare il gruppo di risorse **5102**.
1. Nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Magazzino di output:** *51*
    - **Ubicazione di output:** *001*

1. Nel riquadro azioni selezionare **Salva**.

> [!NOTE]
> L'ubicazione *001* non è un'ubicazione controllata da targa. È possibile configurare un'ubicazione di output senza targa solo se i criteri di lavoro applicabili sono disponibili per l'ubicazione.

### <a name="create-a-production-order-and-report-it-as-finished"></a>Creare un ordine di produzione e segnalarlo come finito

1. Fare clic su **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione**.
1. Nel riquadro azioni, selezionare **Nuovo ordine di produzione**.
1. Nella finestra di dialogo **Crea ordine di produzione**, impostare il campo **Numero articolo** su *L0101*.
1. Selezionare **Crea** per creare l'ordine e chiudere la finestra di dialogo.

    Un nuovo ordine di produzione viene aggiunto alla griglia nella pagina **Tutti gli ordini di produzione**.

    Mantieni selezionato il nuovo ordine di produzione.

1. Nel riquadro azioni, scheda **Ordine di produzione**, gruppo **Processo**, selezionare **Stima**.
1. Nella finestra di dialogo **Stima**, leggere la stima, quindi selezionare **OK** per chiudere la finestra di dialogo.
1. Nel riquadro azioni, scheda **Ordine di produzione**, gruppo **Processo**, selezionare **Avvia**.
1. Nella finestra di dialogo **Avvia**, nella scheda **Generale**, impostare il campo **Consumo DBA automatico** su *Mai*.
1. Selezionare **OK** per salvare l'impostazione e chiudere la finestra di dialogo.
1. Nel riquadro azioni, scheda **Ordine di produzione**, gruppo **Processo**, selezionare **Dichiarazione di finito**.
1. Nella finestra di dialogo **Dichiarazione di finito**, sulla scheda **Generale**, impostare l'opzione **Accetta errore** su *Sì*.
1. Selezionare **OK** per salvare l'impostazione e chiudere la finestra di dialogo.
1. Nella scheda **Magazzino** del riquadro azioni, nel gruppo **Generale**, selezionare **Dettagli lavoro**.

Quando l'ordine di produzione è stato dichiarato finito, nessun lavoro è stato generato per lo stoccaggio. Questo comportamento si verifica perché vengono definiti criteri di lavoro che impediscono la generazione del lavoro quando il prodotto *L0101* viene dichiarato finito all'ubicazione *001*.

## <a name="more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sulle voci di menu dei dispositivi mobili, vedere [Configurare i dispositivi mobili per il lavoro di magazzino](configure-mobile-devices-warehouse.md).

Per altre informazioni relative alla ricezione della targa e ai criteri di lavoro, vedere [Ricezione della targa tramite l'app di magazzino](warehousing-mobile-device-app-license-plate-receiving.md).

Per ulteriori informazioni sulla gestione dei carichi in entrata, vedere [Gestione magazzino dei carichi in entrata per gli ordini fornitore](inbound-load-handling.md).
