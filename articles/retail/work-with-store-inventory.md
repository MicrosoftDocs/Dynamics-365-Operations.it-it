---
title: Gestione scorte di magazzino
description: Questo argomento descrive i tipi di documenti utilizzabili per la gestione delle scorte.
author: rubencdelgado
manager: AnnBe
ms.date: 01/18/2019
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
ms.openlocfilehash: 02f8afbe3bb6f94c66a8b5aa02531c219adc3963
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "339236"
---
# <a name="store-inventory-management"></a>Gestione scorte di magazzino

[!include [banner](includes/banner.md)]

Questo argomento descrive i tipi di documenti utilizzabili per la gestione delle scorte.

È possibile utilizzare i seguenti tipi di documenti per la gestione dell'inventario dell'organizzazione.

Quando si utilizzano le scorte in Dynamics 365 for Retail e l'applicazione POS, è importante notare che il POS offre supporto limitato per le dimensioni inventariali e alcuni tipi di articoli di magazzino.  

La soluzione POS non supporta le seguenti configurazioni articoli:
- Articoli DBA (ad eccezione dei prodotti del kit, che utilizzano alcuni componenti del framework DBA)
- Articoli a peso variabile
- Articoli controllati per batch

L'applicazione POS attualmente non supporta le seguenti dimensioni di tracciabilità nel POS:
- Dimensione Tracciabilità batch
- Dimensione Proprietario

La soluzione POS offre supporto limitato per le dimensioni seguenti. Con supporto limitato si intende che il POS può impostare automaticamente come predefinite alcune di queste dimensioni nelle transazioni di magazzino in base alla configurazione di installazione del punto vendita/magazzino. Il POS non supporterà completamente le dimensioni nel modo in cui sono supportate se una transazione di vendita viene immessa manualmente nell'ERP. 

- Posizione
- Targa (applicabile solo se **Usa processi di gestione magazzino** è stato attivato per l'articolo e il magazzino del punto vendita)
- Numero di serie
- Stato inventario

> [!NOTE]
> Tutte le organizzazioni devono testare le configurazioni articolo mediante il POS in ambienti di sviluppo o test prima della distribuzione delle stesse alla produzione. Testare gli articoli con vendite cash and carry standard che eseguono transazioni e creano ordini cliente (se applicabile) mediante il POS con gli articoli. Il test deve includere un processo di registrazione rendiconti completo nell'ambiente di test e la verifica dell'assenza di errori.
> Se gli articoli sono configurati in un modo non supportato dall'applicazione POS, senza un test appropriato, è possibile che il processo di registrazione rendiconti non riesca in produzione senza un metodo agevole di correzione dei problemi. Le personalizzazioni di partner o clienti nell'applicazione possono eventualmente essere considerate per consentire la corretta esecuzione di tali processi di registrazione. Se le personalizzazioni non sono necessarie, l'organizzazione deve assicurarsi che la configurazione dei prodotti sia stata effettuata in un modo supportato dal processo applicazione POS/creazione ordine/registrazione rendiconti standard.

## <a name="purchase-orders"></a>Ordine fornitore

Gli ordini fornitore vengono creati nella sede centrale. Se un magazzino al dettaglio viene incluso nell'intestazione dell'ordine fornitore, l'ordine può essere ricevuto presso il punto vendita utilizzando Modern POS (MPOS) o il POS cloud in Microsoft Dynamics 365 for Retail. Una volta immesse, è possibile salvare in locale le quantità ricevute all'interno del punto vendita per ulteriori modifiche. In alternativa, i quantitativi possono essere impegnati e inviati alla sede principale. Presso la sede principale i quantitativi ricevuti nel punto vendita vengono visualizzati in Dynamics 365 for Retail, nel campo **Ricevi ora** dell'ordine fornitore.

## <a name="transfer-orders"></a>Ordini di trasferimento

Un ordine di trasferimento può specificare che un particolare punto vendita è un percorso da cui possono essere spediti gli articoli. In questo caso, l'ordine di trasferimento viene visualizzato presso il punto vendita come una richiesta di prelievo in MPSO o POS cloud. Una volta che i quantitativi richiesti sono stati prelevati, vengono impegnati e inviati alla sede principale. Presso la sede principale, i quantitativi prelevati nel punto vendita vengono visualizzati in Dynamics 365 for Retail, nel campo **Spedisci ora** dell'ordine di trasferimento. Un ordine di trasferimento può specificare che un particolare punto vendita è un percorso da cui possono essere spediti gli articoli. In questo caso, l'ordine di trasferimento viene visualizzato presso il punto vendita come una richiesta di ricezione in MPSO o POS cloud. Una volta immesse, è possibile salvare in locale le quantità ricevute all'interno del punto vendita per ulteriori modifiche. In alternativa, i quantitativi possono essere impegnati e inviati alla sede principale. Presso la sede principale i quantitativi ricevuti nel punto vendita vengono visualizzati in Dynamics 365 for Retail, nel campo **Ricevi ora** dell'ordine di trasferimento.

## <a name="stock-counts"></a>Conteggi scorte

I conteggi scorte possono essere pianificati o non pianificati. I conteggi di scorte programmate sono avviati presso la sede principale, la quale specifica gli articoli da conteggiare. La sede principale crea un documento relativo ai conteggi che si può ricevere in punto vendita, dove le quantità delle scorte disponibili effettive vengono inserite in MPOS oppure in POS cloud. I conteggi scorte non pianificati vengono avviati in un punto vendita e le quantità delle scorte disponibili effettive vengono aggiornate in MPOS o POS cloud. A differenza dei conteggi scorte pianificati, i conteggi scorte non pianificati non dispongono di un elenco predefinito di elementi. Al termine di un conteggio scorte di entrambi i tipi, questo viene impegnato e inviato alla sede principale. Presso la sede centrale, il conteggio viene convalidato e registrato.

## <a name="inventory-lookup"></a>Ricerca in magazzino

La quantità corrente di prodotto disponibile per più catene e magazzini può essere visualizzata nella pagina Ricerca in magazzino. Oltre alla quantità corrente di scorte disponibili, le quantità available-to-promise (ATP) future possono essere visualizzate per ogni singolo punto vendita. A questo scopo, selezionare il punto vendita di cui si desidera visualizzare il valore ATP, quindi fare clic su **Mostra disponibilità punto vendita**.
