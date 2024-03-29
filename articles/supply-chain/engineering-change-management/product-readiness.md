---
title: Idoneità prodotto
description: In questo articolo viene illustrato come utilizzare i controlli di idoneità per garantire che i dati master richiesti siano stati completati per un prodotto prima che venga utilizzato nelle transazioni.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a8e76d5fc786b6f4cac7cd0430399ca3ad13a7bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856224"
---
# <a name="product-readiness"></a>Idoneità prodotto

[!include [banner](../includes/banner.md)]

È possibile i controlli di idoneità per garantire che tutti i dati master richiesti siano stati specificati per un prodotto prima che venga utilizzato nelle transazioni. Quando vengono utilizzati i controlli di idoneità, un utente o un team è responsabile della convalida di dati specifici predefiniti relativi al prodotto.

Puoi selezionare la casella di controllo **Attiva** per un prodotto di progettazione, una variante o una versione solo dopo che tutti i dati richiesti sono stati inseriti e verificati e dopo che tutti i controlli di idoneità sono stati elaborati. Se uno o più controlli non sono stati elaborati per il prodotto, la versione o la variante, quando tenti di contrassegnare la casella di controllo **Attiva**, riceverai un messaggio di avviso che non tutti i controlli sono stati completati.

È possibile creare controlli di disponibilità per nuovi prodotti, varianti e versioni di progettazione. È inoltre possibile applicare controlli di disponibilità per prodotti standard (non tecnici) (vedi anche [Controlli di disponibilità sui prodotti standard](#standard-products)). 

Puoi utilizzare prodotti standard nelle transazioni anche se non sono stati completati tutti i controlli di disponibilità. Se è necessario impedire l'utilizzo di un prodotto nelle transazioni, utilizza il relativo stato del ciclo di vita. Puoi assegnare uno stato del ciclo di vita che impedisce l'utilizzo di un prodotto nelle transazioni e quindi, dopo che tutti i controlli di disponibilità sono stati completati, assegnare un nuovo stato del ciclo di vita che consente le transazioni richieste.

## <a name="types-of-readiness-checks"></a>Tipi di controlli di disponibilità

Sono disponibili tre tipi di controlli di disponibilità:

- **Controllo del sistema** - Il sistema verifica se esiste un record valido. Ad esempio, il record potrebbe essere una distinta base attiva.
- **Controllo manuale** - Un utente verifica se il record è valido. Ad esempio, un controllo di disponibilità potrebbe richiedere la convalida delle impostazioni dell'ordine predefinite. In alcuni casi, ad esempio quando il prodotto è ancora in fase di progettazione e quindi non verrà messo in magazzino, non sono richieste impostazioni di ordine predefinite. Tuttavia, le impostazioni dell'ordine predefinite potrebbero essere richieste per un altro prodotto dello stesso tipo, poiché il prodotto può essere tenuto in magazzino. L'utente è responsabile di prendere la corretta decisione se è necessario un controllo di disponibilità.
- **Lista di controllo** - L'utente risponde a una serie di domande da una lista di controllo e il sistema determina se le risposte soddisfano le aspettative. La lista di controllo può avere qualsiasi argomento. Ad esempio, può essere utilizzata per determinare se i materiali di marketing o la documentazione del prodotto sono stati completati.

<a name="checks-engineering"></a>

## <a name="how-readiness-checks-are-created-for-a-new-engineering-product-variant-or-version"></a>Come vengono creati i controlli di disponibilità per un nuovo prodotto, variante o versione di progettazione

I criteri di controllo della disponibilità possono essere applicati a livello di prodotto rilasciato, a livello di variante rilasciata e a livello di versione di progettazione.

Quando crei un nuovo *prodotto di progettazione*, il sistema determina se un [si applica un criterio di controllo dell'idoneità](#assign-policy) ad esso. Se si applica un criterio di controllo dell'idoneità, si verificano i seguenti eventi:

- I controlli di disponibilità vengono creati per il prodotto, in base ai criteri applicabili.
- La versione di progettazione è impostata su inattiva per bloccare l'utilizzo del prodotto. Tutte le versioni di progettazione del prodotto sono impostate su inattive.

Se viene creata una nuova *variante* per un prodotto, il sistema verifica se ad esso si applica un criterio di verifica dell'idoneità. I controlli di idoneità possono essere applicati a livello di variante rilasciata e a livello di versione di progettazione. Se si applica un criterio, si verificano i seguenti eventi:

- I controlli di disponibilità vengono creati per il prodotto, in base ai criteri applicabili.
- La versione e la variante di progettazione è impostata su inattiva per bloccare l'utilizzo del prodotto.

Se viene creata una nuova *versione* di progettazione, il sistema verifica se ad esso si applica un criterio di verifica dell'idoneità. I controlli di idoneità possono essere applicati a livello di versione di progettazione. Se si applica un criterio, si verificano i seguenti eventi:

- I controlli di disponibilità vengono creati per il prodotto, in base ai criteri applicabili.
- La versione di progettazione è impostata su inattiva per bloccare l'utilizzo del prodotto.

> [!NOTE]
> È inoltre possibile configurare criteri dei controlli di idoneità standard (non tecnici). Per ulteriori informazioni, vedi a sezione [Controlli di idoneità su prodotti standard](#standard-products) più avanti in questo articolo.

## <a name="view-readiness-checks"></a>Visualizzare i controlli di disponibilità

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Visualizzare i controlli di disponibilità aperti per un prodotto o una versione del prodotto

Per trovare i controlli di disponibilità aperti per un prodotto, aprire la pagina **Dettagli sui prodotti rilasciati**. Quindi, nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Controlli di disponibilità**, selezionare **Controlli di disponibilità**.

Per trovare i controlli di disponibilità aperti per una versione del prodotto, aprire la pagina **Versioni di progettazione** per un prodotto rilasciato e scegliere una versione. Quindi, nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Elenco di controllo**, selezionare **Controlli di disponibilità**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Visualizzare i controlli di disponibilità aperti che sono stati assegnati all'utente

Per visualizzare i controlli di disponibilità aperti assegnati all'utente, seguire uno di questi passaggi.

- Andare a **Gestione modifiche di progettazione \> Comune \> Idoneità prodotto \> Controlli di disponibilità aperti personali**.
- Andare a **Gestione informazioni sul prodotto \> Aree di lavoro \> Disponibilità del prodotto per la produzione discreta**.

L'impostazione che specifica a chi è assegnato il controllo di disponibilità viene eseguita per il criterio di disponibilità. I controlli di disponibilità possono essere assegnati a una persona o a un team. Se un controllo di disponibilità viene assegnato a un team, una persona nel team deve elaborare il controllo di disponibilità.

## <a name="process-open-readiness-checks"></a>Elaborare controlli di disponibilità aperti

### <a name="process-system-and-manual-readiness-checks"></a>Sistema di processo e controlli manuali di disponibilità

Dopo aver aperto la pagina **Controlli di disponibilità** è possibile visualizzare l'oggetto dei controlli di disponibilità del sistema e manuali selezionando **Visualizza informazioni correlate** nel riquadro azioni. È quindi possibile completare e/o convalidare i dati per il controllo di disponibilità. I controlli di disponibilità aperti hanno un valore **Stato** di *In sospeso*. Questo stato indica che il controllo di disponibilità deve ancora essere elaborato. Per elaborare un controllo di disponibilità, effettuare uno dei seguenti passaggi.

- Nel riquadro azioni selezionare **Controllo/completa** per esaminare e completare il controllo di disponibilità. Al termine, il campo **Stato** viene aggiornato su *Superato*.
- Nel riquadro azioni selezionare **Ignora** per ingnorare un controllo di disponibilità non obbligatorio. Ad esempio, si imposta un controllo di disponibilità per i calcoli dei prezzi. Tuttavia, si decide di ignorare questo controllo mentre il prodotto è ancora in fase di progettazione. In questo caso, il campo **Stato** viene aggiornato su *Ignorato*.

A seconda della configurazione dei criteri di disponibilità, quando il campo **Stato** per un controllo di disponibilità viene aggiornato su *Superato*, potrebbe essere necessario un passaggio aggiuntivo per approvare il controllo di disponibilità. In questo caso, selezionare **Approvazione** per completare il controllo di disponibilità. Questa fase di approvazione è sempre obbligatoria quando il controllo di disponibilità viene ignorato.

Quando tutti i controlli di disponibilità aperti per un nuovo prodotto, variante o versione sono stati elaborati e approvati come richiesto, l'articolo diventa automaticamente attivo e quindi pronto per l'uso.

### <a name="process-checklist-readiness-checks"></a>Elaborare controlli di disponibilità con elenco di controllo

Per aprire un elenco di controllo, aprire la pagina **Controlli di disponibilità** quindi, nel riquadro azioni, selezionare **Avvia elenco di controllo**. Una volta completato l'elenco di controllo, il sistema convalida se il controllo di disponibilità è stato superato, in base alle impostazioni nel questionario. Se il controllo viene superato, il campo **Stato** viene aggiornato su *Superato*. Se il controllo di disponibilità non è obbligatorio, è possibile ignorarlo. In questo caso, il campo **Stato** viene aggiornato su *Ignorato*.

A seconda della configurazione dei criteri di disponibilità, quando il campo **Stato** per un controllo di disponibilità viene aggiornato su *Superato*, potrebbe essere necessario un passaggio aggiuntivo per approvare il controllo di disponibilità. In questo caso, selezionare **Approvazione** per completare il controllo di disponibilità. Questa fase di approvazione è sempre obbligatoria quando il controllo di disponibilità viene ignorato.

Quando tutti i controlli di disponibilità aperti per un nuovo prodotto, variante o versione sono stati elaborati e approvati come richiesto, l'articolo diventa automaticamente attivo e quindi pronto per l'uso.

## <a name="create-and-manage-product-readiness-policies"></a>Creare e gestire i criteri di disponibilità del prodotto

Utilizzare i criteri di disponibilità del prodotto per gestire i controlli di disponibilità che si applicano a un prodotto. Ciascun criterio di disponibilità contiene una serie di controlli di disponibilità. Quando un criterio di disponibilità viene assegnato a una categoria di prodotti di progettazione o a un prodotto condiviso, tutti i prodotti correlati a quella categoria o prodotto condiviso avranno i controlli di disponibilità indicati nei criteri di disponibilità.

Per lavorare con i criteri di disponibilità del prodotto, andare a **Gestione modifiche di progettazione \> Impostazione \> Criteri di disponibilità del prodotto**. Eseguire quindi uno dei passaggi seguenti.

- Per creare un nuovo criterio, selezionare **Nuovo** nel riquadro azioni, quindi impostare i campi come descritto nelle sottosezioni seguenti.
- Per modificare un criterio esistente, selezionarla nel riquadro dell'elenco, selezionare **Modifica** nel riquadro azioni, quindi impostare i campi come descritto nelle sottosezioni seguenti.
- Per eliminare un criterio esistente, selezionarlo nel riquadro dell'elenco, selezionare **Modifica** nel riquadro azioni, quindi nella scheda dettaglio **Generale** assicurarsi che l'opzione **Attivo** sia impostata su *No*. Nel riquadro azioni selezionare quindi **Elimina**.

### <a name="header"></a>Intestazione

Impostare i seguenti campi nell'intestazione dei criteri di disponibilità del prodotto.

| Campo | Descrizione |
|---|---|
| Nome | Immetti un nome per il criterio. |
| Descrizione | Immettere una descrizione dei criteri. |

### <a name="general-fasttab"></a>Scheda dettaglio Generale

Impostare i seguenti campi nella scheda dettaglio **Generale** dei criteri di disponibilità del prodotto.

| Campo | Descrizione |
|---|---|
| Tipo di prodotto | Selezionare se il criterio si applica ai prodotti di tipo *Articolo* o *Servizio*. Non è possibile modificare questa impostazione dopo aver salvato il record. |
| Attive | Usare questa opzione per gestire i criteri di disponibilità. Impostare su *Sì* per tutti i criteri di disponibilità in uso. Impostare su *No* per contrassegnare un criterio di disponibilità come inattivo quando non viene utilizzato. Si noti che non è possibile disattivare un criterio di disponibilità assegnato a una categoria di prodotti di progettazione o un prodotto condiviso ed è possibile eliminare solo i criteri di rilascio inattivi. |

### <a name="readiness-control-fasttab"></a>Scheda dettaglio Controllo di disponibilità

Per ogni tipo di controllo di disponibilità che si desidera includere nei criteri, aggiungere una riga nella scheda dettaglio **Controllo di disponibilità**. Utilizzare i seguenti pulsanti della barra degli strumenti della Scheda dettaglio per aggiungere e rimuovere le righe come richiesto:

- **Aggiungi controllo** - Aggiungere un controllo di disponibilità standard ai criteri. Quando si seleziona questo pulsante, la finestra di dialogo **Aggiungi controllo** viene visualizzata. Qui è possibile selezionare da un elenco di controlli disponibili.
- **Aggiungi questionario esistente** - Aggiungere una riga vuota alla griglia. È quindi possibile assegnare un questionario esistente impostando i campi nella tabella seguente.
- **Copia** - Aggiungere una copia della riga selezionata alla griglia.
- **Elimina** - Eliminare la riga selezionata dalla griglia.

Per ogni riga che si aggiunge, impostare i seguenti campi.

| Campo | Descrizione |
| --- | --- |
| Area di processo | Selezionare l'area a cui è correlato il controllo. |
| Tipo | Selezionare se il controllo è un controllo di sistema, un controllo manuale o un elenco di controllo (questionario). |
| Nome | Se il controllo è un elenco di controllo, immettere un nome. Per i controlli di sistema e manuali, questo campo viene impostato automaticamente. |
| Descrizione | Se il controllo è un elenco di controllo, immettere una descrizione. Per i controlli di sistema e manuali, questo campo viene impostato automaticamente e la descrizione spiega lo scopo del controllo. |
| Applica controlli | Selezionare se la riga deve generare controlli di disponibilità in risposta a un nuovo prodotto rilasciato, una variante rilasciata o una versione rilasciata. |
| Esegui in | Selezionare se i controlli di disponibilità generati dalla riga si applicano a tutte le società o a una singola società. |
| Società | Se si imposta il campo **Esegui in** su *Singola società*, selezionare la società. |
| Tipo di proprietario | Seleziona se i controlli di disponibilità generati dalla riga devono essere assegnati a una persona o a un team. |
| Proprietario | Seleziona la persona o il team a cui devono essere assegnati i controlli di disponibilità generati dalla riga. |
| Gestione questionari | Seleziona il questionario da utilizzare per l'elenco di controllo. L'elenco di controllo è un elenco di controllo locale nella società in cui viene effettuato il controllo di disponibilità. Il sistema deve essere in grado di valutare se l'elenco di controllo ha una risposta corretta. Pertanto, l'elenco di controllo deve essere impostato in modo che venga eseguita una valutazione basata su risposte corrette. Per ulteriori informazioni su come creare questionari, vedi [Utilizzo dei questionari](/dynamicsax-2012/appuser-itpro/using-questionnaires) e gli articoli correlati. |
| Approvazione automatica | I record del controllo di disponibilità includono una casella di controllo **Approvato** che indica lo stato di approvazione. Selezionare la casella di controllo **Approvazione automatica** per i controlli che devono essere impostati su approvato immediatamente dopo essere stati completati dall'utente assegnato. Deselezionare questa casella di controllo per richiedere l'approvazione esplicita come passaggio aggiuntivo. |
| Obbligatorio | Selezionare questa casella di controllo per i controlli che devono essere completati dall'utente assegnato. I controlli obbligatori non possono essere ignorati. |

<a name="assign-policy"></a>

## <a name="assign-readiness-policies-to-standard-and-engineering-products"></a>Assegnare criteri di disponibilità a prodotti standard e tecnici

Quando crei un nuovo prodotto basato su una categoria tecnica, crei sia un *prodotto rilasciato* che un relativo *prodotto condiviso*. Il modo in cui i criteri di disponibilità vengono risolti per un prodotto rilasciato dipende dall'attivazione della funzionalità *Controlli di disponibilità prodotto* per il sistema (vedi la sezione [Controlli di disponibilità su prodotti standard](#standard-products) più avanti in questo articolo per dettagli su questa funzionalità e su come attivarla o disattivarla).

- Quando la funzionalità *Controlli di disponibilità del prodotto* viene *disattivata* sul tuo sistema, il criterio di disponibilità è impostato e mostrato solo sui record [categoria di ingegneria](engineering-versions-product-category.md). Per sapere quale criteri si applica a un prodotto rilasciato, il sistema controlla il campo **Criterio di disponibilità del prodotto** per la categoria di progettazione correlata. È possibile modificare il criterio di disponibilità per un prodotto esistente modificando la categoria di progettazione correlata (non il prodotto condiviso).
- Quando la funzionalità *Controlli di disponibilità del prodotto* è *attivata*, aggiunge un campo **Criterio di disponibilità** alla pagina **Prodotto** (dove sono impostati i prodotti condivisi) e alla pagina **Prodotto rilasciato** (dove il valore è di sola lettura ed è preso dal prodotto condiviso correlato). Il sistema trova il criterio di disponibilità per un prodotto rilasciato controllando il prodotto condiviso correlato. Quando si utilizza una categoria di progettazione per creare un nuovo prodotto di progettazione, il sistema crea sia un prodotto condiviso che un prodotto rilasciato e copia qualsiasi impostazione **Criterio di disponibilità del prodotto** per la categoria di progettazione sul nuovo prodotto condiviso. È possibile modificare il criterio di disponibilità per un prodotto esistente modificando il relativo prodotto condiviso (non la categoria di progettazione rilasciata).

Per assegnare un criterio di disponibilità a un prodotto condiviso, attenersi alla procedura seguente.

1. Vai a **Informazioni sul prodotto \> Prodotti \> Prodotti**.
1. Apri o crea il prodotto a cui desideri assegnare un criterio di disponibilità.
1. Nella Scheda dettaglio **Generale**, imposta il campo **Criterio di disponibilità del prodotto** sul nome del criterio da applicare al prodotto.

Per assegnare un criterio di disponibilità a una categoria di progettazione, attenersi alla procedura seguente.

1. Vai a **Gestione modifiche di progettazione \> Configura \> Dettagli categoria prodotti di progettazione**.
1. Apri o crea la categoria di progettazione a cui desideri assegnare un criterio di disponibilità.
1. Nella Scheda dettaglio **Criterio di disponibilità del prodotto**, imposta il campo **Criterio di disponibilità del prodotto** sul nome del criterio da applicare alla categoria di progettazione.

<a name="standard-products"></a>

## <a name="readiness-checks-on-standard-products"></a>Controlli di disponibilità su prodotti standard

È possibile abilitare i controlli di disponibilità del prodotto per i prodotti standard (non tecnici) attivando la funzionalità *Controlli di disponibilità del prodotto* in Gestione funzionalità. Questa funzionalità apporta alcune piccole modifiche al sistema di controllo della disponibilità in modo che supporti i prodotti standard.

### <a name="enable-or-disable-readiness-checks-on-standard-products"></a>Abilitare o disabilitare controlli di disponibilità su prodotti standard

Questa funzionalità richiede che entrambe le funzionalità *Gestione modifiche di progettazione* e *Controlli di disponibilità prodotto* siano attivate per il sistema. Per dettagli su come attivare o disattivare queste funzionalità, vedere [Panoramica della gestione delle modifiche di progettazione](product-engineering-overview.md).

### <a name="create-readiness-policies-for-standard-products"></a>Creare criteri di disponibilità per i prodotti standard

Crei criteri di disponibilità per i prodotti standard proprio come fai per i prodotti di progettazione. Vedi le informazioni in precedenza nell'articolo.

### <a name="assign-readiness-policies-to-standard-products"></a>Assegnare criteri di disponibilità ai prodotti standard

Per assegnare un criterio di disponibilità a un prodotto standard, apri il prodotto condiviso correlato e imposta il campo **Criterio di disponibilità del prodotto** sul nome del criterio da applicare. Per ulteriori informazioni, vedi la sezione [Assegnare criteri di disponibilità a prodotti standard e tecnici](#assign-policy) precedente in questo articolo.

### <a name="view-and-process-readiness-checks-on-standard-products"></a>Visualizzare ed elaborare i controlli di disponibilità su prodotti standard

Quando questa funzionalità è attiva, puoi visualizzare ed elaborare i controlli di disponibilità per i prodotti standard proprio come si fa per i prodotti di progettazione. Vedi le informazioni in precedenza nell'articolo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
