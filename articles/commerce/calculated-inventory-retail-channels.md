---
title: Calcolare la disponibilità scorte per i canali di vendita al dettaglio
description: In questo argomento viene descritto come un'azienda può utilizzare Microsoft Dynamics 365 Commerce per visualizzare la disponibilità scorte stimata per i prodotti nei canali online e dei punti vendita.
author: hhainesms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: da79aadace09ad480fa34bc03220831023e469645bb7d53af1647bd2d35af0ea
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741814"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Calcolare la disponibilità scorte per i canali di vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come un'azienda può utilizzare Microsoft Dynamics 365 Commerce per visualizzare la disponibilità scorte stimata per i prodotti nei canali online e dei punti vendita.

## <a name="accuracy-of-inventory-availability"></a>Precisione della disponibilità scorte

Commerce utilizza più server e database per garantire scalabilità e prestazioni. Pertanto, è importante comprendere che i valori delle scorte disponibili forniti tramite l'applicazione POS, le API per la disponibilità delle scorte e-commerce e le pagine di scorte disponibili in Commerce Headquarters potrebbero non essere accurati al 100% in tempo reale. Se le transazioni create per i prodotti nel canale online o del punto vendita non sono ancora state sincronizzate con Headquarters, le pagine delle scorte disponibili in Headquarters potrebbero non mostrare un valore di scorte in tempo reale accurato per tali prodotti. Al contrario, se l'azienda è stata configurata in modo che gli utenti di Headquarters o di altre applicazioni integrate possano vendere, ricevere, restituire o altrimenti modificare le scorte da un punto vendita o un magazzino online, il POS o il canale online potrebbero non avere tutte le informazioni richieste per mostrare valori accurati per le scorte disponibili in tempo reale.

È fondamentale comprendere che tutti i dati sulle scorte disponibili forniti durante la giornata operativa sono considerati un valore stimato. Pertanto, se si tenta di confrontare le informazioni delle scorte disponibili fornite dall'applicazione con l'inventario fisico effettivo sugli scaffali o se si tenta di confrontare i valori delle scorte disponibili mostrati in POS con i dati delle scorte disponibili che si trovano nello stesso magazzino di Headquarters, i valori potrebbero differire. Questa differenza durante la giornata operativa è prevista e non deve essere considerata un problema. Se si desidera controllare i dati e assicurarsi che i valori forniti nel POS, nelle API e in Headquarters corrispondano alle unità fisiche effettive che trovi sugli scaffali del tuo punto vendita o magazzino, il momento migliore per farlo è dopo che le operazioni del canale sono state arrestate per quel giorno e tutte le transazioni sono state correttamente sincronizzate tra Headquarters e i canali.

## <a name="channel-side-inventory-calculation"></a>Calcolo delle scorte lato canale

Il calcolo delle scorte lato canale è un meccanismo che prende gli ultimi dati di inventario del canale noti in Headquarters come base di riferimento e quindi tiene conto di ulteriori modifiche alle scorte avvenute sul lato canale che non sono incluse in tale base di riferimento per calcolare un livello di scorte disponibili stimato quasi in tempo reale. 

Le seguenti modifiche alle scorte sono attualmente considerate nella logica di calcolo delle scorte lato canale:

- Scorte vendute tramite ordini cash and carry in punto vendita
- Scorte vendute tramite ordini cliente in punto vendita o canale online
- Scorte restituite al punto vendita
- Scorte evase (prelievo, imballaggio, spedizione) dal magazzino del punto vendita

Per utilizzare il calcolo delle scorte lato canale, come prerequisito uno snapshot periodico dei dati di inventario da Headquarters creato dal processo **Disponibilità prodotto** deve essere inviato ai database del canale. Lo snapshot rappresenta le informazioni presenti in Headquarters in merito alla disponibilità scorte per una combinazione specifica di prodotto o variante di prodotto e magazzino. Include solo le transazioni di inventario che sono state elaborate e registrate in Headquarters nel momento in cui è stato preso lo snapshot e potrebbe non essere preciso al 100% in tempo reale a causa della costante elaborazione delle vendite che si verifica sui server distribuiti.

- Se le scorte sono state vendute per un prodotto in un punto vendita tramite una vendita ordine cliente icash-and-carry o asincrono nell'applicazione POS, Headquarters non avrà immediatamente le informazioni sulla relativa transazione di uscita dal magazzino per la vendita. Headquarters conterrà le informazioni sulle scorte vendute per questi tipi di vendite del punto vendita solo dopo che il processo P ha caricato la relativa transazione dal database del canale del punto vendita in Headquarters e i relativi ordini cliente sono stati creati mediante la registrazione degli estratti conto o i processi di registrazione su inserimento continuo. Il processo di creazione degli ordini in Headquarters crea le relative transazioni di inventario. 
- Per gli ordini di canale e-commerce, Headquarters ha le informazioni sulle transazioni di inventario solo dopo che le transazioni sono state inviate a Headquarters tramite il processo P e dopo che il processo di sincronizzazione degli ordini è stato completato.

Per creare uno snapshot di scorte in Commerce Headquarters, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Prodotti e inventario \> Disponibilità prodotto**.
1. Selezionare **OK** per eseguire il processo **Disponibilità prodotto**. È inoltre possibile pianificare questo processo in modo che venga eseguito in batch.

Una volta terminata l'esecuzione del processo **Disponibilità prodotto**, i dati acquisiti devono essere inviati ai database del canale, in modo che lo snapshot più recente di scorte di Headquarters possa essere considerato nel calcolo lato canale delle scorte disponibili stimate.

Per sincronizzare i dati dello snapshot da headquarters con i database del canale, segui questi passaggi.

1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Eseguire il processo **1130** (**Disponibilità prodotto**) per sincronizzare i dati dello snapshot che il processo **Disponibilità prodotto** ha creato da Headquarters ai database del canale.

## <a name="inventory-availability-apis-for-e-commerce"></a>API di disponibilità scorte per e-commerce

Commerce fornisce le seguenti API per gli scenari di e-commerce per conoscere la disponibilità scorte di un prodotto:

- **GetEstimatedAvailability** - Utilizza questa API per eseguire query sulle scorte di un prodotto o una variante di prodotto nel magazzino del canale online o nei magazzini collegati al gruppo di evasione del canale online.
- **GetEstimatedProductWarehouseAvailability** - Utilizzare questa API per eseguire query sulle scorte di un prodotto o variante di prodotto di un magazzino specifico.

> [!NOTE]
> Queste API sostituiscono le API **GetProductAvailabilities** e **GetAvailableInventoryNearby** nella versione Commerce 10.0.7 e precedenti.

Entrambe le API utilizzano internamente la logica di calcolo lato canale e restituiscono una stima di quantità **fisica disponibile**, quantità **totale disponibile**, **unità di misura (UdM)** e **livello di scorte** per il prodotto e il magazzino richiesti. Se desiderato, i valori restituiti possono essere visualizzati sul sito e-commerce oppure possono essere utilizzati per attivare altre logiche aziendali sul sito e-commerce. Ad esempio, puoi impedire l'acquisto di prodotti con un livello di scorte "esaurito".

Sebbene altre API disponibili in Commerce possano accedere direttamente a Headquarters per recuperare le quantità di scorte disponibili per i prodotti, non è consigliabile utilizzarle in un ambiente di e-commerce a causa di potenziali problemi di prestazioni e del relativo impatto che queste frequenti richieste possono avere sui server Headquarters. Inoltre, con il calcolo lato canale, le due API sopra menzionate possono fornire una stima più accurata della disponibilità di un prodotto tenendo conto delle transazioni create nei canali che non sono ancora noti a Headquarters.

Per utilizzare le due API, devi abilitare la funzionalità **Calcolo della disponibilità del prodotto ottimizzato** attraverso l'area di lavoro **Gestione funzionalità** in Headquarters. Se i tuoi canali online e del punto vendita utilizzano gli stessi magazzini di evasione ordini, devi abilitare anche la funzionalità **Logica di calcolo scorte lato canale e-commerce migliorata** per avere la logica di calcolo lato canale all'interno delle due API per tenere conto delle transazioni non registrate (cash-and-carry, ordini cliente, resi) create nel canale del punto vendita. Dovrai eseguire il processo **1070** (**Configurazione canale**) dopo aver abilitato queste funzioni.

Per definire come deve essere restituita la quantità di prodotto nell'output dell'API, segui questi passaggi.

1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri di commercio**.
1. Seleziona la scheda **Scorte**, quindi nella Scheda dettaglio **API per la disponibilità scorte per l'e-commerce** configura il valore di **Quantità in output API**.
1. Esegui il processo **1070** (**Configurazione canale**) per sincronizzare l'impostazione più recente nei canali.

L'impostazione **Quantità in output API** fornisce tre opzioni:

- **Restituisci quantità scorte** - La quantità fisica disponibile e la quantità disponibile totale di un prodotto richiesto vengono restituite nell'output API.
- **Restituisci quantità scorte meno buffer di scorte** - La quantità restituita nell'output dell'API viene regolata sottraendo il valore del buffer di scorte. Per ulteriori informazioni sul buffer di scorte, vedere [Configurare i buffer di scorte e i livelli di scorte](inventory-buffers-levels.md).
- **Non restituire la quantità di scorte** - Solo il livello di scorte viene restituito nell'output dell'API. Per ulteriori informazioni sui livelli di scorte, vedere [Configurare i buffer di scorte e i livelli di scorte](inventory-buffers-levels.md).

Puoi usare il parametri API `QuantityUnitTypeValue` per specificare il tipo di unità in cui desideri che le API restituiscano la quantità. Questo parametro supporta le opzioni **unità di magazzino** (predefinita), **unità di acquisto**, e **unità di vendita**. La quantità restituita viene arrotondata alla precisione definita della corrispondente unità di misura (UsM) in Headquarters.

L'API **GetEstimatedAvailability** offre i seguenti parametri di input per supportare diversi scenari di query:

- `DefaultWarehouseOnly`- Utilizza questo parametro per le query sulle scorte di un prodotto nel magazzino predefinito del canale online. 
- `FilterByChannelFulfillmentGroup` e `SearchArea` - Utilizza questi due parametri per eseguire query sulle cscorte di un prodotto da tutte le località di prelievo all'interno di una specifica area di ricerca, in base a `longitude`, `latitude` e `radius`. 
- `FilterByChannelFulfillmentGroup` e `DeliveryModeTypeFilterValue` - Utilizza questi due parametri per eseguire query sulle scorte di un prodotto da magazzini specifici collegati a un gruppo di evasione ordini del canale online e configurati per supportare determinate modalità di consegna. Il parametro `DeliveryModeTypeFilterValue` supporta le opzioni **tutte** (predefinita), **spedizione** e **prelievo**. Ad esempio, in uno scenario in cui un ordine online può essere evaso da più magazzini di spedizione, è possibile utilizzare questi due parametri per eseguire query sulla disponibilità di scorte di un prodotto in tutti quei magazzini di spedizione. L'API in questo caso restituisce la quantità disponibile del prodotto e il livello di scorte in ciascuno dei magazzini di spedizione, più una quantità aggregata e un livello di scorte aggregato da tutti i magazzini di spedizione nell'ambito della query.
 
I moduli Casella acquisti, selettore punto vendita, lista dei desideri, carrello e icona del carrello di Commerce utilizzano le API e i parametri sopra menzionati per visualizzare i messaggi sul livello di scorte in tutto il sito di e-commerce. Creazione di siti di Commerce fornisce varie impostazioni di inventario per controllare il comportamento di merchandising e di acquisto. Per ulteriori informazioni, vedere [Applicare impostazioni relative alle scorte](inventory-settings.md).

## <a name="pos-inventory-lookup-with-channel-side-calculation"></a>Ricerca in magazzino POS con calcolo lato canale

In Commerce versione 10.0.9 e precedenti, l'operazione **Ricerca in magazzino** nel POS ha utilizzato una chiamata di servizio in tempo reale a Headquarters per ottenere informazioni sulle scorte per il prodotto selezionato, sia per il punto vendita corrente dell'utente sia per tutti gli altri punti vendita configurati per il gruppo di evasione come parte della configurazione del canale per il punto vendita. Nella versione Commerce 10.0.10 e successive, è possibile disattivare le chiamate di servizio in tempo reale a Headquarters e utilizzare invece il calcolo lato canale sul server Commerce per determinare le scorte fisicamente disponibili per il punto vendita e qualsiasi altra ubicazione  definita nel gruppo di evasione. Questa configurazione di inventario calcolata dal canale è utile anche per le ubicazioni in cui la connettività Internet non è affidabile, poiché non è necessario essere online per ottenere ricerche in magazzino da Headquarters.

Quando il calcolo lato canale è configurato e gestito correttamente, può fornire una stima più affidabile delle scorte attuali del punto vendita, poiché utilizza i dati transazionali presenti nel database del canale Commerce, ma per i quali Headquarters potrebbe non disporre ancora delle informazioni. Ad esempio, se si utilizza la chiamata di servizio in tempo reale esistente per le ricerche in magazzino nel POS, probabilmente Headquarters non avrà ancora le informazioni su una vendita cash-and-carry appena avvenuta per un prodotto. Pertanto, il valore delle scorte disponibili restituito da Headquarters per quel prodotto supererà probabilmente le scorte disponibili effettive del punto vendita di un'unità. Tuttavia, se si utilizza il calcolo sul lato canale, la vendita cash-and-carry può essere presa in considerazione nel calcolo e detratta dal valore di scorte disponibili che viene mostrato. Sebbene i valori forniti sia dal calcolo lato canale sia dalla chiamata di servizio in tempo reale siano solo stime delle scorte disponibili, il valore fornito dal calcolo lato canale è molto più probabile che sia accurato per il punto vendita corrente.

Per configurare l'operazione **ricerca in magazzino** del POS in Commerce headquarters al fine di utilizzare la logica di calcolo sul lato canale e disattivare la chiamata di servizio in tempo reale, è necessario prima abilitare la funzionalità **Calcolo della disponibilità del prodotto ottimizzato** attraverso l'area di lavoro **Gestione funzionalità** in Commerce Headquarters, quindi attenersi ai passaggi che seguono.

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**.
1. Selezionare un profilo funzionalità.
1. Nella scheda dettaglio **Funzioni**, nella sezione **Calcolo disponibilità scorte**, cambiare il valore del campo **Modalità di calcolo disponibilità scorte** da **Servizio in tempo reale** a **Canale**. Per impostazione predefinita, tutti i profili di funzionalità utilizzano chiamate di servizio in tempo reale. È necessario modificare il valore di questo campo se si desidera utilizzare la logica di calcolo sul lato canale. Ogni punto vendita al dettaglio collegato al profilo di funzionalità selezionato sarà interessato da questa modifica.

Devi quindi sincronizzare le modifiche con i canali attraverso il processo di pianificazione della distribuzione in Headquarters procedendo come segue:

1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Eseguire il processo **1070** (**Configurazione canale**).

Al termine della configurazione, le informazioni fornite sulle scorte fisicamente disponibili non utilizzano più una chiamata di servizio in tempo reale quando un utente nell'applicazione POS utilizza l'operazione **Ricerca in magazzino** (visualizzazioni standard e matrice). I dati sulle scorte fisicamente disponibili per il negozio corrente e tutti i negozi nel gruppo di evasione ordini vengono calcolati in base all'ultimo snapshot noto che è stata consegnata al database del canale da Commerce Headquarters. Il valore dello snapshot viene ulteriormente perfezionato dal calcolo sul lato canale per rettificare il valore delle scorte fisicamente disponibili, in base alle vendite aggiuntive o alle transazioni di reso esistenti per il prodotto selezionato nel database del canale che non sono state incluse nell'ultimo snapshot sincronizzato dal processo 1130. Se il database del canale non contiene dati transazionali per nessuno dei magazzini o negozi nel gruppo di evasione ordini, non contiene le transazioni aggiuntive che possono essere prese in considerazione in un ricalcolo del valore. Pertanto, la migliore stima delle scorte disponibili che può essere mostrata per quei magazzini o negozi è costituita dai dati dell'ultimo snapshot di Commerce Headquarters noto.

Le schermate **Evasione ordine** del POS sfruttano anche il calcolo lato canale per mostrare le scorte disponibili per gli articoli quando viene selezionata una riga di evasione dell'ordine e un utente visualizza il pannello **Dettagli** per le scorte disponibili dell'articolo selezionato.

## <a name="optimize-your-inventory-data"></a>Ottimizzare i dati di magazzino

Per garantire la migliore stima possibile dell'inventario, è fondamentale utilizzare i seguenti processi batch Commerce ed eseguirli frequentemente:

- **Processo P** - Il processo P è disponibile nella pagina **Programmazioni della distribuzione** e deve essere eseguito frequentemente. Questo processo porta gli ordini e-Commerce, gli ordini asincroni dei clienti creati dal POS e gli ordini cash-and-carry creati dal POS dai database del canale in Commerce Headquarters in modo che possano essere elaborati ulteriormente. Fino a quando questi dati non vengono sincronizzati dal canale in Commerce Headquarters, Commerce Headquarters non ha informazioni sulle rettifiche delle scorte dei prodotti nei magazzini risultanti da tali transazioni.
- **Sincronizza ordini** - Questo processo elabora i dati transazionali non elaborati in Commerce Headquarters forniti dal processo P e converte le transazioni e-commerce e degli ordini asincroni dei clienti in ordini di vendita in Commerce Headquarters. Fino a quando questo processo non viene elaborato e non vengono creati gli ordini cliente, non vengono create le transazioni di inventario. Pertanto, le scorte disponibili in Commerce Headquarters non prendono in considerazione le transazioni.
- **Calcola rendiconti transazionali in batch** - Per le transazioni cash-and-carry create nel punto vendita, il processo di registrazione dell'alimentazione su inserimento continuo assicura che l'inventario correlato alle vendite venga aggiornato in modo efficiente. Per ottenere l'elaborazione più efficiente delle transazioni di inventario per gli ordini cash-and-carry, assicurarsi di configurare il sistema per l'uso della [registrazione su inserimento continuo](./trickle-feed.md).
- **Registra rendiconti transazionali in batch** - Questo processo è richiesto anche per la registrazione su inserimento continuo. Segue il processo **Calcola rendiconti transazionali in batch**. Questo processo registra sistematicamente gli estratti conto calcolati, in modo che gli ordini di vendita per le vendite cash-and-carry vengano creati in Commerce Headquarters che riflette in modo più accurato l'inventario del punto vendita.
- **Disponibilità prodotto** - Questo processo crea lo snapshot dell'inventario da Commerce Headquarters.
- **1130 (disponibilità prodotto)** - Questo processo si trova nella pagina **Programmazioni della distribuzione** e deve essere eseguito immediatamente dopo il processo **Disponibilità prodotto**. Questo processo trasporta i dati dello snapshot dell'inventario da Commerce Headquarters ai database del canale.

> [!NOTE]
> - In generale, è buona norma eseguire i processi **Disponibilità prodotto** e **1130** su base oraria e pianificare il processo P, sincronizzare gli ordini e i processi relativi alla registrazione basata su inserimento continuo con la stessa frequenza o una frequenza maggiore.
> - Per motivi di prestazioni, quando vengono utilizzati i calcoli delle scorte disponibili sul lato canale per effettuare una richiesta di disponibilità scorte utilizzando l'API e-Commerce o la logica di inventario lato canale POS, il calcolo utilizza una cache per determinare se è trascorso abbastanza tempo per giustificare la nuova esecuzione della logica di calcolo. La cache predefinita è impostata su 60 secondi. Ad esempio, hai attivato il calcolo lato canale per il tuo negozio e hai visualizzato le scorte disponibili per un prodotto nella pagina **Ricerca in magazzino**. Se viene venduta un'unità del prodotto, la pagina **Ricerca in magazzino** non mostrerà l'inventario ridotto fino a quando la cache non sarà stata canCellaata. Dopo che gli utenti registrano le transazioni nel POS, devono attendere 60 secondi prima di verificare che l'inventario disponibile sia stato ridotto.

Se lo scenario aziendale richiede un tempo di cache inferiore, contattare il rappresentante del supporto prodotto per assistenza.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
