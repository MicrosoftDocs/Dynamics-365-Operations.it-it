---
title: Impostare tassi d'interesse per un codice interessi
description: I codici interessi contengono le impostazioni che determinano quando gli interessi vengono addebitati e come vengono calcolati nei conti scaduti.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 665c58fd29fb986bf51e10f5814c4793940c0a47
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "317777"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a>Impostare tassi d'interesse per un codice interessi

[!include [banner](../includes/banner.md)]

I codici interessi contengono le impostazioni che determinano quando gli interessi vengono addebitati e come vengono calcolati nei conti scaduti.

È possibile impostare un singolo codice interessi e applicarlo a più profili di registrazione cliente, codici di fatturazione o righe specifiche della fattura. Quando i dettagli del codice interessi vengono modificati, tutte le funzionalità che utilizzano il codice implementeranno automaticamente le modifiche nelle nuove transazioni. Per ogni codice interessi, è possibile impostare due tipi di tassi:
-   Tassi per gli interessi attivi - Rappresentano i ricavi ottenuti tramite l'addebito di interessi sulle fatture o sulle note d'interesse.
-   Tassi per gli interessi passivi - Rappresentano un costo pagato per l'interesse sulle note di accredito.

Questi tipi di tassi possono essere utilizzati contemporaneamente e nello stesso codice interessi. I tassi d'interesse possono essere basati su tre tipi di calcolo:
-   Interesse in base a percentuale.
-   Interesse in base a importo.
-   Interesse in base a intervallo, che determina una singola percentuale o un singolo importo.

Quando si utilizza un codice interessi per calcolare gli interessi, viene creata una nota d'interesse separata per ogni tasso d'interesse in vigore nel periodo in cui il pagamento ha superato la scadenza della transazione. Utilizzare la scheda **Redditi** nella pagina **Codice interessi** per impostare i tassi per l'interesse guadagnato con l'addebito di interessi. Per impostare i tassi per gli interessi pagati, utilizzare invece la scheda **Pagamenti**.

## <a name="interest-rates-based-on-a-percentage"></a>Tassi d'interesse in base a una percentuale
È possibile impostare tassi d'interesse che calcolano una percentuale specificata.

- L'importo degli interessi si applica a tutte le valute.
- È possibile immettere limiti per l'importo interessi facoltativi.
- <strong>Percentuale</strong> è selezionato nel campo <strong>Calcola interessi in base a</strong> nella pagina <strong>Imposta codici interessi</strong>.

Ad esempio, per impostare un codice interessi che valuta un interesse del 5% per ogni due mesi in cui il pagamento della fattura supera la data di scadenza della transazione, immettere 2 nel campo **Calcola interessi ogni** quindi selezionare **Mese**.

## <a name="interest-rates-based-on-amounts"></a>Tassi d'interesse in base agli importi
È possibile impostare tassi d'interesse che calcolano una quantità specificata per valuta.
- Un importo interessi è specificato per ciascuna valuta relativa al codice interessi.
- È possibile immettere limiti per l'importo interessi facoltativi.
- **Importo** è selezionato nel campo**Calcola interessi in base a** nella pagina **Imposta codici interessi**.

Ad esempio, per impostare un codice interessi che valuta un interesse pari a 25,00 per ogni 20 giorni in cui il pagamento della fattura supera la data di scadenza della transazione, immettere 20 nel campo **Calcola interessi ogni** e selezionare **Giorno**.

## <a name="interest-rates-based-on-ranges"></a>Tassi d'interesse in base agli intervalli
È possibile impostare tassi d'interesse che variano a seconda dell'importo scaduto e del numero di giorni o mesi accumulati dalla scadenza della fattura.
-   È possibile utilizzare la scheda **Utili per valuta** per definire le impostazioni specifiche degli interessi per ciascuna valuta. Qui è inoltre possibile definire l'intervallo.
-   Utilizzare il pulsante **Intervalli** per aggiungere righe che rappresentano gli intervalli che si desidera impostare. Il valore **Da** rappresenta l'inizio dell'intervallo e il numero in **Valore d'interesse** rappresenta una percentuale o un importo, a seconda della selezione nel campo **Calcola interessi in base a** nella pagina **Imposta codici interessi**.

## <a name="example-1-interest-by-range--amount"></a>Esempio 1: Interessi in base a intervallo = Importo
Si imposta un codice interessi che valuta gli interessi una volta per ogni tre mesi in cui il pagamento della fattura supera la data di scadenza della transazione. Si desidera basare il calcolo su un valore di interesse percentuale, in base a intervalli di importi graduali. Il valore degli interessi corrisponderà all'1% per gli importi della fattura fino a 1.000,00, al 2% per gli importi da 1.001,00 a 5.000,00 e al 3% per gli importi superiori a 5.000,00. I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.

| **Nome campo**                  | **Valore campo** |
|---------------------------------|-----------------|
| **Codice interessi**               | 3M%ByAmt        |
| **Calcola interessi ogni**    | 3/Mese         |
| **Interessi in base a intervallo**           | Importo          |
| **Calcola interessi in base a** | Percentuale      |

Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.

| **Dal valore** | **Valore interessi** |
|----------------|--------------------|
| 0              | 1                  |
| 1,001          | 2                  |
| 5,001          | 3                  |


## <a name="example-2-interest-by-range--days"></a>Esempio 2: Interessi in base a intervallo = Giorni
--------------------------------------------------

Si imposta un codice interessi che valuta gli interessi una volta per ogni 15 giorni in cui il pagamento della fattura supera la data di scadenza della transazione. Si desidera basare il calcolo su un valore di interesse importo, in base a intervalli di giorni graduali. Il valore degli interessi sarà pari a 10,00 per 15 giorni durante i primi 60 giorni, 15,00 per 15 giorni durante l'intervallo di giorni da 61 a 90 e 20,00 per 15 giorni dal giorno 91 in poi. I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.

| **Nome campo**                  | **Valore campo** |
|---------------------------------|-----------------|
| **Codice interessi**               | 15DAmtXDay      |
| **Calcola interessi ogni**    | 15/Giorno          |
| **Interessi in base a intervallo**           | Giorni            |
| **Calcola interessi in base a** | Importo          |

Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.

| **Dal valore** | **Valore interessi** |
|----------------|--------------------|
| 0              | 10                 |
| 61             | 15                 |
| 91             | 20                 |


## <a name="example-3-interest-by-range--months"></a>Esempio 3: Interessi in base a intervallo = Mesi
----------------------------------------------------

Si imposta un codice interessi che valuta gli interessi una volta per ogni mese in cui il pagamento della fattura supera la data di scadenza della transazione. Si desidera basare il calcolo su un valore di interesse percentuale, in base a intervalli di mesi graduali. Il valore degli interessi sarà dell'1,5% al mese per i primi tre mesi di ritardo, del 2,0% al mese per i tre mesi successivi e del 2,5% al mese per ogni mese successivo ai primi sei. I valori del campo del codice interessi vengono impostati nel modo indicato di seguito.

| **Nome campo**                  | **Valore campo** |
|---------------------------------|-----------------|
| **Codice interessi**               | 1M%ByMth        |
| **Calcola interessi ogni**    | 1/Mese         |
| **Interessi in base a intervallo**           | Mesi          |
| **Calcola interessi in base a** | Percentuale      |

Le informazioni sull'intervallo vengono impostate nel modo indicato di seguito.

| **Dal valore** | **Valore interessi** |
|----------------|--------------------|
| 0              | 1.5                |
| 4              | 2                  |
| 7              | 2,5                |

## <a name="new-versions"></a>Nuove versioni
I codici interessi contengono una data valida. Se si desidera modificare il tasso d'interesse, è possibile creare una **nuova versione** valida a partire da una data futura.

Per visualizzare versioni diverse, è possibile utilizzare l'opzione di menu **In data** per selezionare la data limite. È inoltre possibile selezionare **Visualizza tutti i record** per visualizzare tutti i codici interessi nella pagina.



