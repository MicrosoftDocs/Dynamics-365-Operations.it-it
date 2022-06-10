---
title: Registrazione magazzino
description: Questo argomento spiega la scheda Registrazione magazzino nella pagina Profilo registrazione inventario.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 464ffccd658003271b517038f430914fd5d8d50e
ms.sourcegitcommit: 6744cc2971047e3e568100eae338885104c38294
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2022
ms.locfileid: "8783370"
---
# <a name="inventory-posting"></a>Registrazione magazzino

La scheda **Inventario** nella pagina **Profili di registrazione inventario** viene utilizzata per controllare la modalità di registrazione delle transazioni di inventario nella contabilità generale. Le transazioni di inventario sono transazioni che non vengono create da ordini cliente, ordini fornitore o ordini di produzione. Registrano automaticamente gli aggiornamenti fisici e finanziari nell'inventario contemporaneamente. Un'eccezione sono gli ordini di trasferimento che separano gli aggiornamenti fisici e finanziari quando spedisci e ricevi l'inventario.

Nella tabella seguente sono riportati alcuni esempi di transazioni di inventario.

| Tipo di transazione | Entrata o uscita | Registrazione fisica, registrazione finanziaria o entrambe | Description |
|---|---|---|---|
| Movimento | Entrambi | Entrambi | <p>Un giornale di registrazione movimenti è un giornale di registrazione di magazzino che è possibile utilizzare per aggiungere o rimuovere scorte. Funziona come un giornale di registrazione di rettifica magazzino. Tuttavia, una differenza fondamentale è che viene specificato il conto principale che compensa l'articolo.</p><p>Il giornale di registrazione movimenti registra i saldi iniziali e le rettifiche occasionali che devono essere spese. Ad esempio, viene utilizzato quando l'inventario viene rimosso per un campione di vendita.</p><p>Quando il giornale di registrazione viene registrato, gli aggiornamenti fisici e finanziari si verificano contemporaneamente.</p><p>Le quantità positive nelle righe del giornale di registrazione rappresentano le entrate e le quantità negative rappresentano le uscite.</p> |
| Rettifica scorte | Entrambi | Entrambi | Un giornale di registrazione di rettifica magazzino viene utilizzato per aggiungere o rimuovere scorte. Non ti consente di selezionare un conto di contropartita. Solo i conti specificati nella pagina **Profilo di registrazione dell'inventario** vengono utilizzati per aggiornare il movimento di contabilità generale. |
| Trasferimento (giornale di registrazione) | Entrambi | Entrambi | <p>Un giornale di registrazione trasferimenti viene utilizzato per spostare le scorte da un'ubicazione all'altra (utilizzando le dimensioni di immagazzinamento). Aggiorna le informazioni sul prodotto in una transazione di inventario con nuove dimensioni di tracciabilità o prodotto.</p><p>Un giornale di registrazione trasferimenti crea una riga per il movimento di un articolo. Questa riga contiene i campi "da" e "a" per le dimensioni dell'inventario. Ciascuna riga in un giornale di registrazione trasferimenti crea due transazioni di inventario. Viene creata una transazione per le dimensioni inventariali "da". Rappresenta l'uscita e ha una quantità negativa. L'altra transazione viene creata per le dimensioni inventariali "a". Rappresenta l'entrata e ha una quantità positiva.</p><p>I giornali di registrazione trasferimenti potrebbero non creare un giustificativo se il movimento del magazzino è considerato un trasferimento non finanziario. Le dimensioni di magazzino che differiscono per i valori "da" e "a" non sono contrassegnate dall'opzione **Inventario finanziario** nella pagina **Gruppo di dimensioni di immagazzinamento** o **Gruppo di dimensioni di tracciabilità**. Ad esempio, se l'opzione **Inventario finanziario** non è contrassegnata sulla dimensione **Ubicazione** e sposti l'inventario da un'ubicazione a un'altra ubicazione nello stesso sito e magazzino, non viene creato alcun giustificativo.</p><p>I giornali di registrazione di trasferimento differiscono dagli ordini di trasferimento in quanto non sono presenti documenti per il movimento. L'aggiornamento viene eseguito in un'unica transazione registrando il giornale di registrazione. Al contrario, un ordine di trasferimento può generare documenti di prelievo e spedizione e richiede due aggiornamenti per elaborare la transazione.</p> |
| Spedizione ordine di trasferimento | Problema | Entrambi | <p>Quando crei un nuovo ordine di trasferimento, ogni combinazione di una riga e di una dimensione di magazzino ha due transazioni di inventario: una per la spedizione dell'ordine di trasferimento e una per la ricevuta dell'ordine di trasferimento. Quando si spedisce l'ordine di trasferimento, vengono aggiornate due transazioni di inventario e vengono create due transazioni di inventario aggiuntive per il transito delle merci, per un totale di quattro transazioni di inventario.</p><ol><li>La prima transazione di inventario viene utilizzata per rimuovere l'articolo dal magazzino e dall'ubicazione di origine. Lo stato dell'uscita di questa transazione è **Venduto** per indicare che l'articolo non è più disponibile a magazzino.</li><li>La seconda transazione di inventario viene utilizzata per aggiungere l'articolo al magazzino di transito selezionato per il magazzino da cui viene trasferito l'articolo. Lo stato di entrata di questa transazione è **Acquistato**.</li><li>La terza transazione di inventario riguarda il trasferimento dal magazzino di transito al magazzino di destinazione. Lo stato dell'uscita di questa transazione è **Fisico riservato**. Questo stato garantisce che l'articolo non possa essere consumato da un altro processo mentre è ancora in transito.</li><li>La quarta transazione di inventario riguarda il ricevimento delle merci nel magazzino di destinazione. Lo stato di entrata di questa transazione è **Ordinato**.</li></ol> |
| Ricevimento ordine di trasferimento | Ricevimento | Entrambi | Quando un ordine di trasferimento viene ricevuto nel magazzino di destinazione, lo stato dell'inventario della transazione di inventario che si trova nel magazzino di transito (numero 3 nell'esempio precedente) viene aggiornato a **Venduto** e lo stato del magazzino della transazione del magazzino di destinazione viene aggiornato su **Acquistato**. |
| Distinte base | Entrambi | Entrambi | È possibile utilizzare un giornale di registrazione distinta base (DBA) per dichiarare un prodotto come finito e utilizzare le materie prime consumate durante il processo senza utilizzare un ordine di produzione. Un giornale di registrazione DBA in genere include almeno una riga positiva per il prodotto finito e una o più righe negative per le materie prime che vengono consumate. La riga del prodotto finito è un'entrata in magazzino, mentre le righe negative sono uscite di magazzino per le materie prime. Quando si crea un giornale di registrazione DBA, la prima riga è l'intestazione DBA e le righe successive aggiunte sono le righe DBA. |
| Modifica proprietà inventario | Entrambi | Entrambi | Il giornale di registrazione modifiche proprietà inventario viene utilizzato per cambiare il proprietario dell'inventario di spedizione dal fornitore all'organizzazione. I giornali di registrazione di modifica della proprietà dell'inventario assomigliano ai giornali di registrazione di trasferimento di magazzino in quanto due transazioni di inventario sono correlate a ciascuna combinazione di riga e dimensione inventariale. Una transazione di inventario rimuove l'inventario dal fornitore nella dimensione **Proprietà** e l'altra aggiunge l'articolo alla persona giuridica nella dimensione **Proprietà**. |
| Arrivo articoli | Ricevimento | Fisica | Un giornale di registrazione arrivi articolo viene utilizzato per aggiornare lo stato di ricevimento dell'inventario su **Registrato**. Viene in genere utilizzato per la ricezione di ordini fornitore di merci e per i resi degli ordini cliente. |
| Entrata produzione | Ricevimento | Fisica | Un giornale di registrazione input di produzione è simile a un giornale di registrazione arrivi articolo. L'input di produzione viene utilizzato per ricevere i prodotti finiti da un ordine di produzione nel magazzino. Quando il giornale di registrazione viene registrato, lo stato della transazione di inventario viene aggiornato su **Registrato**. |
| Conteggio | Entrambi | Entrambi | Un giornale di registrazione di conteggio viene utilizzato per registrare la quantità di articoli che sono stati conteggiati per una specifica combinazione di dimensioni inventariali. Le transazioni di inventario vengono create quando la riga del giornale di registrazione presenta una differenza di conteggio. Una riga con una quantità conteggiata superiore provoca un'entrata in magazzino. Una riga con una quantità conteggiata inferiore provoca un'uscita dal magazzino. Le righe in cui la quantità conteggiata corrisponde alla quantità prevista non hanno transazioni di inventario. |
| Conteggio tag | Non applicabile | Non applicabile | Un giornale di registrazione di conteggio dei tag viene utilizzato per tenere traccia dei tag di inventario assegnati e utilizzati in un conteggio completo dell'inventario. È possibile utilizzare il giornale di registrazione per assegnare un numero di tag a una combinazione specifica di un articolo e una dimensione inventariale e per tenere traccia dello stato del tag durante un inventario completo. I giornali di registrazione di conteggio tag non creano transazioni di inventario. |
| Ordini di controllo qualità | Problema | Fisica | <p>Un ordine di controllo qualità viene utilizzato per registrare i risultati dei test per un determinato lotto nell'inventario. Ciascun ordine di controllo qualità è correlato a una transazione di inventario esistente o a una parte di una transazione di inventario.</p><p>Un ordine di controllo qualità genererà una nuova transazione di inventario in due situazioni:</p><ul><li>L'ordine di controllo qualità è contrassegnato come **Test distruttivo** sulla scheda **Generale**.</li><li>L'ordine di controllo qualità è contrassegnato come **Quarantena in caso di errore di convalida** sulla scheda **Generale** e il test non supera la convalida. In questo caso vengono create due transazioni di inventario. Una transazione di inventario rimuove l'articolo dalla combinazione di dimensioni inventariali e dall'ubicazione originali e l'altra aggiunge l'articolo al magazzino di quarantena.</li></ul> |
| Ordini di quarantena | Entrambi | Entrambi | <p>Le transazioni di inventario degli ordini di quarantena sono come un ordine di trasferimento. Un magazzino di quarantena viene utilizzato per tenere traccia dell'inventario. Sono presenti due transazioni di entrata e due transazioni di uscita.</p><p>Quando crei inizialmente l'ordine, vengono create due transazioni. La transazione di entrata ha lo stato **Ordinato** per il magazzino di quarantena collegato al magazzino in cui si trova l'articolo. La transazione di uscita ha lo stato **Merci ordinate in corso di consegna** per il magazzino in cui è immagazzinato l'articolo.</p><p>Quando si avvia l'ordine di quarantena, vengono create due transazioni aggiuntive e le transazioni esistenti vengono aggiornate. Lo stato della transazione di entrata per il magazzino di quarantena viene aggiornato su **Ricevuto** e lo stato della transazione di uscita per il magazzino di stoccaggio viene aggiornato su **Detratto**.</p><p>Le due nuove transazioni servono ad indicare l'eventuale ritorno al magazzino di stoccaggio. La transazione di entrata ha lo stato **Ordinato** per il magazzino di stoccaggio e tale transazione di uscita ha lo stato **Fisico riservato** per il magazzino di quarantena.</p><p>Quando si segnala un ordine di quarantena come terminato, questa operazione rappresenta l'aggiornamento fisico dell'ordine di quarantena. Lo stato del ricevimento nel magazzino di stoccaggio viene aggiornato su **Ricevuto**.</p><p>Quando si termina un ordine di quarantena, questa operazione rappresenta l'aggiornamento finanziario dell'ordine di quarantena. Lo stato delle transazioni di uscita è aggiornato a **Venduto** e lo stato delle transazioni di entrata viene aggiornato su **Acquistato**.</p><p>In alternativa, puoi eliminare l'ordine di quarantena. Questa operazione rimuove l'articolo dall'inventario. Quando elimini un ordine di quarantena, rimangono solo tre transazioni. La transazione di entrata per il magazzino di stoccaggio viene rimossa e lo stato della transazione in entrata rimanente viene aggiornato su **Acquistato**. Lo stato delle sue transazioni di uscita viene aggiornato a **Venduto**. Questa operazione è un aggiornamento fisico e finanziario per l'ordine.</p> |

## <a name="fixed-receipt-price-posting"></a>Registrazione del prezzo di entrata fisso

Il prezzo di entrata fisso ti consente di utilizzare un costo standard per un prodotto. È un'alternativa alla selezione dell'opzione **Costo standard** nella pagina **Gruppo di modelli di articoli** per un articolo. La differenza principale quando si utilizza un prezzo di entrata fisso è che il prezzo di costo attualmente configurato verrà utilizzato per l'articolo quando il ricevimento in magazzino viene registrato. Non esiste un processo di rivalutazione dei costi per un prezzo di entrata fisso. Quando viene registrato un aggiornamento finanziario, al momento della registrazione viene utilizzato il prezzo di costo corrente. Se il prezzo di costo utilizzato al ricevimento e la fattura differiscono, lo scostamento verrà registrato nei conti profitti e perdite del prezzo fisso di entrata.

Per utilizzare facoltativamente un prezzo di entrata fisso per un prodotto, è necessario completare la seguente configurazione:

- Seleziona la casella di controllo **Registra inventario fisico** nella pagina **Gruppo di modelli di articoli** per l'articolo selezionato nella riga della transazione di inventario.
- Seleziona la casella di controllo **Prezzo di entrata fisso** nella pagina **Gruppi di modelli di articoli**.
- Specifica i conti principali per i seguenti tipi di registrazione nella pagina **Profilo di registrazione inventario**:

    - Profitto sul prezzo di entrata fisso
    - Perdita sul prezzo di entrata fisso

Per ulteriori informazioni, vedi [Prezzo di entrata fisso](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="catch-weight-posting"></a>Registrazione a peso variabile

I prodotti a peso variabile sono spesso utilizzati in settori come l'industria alimentare, dove i prodotti possono variare leggermente in base al peso, alle dimensioni o a entrambi. Per i prodotti a peso variabile si utilizzano due unità di misura: un'unità di magazzino e un'unità a peso variabile. Il peso delle scorte quando entrano in un magazzino può differire dal peso quando le scorte escono dal magazzino. L'elaborazione del prodotto a peso variabile rettifica l'inventario.

In caso di variazione del peso variabile, le differenze vengono registrate nei conti specificati nei campi **Conto perdite prodotti a peso variabile** e **Conto profitti prodotti a peso variabile** della pagina **Profilo di registrazione inventario**. In genere, in entrambi i campi viene specificato lo stesso conto principale.

La tabella seguente mostra esempi dei tipi di registrazione predefiniti con conti principali e descrizioni di esempio.

- La colonna "Dare/Avere" indica se la transazione in genere registra un addebito o un credito. In alcuni casi, la transazione può registrare addebiti o crediti.
- La colonna "Conto di compensazione" indica che il tipo di registrazione è un conto di compensazione. In altre parole, l'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva.
- La colonna "P/F" indica il tipo di registrazione. "P" rappresenta la registrazione fisica e "F" rappresenta la registrazione finanziaria.
- La colonna "Segui" indica se il conto principale per un tipo di registrazione specifico è in genere uguale al conto principale per un altro tipo di registrazione. In particolare, indica il tipo di registrazione generalmente utilizzato per la registrazione.

> [!NOTE]
> I conti principali e i nomi di conti principali nella tabella sono suggerimenti. Ti consigliamo di collaborare con il tuo commercialista per determinare la configurazione migliore per le tue esigenze aziendali.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | P/F | Segui | Description |
|---|---|---|---|---|---|---|---|---|
| Conto perdite prodotti a peso variabile | 510520 | Rettifica scorte | Spese | | Numero | Entrambi | Conto profitti prodotti a peso variabile | Questo conto viene utilizzato quando si registra una transazione di inventario in cui l'importo del peso variabile è inferiore. |
| Conto profitti prodotti a peso variabile | 510520 | Rettifica scorte | Spese | | Numero | Entrambi | Conto perdite prodotti a peso variabile | Questo conto viene utilizzato quando si registra una transazione di inventario in cui l'importo del peso variabile è superiore. |

Per ulteriori informazioni sui prodotti a peso variabile, vedi [Informazioni sugli articoli a peso variabile](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.md) e [Elaborazione del prodotto a peso variabile con gestione del magazzino](/supply-chain/warehousing/catch-weight-processing.md).

## <a name="inventory-to-fixed-asset-transfer-posting"></a>Registrazione del trasferimento da magazzino a cespite

Il giornale di registrazione del trasferimento da magazzino a cespite (**Cespiti** \> **Giornali di registrazione** \> **Giornale di registrazione trasferimenti da scorte a cespiti**) viene utilizzato per spostare gli articoli fuori dall'inventario e convertirli in cespiti. Per ulteriori informazioni, vedere [Integrazione dei cespiti](/fixed-assets/fixed-asset-integration.md).

La tabella seguente mostra esempi dei tipi di registrazione predefiniti con conti principali e descrizioni di esempio.

- La colonna "Dare/Avere" indica se la transazione in genere registra un addebito o un credito. In alcuni casi, la transazione può registrare addebiti o crediti.
- La colonna "Conto di compensazione" indica che il tipo di registrazione è un conto di compensazione. In altre parole, l'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva.
- La colonna "P/F" indica il tipo di registrazione. "P" rappresenta la registrazione fisica e "F" rappresenta la registrazione finanziaria.
- La colonna "Segui" indica se il conto principale per un tipo di registrazione specifico è in genere uguale al conto principale per un altro tipo di registrazione. In particolare, indica il tipo di registrazione generalmente utilizzato per la registrazione.

> [!NOTE]
> I conti principali e i nomi di conti principali nella tabella sono suggerimenti. Ti consigliamo di collaborare con il tuo commercialista per determinare la configurazione migliore per le tue esigenze aziendali.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | P/F | Segui | Description |
|---|---|---|---|---|---|---|---|---|
| Uscita cespite | 180100 | Cespiti tangibili | Cespite | Credito | Numero | Entrambi | Non applicabile | Questo conto viene utilizzato quando si registra un inventario nel giornale di registrazione cespiti per rimuovere un articolo dall'inventario e convertirlo in un cespite. |

## <a name="moving-average-posting"></a>Registrazione della media mobile

La media mobile è un metodo di determinazione costi perpetuo basato sul principio della media. I costi sulle uscite di inventario non cambiano quando cambia il costo di acquisto. La differenza viene capitalizzata e basata su un calcolo proporzionale. L'importo che rimane viene calcolato come spesa.

La tabella seguente mostra esempi dei tipi di registrazione predefiniti con conti principali e descrizioni di esempio.

- La colonna "Dare/Avere" indica se la transazione in genere registra un addebito o un credito. In alcuni casi, la transazione può registrare addebiti o crediti.
- La colonna "Conto di compensazione" indica che il tipo di registrazione è un conto di compensazione. In altre parole, l'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva.
- La colonna "P/F" indica il tipo di registrazione. "P" rappresenta la registrazione fisica e "F" rappresenta la registrazione finanziaria.
- La colonna "Segui" indica se il conto principale per un tipo di registrazione specifico è in genere uguale al conto principale per un altro tipo di registrazione. In particolare, indica il tipo di registrazione generalmente utilizzato per la registrazione.

> [!NOTE]
> I conti principali e i nomi di conti principali nella tabella sono suggerimenti. Ti consigliamo di collaborare con il tuo commercialista per determinare la configurazione migliore per le tue esigenze aziendali.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | P/F | Segui | Description |
|---|---|---|---|---|---|---|---|---|
| Differenza di prezzo per media mobile | 510600 | Differenza di prezzo per media mobile | Spese | Entrambi | Numero | Entrambi | Non applicabile | Questo conto viene utilizzato quando c'è una differenza di costo tra la ricevuta e la fattura. |
| Rivalutazione per media mobile | 510610 | Rivalutazione media mobile | Spese | Entrambi | Numero | Entrambi | Non applicabile | Questo conto viene utilizzato quando modifichi il costo medio mobile di un prodotto |

## <a name="sample-posting-profile-configuration"></a>Esempio di configurazione del profilo di registrazione

La tabella seguente mostra esempi dei tipi di registrazione predefiniti con conti principali e descrizioni di esempio.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | P/F | Segui | Description |
|---|---|---|---|---|---|---|---|---|
| Uscita inventario | 140100 | Inventario dei materiali | Cespite | Credito | Numero | Entrambi | Entrata inventario | Questo conto viene utilizzato quando una transazione di inventario registrata è un'uscita (quantità negativa) e non è correlata a vendite, acquisti o produzione. La compensazione su questo conto è il conto spese di inventario, perdite. Questo conto rappresenta in genere l'inventario nello stato patrimoniale. |
| Spese di magazzino, perdita | 510100 | Profitti e perdite inventario | Spese | Dare | Numero | Entrambi | Spese di magazzino, profitto | Questo conto viene utilizzato quando una transazione di inventario registrata è un'uscita (quantità negativa) e non è correlata a vendite, acquisti o produzione. La compensazione su questo conto è il conto uscite da magazzino. |
| Entrata inventario | 140100 | Inventario dei materiali | Cespite | Dare | Numero | Entrambi | Uscita inventario | Questo conto viene utilizzato quando una transazione di inventario registrata è un'entrata (quantità positiva) e non è correlata a vendite, acquisti o produzione. La compensazione su questo conto è il conto spese di inventario, profitti. Questo conto rappresenta in genere l'inventario nello stato patrimoniale. |
| Spese di magazzino, profitto | 510100 | Profitti e perdite inventario | Spese | Credito | Numero | Entrambi | Spese di magazzino, perdita | Questo conto viene utilizzato quando una transazione di inventario registrata è un'entrata (quantità positiva) e non è correlata a vendite, acquisti o produzione. La compensazione su questo conto è il conto entrate in magazzino. |
| Conto fornitori interunità | 231500 | Interunità - Debito | Passività | Dare | Numero | Entrambi | | Questo conto viene utilizzato quando l'inventario viene trasferito tra dimensioni inventariali come i siti e il costo di un articolo differisce tra i siti. |
| Conto clienti interunità | 131500 | Interunità - Credito | Cespite | Credito | Numero | Entrambi | | Questo conto viene utilizzato quando l'inventario viene trasferito tra dimensioni inventariali come i siti e il costo di un articolo differisce tra i siti. |
