---
title: Versioni di progettazione e categorie di prodotti di progettazione
description: Questo argomento fornisce informazioni sul concetto di versioni di progettazione. Le versioni di progettazione garantiscono che i diversi stati di un prodotto e dei dati siano aggiornati e cancellati e che possano essere visualizzati nel sistema.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgLookupDynastring, EngChgProductVersionNumberRule, EngChgEcmProductRoute, EngChgEcmRequestProducts, EngChgEcmProductRoute, EngChgEcmProductPreview,EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmProductCreate, EngChgEcmProductLookup, EngChgProductVersionPrCompany, ngChgProductTypeLookup, EngChgProductType, EngChgProductItemPart, EngChgProductItem, EngChgEcmCategory, EngChgEcmBomDesignerEditBom, EngChgEcmBomDesigner, EngChgEcmBOMCopyDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 18f187ef6805b8d2bfe777aaad54ad2cf0fb0d71a981c5b02932f3cccf2404e9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776412"
---
# <a name="engineering-versions-and-engineering-product-categories"></a>Versioni di progettazione e categorie di prodotti di progettazione

[!include [banner](../includes/banner.md)]

I prodotti di progettazione si evolvono durante il loro ciclo di vita del prodotto, per molte ragioni. Ad esempio, potrebbero essere introdotte modifiche per migliorare la funzionalità del prodotto, cambiare un componente perché il fornitore non lo offre più, rispondere a nuove informazioni dettagliate o correggere errori nella progettazione iniziale. Ci sono anche molte ragioni per cui queste modifiche devono essere memorizzate come parte di un prodotto in corso, in modo tale che i dati precedenti non vengano sovrascritti. Di seguito sono riportate alcune motivazioni:

- Si desidera tenere traccia del prodotto così come è stato fabbricato e consegnato ai clienti negli stati del ciclo di vita precedenti.
- È necessario un lead time prima di approvare e applicare le modifiche.
- È necessario un timestamp su ogni modifica e consegnare i prodotti fabbricati in precedenza separatamente l'uno dall'altro.

Le *versioni di progettazione* garantiscono che i vari stati di un prodotto e dei dati siano aggiornati e cancellati e che possano essere visualizzati nel sistema. Questo concetto consente di mantenere la coerenza, bloccare la distinta base (BOM) per la produzione, eliminare la variabilità e identificare facilmente le modifiche.

In generale, la regola *forma-adattamento-funzione* viene applicata per determinare se una modifica richiede un nuovo prodotto, una nuova versione o un aggiornamento a una versione esistente. Ciascuno dei tre termini nel nome di questa regola si riferisce a un aspetto specifico di una parte, che aiuta i tecnici ad abbinare le parti alle esigenze. La regola forma-adattamento-funzione aumenta la flessibilità delle modifiche al progetto, poiché per modificare una parte sono necessari documentazione e costi di progettazione minimi, a condizione che vengano mantenuti adattamento, forma e funzione del prodotto.

- **Adattamento** si riferisce alla capacità della parte o funzione di connettersi, abbinarsi o unirsi a un'altra funzione o parte in un assieme. L'adattamento consente alla parte di soddisfare le tolleranze di assemblaggio richieste in modo da tornare utile.
- **Forma** si riferisce alle caratteristiche di una parte o di un assembly, come le dimensioni esterne, il peso, le dimensioni e l'aspetto visivo. La forma è l'aspetto che più risente delle scelte estetiche di un tecnico. Comprende la chiusura, lo chassis e il pannello di controllo, che diventano la "faccia" esterna del prodotto.
- **Funzione** è un criterio che viene soddisfatto quando la parte esegue efficacemente e in modo affidabile lo scopo dichiarato. Ad esempio, in un prodotto elettronico, la funzione può dipendere dai componenti stato solido utilizzati e dal software o firmware. Spesso può dipendere anche dalle funzionalità della chiusura selezionata. Due dei motivi più comuni per cui una chiusura può non soddisfare il criterio di funzione sono le porte posizionate in modo errato o di dimensioni insufficienti e l'etichettatura fuorviante o mancante. 

## <a name="engineering-versions"></a>Versioni di progettazione

Quando si utilizzano prodotti di progettazione, ogni prodotto ha almeno una versione di progettazione. La versione di progettazione iniziale viene creata automaticamente quando si crea un prodotto di progettazione. Ogni versione di progettazione memorizza i dati rilevanti per la progettazione specifici per quella versione. Di seguito sono riportati alcuni esempi di questi dati:

- Il numero di versione e il numero di versione precedente (se applicabile)
- Le date di inizio validità e di fine validità
- Lo stato attivo della versione del prodotto, che indica se la versione può essere rilasciata e utilizzata nelle transazioni (per ulteriori informazioni, vedere [Preparazione del prodotto](product-readiness.md)).
- La società di progettazione che ha creato ed è proprietaria del prodotto (per ulteriori informazioni, vedere [Società di progettazione e regole della proprietà dei dati](engineering-org-data-ownership-rules.md)).
- Documenti di progettazione correlati, come un manuale di assemblaggio, istruzioni per l'utente, immagini e collegamenti
- Gli attributi di progettazione (per ulteriori informazioni, vedere [Attributi di progettazione e ricerca di attributi di progettazione](engineering-attributes-and-search.md).)
- Distinta base (BOM) per prodotti di progettazione
- Formule per prodotti di processi di produzione
- I cicli di lavorazione di progettazione

È possibile aggiornare questi dati in una versione esistente o creare una nuova versione utilizzando un *ordine di modifica di progettazione*. Per ulteriori informazioni, vedere [Gestire le modifiche ai prodotti di progettazione](engineering-change-management.md). Se si crea una nuova versione di un prodotto, il sistema copia tutti i dati rilevanti per la progettazione in quella nuova versione. È quindi possibile modificare i dati per quella nuova versione. In questo modo, è possibile tenere traccia di dati specifici per ogni versione consecutiva. Per confrontare le differenze tra versioni di progettazione consecutive, ispezionare l'ordine di modifica di progettazione, che include i tipi di modifica che indicano tutte le modifiche.

Come già indicato, la versione di progettazione iniziale viene creata automaticamente quando si crea un prodotto di progettazione. Il numero di versione per questa versione segue la regola del numero di versione definita nella categoria di progettazione per il prodotto. Per passare a una versione successiva, è necessario aggiungere il prodotto a un ordine di modifica di progettazione come riga e impostare Il campo **Impatto** su *Nuova versione*. L'ordine di modifica di progettazione includerà i dettagli della modifica dalla versione corrente a quella successiva.

Tenere presente che un prodotto di progettazione può essere incluso in un solo ordine di modifica di progettazione alla volta. Questa restrizione garantisce l'accuratezza dei dati e aiuta a evitare modifiche sovrapposte o contraddittorie nel prodotto. Si noti inoltre che il campo **Tecnico** nella visualizzazione **Intestazione** dell'ordine di modifica di progettazione mostra il tecnico responsabile dell'ordine di modifica. Se il tecnico appartiene a un team definito nel sistema, il campo **Responsabile** mostra il leader di tale team.

## <a name="track-versions-in-transactions"></a>Tenere traccia delle versioni nelle transazioni

Quando si utilizza la gestione delle modifiche di progettazione, i dati di rappresentazione generale prodotto includono sempre una o più versioni di progettazione. Nella configurazione dei prodotti di progettazione, è possibile scegliere se la versione di progettazione fa anche parte di *transazioni logistiche*. Per ulteriori informazioni, vedere la sezione [Impostare le categorie di prodotti di progettazione](#product-category) più avanti in questo argomento. Se l'impatto logistico è rilevante, differisce per prodotto e per azienda. A volte viene utilizzata solo l'ultima versione di un prodotto. Pertanto, quando si introduce una nuova versione, la versione precedente non può più essere utilizzata. In altri casi, la versione precedente è richiesta nelle transazioni logistiche per superare le seguenti sfide:

- Il reparto Logistica deve spedire due pezzi di un prodotto a un cliente. In questo caso, è necessario decidere se si desidera o consentire la spedizione di due versioni diverse.
- Successivamente viene scoperto che si verifica un problema e che è correlato a una modifica specifica. In questo caso, potrebbe essere utile determinare esattamente quale versione è stata spedita in ogni ordine.
- Le aziende in genere vogliono prima spedire le vecchie versioni, per eliminarle gradualmente dall'inventario. Soprattutto per i prodotti a basso volume, questo approccio può spesso essere gestito determinando le date di validità della nuova versione in relazione alle previsioni su quando le scorte della vecchia versione saranno esaurite. Tuttavia, a volte potrebbe non essere possibile fare questo confronto o considerare l'incertezza delle previsioni sul livello delle scorte troppo alta.

La decisione se rendere visibili le versioni nell'inventario dipende da fattori come quelli menzionati in precedenza, oltre alle procedure aziendali e ad altre considerazioni specifiche di ciascuna azienda. È possibile specificare il comportamento per la *categoria di prodotto di progettazione*. Verrà quindi applicato a tutti i prodotti creati da quella categoria, per tutte le aziende a cui il prodotto viene rilasciato.

Per i prodotti impostati in modo da avere un impatto logistico, la versione di progettazione deve essere specificata in ogni transazione. Sebbene il sistema proporrà l'*ultima versione attiva*, è possibile selezionare tra tutte le versioni attive disponibili per l'azienda. Per i prodotti impostati in modo da non avere un impatto logistico, la versione di progettazione non è specificata nelle transazioni. Tuttavia, il sistema utilizza l'ultima versione attiva. Ad esempio, quando si aggiunge un prodotto a una distinta base di produzione, verrà utilizzata la versione più recente e quando si esegue la pianificazione generale, verrà utilizzata l'ultima versione.

## <a name="set-up-engineering-product-categories"></a><a name="product-category"></a>Impostare le categorie di prodotti di progettazione

Una categoria di prodotti di progettazione fornisce una base per la creazione di un prodotto di progettazione specifico. Ciascuna categoria stabilisce una serie di valori e criteri predefiniti. Pertanto, quando si crea un prodotto di progettazione si seleziona prima la categoria da cui crearlo.

Tenere presente che un nuovo tipo di gerarchia di categorie (*gerarchia di prodotti di progettazione*) viene impostato automaticamente. È possibile creare manualmente le categorie andando a **Gestione modifiche di progettazione \> Impostazione \> Dettagli categoria prodotti di progettazione**.

Ciascuna categoria di prodotti di progettazione stabilisce il comportamento predefinito dei prodotti di progettazione che vengono creati in base a quella categoria. Dopo aver creato un prodotto di progettazione, non è possibile modificare la sua categoria di prodotto di progettazione. Tuttavia, se si seleziona la categoria errata, è possibile eliminare il prodotto e poi ricrearlo.

Quando viene creata una categoria di prodotti di progettazione, non è possibile modificare le seguenti impostazioni:

- Società di progettazione
- Tipo di prodotto
- Sottotipo di prodotto
- Gruppo di dimensioni prodotto
- Tecnologia di configurazione
- Regola numero di versione

Altre impostazioni potrebbero ereditare i valori predefiniti impostati per la categoria di prodotto di progettazione. Tuttavia, in base alle regole di sistema, questi valori possono essere modificati.

Per utilizzare le categorie di prodotto di progettazione, andare a **Gestione modifiche di progettazione \> Impostazione \> Dettagli categoria prodotti di progettazione**. Eseguire quindi uno dei passaggi seguenti.

- Per creare una nuova categoria, selezionare **Nuovo** nel riquadro azioni, quindi impostare i campi come descritto nelle sottosezioni seguenti.
- Per modificare una categoria esistente, selezionarla nel riquadro dell'elenco, selezionare **Modifica** nel riquadro azioni, quindi impostare i campi come descritto nelle sottosezioni seguenti.
- Per eliminare una categoria esistente, selezionarla nel riquadro dell'elenco, quindi selezionare **Elimina** nel riquadro azioni.

### <a name="header"></a>Intestazione

Impostare i seguenti campi nell'intestazione di una categoria di prodotti di progettazione.

| Campo | Descrizione |
|---|---|
| Nome | Immettere un nome per la categoria di prodotti di progettazione. |
| Società di progettazione | Selezionare la società di progettazione in cui è possibile creare i prodotti in questa categoria di prodotti di progettazione e in cui verranno mantenuti. |

### <a name="details-fasttab"></a>Scheda dettaglio Dettagli

Impostare i seguenti campi nella Scheda dettaglio **Dettagli** di una categoria di prodotti di progettazione.

| Campo | Descrizione |
|---|---|
| Tipo di prodotto | Selezionare se la categoria si applica a prodotti o servizi. |
| Tipo di produzione | Questo campo viene visualizzato solo quando hai abilitato la [gestione delle modifiche alla formula](manage-formula-changes.md) nel tuo sistema. Seleziona il tipo di produzione a cui si applica questa categoria di prodotti di progettazione:<ul><li>**Elemento di pianificazione**: utilizza questa categoria di progettazione per eseguire la gestione del cambiamento di formula per gli elementi di pianificazione. Gli elementi di pianificazione utilizzano formule. Assomigliano a formule, ma vengono utilizzati per produrre solo co-prodotti e sottoprodotti, non prodotti finiti. Le formule vengono utilizzate durante la produzione di processo.</li><li>**BOM**: utilizza questa categoria di progettazione per gestire i prodotti di progettazione, che non utilizzano formule e in genere (ma non necessariamente) includono le distinte materiali.</li><li>**Formula**: utilizza questa categoria di progettazione per eseguire la gestione delle modifiche per i prodotti finiti. Questi articoli avranno una formula ma non una distinta base. Le formule vengono utilizzate durante la produzione di processo.</li></ul> |
| Peso variabile | Questa opzione viene visualizzata solo quando hai abilitato la [gestione delle modifiche alla formula](manage-formula-changes.md) nel tuo sistema. È disponibile solo quando il campo **Tipo di produzione** è impostato su *Elemento di pianificazione* o *Formula*. Imposta questa opzione su *Sì* se utilizzerai questa categoria di progettazione per gestire gli articoli che richiedono il supporto del peso variabile. |
| Tenere traccia delle versioni nelle transazioni | Selezionare se la versione del prodotto deve essere apposta su tutte le transazioni (impatto logistico). Ad esempio, se si tiene traccia della versione nelle transazioni, ogni ordine cliente mostrerà quale versione specifica del prodotto è stata venduta in quell'ordine cliente. Se non si tiene traccia della versione nelle transazioni, gli ordini cliente non mostreranno quale versione specifica è stata venduta. Invece, mostrano sempre l'ultima versione.<ul><li>Se questa opzione è impostata su *Sì*, viene creata una rappresentazione generale prodotto per il prodotto e ogni versione del prodotto sarà una variante che utilizza la dimensione del prodotto *versione*. Il campo **Sottotipo di prodotto** viene impostato automaticamente su *Rappresentazione generale prodotto* ed nel campo **Gruppo di dimensioni prodotto** è necessario selezionare un gruppo di dimensioni del prodotto in cui la dimensione *versione* è attiva. Solo gruppi di dimensioni prodotto dove *versione* è una dimensione attiva verranno mostrati. È possibile creare nuovi gruppi di dimensioni prodotto selezionando il pulsante **Modifica** (simbolo della matita).</li><li>Se questa opzione è impostata su *No*, la dimensione del prodotto *versione* non verrà utilizzata. È quindi possibile selezionare se creare un prodotto o una rappresentazione generale prodotto che utilizza le altre dimensioni.</li></ul><p>Questa opzione viene spesso utilizzata per prodotti che presentano una differenza di costo tra le versioni o per prodotti in cui si applicano condizioni diverse in relazione al cliente. Pertanto, è importante indicare quale versione è stata utilizzata in ciascuna transazione.</p> |
| Sottotipo di prodotto | Selezionare se la categoria conterrà prodotti o rappresentazioni generali prodotto. Per le rappresentazioni generali prodotto, verranno utilizzate le dimensioni del prodotto.
| Gruppo di dimensioni prodotto | L'impostazione **Tenere traccia delle versioni nelle transazioni** aiuta a selezionare il gruppo di dimensioni del prodotto. Se è stato specificato di voler tenere traccia della versione nelle transazioni, i gruppi di dimensioni prodotto in cui la dimensione *versione* è usata verranno mostrati. In caso contrario, solo gruppi di dimensioni prodotto dove la dimensione *versione* non è utilizzata verranno mostrati. |
| Stato del ciclo di vita del prodotto alla creazione | Impostare lo stato del ciclo di vita del prodotto predefinito che un prodotto di progettazione deve avere quando viene creato per la prima volta. Per ulteriori informazioni, vedere [Stati e transazioni del ciclo di vita del prodotto](product-lifecycle-state-transactions.md). |
| Regola numero di versione | Selezionare la regola del numero di versione che si applica alla categoria:<ul><li>**Manuale** - Scegliere il numero di versione per ogni nuova versione.</li><li>**Automatico** - Il sistema imposta il numero di versione, in base a un formato definito dall'utente. Quando si imposta il formato, utilizzare un segno di numero (\#) per rappresentare una cifra e qualsiasi altro carattere per rappresentare un valore costante. Ad esempio, se definisci il formato come *V-\#\#*, la prima versione sarà "V-01", la seconda versione sarà "V-02" e così via.</li><li>**Elenco** - Il sistema utilizza il numero successivo di un elenco predefinito di valori personalizzati definiti dall'utente.</li></ul> |
| Applica validità | Selezionare se le date di validità delle versioni di progettazione devono essere contigue o se possono esserci salti e sovrapposizioni. Questa impostazione influisce sul modo in cui è possibile utilizzare i campi **Valido da** e **Valido fino a** per ogni versione di progettazione in cui si applica la categoria.<ul><li>Se questa opzione è impostata su *Sì*, un valore **Valido da** deve essere specificato per ciascuna versione e non sono consentite sovrapposizioni né salti tra le versioni. L'intervallo di date per ciascuna versione di progettazione è collegato direttamente alla versione di progettazione precedente e successiva, se esistono. In questo scenario, viene sempre utilizzata la versione più recente e le versioni precedenti non vengono più utilizzate.</li><li>Se questa opzione è impostata su **No**, non ci sono restrizioni sui campi della data di validità per le versioni di progettazione e sono consentite sia le sovrapposizioni che i salti di numerazione. In questo scenario, più versioni possono essere attive contemporaneamente ed è possibile lavorare con qualsiasi versione attiva.</li></ul><p>Questa opzione influisce anche sulle distinte base e sui cicli di lavorazione collegati a una versione del prodotto. Per ulteriori informazioni, vedere la sezione [Collegare le distinte vase e i cicli di lavorazione alle versioni di progettazione](#boms-routes) più avanti in questo argomento.</p> |
| Utilizza la nomenclatura per le regole dei numeri | Impostare questa opzione su *Sì* per abilitare le regole per la definizione di un numero di prodotto utilizzando le sequenze numeriche, i nomi e i valori di attributi di progettazione e le costanti di testo come segmenti. Per creare o modificare le regole, selezionare il pulsante **Modifica**. |
| Utilizza la nomenclatura per le regole dei nomi | Impostare questa opzione su *Sì* per abilitare le regole per la definizione di un nome utilizzando i nomi di attributi di progettazione, i valori di attributo di progettazione e le costanti di testo come segmenti. Per creare o modificare le regole, selezionare il pulsante **Modifica**. |
| Utilizza la nomenclatura per le regole di descrizione | Impostare questa opzione su *Sì* per abilitare le regole per la definizione della descrizione utilizzando i nomi di attributi di progettazione, i valori di attributo di progettazione e le costanti di testo come segmenti. Per creare o modificare le regole, selezionare il pulsante **Modifica**. |

### <a name="attributes-fasttab"></a>Scheda dettaglio Attributi

Usare la griglia nella Scheda dettaglio **Attributi** per impostare gli attributi di progettazione che si applicano ai prodotti che appartengono a questa categoria. Per informazioni su come creare gli attributi di progettazione, vedere [Attributi di progettazione e ricerca di attributi di progettazione](engineering-attributes-and-search.md).

Utilizzare i pulsanti nella Scheda dettaglio **Attributi** per aggiungere, rimuovere e disporre gli attributi nella griglia.

Se si modifica la selezione degli attributi per una categoria di progettazione ed esistono già prodotti basati su quella categoria, è necessario decidere se applicare le modifiche a tali prodotti. Se si desidera che i prodotti esistenti riflettano le modifiche, selezionare **Aggiorna prodotti esistenti** nella scheda dettaglio **Attributi**.

Per ogni riga che si aggiunge alla griglia, impostare i seguenti campi.

| Campo | Descrizione |
|---|---|
| Nome | Selezionare l'attributo da aggiungere. |
| Valore | Selezionare il valore predefinito dell'attributo. |
| Obbligatorio | Per gli attributi di tipo *Booleano*, se questa opzione è impostata su *Sì*, gli utenti devono impostare l'attributo su *Sì*. Se questa opzione è impostata su *No*, gli utenti possono impostare l'attributo su *Sì* o *No*. Per altri tipi di dati, l'impostazione di questa opzione è solo a scopo informativo. |
| Attributo batch | Selezionare se l'attributo deve essere propagato tramite la funzionalità batch. |

### <a name="readiness-policy-fasttab"></a>Scheda dettaglio Criteri di preparazione

Utilizza il campo **Criteri di preparazione prodotto** per selezionare i criteri di preparazione che si applicano ai prodotti che vengono creati in base alla categoria di progettazione. Per ulteriori informazioni, vedere [Preparazione del prodotto](product-readiness.md).

> [!NOTE]
> IL campo **Criterio di disponibilità del prodotto** funziona in modo leggermente diverso se hai attivato la funzionalità *Controlli di disponibilità del prodotto* nel tuo sistema. (Questa funzionalità consente di applicare i criteri di disponibilità ai prodotti standard\[non ingegneristici\]). Per altre informazioni, vedi [Assegnare criteri di disponibilità a prodotti standard e tecnici](product-readiness.md#assign-policy).

### <a name="release-policy-fasttab"></a>Scheda dettaglio Criteri di rilascio

Utilizzare il campo **Criteri di rilascio prodotto** per selezionare i criteri di rilascio che si applicano ai prodotti che appartengono a questa categoria. Per ulteriori informazioni, vedere [Strutture di rilascio prodotti](release-product-structure.md).

## <a name="connect-boms-and-routes-to-engineering-versions"></a><a name="boms-routes"></a>Collegare le distinte vase e i cicli di lavorazione alle versioni di progettazione

L'impostazione dell'opzione **Applica validità** è importante per il collegamento di distinte base e cicli di lavorazione a ciascuna versione di progettazione. È possibile attivare più distinte base o cicli di lavorazione per ogni prodotto solo se c'è una differenza in una delle seguenti impostazioni:

- Dimensione prodotto
- Quantità
- Sito
- Date di validità

Le distinte base e i cicli di lavorazione vengono creati dalla versione di progettazione in cui si applicano. Possono essere riconosciuti dal segno di spunta nella casella di controllo **Progettazione controllata**. Quando si lavora con distinte base e cicli di lavorazione di progettazione, in genere non li si progetta utilizzando quantità diverse. Inoltre, in genere non si progettano distinte base diverse per ogni sito. Inoltre, per le distinte base e i cicli di lavorazione di progettazione, le date di validità sono sempre prese dalla versione di progettazione. Pertanto, una versione cicli di lavorazione, la sua distinta base e il suo ciclo di lavorazione avranno tutte le stesse date di validità.

Per i prodotti in cui si utilizza la dimensione del prodotto *versione* (insieme all'impatto logistico sulle transazioni), la versione viene aggiunta anche alle distinte base e ai cicli di lavorazione. Questo comportamento aiuta a differenziare le distinte base e i cicli di lavorazione di versioni consecutive, indipendentemente dall'impostazione **Applica validità**.

Per i prodotti in cui non si utilizza la dimensione del prodotto *versione* (senza l'impatto logistico sulle transazioni), la versione non viene aggiunta anche alle distinte base o ai cicli di lavorazione. Pertanto, non ci saranno differenze tra le distinte base e i cicli di lavorazione di versioni consecutive. In questo caso, consigliamo vivamente di impostare l'opzione **Applica validità** su *Sì*. In questo modo, si aiuta a prevenire la sovrapposizione delle versioni di progettazione e si può anche attivare la distinta base e il ciclo di lavorazione di una versione più recente senza dover prima disattivare la DBA e il ciclo di lavorazione della versione precedente. Se si imposti l'opzione **Applica validità** su *Sì* in questo caso, è necessario disattivare manualmente le distinte base e i cicli di lavorazione delle versioni precedenti prima di poter attivare la versione più recente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
