---
title: Gestione scorte di magazzino
description: Questo argomento descrive i tipi di documenti utilizzabili per la gestione delle scorte.
author: rubencdelgado
manager: AnnBe
ms.date: 04/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: efc729c83b81bd8afb806c403d52fd85b36efc9d
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1523763"
---
# <a name="store-inventory-management"></a>Gestione scorte di magazzino

[!include [banner](includes/banner.md)]

Quando si utilizzano le scorte in Dynamics 365 for Retail e l'applicazione POS, è importante notare che il POS offre supporto limitato per le dimensioni inventariali e alcuni tipi di articoli di magazzino.  

La soluzione POS non supporta le seguenti configurazioni articoli:
- Articoli DBA (ad eccezione dei prodotti del kit, che utilizzano alcuni componenti del framework DBA)
- Articoli a peso variabile
- Articoli controllati per batch

L'applicazione POS attualmente non supporta le seguenti dimensioni di tracciabilità nel POS:
- Dimensione Tracciabilità batch
- Dimensione Proprietario

La soluzione POS offre supporto limitato per le dimensioni seguenti. Con supporto limitato si intende che il POS può impostare automaticamente come predefinite alcune di queste dimensioni nelle transazioni di magazzino in base alla configurazione di installazione del punto vendita/magazzino. Il POS non supporterà completamente le dimensioni nel modo in cui sono supportate se una transazione di vendita viene immessa manualmente nell'ERP. 

- **Ubicazione di magazzino** - Gli utenti non avranno la possibilità di gestire l'ubicazione del magazzino ricevente per gli articoli ricevuti in un magazzino di punto vendita quando il punto vendita non è stato configurato per utilizzare il processo di gestione del magazzino.  Per questi articoli verrà utilizzata un'ubicazione di ricevimento predefinita specificata nel magazzino del punto vendita.  Se il processo di gestione del magazzino è stato abilitato per il punto vendita, verrà attivato il supporto limitato che richiede all'utente di scegliere un'ubicazione per l'intero ricevimento.  Gli articoli venduti dal punto vendita vengono venduti sempre dall'ubicazione di vendita al dettaglio predefinita in base all'impostazione del magazzino di punto vendita.   L'ubicazione per la gestione delle scorte dei resi può essere controllata tramite la definizione dell'ubicazione di reso predefinita nel magazzino del punto vendita o in base ai codici motivo di reso definiti nei criteri dell'ubicazione di reso.
- **Targa** - Applicabile solo se **Usa processi di gestione magazzino** è stato attivato per l'articolo e il magazzino del punto vendita.  Nel POS, se le scorte vengono ricevute in un magazzino di punto vendita in cui il processo di gestione del magazzino è stato abilitato e l'ubicazione scelta per ricevere l'articolo è legata a un profilo di posizione che richiede il controllo della targa, l'applicazione POS applicherà sistematicamente una targa alla riga ricevimento.  Gli utenti del POS non avranno la possibilità di modificare o gestire questi dati della targa.   Se è necessaria la gestione completa delle targhe, è consigliabile che il punto vendita utilizzi l'applicazione mobile WMS o il client ERP di back office per gestire il ricevimento di tali articoli.
- **Numero di serie** - L'applicazione POS ha un supporto limitato per un numero di serie singolo da registrare su una riga di vendita transazione per gli ordini creati nel POS con articoli serializzati.  Questo numero di serie non viene convalidato rispetto ai numeri di serie già registrati in magazzino.  Se un ordine cliente viene creato tramite il canale del call center o soddisfatto tramite l'ERP e più numeri di serie vengono registrati su una singola riga di vendita durante il processo di evasione nell'ERP, questi numeri di serie non potranno essere applicati o convalidati se un reso viene elaborato in POS per questi ordini.
- **Stato inventario** - Per gli articoli che utilizzano il processo di gestione del magazzino e richiedono uno stato dell'inventario, questo campo di stato non può essere impostato o modificato tramite l'applicazione POS.  Lo stato di inventario predefinito specificato nella configurazione del magazzino di punto vendita verrà utilizzato quando gli articoli vengono ricevuti.  

> [!NOTE]
> Tutte le organizzazioni devono testare le configurazioni articolo mediante il POS in ambienti di sviluppo o test prima della distribuzione delle stesse alla produzione. Testare gli articoli con vendite cash and carry standard che eseguono transazioni e creano ordini cliente (se applicabile) mediante il POS con gli articoli. Il test deve includere un processo di registrazione rendiconti completo nell'ambiente di test e la verifica dell'assenza di errori.
> Se gli articoli sono configurati in un modo non supportato dall'applicazione POS, senza un test appropriato, è possibile che il processo di registrazione rendiconti non riesca in produzione senza un metodo agevole di correzione dei problemi. Le personalizzazioni di partner o clienti nell'applicazione possono eventualmente essere considerate per consentire la corretta esecuzione di tali processi di registrazione. Se le personalizzazioni non sono necessarie, l'organizzazione deve assicurarsi che la configurazione dei prodotti sia stata effettuata in un modo supportato dal processo applicazione POS/creazione ordine/registrazione rendiconti standard.

## <a name="purchase-orders"></a>Ordine fornitore

Gli ordini fornitore vengono creati nella sede centrale. Se un magazzino al dettaglio viene incluso nell'intestazione dell'ordine fornitore, l'ordine può essere ricevuto presso il punto vendita utilizzando Modern POS (MPOS) o Cloud POS di Microsoft Dynamics 365 for Retail tramite l'operazione **Prelievo/Ricevimento**. Dopo che le quantità ricevute al punto vendita sono state immesse nel campo **Ricevi ora** del POS per il documento di ordine fornitore, è possibile salvarle in locale o confermarle. Salvare questi dati localmente non ha alcun effetto sulle scorte di articoli a magazzino. Il salvataggio deve essere effettuato solo se l'utente non è pronto per la registrazione dell'entrata nella sede centrale e necessita di un modo per memorizzare temporaneamente i dati immessi in precedenza di **Ricevi ora**.  Ciò consente di salvare i dati Ricevi ora localmente nel database dei canali dell'utente. Quando il documento viene elaborato con l'opzione **Conferma**, i dati **Ricevi ora** vengono inviati alla sede centrale e il ricevimento dell'ordine fornitore verrà registrata. 

## <a name="transfer-orders"></a>Ordini di trasferimento

Un ordine di trasferimento può specificare che un determinato punto vendita è il luogo in cui gli articoli possono essere spediti o il luogo in cui le scorte saranno ricevute. Se l'utente del POS è il magazzino di spedizione per un ordine di trasferimento, potrà immettere le quantità **Spedisci ora** dal POS.  I dati immessi dal punto vendita di spedizione possono essere salvati localmente o confermati.  Se salvati localmente, non vengono apportati aggiornamenti al documento dell'ordine di trasferimento nella sede centrale. Il salvataggio deve essere effettuato solo se l'utente non è pronto per la registrazione della spedizione nella sede centrale e necessita di un modo per memorizzare temporaneamente i dati immessi in precedenza di **Spedisci ora**. Dopo che il punto vendita è pronto per confermare la spedizione, l'opzione **Conferma** deve essere selezionata. Questo registra la spedizione dell'ordine di trasferimento nella sede centrale in modo che il magazzino ricevente sia ora in grado di ricevere rispetto all'ordine. 

Se l'utente del POS è il magazzino di ricevimento per un ordine di trasferimento, potrà immettere le quantità **Ricevi ora** dal POS.  I dati immessi dal punto vendita di ricevimento possono essere salvati localmente o confermati. Il salvataggio deve essere effettuato solo se l'utente non è pronto per la registrazione dell'entrata nella sede centrale e necessita di un modo per memorizzare temporaneamente i dati immessi in precedenza di **Ricevi ora**. Ciò consente di salvare i dati Ricevi ora localmente nel database dei canali dell'utente. Quando il documento viene elaborato con l'opzione **Conferma**, i dati **Ricevi ora** vengono inviati alla sede centrale e il ricevimento dell'ordine di trasferimento verrà registrata. È importante notare che il punto vendita di ricevimento sarà limitato alla sola possibilità di confermare quantità di ricevimento uguali o inferiori alle quantità spedite. Un tentativo di ricevere quantità su un ordine di trasferimento che non è stato spedito in precedenza causerà errori e il ricevimento non sarà confermato nella sede centrale.

## <a name="stock-counts"></a>Conteggi scorte

I conteggi scorte possono essere pianificati o non pianificati. I conteggi di scorte programmate sono avviati presso la sede principale, la quale specifica gli articoli da conteggiare. La sede principale crea un documento relativo ai conteggi che si può ricevere in punto vendita, dove le quantità delle scorte disponibili effettive vengono inserite in MPOS oppure in POS cloud. I conteggi scorte non pianificati vengono avviati in un punto vendita e le quantità delle scorte disponibili effettive vengono aggiornate in MPOS o POS cloud. A differenza dei conteggi scorte pianificati, i conteggi scorte non pianificati non dispongono di un elenco predefinito di elementi. Al termine di un conteggio scorte di entrambi i tipi, questo viene impegnato e inviato alla sede principale. Presso la sede centrale, il conteggio viene convalidato e registrato come passaggio distinto.

## <a name="inventory-lookup"></a>Ricerca in magazzino

La quantità corrente di prodotto disponibile per più catene e magazzini può essere visualizzata nella pagina **Ricerca in magazzino**. Oltre alla quantità corrente di scorte disponibili, le quantità available-to-promise (ATP) future possono essere visualizzate per ogni singolo punto vendita. A questo scopo, selezionare il punto vendita di cui si desidera visualizzare il valore ATP, quindi fare clic su **Mostra disponibilità punto vendita**.
