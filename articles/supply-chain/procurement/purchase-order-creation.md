---
title: Creazione degli ordini fornitore
description: In questo articolo vengono descritti il processo e le opzioni di creazione manuale di un ordine fornitore.
author: RichardLuan
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93053
ms.assetid: 25b1c9f1-20f8-4cf5-b87c-876e32f68846
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28407ee694fa788def68aba92366d91248fd6541
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216011"
---
# <a name="create-purchase-orders"></a>Creazione degli ordini fornitore

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritti il processo e le opzioni di creazione manuale di un ordine fornitore.

Quando si crea un ordine fornitore (PO), le informazioni generali sull'intero ordine vengono specificate nell'intestazione dell'ordine fornitore e si aggiungono quindi una o più righe al PO. Questo articolo descrive alcune delle opzioni disponibili utilizzati più di frequente.  

È inoltre possibile creare PO copiando le righe da un altro documento di ordine fornitore o cliente. In questo caso, è possibile invertire il segno in magazzino, come si invertirebbe il segno di una fattura per indicare credito.  

Sebbene sia possibile creare manualmente PO, di solito vengono generati da altri processi. Gli ordini possono essere creati automaticamente in base ad altri documenti, quali le richieste. In alternativa, possono essere creati durante il processo di pianificazione generale tramite ordini fornitore pianificati. Se si utilizzano i contratti di acquisto, gli ordini fornitore può essere creata tramite l'azione **Ordine di rilascio**. Vi sono anche metodi più avanzati per la creazione automatica di un ordine fornitore. Ad esempio è possibile creare ordini quando si utilizza la consegna diretta o le catene di ordini interaziendali.

## <a name="creating-a-purchase-order-header"></a>Creazione dell'intestazione di un ordine fornitore
Quando si crea un nuovo ordine fornitore, viene visualizzata una finestra di dialogo in cui è possibile immettere le informazioni più comuni per l'intestazione dell'ordine fornitore. Quando fa clic su **OK** per chiudere la finestra di dialogo, l'ordine viene creato e quindi è possibile specificare ulteriori informazioni nell'intestazione.  

I primi dettagli da considerare nella creazione di un PO sono il tipo di ordine. Il tipo **Ordine fornitore** viene utilizzato molto spesso. Tuttavia, se è rochiesta una fattura nota di accredito, è possibile utilizzare il tipo **Ordine di reso**.  

È necessario specificare il fornitore nel campo **Conto fornitore**. Per questo campo, è possibile cercare il conto o il nome del fornitore. Se un fornitore consegna da più ubicazioni, ma utilizza un singolo conto di fatturazione, è possibile selezionare il conto fatture nel campo **Conto fatture** e quindi utilizzarlo con differenti conti fornitore. Se è necessario creare un ordine fornitore per prodotti che verranno ordinati ripetutamente, è possibile utilizzare l'opzione **Fornitore occasionale**. Questa opzione crea automaticamente un nuovo conto fornitore che è contrassegnato come conto occasionale, per supportare un processo di pulitura in un secondo momento per i conti occasionali nel modulo **Contabilità fornitori**. Quando si seleziona un conto fornitore, molti campi dell'intestazione dell'ordine fornitore ereditano i valori predefiniti dalle informazioni che sono associate al conto fornitore. Ad esempio, il sito di consegna e il magazzino predefiniti vengono copiati dalle informazioni del fornitore. Tuttavia, è possibile ignorare tali valori predefiniti se l'acquisto è destinato a un'altra ubicazione.  

Se il fornitore ha fornito un numero di riferimento per l'ordine, è possibile registrare queste informazioni nel campo **Riferimento fornitore**. Per gli ordini di reso, è necessario specificare un valore nel campo **NAR** per fare riferimento all'autorizzazione del fornitore per l'elaborazione del reso.  

Se un contratto di acquisto è associato all'ordine, è necessario specificare queste informazioni nel campo **Contratto di acquisto**.  

L'intestazione del PO contiene inoltre informazioni sulle spese che riguardano l'intero ordine anziché singole righe. Le spese possono essere aggiunte automaticamente all'ordine se le spese automatiche sono state impostate per il fornitore o il gruppo di spese del fornitore. È anche possibile aggiungere manualmente spese all'intestazione dell'ordine facendo clic su **Gestisci spese** nel riquadro azioni.

## <a name="adding-purchase-order-lines"></a>Aggiunta di righe all'ordine fornitore
I PO possono riguardare prodotti fisici o servizi. Un'impostazione del gruppo di modelli inventariali determina se un numero articolo particolare si applica a un prodotto o un servizio. In genere, l'articolo acquistato è specificato da un numero di articolo. Tuttavia, se l'ordine è per prodotti o servizi che vengono utilizzati direttamente, è possibile specificare l'articolo anche utilizzando una categoria di approvvigionamento.  

Le righe di ordine fornitore contengono numerosi campi, ma molti di questi campi hanno un valore predefinito o un valore che viene ereditato dall'intestazione dell'ordine. Campi aggiuntivi vengono impostati quando si seleziona un prodotto o servizio. I campi che sono spesso impostati manualmente includono i campi per il numero di articolo, quantità e data di consegna richiesta. Informazioni su prezzo unitario e gli sconti sono anche molto importanti, ma i valori di tali campi sono spesso determinati da accordi commerciali o contratti di acquisto.  

Quando si seleziona un prodotto, è possibile cercare in tutto o parte del nome del prodotto anziché il numero di articolo. Se il prodotto presenta diverse varianti, quali dimensioni diverse, è possibile visualizzare una panoramica delle varianti disponibili tramite la funzione **Aggiungi righe** o tramite la ricerca disponibile nel campo **Numero variante**.  

Spesso, è necessario specificare dimensioni diverse per l'articolo selezionato in ogni riga dell'ordine fornitore. Le dimensioni che devono essere specificate dipendono dai gruppi di dimensioni che sono stati assegnati per la definizione della rappresentazione generale del prodotto. Ad esempio, è spesso necessario specificare un sito e magazzino per indicare l'ubicazione in cui il prodotto deve essere consegnato. Si identificanole varianti del prodotto specificando un numero di variante o immettendo valori per uno o più dimensioni di prodotto, ad esempio colore, dimensione, configurazione o stile. Le dimensioni di tracciabilità, come batch e numero di serie, consentono di identificare in modo univoco ciascun lotto di magazzino. Dopo aver creato un ordine, è possibile acquisire i valori delle dimensioni dell'ordine utilizzando l'azione **Registrazione**. Ad esempio, si è ordinata una quantità pari a cinque pezzi di un articolo. Successivamente si registra che tre di questi pezzi saranno neri e due di essi saranno blu. Questo approccio costituisce un'alternativa all'acquisizione di informazioni sulle dimensioni durante la registrazione di arrivo.  

È possibile verificare i dettagli dello stato di transazione di magazzino per i prodotti stoccati. Si può ad esempio decidere di controllare le scorte disponibili per decidere la quantità da ordinare. In alternativa, è possibile verificare lo stato del magazzino di una quantità ordinata per vedere se si è verificata una registrazione degli arrivi in entrata.  

Una riga di ordine fornitore che viene utilizzata per restituire un prodotto al fornitore avrà una quantità negativa. È possibile selezionare un lotto specifico da restituire utilizzando l'azione **Prenotazione**.  

In alcuni casi, è possibile che si voglia dividere la quantità che è stata ordinata, in modo che diverse parti vengono recapitate in date diverse. È possibile impostare tali consegne utilizzando l'azione **Programmazione consegna**, disponibile nel menu **Riga ordine fornitore** nella visualizzazione **Righe**.  

Le spese possono essere aggiunte automaticamente alle righe dell'ordine se le spese automatiche sono state impostate per il fornitore o il gruppo di spese del fornitore e per l'articolo o il gruppo di spese dell'articolo. Tuttavia, in genere, le spese vengono aggiunte manualmente a livello di riga dell'ordine. Per aggiungere una spesa, aprire la pagina **Gestisci spese** utilizzando l'azione **Gestisci spese** nel menu **Dati finanziari** della visualizzazione **Righe**. Il vantaggio dell'aggiunta di spese direttamente a livello di riga è che l'addebito può essere allocato come un costo di magazzino. Per impostare i codici di addebito in modo da registrare il costo del prodotto, utilizzare l'opzionedi addebito **Articolo**. Questi tipi di spese devono essere allocati dall'intestazione dell'ordine fornitore alle righe prima di poter confermare l'ordine. Ad esempio, si potrebbe desiderare di allocare le spese in base alla quantità di ciascuna riga. La categoria di spesa influisce anche su come le spese vengono registrate. Ad esempio, le spese fisse specificano un importo fisso e le spese percentuali vengono calcolate come percentuale dell'importo netto per la riga ordine. I PO possono essere assegnati a un carico e il carico può includere una stima della spesa prevista per il costo di trasporto. È possibile allocare questa spesa dal carico alle righe dell'ordine fornitore.

## <a name="purchase-order-actions"></a>Azioni degli ordini fornitore
Dopo aver aggiunto l'intestazione e righe all'ordine fornitore, spesso è necessario completare passaggi aggiuntivi prima che l'ordine sia pronto per essere confermato. Perché così tante opzioni sono disponibili, potrebbe essere utile utilizzare [Ricerca di azioni](../../fin-and-ops/get-started/action-search.md) per trovare la voce di menu desiderata.  

È possibile configurare i prodotti nell'ordine in modo che abbiano articoli supplementari. Gli articoli supplementari sono prodotti che devono o possono essere acquistati con altri prodotti. Prodotti supplementari possono essere aggiunti come prodotti di accompagnamento gratuiti, o potrebbe essere possibile decidere se si aggiungerli all'ordine o no. È possibile esaminare gli articoli supplementari dopo ogni riga di ordine che viene aggiunta. Tuttavia, è probabilmente più comodo rivedere e aggiungere articoli supplementari pertinenti per tutte le righe ordine utilizzando la pagina **Articoli supplementari** che è possibile aprire dal riquadro azioni.  

Gli sconti in genere vengono aggiunti alle righe quando vengono create. Tuttavia, alcuni sconti si applicano all'intero ordine:

-   L'azione **Sconto totale** calcola una percentuale di sconto totale che viene applicata all'intero ordine. Non confondere questo sconto con la percentuale di sconto di cassa. Gli sconti di cassa vengono applicati quando la fattura viene pagata, e dipendono dalla liquidazione entro una data specifica.
-   Se si applica uno sconto plurimo, è necessario utilizzare l'azione **Sconto plurimo** per calcolarlo e assegnarlo all'ordine. Gli sconti plurimi sono gli sconti che possono essere proposto se un mix di prodotti dell'ordine supera una soglia comune. Solo alcune aziende utilizzano questo tipo di sconto.

Spese con un codice di addebito che utilizza il tipo di addebito **Articolo** devono essere assegnate a livello di riga prima di poter confermare l'ordine. Potrebbe essere utile assegnare tali spese a livello di intestazione dell'ordine, in modo che sia possibile specificare l'importo totale delle spese. Tuttavia, in questo caso, la spesa deve quindi essere allocata a ogni riga prima di poter confermare l'ordine. È possibile utilizzare l'azione **Assegna spese** per suddividere gli importi di spese assegnati a livello di intestazione tra le righe dell'ordine. È possibile dividere le spese secondo l'importo netto di ogni riga, secondo la quantità che è stata ordinata o in modo uniforme tra le righe dell'ordine. Dopo aver allocato le spese alle righe, l'addebito viene rimosso dall'intestazione dell'ordine.  

I PO possono essere configurati per richiedere che i fondi budget siano allocati all'ordine prima che possa essere elaborato. In questo caso, è possibile utilizzare l'azione **Verifica budget** per allocare il budget.  

Potrebbe essere necessario ritardare il completamento di un ordine fornitore. Ad esempio, si potrebbero richiedere ulteriori informazioni sui prodotti o servizi, o potrebbe essere necessario ottenere l'autorizzazione per la spesa. Esistono diversi modi per sospendere un ordine. Ad esempio, è possibile attendere per confermare l'ordine. In alternativa, se si utilizza un flusso di lavoro di gestione delle modifiche, non inviare l'ordine per l'approvazione. Se è necessario bloccare tutti gli ordini per un determinato fornitore, è anche possibile contrassegnare il fornitore come **In attesa** di elaborazione nei dati master fornitori. Esistono inoltre circostanze che potrebbero impedire l'elaborazione dell'ordine. Ad esempio, l'elaborazione potrebbe essere impedita se sono stati superati i limiti di credito, o se i fondi budget richiesti non sono disponibili.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica degli ordini fornitore](purchase-order-overview.md)

[Approvare e confermare gli ordini fornitore](purchase-order-approval-confirmation.md)

[Entrata prodotti e ordini fornitore](product-receipt-against-purchase-orders.md)

[Panoramica delle fatture fornitore](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]