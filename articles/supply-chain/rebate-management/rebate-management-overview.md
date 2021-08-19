---
title: Panoramica del modulo di gestione degli sconti
description: In questo argomento viene fornita una panoramica del modulo di gestione degli sconti per Microsoft Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 136e528093e6e73ffe090cea0c02a4cdbf787c5efc3d9c0664869c995a682daa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720254"
---
# <a name="rebate-management-module-overview"></a>Panoramica del modulo di gestione degli sconti

[!include [banner](../includes/banner.md)]

Puoi usare il modulo **Gestione degli sconti** per creare contratti, transazioni o accordi tra la tua azienda e i clienti o i fornitori, in modo da poter calcolare sconti, detrazioni e royalty. La gestione degli sconti tiene traccia e mantiene le transazioni di sconti e detrazioni in una posizione centrale in cui gli utenti possono crearle, rivederle ed elaborarle in modo efficace.

La gestione degli sconti supporta la creazione, la manutenzione e l'elaborazione degli *sconti*. Uno sconto è la restituzione di una parte del prezzo di acquisto da parte di un venditore o di un acquirente. Gli sconti si basano in genere sull'acquisto di una quantità o valore specifico di merci durante un periodo specifico. A differenza dei ribassi, gli sconti vengono effettuati dopo che l'importo dell'acquisto è stato completamente fatturato.

La gestione degli sconti supporta anche le *detrazioni*. Una detrazione è un compenso, un corrispettivo o una commissione pagata per una licenza o il privilegio di utilizzare la proprietà intellettuale come marchio, copyright o brevetto, o per il privilegio di utilizzare una risorsa naturale per uno scopo come pesca, caccia o estrazione mineraria. Le detrazioni sono generalmente calcolate come percentuale del ricavo o del profitto derivante dall'utilizzo realizzato. Più viene utilizzata la proprietà intellettuale o la risorsa naturale, maggiore è la detrazione che si ottiene.

Inoltre, la gestione degli sconti supporta le *royalty* del cliente. Le royalty sono pagamenti che una parte effettua al licenziatario o all'affiliato per il diritto di utilizzare un bene.

La gestione degli sconti consente di definire i profili di registrazione per accantonamenti, sconti e annullamenti. Inoltre, le registrazioni possono essere definite per un cliente o fornitore specifico. In questo modo, le transazioni che non si applicano a tutti gli scenari di clienti o fornitori possono essere tracciate tramite registrazioni.

Le transazioni di sconto vengono generate automaticamente, in base al metodo di calcolo selezionato e pianificato nei processi batch. Inoltre, puoi impostare flussi di lavoro per gestire, rivedere e approvare gli accordi.

## <a name="basis-calculation"></a>Base di calcolo

Gli sconti dei clienti, le royalty dei clienti e gli sconti dei fornitori possono tutti utilizzare una base diversa, a seconda delle esigenze aziendali:

- Gli sconti dei clienti possono essere basati su ordini cliente, bolle di consegna o fatture.
- Le royalty dei clienti possono essere basate su ordini cliente, bolle di consegna o fatture pagate.
- Gli sconti dei fornitori possono essere basati su ordini fornitore o ordini cliente. Possono essere calcolati in base ai prodotti acquistati dal fornitore di sconti e venduti ai clienti tramite fatture di vendita.

## <a name="flexible-calculations"></a>Calcoli flessibili

I periodi di calcolo dello sconto sono disponibili sia per le transazioni con i clienti che con i fornitori. Un periodo di calcolo definisce la durata della transazione, la frequenza di calcolo e il periodo di calcolo. Gli sconti possono essere accumulati in base alle quantità o agli importi dell'ordine cliente per i prodotti qualificati durante il periodo di sconto.

Per ogni calcolo del contratto, è possibile impostare uno dei seguenti periodi:

- Fattura
- Giorno
- Settimana
- Mese
- Trimestre
- Anno
- Periodo personalizzato
- Qualsiasi multiplo di uno qualsiasi dei periodi elencati in precedenza

Il calcolo può essere applicato a singoli clienti e prodotti, gruppi di clienti e prodotti o tutti i clienti e prodotti. Gli sconti con più righe di dettaglio possono avere intervalli di date idonee diversi. I periodi di accantonamento e richiesta possono differire. Ad esempio, gli accantonamenti possono essere elaborati ogni giorno, mentre le richieste vengono elaborate una volta al mese.

Gli sconti possono essere configurati in base a molti parametri diversi. Ad esempio, possono essere configurati per percentuale, tariffa o importo fisso. Esistono quattro metodi di calcolo principali:

- Graduale
- Cumulativo
- Rolling
- Valore totale

I risultati del calcolo dello sconto possono essere ridotti anche da altri sconti, a seconda che lo sconto sia impostato per essere calcolato in base all'importo netto.

Dal lato del fornitore, gli sconti basati su ordini cliente possono calcolare il prezzo in base a una regola FIFO (first in, first out), l'ultimo prezzo di acquisto, il prezzo di acquisto medio o il prezzo di vendita.

## <a name="rebate-target-transactions"></a>Transazioni di destinazione sconto

Gli output generati dalla transazione o dal contratto di sconto possono essere dati finanziari o articoli.

I risultati finanziari sono determinati dal tipo di pagamento assegnato al contratto dal profilo di registrazione. Questi output possono includere giornali di registrazione detrazione cliente, fatture a testo libero e fatture fornitore. Ai fini del controllo, le transazioni di destinazione sconto per dati finanziari includono un riferimento al contratto di sconto di origine.

Gli output degli articoli creano un ordine cliente per articolo gratuito per sconti cliente e un ordine fornitore per sconti fornitore. Le transazioni di destinazione sconto per articolo contengono opzioni per determinare quale riferimento dello sconto deve essere immesso nell'ordine cliente per articolo gratuito o nell'ordine di acquisto.

## <a name="accurate-rebate-calculations"></a>Calcoli accurati degli sconti

La combinazione delle transazioni associate, la frequenza dei calcoli, la base di calcolo e il metodo di calcolo selezionato determina l'accuratezza e la precisione dei calcoli degli sconti. Gli accantonamenti per sconti possono essere utilizzati per accumulare valori registrati e richiesti.

Gli accantonamenti possono essere gestiti giornalmente, settimanalmente, mensilmente o secondo un periodo personalizzato. Tuttavia, la funzionalità può assegnare o pagare lo sconto, o riceverne il pagamento, a qualsiasi frequenza definita che sia uguale o superiore alla frequenza di fornitura. L'annullamento utilizza la stessa frequenza dello sconto. Gli utenti possono modificare facilmente un piano o gli importi dei pagamenti in qualsiasi momento durante il pagamento.

Gli utenti non devono più gestire transazioni o accantonamenti in due passaggi. Gli accantonamenti e gli annullamenti vengono registrati direttamente nel libro mastro. Inoltre, le note di credito possono essere create automaticamente. Pertanto, vi è piena integrazione tra la contabilità fornitori e la contabilità clienti. Durante l'elaborazione, i calcoli prendono in considerazione sconti di liquidazione, fatture pagate, sconti commerciali e note di credito esistenti per garantire che importi e valori siano calcolati accuratamente.

Quando vengono calcolati gli sconti, il processo crea transazioni che possono essere riviste prima della registrazione. Un processo separato registra le transazioni di gestione degli sconti. È quindi possibile creare un giornale di registrazione, una nota di accredito o una transazione di addebito durante la registrazione nelle transazioni proposte. È possibile ottenere dichiarazioni di rendiconti ed elenchi di transazioni per garantire conformità, efficacia e trasparenza.

## <a name="guaranteed-royalty-payments"></a>Pagamenti di royalty garantiti

Nella gestione degli sconti, la generazione automatica del pagamento consente di gestire le royalty in modo rapido e semplice, anche quando si applicano i minimi garantiti.

## <a name="maximizing-spend-versus-rebates"></a>Massimizzare la spesa rispetto agli sconti

Fornitori e prodotti possono essere raggruppati per territorio e possono essere fornite offerte diverse, a seconda del paese o della regione della transazione. Quando gli utenti selezionano i prodotti, possono definire gli articoli inclusi e il numero di articoli che verranno utilizzati nella liquidazione dello sconto.
