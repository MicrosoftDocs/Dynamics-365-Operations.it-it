---
title: Gestione scorte di magazzino
description: Questo argomento descrive i tipi di documenti utilizzabili per la gestione delle scorte.
author: rubencdelgado
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 43625d17e0e2827396edb69a1d1d73a8472294ea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252536"
---
# <a name="commerce-inventory-management"></a>Gestione scorte e-commerce

[!include [banner](includes/banner.md)]

Quando lavori con le scorte in Microsoft Dynamics 365 Commerce e utilizzi una qualsiasi delle applicazioni Commerce collegate a una CSU (Commerce Scale Unit), è importante sapere che la logica di elaborazione degli ordini in CSU fornisce un supporto limitato per alcune dimensioni delle scorte e alcuni tipi di articoli di magazzino. Le applicazioni Commerce non supporta l'intera gamma di funzionalità di configurazione degli articoli disponibili tramite le opzioni di configurazione degli articoli in Dynamics 365 Supply Chain Management.

Le applicazioni Commerce eseguite su CSU non supportano le seguenti dimensioni e configurazioni degli articoli:

- Dimensioni del prodotto di configurazione e articoli della distinta base (BOM) (eccetto i prodotti del kit di vendita al dettaglio, che utilizzano alcuni componenti del framework della distinta base)
- Articoli a peso variabile
- Articoli controllati in base alle dimensioni della versione del prodotto

Le applicazioni Commerce eseguite su CSU non supportano le seguenti dimensioni di tracciabilità:
- Dimensione Proprietario

- L'applicazione per punti vendita (POS) può offrire un supporto limitato per le seguenti dimensioni. Il POS può impostare automaticamente alcune dimensioni nelle transazioni di inventario in base alla configurazione del magazzino o alla configurazione del negozio. Il POS non supporterà completamente le dimensioni nel modo in cui sono supportate se una transazione di vendita viene immessa manualmente in Commerce Headquarters. 

- **Ubicazione magazzino**: quando usano le nuove operazioni POS [Operazione in entrata](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) e [Operazione in uscita](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), gli utenti possono selezionare una posizione di inventario di magazzino per ricevere gli articoli o da cui spedire gli articoli dell'ordine di trasferimento in uscita. Se usano l'operazione obsoleta **Prelievo e ricevimento**, è disponibile un supporto di gestione della posizione limitato per il ricevimento e la spedizione di trasferimenti in uscita. Tale supporto è disponibile solo se l'opzione **Usa processi di gestione magazzino** è stata attivata l'opzione per l'articolo e il magazzino del negozio. Una ubicazione di inventario al momento non può essere utilizzata con l'operazione **Conteggio scorte** o **Ricerca in magazzino**.

- **Targa**: applicabile solo se l'opzione **Usa processi di gestione magazzino** è stata attivata per l'articolo e il magazzino del punto vendita. In POS, se l'inventario viene ricevuto in un magazzino del negozio utilizzando l'operazione **Operazione in entrata** o **Prelievo e ricevimento** in cui il processo di gestione del magazzino è stato attivato e se l'ubicazione selezionata per ricevere l'articolo è collegata a un profilo di ubicazione che richiede il controllo della targa, l'applicazione POS applica sistematicamente una targa alla riga di ricezione. Gli utenti POS non possono modificare o gestire i dati di questa targa. Se è necessaria la gestione completa delle targhe, è consigliabile che il negozio utilizzi l'[app di magazzino](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/install-configure-warehousing-app) o il client di back-office per gestire la ricezione di tali articoli.

- **Numero di serie**: l'applicazione POS fornisce un supporto limitato per la registrazione di un numero di serie singolo su una riga di vendita transazione per gli ordini creati nel POS e che includono articoli serializzati. Questo numero di serie non viene convalidato rispetto ai numeri di serie già registrati in magazzino. Se un ordine cliente viene creato tramite il canale del call center o soddisfatto tramite l'ERP (Enterprise Resource Planning) e più numeri di serie vengono registrati su una singola riga di vendita durante il processo di evasione nell'ERP, tali numeri di serie non possono essere applicati o convalidati se un reso viene elaborato in POS per l'ordine. Quando l'inventario viene ricevuto utilizzando l'operazione **Operazione in entrata**, gli utenti possono [registrare o confermare i numeri di serie ricevuti](https://docs.microsoft.com/dynamics365/commerce/pos-serialized-items).

- **ID batch**: l'applicazione POS fornisce supporto limitato durante la registrazione del rendiconto se un articolo controllato in batch viene venduto, ma gli utenti POS non sono in grado di definire l'ID di un batch venduto o selezionato quando si utilizza un'applicazione POS.

- **Stato inventario**: per gli articoli che utilizzano il processo di gestione del magazzino e richiedono uno stato dell'inventario, questo campo di stato non può essere impostato o modificato tramite l'applicazione POS. Lo stato di inventario predefinito specificato nella configurazione del magazzino di punto vendita viene utilizzato quando gli articoli vengono ricevuti.

> [!NOTE]
> Tutte le organizzazioni devono testare le configurazioni mediante le app Commerce in ambienti di test o di sviluppo prima che distribuiscano tali configurazioni di articoli agli ambienti di produzione. Metti alla prova i tuoi articoli utilizzandoli per eseguire normali transazioni di vendita cash-and-carry nel POS e creare ordini dei clienti (se applicabile) tramite POS, call center o e-commerce per verificare che possano essere completamente supportati. È inoltre necessario testare i processi di evasione e inventario dei POS (come le operazioni di ricezione ed evasione degli ordini) prima di distribuire qualsiasi nuova configurazione degli articoli, per assicurarsi che l'applicazione POS possa supportarli. I test devono includere l'esecuzione di un processo completo di registrazione/ordine delle dichiarazioni nel proprio ambiente di test e la verifica che non si verifichino problemi di registrazione quando gli ordini per questi articoli vengono creati e registrati in Commerce Headquarters.
>
> Se gli articoli sono configurati in un modo che non è supportato dalle applicazioni Commerce e non vengono eseguiti test appropriati, potrebbero verificarsi errori nei dati che non sono facilmente corretti o che potrebbero non essere risolti affatto.

## <a name="purchase-orders"></a>Ordine fornitore

Gli ordini di acquisto vengono creati in Commerce headquarters. Se un magazzino di un negozio è incluso nell'intestazione di un ordine fornitore o nelle righe di un ordine fornitore, le righe possono essere ricevute dal negozio usando l'[Operazione in entrata](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) operation in POS. 

## <a name="transfer-orders"></a>Ordini di trasferimento

Gli ordini di trasferimento possono essere creati in Commerce headquarters o tramite l'[Operazione in entrata](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) o l'[Operazione in uscita](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) in POS. Usa l'operazione POS **Operazione in entrata** per creare una richiesta di ordine di trasferimento per avere l'inventario inviato al negozio da un altro magazzino o ubicazione del negozio. Usa l'operazione POS **Operazione in uscita** per creare una richiesta di ordine di trasferimento per avere l'inventario spedito dal negozio a un altro magazzino o ubicazione del negozio. Dopo aver creato un ordine di trasferimento per un negozio, quel negozio può gestire la ricezione dell'inventario per l'ordine di trasferimento tramite l'operazione **Operazione in entrata** in POS. Se il negozio sta spedendo l'inventario a un'altra posizione, l'operazione **Operazione in uscita** in POS viene utilizzata per gestire il processo di spedizione in uscita di quel negozio.

## <a name="stock-counts"></a>Conteggi scorte

I conteggi scorte possono essere pianificati o non pianificati. Il conteggio delle scorte pianificato viene creato attraverso Commerce headquarters creando un giornale di registrazione di tipo Conteggio collegato al magazzino del negozio. Questo diario specifica gli articoli che devono essere contati. Il negozio può quindi accedere a questi giornali di registrazione predefiniti e agire su di essi utilizzando l'operazione **Conteggio scorte** in POS. Gli utenti del negozio avviano un conteggio delle scorte non pianificato poiché è necessario quando utilizzano l'operazione **Conteggio scorte** in POS. A differenza dei conteggi scorte pianificati, i conteggi scorte non pianificati non dispongono di un elenco predefinito di elementi. Al termine di un conteggio scorte di entrambi i tipi in POS, questo viene impegnato e inviato alla sede principale. Nella sede principale, il conteggio deve quindi essere convalidato e registrato in Commerce headquarters come un passaggio separato.

## <a name="inventory-lookup"></a>Ricerca in magazzino

La quantità di prodotto attualmente disponibile per più negozi e magazzini può essere visualizzata nella pagina **Ricerca in magazzino**. Oltre alla quantità disponibile corrente, le quantità available-to-promise (ATP) future possono essere visualizzate per ogni negozio. Seleziona il negozio per visualizzare le quantità ATP e quindi seleziona **Mostra disponibilità punto vendita**. Per informazioni sulle opzioni di configurazione disponibili, vedi [Calcolare la disponibilità scorte per i canali di vendita al dettaglio](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).


[!INCLUDE[footer-include](../includes/footer-banner.md)]