---
title: Creare direttive di ubicazione
description: In questo argomento viene illustrato come creare le direttive ubicazione. Le direttive ubicazione sono regole definite dall'utente che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte.
author: Mirzaab
manager: tfehr
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-28
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: bdd99b5faefd7054023b45a91fad070aac055a26
ms.sourcegitcommit: ecad92c9cb7e9e57688e678f79f747673c921df5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "3692140"
---
# <a name="create-location-directives"></a>Creare direttive di ubicazione

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come creare le direttive ubicazione. Le direttive ubicazione sono regole definite dall'utente che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte. Ad esempio, per una transazione dell'ordine cliente, la direttiva ubicazione determina il punto di prelievo e il punto di stoccaggio degli articoli.

> [!NOTE]
> Questo argomento si applica alle funzionalità nel modulo **Gestione magazzino**. Non viene applicato alle funzionalità nel modulo [Gestione inventario](../inventory/inventory-home-page.md).

È possibile utilizzare le direttive ubicazione per effettuare le seguenti attività:

- Stoccare gli articoli in arrivo.
- Prelevare e stoccare gli articoli per le transazioni in uscita.
- Prelevare e stoccare le materie prime per la produzione.
- Rifornire le ubicazioni.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter creare una direttiva di ubicazione, è necessario seguire questi passaggi per assicurarsi che i prerequisiti siano presenti.

1. Selezionare **Gestione magazzino \> Impostazioni \> Magazzino \> Magazzini**.
1. Creare un magazzino.
1. Nella scheda **Magazzino**, impostare l'opzione **Usa processi di gestione magazzino** su *Sì*.
1. Creare le ubicazioni, i tipi di ubicazione, i profili e i formati delle ubicazioni. Per ulteriori informazioni, vedere [Configurare le ubicazioni in un magazzino abilitato WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Creare siti, zone e gruppi di zone. Per ulteriori informazioni, vedere [Impostare un magazzino](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) e [Configurare le ubicazioni in un magazzino abilitato WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="setup"></a>Attrezzaggio

### <a name="create-location-directives"></a>Creare direttive di ubicazione

Per creare una direttiva ubicazione, completare i passaggi seguenti.

1. Andare a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel riquadro elenco, impostare il campo **Tipo di ordine di lavoro** sul tipo di transazione di inventario per cui stai creando una direttiva di ubicazione.
1. Nel riquadro azioni, seleziona **Nuova** per creare una direttiva di ubicazione.
1. Per la nuova direttiva di ubicazione, impostare i campi come descritto nella tabella seguente.

    | Campo | descrizione |
    |---|---|
    | Numero progressivo | Immettere un numero intero che indichi l'ubicazione della sequenza della direttiva di ubicazione. Le ubicazioni della sequenza determinano quando ciascuna direttiva di ubicazione viene elaborata per il tipo di ordine di lavoro selezionato. |
    | Nome | Immettere un nome per la direttiva ubicazione. | 
    | Tipo di lavoro | Selezionare il tipo di lavoro da eseguire. L'elenco di valori dipende dal tipo di transazioni di inventario selezionato nel campo **Tipo ordine di lavoro**. Potrebbero essere disponibili i valori seguenti:<ul><li>**Inserisci**: la direttiva ubicazione cercherà di trovare la posizione migliore in cui posizionare o individuare le scorte che entrano nel sistema attraverso la ricezione, la produzione o le correzioni delle scorte. La direttiva ubicazione viene utilizzata anche per definire l'ubicazione di stoccaggio o l'ubicazione di spedizione al portellone finale nel flusso in uscita.</li><li>**Preleva**: la direttiva ubicazione proverà a trovare le ubicazioni migliori da cui prenotare fisicamente le scorte (creare lavoro). Il prelievo può essere completato (la riga di lavoro di prelievo può essere chiusa) anche se il lavoro non è completato. L'utente può completare il prelievo fisico. Nel sistema, quell'azione è un passaggio di prelievo. L'utente può quindi annullare dal dispositivo mobile e completare il lavoro in un secondo momento (ad esempio). Tuttavia, l'intestazione del lavoro viene chiusa innanzitutto quando viene completato l'inserimento finale.</li><li>**Conteggio**, **Rettifiche**, **Personalizzato**, **Modifica stato magazzino**, **Compilazione targa**, **Stampa**, **Modifica statoe** e **Imballa in targhe nidificate** : questi valori non possono essere utilizzati in alcuna configurazione di direttiva ubicazione.</li></ul> |
    | Sito | Selezionare il sito in cui il lavoro deve essere completato. |
    | Magazzino | Selezionare l'ubicazione magazzino in cui il lavoro deve essere completato. |
    | Codice direttiva | Selezionare un codice direttiva per guidare la selezione delle direttive di localizzazione relative alle righe di inserimento del modello di lavoro a cui questo codice è assegnato. Nella pagina **Codice direttiva**, è possibile creare nuovi codici che possono essere utilizzati per collegare un modello di lavoro a una direttiva ubicazione. È inoltre possibile utilizzare la pagina per impostare il collegamento tra una qualsiasi riga del modello di lavoro e una direttiva ubicazione (ad esempio il portellone o l'ubicazione di gestione temporanea). Per ulteriori informazioni su come configurare un codice direttiva con un modello di lavoro, vedere [Controllo del lavoro di magazzino con modelli di lavoro e direttive di ubicazione](control-warehouse-location-directives.md).<p>Se il codice direttiva è impostato, quando il lavoro deve essere generato, il sistema cercherà le direttive ubicazione non in base al codice della direttiva ma in base alla sequenza. In questo modo, è possibileessere più precisi riguardo il modello di ubicazione utilizzato per un passaggio specifico in un modello di lavoro, ad esempio la gestione temporanea dei materiali.</p> |
    | Codice smaltimento | Selezionare un codice smaltimento per cambiare il percorso per lo stoccaggio degli articoli ricevuti. (Per ulteriori informazioni, vedere [Impostare codici di smaltimento](tasks/set-up-dispositions-codes.md)). Questo campo è disponibile solo quando il campo **Tipo di ordine di lavoro** è impostato su *Ordini fornitore*, *Ordini di reso* o *Stoccaggio dei prodotti finiti*. |
    | Più SKU | Selezionare questa opzione su *Sì* per utilizzare più unità SKU su un'ubicazione. Ad esempio, questa opzione deve essere impostata su *Sì* per il portellone.<p>Se l'opzione **Più SKU** è impostata su *Sì*, l'ubicazione di stoccaggio verrà specificata nel lavoro (come previsto). Tuttavia, l'ubicazione di stoccaggio sarà in grado di gestire più articoli solo se il lavoro include diverse unità SKU che devono essere prelevate e stoccate, non se il lavoro include solo una singola SKU che deve essere inserita.</p><p>Se l'opzione **Più SKU** è impostata su *No*, l'ubicazione di stoccaggio verrà specificata solo se lo stoccaggio ha un unico tipo di SKU.</p><p>Per utilizzare entrambi gli approcci, è necessario specificare due linee che hanno la stessa struttura e impostazione, ma impostare l'opzione **Più SKU** su *Sì* per una delle righe e su *No* per le altre. In altre parole, sono necessarie due direttive ubicazioni identiche per le operazioni di stoccaggio, anche se non si fa distinzione tra più SKU o una singola SKU nell'ID lavoro. È inoltre necessario impostare una direttiva ubicazione, se si dispone di un ordine con più articoli.</p><p>**Nota:** se si utilizza l'opzione **Più SKU** impostata su *Sì* per una direttiva ubicazione del tipo di lavoro *Inserisci*, il sistema selezionerà sempre la prima riga direttiva ubicazione indipendentemente da altre restrizioni create nelle righe.</p> |

1. Facoltativo: nel riquadro azioni, selezionare **Modifica query** per selezionare le ubicazioni o per specificare qualsiasi restrizione che si applica quando si seleziona una specifica direttiva ubicazione.
1. Nella scheda **Righe**, creare una o più righe per specificare le unità e per individuare o prenotare la quantità in un magazzino.
1. Su ciascuna riga, impostare i campi come descritto nella tabella seguente.

    | Campo | descrizione |
    |---|---|
    | Numero progressivo | Immettere un numero intero che indichi l'ubicazione della sequenza della direttiva di ubicazione. Le ubicazioni della sequenza determinano quando ciascuna direttiva di ubicazione viene elaborata per il tipo di lavoro selezionato. |
    | Da quantità | Specificare l'intervallo di quantità iniziale per quando deve essere selezionata la sequenza di griglia intermedia. Specificare la quantità in unità di misura selezionata nel campo **Unità**. |
    | A quantità | Specificare l'intervallo di quantità finale per quando deve essere selezionata la sequenza di griglia intermedia. Specificare la quantità in unità di misura selezionata nel campo **Unità**. |
    | Unità | Selezionare l'unità di misura per gli articoli.<p>È possibile specificare una quantità minima e una quantità massima a cui deve essere applicata la direttiva. È inoltre possibile specificare che la direttiva deve essere utilizzata per un'unità di magazzino specifica. Il campo **Unità** nella riga viene utilizzato solo per valutare le quantità.</p><p>Per determinare se si applica una riga della direttiva ubicazione, il sistema valuta le quantità utilizzando il valore **Unità** specificato sulla riga. Ogni volta che si accede a una riga della direttiva ubicazione, il sistema tenterà di convertire l'unità della domanda all'unità specificata nella riga. Se la conversione delle unità non esiste, il sistema passerà alla riga successiva.</p> |
    | Trova quantità | Questo campo è valido solo quando si tenta di inserire o individuare la quantità nel magazzino. In altre parole, è valido solo per il lavoro *Inserisci*. Selezionare il metodo utilizzato per valutare se la quantità rientra nell'intervallo impostato nei campi **Da quantità** e **A quantità**. Se la direttiva ubicazione è per una transazione in entrata, selezionare una delle seguenti opzioni:<ul><li>**Quantità targa**: per valutare se una quantità è compresa nell'intervallo delle quantità di destinazione, usare la quantità sulla targa ricevuta.</li><li>**Quantità in unità**: per valutare se la quantità è compresa nell'intervallo delle quantità di destinazione, usare la quantità in unità durante la transazione. Ad esempio, se in un magazzino è possibile ricevere una quantità pari a 1.000 e suddividerla in 10 targhe di 100 ciascuna, è possibile utilizzare una quantità pari a 1.000 articoli anziché la quantità di targa di 100.</li><li>**Quantità rimanente**: per valutare se una quantità rientra nell'intervallo di quantità di destinazione, utilizzare la quantità rimanente nella riga dell'ordine fornitore che attualmente viene archiviata.</li><li>**Quantità prevista**: per valutare se una quantità rientra nell'intervallo di destinazione, utilizzare la quantità totale della riga dell'ordine fornitore, indipendentemente dalla quantità già ricevuta.</li></ul> |

1. Facoltativo: sulla scheda **Righe**, è possibile impostare i campi aggiuntivi seguenti.

    | Campo | descrizione |
    |---|---|
    | Limita per unità | Selezionare questa casella di controllo per limitare le unità di misura considerate criteri di selezione validi per le righe della direttiva ubicazione. Quando sono state specificate le unità di misura, solo le voci in cui l'unità corrisponde ad almeno un'unità definita per il gruppo di sequenze delle unità saranno considerate valide per la selezione della riga.<p>Ad esempio, l'unità è limitata ai pallet e l'articolo è associato a un gruppo di sequenze di unità che include l'unità *pallet*. In questo caso, gli articoli saranno considerati un'opzione valida per la direttiva ubicazione.</p><p>Tuttavia, la casella di controllo **Limita per unità** non controlla l'unità o le unità applicate alle righe di lavoro. La restrizione delle unità si applica solo alle unità rese disponibili tramite il gruppo di sequenze delle unità.</p><p>Ad esempio, un'unità è associata a un gruppo di sequenze di unità che include le unità *pallet* e *pz*. È stata definita un'unità di misura dove 1 pallet = 100 pezzi e la direttiva ubicazione utilizza lafunzione **Limita per unità** solo per i pallet. Inoltre, è stato definito un modello di lavoro che limita la creazione dell'intestazione di lavoro a 50 pezzi. In questo caso verranno create righe di lavoro da 50 pz.</p><p>Seguire questi passaggi per specificare l'unità di misura per la restrizione</p><ol><li>Nella scheda **Righe**, selezionare **Limita per unità**. Questo pulsante diventa disponibile solo dopo aver selezionato la casella di controllo **Limita per unità** sulla riga, quindi selezionare **Salva**.</li><li>Nel campo **Unità** selezionare l'unità di misura per limitare i processi di prelievo e stoccaggio.</li></ol> |
    | Arrotonda a unità | Selezionare questa opzione per indicare se il prelievo di materie prime viene arrotondato per eccesso a un multiplo dell'unità movimentazione specificata nella campo **Limita per unità**. Questo campo si applica solo a al prelievo di materie prime e alle direttive ubicazione di tipo *Prelievo*. |
    | Individua quantità di imballaggio | Selezionare questa casella di controllo se nella pagina **Ordine cliente** è specificata una quantità di unità di imballaggio. Se si seleziona questa casella di controllo, solo le ubicazioni con questa quantità di unità di imballaggio verranno selezionate. |
    | Consenti divisione | Selezionare questa casella di controllo per suddividere la quantità tra più ubicazioni. |
    | Modello per il rifornimento immediato | Creare una connessione a un modello di rifornimento per iniziare immediatamente il rifornimento se gli articoli non sono allocati. Se il campo viene lasciato vuoto, il rifornimento degli articoli non inizierà fino all'elaborazione di tutte le righe della direttiva ubicazione.<p>Questo campo è disponibile solo su tipi di ordine di lavoro selezionati in cui è consentito il rifornimento, ad esempio *Ordini cliente* e *Prelievo materie prime*.</p> |

1. Nella scheda **Azioni direttiva ubicazione**, selezionare **Nuovo** per selezionare la posizione o l'intervallo delle ubicazioni.
1. Il campo **Numero progressivo** mostra la sequenza in cui verrà elaborata la direttiva ubicazione per il tipo di lavoro selezionato. È possibile modificare la sequenza. Tuttavia, prestare attenzione ai numeri progressivi per le azioni della direttiva ubicazione, perché le azioni della direttiva ubicazione verranno sempre eseguite in questa sequenza.
1. Nel campo **Nome** immettere il nome e il percorso per l'azione della direttiva ubicazione. Essere specifici, in modo che sia chiaro qual è l'azione.
1. Facoltativo: selezionare **Modifica query** per modificare le ubicazioni di magazzino e altri criteri.
1. Facoltativo: è possibile impostare i seguenti campi aggiuntivi per una direttiva ubicazione.

    | Campo | descrizione |
    |---|---|
    | Utilizzo ubicazioni fisse | Selezionare le ubicazioni considerate dalla direttiva ubicazione:<ul><li>**Posizioni fisse e non fisse**: la direttiva ubicazione considererà tutte le ubicazioni.</li><li>**Solo ubicazioni fisse per il prodotto**: la direttiva ubicazione considererà solo le ubicazioni fisse per i prodotti.</li><li>**Solo ubicazioni fisse per la variante prodotto**: la direttiva ubicazione considererà solo le ubicazioni fisse per le varianti prodotti.</li></ul> |
    | Consenti inventario negativo | Selezionare questa casella di controllo per consentire scorte negative degli articoli nell'ubicazione di magazzino specificata. |
    | Batch abilitato | Selezionare questa casella di controllo per utilizzare le strategie batch per gli articoli che vengono abilitati per il batch. Se questa casella di controllo è selezionata e il campo **Strategia** è impostato su *Nessuna*, il sistema passerà alla successiva riga dell'azione. |
    | Strategia | Selezionare la strategia che la direttiva ubicazione dovrebbe utilizzare:<ul><li>**Nessuna** - Non verrà utilizzata alcuna strategia.</li><li>**Corrispondenza quantità imballaggio** - Questa strategia consente di verificare se un'ubicazione di prelievo dispone della quantità di imballaggio specificata. Questa strategia è valida solo quando il campo **Tipo di lavoro** è impostato su *Preleva*.</li><li>**Consolidato** - Questa strategia consente di consolidare gli articoli in un'ubicazione specifica quando articoli simili sono già disponibili. Questa strategia è valida solo quando il campo **Tipo di lavoro** è impostato su *Inserisci*. In una configurazione tipica di stoccaggio, il sistema tenta di consolidare la prima riga dell'azione, quindi, la seconda riga dell'azione, tenta di inserire senza consolidamento. Il consolidamento delle merci rende più efficiente il prelievo in un secondo momento.</li><li>**Prenotazione batch FEFO** - Questa strategia viene utilizzata quando il magazzino viene individuato utilizzando una data di scadenza batch e viene allocato per la prenotazione batch. La strategia di prenotazione batch FEFO (First Expired, First Out) viene inoltre utilizzata quando le scorte vengono individuate utilizzando una data di consumo consigliata per il batch oltre alla data di scadenza. È possibile utilizzare questa strategia solo per gli articoli abilitati per il batch. Questa strategia è valida solo quando il campo **Tipo di lavoro** è impostato su *Preleva*. Quando si seleziona questa strategia, si sovrascrive qualsiasi ordinamento di query per i numeri di batch applicati.</li><li>**Arrotonda per eccesso alla targa completa** - Questa strategia consente di arrotondare la quantità di scorte da abbinare alla quantità di targa assegnata agli articoli da prelevare. Questa strategia può essere utilizzata solo per il tipo di rifornimento delle direttive di ubicazione e solo quando il campo **Tipo di lavoro** è impostato su *Preleva*.</li><li>**Ubicazione vuota senza alcun lavoro in entrata** - Questa strategia viene utilizzata per individuare le ubicazioni vuote. Un'ubicazione viene considerata vuota se non è presente un inventario fisico e non è previsto lavoro in entrata. Questa strategia è valida solo quando il campo **Tipo di lavoro** è impostato su *Inserisci*.</li></ul> |

## <a name="example-of-the-use-of-location-directives"></a>Esempio di utilizzo delle direttive ubicazione

Per questo esempio, considerare un processo di ordine fornitore in cui la direttiva ubicazione deve individuare capacità libera all'interno di un magazzino per gli articoli di magazzino registrati immediatamente alla banchina di entrata. Innanzitutto, occorre cercare capacità libera all'interno del magazzino consolidando le scorte disponibili esistenti. Se il consolidamento non è possibile, occorre cercare di individuare un'ubicazione vuota.

Per questo scenario, è necessario definire due azioni di direttiva ubicazione. La prima azione nella sequenza deve utilizzare la strategia **Consolida** e la seconda deve utilizzare la strategia **Ubicazione vuota senza alcun lavoro in entrata**. A meno che non si definisca una terza azione per gestire uno scenario di overflow, sono possibili due risultati in caso non vi sia più capacità in magazzino: il lavoro può essere creato anche se non è definita un'ubicazione o il processo di creazione di lavoro può interrompersi. Il risultato viene determinato dall'impostazione nella pagina **Errori direttiva ubicazione**, in cui è possibile decidere se selezionare l'opzione **Interrompi lavoro in caso di errore direttiva ubicazione** per ogni tipo di ordine di lavoro.

## <a name="next-step"></a>Passaggio successivo

Una volta create le direttive ubicazione, è possibile associare ciascun codice di direttiva a un codice di modello di lavoro per la creazione del lavoro. Per ulteriori informazioni, vedere [Rifornimento e Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="technical-information-for-system-admins"></a>Informazioni tecniche per gli amministratori di sistema

Se non si ha accesso alle pagine utilizzate per completare questa attività, contattare l'amministratore di sistema e fornire le informazioni indicate nella tabella che segue.

| Categoria | Prerequisito |
|---|---|
| Chiavi di configurazione | Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**. Espandere il codice di licenza **Commerciale** e selezionare la chiave di configurazione **Gestione magazzino e trasporto**. |
