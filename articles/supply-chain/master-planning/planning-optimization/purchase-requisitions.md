---
title: Richieste di acquisto
description: In questo argomento viene descritto come le richieste di acquisto sono supportate in Ottimizzazione pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8075f8d7c3868c6d6012edbce17dbbb4749209ab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992346"
---
# <a name="purchase-requisitions"></a>Richieste di acquisto

La pianificazione generale può rifornire le richieste di acquisto approvate. Pertanto, per coprire le richieste di acquisto, gli utenti non devono utilizzare un flusso di lavoro per creare ordini fornitore. Invece, le richieste di acquisto possono essere coperte dalla pianificazione generale. Grazie a questa funzionalità, una richiesta di acquisto può produrre un ordine fornitore, un ordine di trasferimento o un ordine di produzione, a seconda del valore **Tipo di ordine pianificato** impostato per il prodotto correlato.

## <a name="enable-master-plans-to-include-requisitions"></a>Abilitare i piani generali per includere le richieste

Per includere richieste durante il calcolo della copertura per un piano generale, attenersi alla seguente procedura.

1. Andare a **Pianificazione generale** \> **Imposta** \> **Piani** \> **Piani generali**.
1. Selezionare o creare un piano generale.
1. Nella Scheda dettaglio **Generale**, impostare l'opzione **Includi richieste** su *Sì*.
1. Ripetere i passaggi 2 e 3 per ogni piano generale aggiuntivo in cui si desidera includere le richieste.

## <a name="approved-requisitions-time-fence"></a>Intervallo temporale richieste approvate

L'opzione *Intervallo temporale richieste approvate* stabilisce quanto indietro (in giorni) un piano generale includerà la domanda proveniente dalle richieste di rifornimento approvate. È possibile impostare un intervallo di tempo per le richieste approvate sia a livello di gruppo di copertura che a livello di piano generale.

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a>Impostare l'intervallo di tempo per le richieste approvate per un gruppo di copertura

1. Andare a **Pianificazione generale** \> **Imposta** \> **Copertura** \> **Gruppi di copertura**.
1. Creare o selezionare un gruppo di copertura.
1. Nella Scheda dettaglio **Altro**, impostare il campo **Intervallo temporale richieste approvate (giorni)** sul numero di giorni da includere nell'intervallo temporale.
1. Ripetere i passaggi 2 e 3 per ogni gruppo di copertura aggiuntivo in cui si desidera impostare un intervallo di tempo per le richieste approvate.

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a>Impostare l'intervallo di tempo per le richieste approvate per i singoli piani generali

Quando si imposta un intervallo temporale per le richieste approvate per un singolo piano generale, l'impostazione sostituisce l'impostazione dell'intervallo temporale per qualsiasi gruppo di copertura applicabile.

1. Andare a **Pianificazione generale** \> **Imposta** \> **Piani** \> **Piani generali**.
1. Selezionare o creare un piano generale.
1. Nella Scheda dettaglio **Intervalli temporali in giorni**, impostare il campo **Intervallo temporale richieste approvate (giorni)** sul numero di giorni da includere nell'intervallo temporale.
1. Ripetere i passaggi 2 e 3 per ogni piano generale aggiuntivo in cui si desidera impostare un intervallo di tempo per le richieste approvate.

> [!IMPORTANT]
> **Presto disponibili:** gli intervalli temporali delle richieste approvate non sono ancora supportati per l'ottimizzazione della pianificazione. Fino a quando non sono supportati, tutti i valori immessi nel campo **Intervallo temporale per le richieste approvate (giorni)** verrà ignorato.

## <a name="independent-supply-regardless-of-coverage-code"></a>Fornitura indipendente, indipendentemente dal codice di copertura

Le richieste di acquisto sono sempre coperte da ordini pianificati indipendenti, indipendentemente dal codice di copertura. Questo comportamento garantisce una chiara tracciabilità e flussi di lavoro tra le richieste di acquisto e gli ordini di rifornimento.

### <a name="example-1"></a>Esempio 1

Un prodotto è impostato in modo che abbia un valore **Codice di copertura** pari a *Min/max* . Presenta i seguenti stati di inventario e richiesta:

- Quantità scorte disponibili = 10.
- Quantità minima in magazzino = 15.
- Quantità massima in magazzino = 20.
- Esiste una richiesta di acquisto per un pezzo. Ha una data richiesta di oggi.

Quando viene eseguita la pianificazione generale, vengono creati due ordini pianificati: uno per 10 pezzi per rifornire le scorte alla quantità massima e uno per un pezzo per rifornire la richiesta di acquisto.

### <a name="example-2"></a>Esempio 2

Un prodotto è impostato in modo che abbia un valore **Codice di copertura** pari a *Min/max* . Presenta i seguenti stati di inventario e richiesta:

- Quantità scorte disponibili = 17.
- Quantità minima in magazzino = 15.
- Quantità massima in magazzino = 20.
- Esiste una richiesta di acquisto per un pezzo. Ha una data richiesta di oggi.

Quando viene eseguita la pianificazione generale, viene creato un ordine pianificato per un pezzo per rifornire la richiesta di acquisto.

### <a name="example-3"></a>Esempio 3

Un prodotto è impostato in modo che abbia un valore di **Codice di copertura** di *Periodo* e un periodo di sette giorni. Presenta i seguenti stati di inventario, ordine cliente e richiesta:

- Quantità scorte disponibili = 0.
- Esiste un ordine cliente per cinque pezzi. Ha una data di spedizione prevista per oggi più un giorno.
- Esiste una richiesta di acquisto per tre pezzi. Ha una data richiesta di oggi più tre giorni.

Quando viene eseguita la pianificazione generale, vengono creati due ordini pianificati: uno per tre pezzi per rifornire la richiesta di acquisto e uno per cinque pezzi per rifornire la domanda dell'ordine cliente.

> [!NOTE]
> Dopo che un ordine pianificato con pegging a una richiesta di acquisto è stato stabilizzato, il motore di pianificazione mantiene il pegging alla richiesta di acquisto. Se in seguito si scopre che nell'ordine stabilizzato manca una quantità necessaria per soddisfare la richiesta di acquisto, il sistema creerà un nuovo ordine pianificato per la differenza.

Per ulteriori informazioni sulle richieste di acquisto, vedere [Panoramica della richiesta di acquisto](../../procurement/purchase-requisitions-overview.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]