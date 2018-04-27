---
title: Metodi di calcolo IVA nel campo Origine
description: Questo articolo illustra le opzioni nel campo Origine nella pagina Codici IVA e spiega come viene calcolata l'IVA in base all'opzione selezionata per un codice IVA.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b36b290026f384109ccd710a9979892dd5268307
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-calculation-methods-in-the-origin-field"></a>Metodi di calcolo IVA nel campo Origine

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

Questo articolo illustra le opzioni nel campo Origine nella pagina Codici IVA e spiega come viene calcolata l'IVA in base all'opzione selezionata per un codice IVA.

Per ogni codice IVA creato nella pagina Codici IVA è necessario selezionare il metodo di calcolo da applicare all'importo imponibile nel campo Origine.

## <a name="percentage-of-net-amount"></a>Percentuale dell'importo netto
Il metodo di calcolo Percentuale dell'importo netto è il valore predefinito nel campo Origine. L'IVA viene calcolata come percentuale dell'importo di acquisto o di vendita, esclusi gli altri importi IVA.
### <a name="example"></a>Esempio

L'aliquota IVA è 25%. Si supponga che nella riga della fattura sia indicata una quantità pari a 10 articoli al prezzo di 1,00 ciascuno e che al cliente venga concesso uno sconto riga del 10%. Importo netto: (10 x 1,00) -10% = 9,00 IVA: 9,00 x 25% = 2,25 Importo totale: 9,00 + 2,25 = 11,25

## <a name="percentage-of-gross-amount"></a> Percentuale dell'importo lordo
Se si seleziona il metodo Percentuale dell'importo lordo, l'IVA viene calcolata come percentuale dell'importo di vendita lordo. L'importo lordo è l'importo netto della riga più eventuali imposte e commissioni per la riga tranne l'imposta con Origine = Percentuale dell'importo lordo.
### <a name="example"></a>Esempio

L'ufficio tributario richiede il versamento di imposte speciali su un articolo. Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'IVA. Dati i codici IVA seguenti:
-   IMPOSTA 1 = 10%, con il metodo di calcolo Percentuale dell'importo netto
-   IMPOSTA 2 = 20%, con il metodo di calcolo Percentuale dell'importo netto
-   IVA = 25%, con il metodo di calcolo Percentuale dell'importo lordo

Se l'importo netto è 10,00, IMPOSTA 1 sarà 1,00 (10,00 x 10%) e IMPOSTA 2 sarà 2,00 (10,00 x 20%). Gli importi sarebbero i seguenti: Importo lordo: Importo netto + importo IMPOSTA 1 + importo IMPOSTA 2 (10,00 + 1,00 + 2,00) = 13,00 IVA = 13,00 x 25% = 3,25 Totale IMPOSTE e IVA: 1,00 + 2,00 + 3,25 = 6,25 Importo totale: 10,00 + 6,25 = 16,25

| **Nota**                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Un solo codice IVA con Origine = Percentuale dell'importo lordo può essere utilizzato per una transazione. Se più di un codice di questo tipo viene determinato per una transazione, verrà visualizzato l'errore che l'IVA non può essere calcolata. |


<a name="percentage-of-sales-tax"></a>Percentuale IVA
-----------------------

Quando si seleziona Percentuale IVA nel campo Origine, l'IVA viene calcolata come percentuale dell'IVA selezionata nel campo IVA sull'IVA. Viene innanzitutto calcolata l'IVA selezionata nel campo IVA sull'IVA. Il secondo importo IVA viene quindi calcolato in base al primo importo.
### <a name="example"></a>Esempio

Dati i codici IVA seguenti:
-   IMPOSTA 1 = 10%, con il metodo Percentuale dell'importo netto
-   IMPOSTA 2 = 20%, con il metodo Percentuale del IVA, con Imposta 1 nel campo IVA sull'IVA
-   IVA = 25%, con il metodo Percentuale dell'importo lordo

Importo netto: 10,00 IMPOSTA 1: 10,00 x 10% = 1,00 IMPOSTA 2: 1,00 x 20% = 0,20 Importo lordo: 10,00 + 1,00 + 0,20 = 11.20 IVA: 11,20 x 25% = 2,80 Totale IMPOSTE e IVA: 1,00 + 0,20 + 2,80 = 4,00 Importo totale: 10,00 + 4,00 = 14,00

| **Nota**                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I calcoli di imposta su imposta multilivello non sono possibili. Un'imposta non può essere calcolata in base a un'imposta che viene già calcolata in base a un'altra imposta. Più codici imposta su imposta a livello singolo possono essere calcolati per una transazione. |

## <a name="amount-per-unit"></a> Importo unitario
Quando si seleziona Importo unitario nel campo Origine, l'IVA viene calcolata come importo fisso per unità moltiplicato per la quantità immessa nella riga del documento. Un'unità deve essere selezionata nel campo Unità. L'importo unitario è specificato nella pagina Valori codice IVA.
### <a name="example"></a>Esempio

Il codice IVA è impostato come: 1,20 USD per unità = scatola In una riga di fattura di vendita 25 scatole di un articolo sono vendute L'IVA è calcolata come 25 x 1,20 = 30,00

| **Nota**                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se la transazione è stata immessa in un'unità diversa dall'unità specificata nel codice IVA, viene convertita automaticamente in base alle conversioni unità impostate nella pagina Conversioni unità. |

###  <a name="amount-per-unit-additional-option"></a> Importo unitario con opzioni aggiuntive

Nella scheda Calcolo, è possibile scegliere se l'IVA per un importo unitario viene calcolata prima di altri codici imposta e viene aggiunta all'importo netto prima che altri codici con Origine = Percentuale dell'importo netto vengano calcolati.

### <a name="examples"></a>Esempi

Si presupponga il calcolo di 2 codici IVA per una transazione:

-   IMPOSTA: Origine = Importo unitario e IVA, il valore viene impostato su 5,00 per unità = pz
-   IVA: Origine = come illustrato negli esempi successivi, il valore viene impostata su 25%

Vendiamo 1 pezzo di un articolo al prezzo unitario di 10,00
#### <a name="example-1"></a>Esempio 1

IVA: Origine = Metodo Percentuale dell'importo lordo L'opzione Calcola prima dell'IVA non ha effetto, poiché IVA viene calcolata come percentuale dell'importo lordo. IMPOSTA: 1 x 5,00 = 5,00 Importo lordo: 10,00 + 5,00 = 15,00 IVA: 15,00 x 25% = 3,75 Totale IVA: 5,00 + 3,75 = 8,75 Importo totale: 10,00 + 8,75 = 18,75

#### <a name="example-2"></a>Esempio 2

IVA: Origine = Percentuale dell'importo netto L'opzione Calcola prima dell'IVA non è selezionata per il calcolo di IMPOSTA. Importo netto: 10,00 IMPOSTA: 1 x 5,00 = 5,00 IVA: 10,00 x 25% = 2,50: Totale IVA: 5,00 + 2,50 = 7,50 Importo totale: 10,00 + 7,50 = 17,50

#### <a name="example-3"></a>Esempio 3

IVA: Origine = Percentuale dell'importo netto L'opzione Calcola prima dell'IVA è selezionata per il calcolo di IMPOSTA. Importo netto: 10,00 IMPOSTA: 1 x 5,00 = 5,00 IVA: (10,00 + 5,00) x 25% = 3,75: Totale IVA: 5,00 + 3,75 = 8,75 Importo totale: 10,00 + 8,75 = 18,75

#### <a name="example-4"></a>Esempio 4

Il risultato degli esempi 3 e 1 è lo stesso in quanto è presente una sola imposta. Si supponga di avere due IMPOSTE e una sola di esse viene inclusa nell'importo netto per il calcolo dell'IVA: IMPOSTA 1: 5,00, con il metodo Importo unitario e l'opzione Calcola prima dell'IVA selezionata IMPOSTA 2: 2,50, con il metodo Importo unitario e l'opzione Calcola prima dell'IVA non selezionata IVA: 25%, con il metofo Percentuale dell'importo netto Importo netto: 10,00 IMPOSTA 1: 1 x 5,00 = 5,00 IMPOSTA 2: 1 x 2,50 = 2,50 Importo netto soggetto a IVA: 10,00 + 5,00 = 15,00 IVA: 15,00 x 25% = 3,75 Totali IVA, incluse imposte: 5,00 + 2,50 + 3,75 = 11,25 Importo totale: 10,00 + 11,25 = 21,25 Il 25% di IVA è calcolato per la somma dell'importo netto (10,00) + IMPOSTA 1 (5,00) = 15,00. Dopo il calcolo dell'IVA, all'importo IVA viene aggiunto l'importo di IMPOSTA 2.

## <a name="calculated-percentage-of-net-amount"></a> Percentuale calcolata dell'importo netto
La Percentuale calcolata dell'importo netto gestisce il calcolo dell'IVA in modo diverso a seconda dell'impostazione del parametro Importo IVA inclusa del documento o del giornale di registrazione.
### <a name="example-1"></a>Esempio 1

Il documento/giornale di registrazione è impostato su Importo IVA inclusa =Sì Importo riga di transazione: 10,00 Aliquota IVA: 25%: IVA: Importo riga di transazione x aliquota IVA (10,00 x 25%) = 2,50 Importo imponibile (importo origine): Importo riga di transazione - IVA (10,00 - 2,50) = 7,50

### <a name="example-2"></a>Esempio 2

Il documento/giornale di registrazione è impostato su Importo IVA inclusa =No Importo riga di transazione: 10,00 Aliquota IVA: 25%: IVA: (Importo riga di transazione x aliquota IVA) / (100 - aliquota IVA) (10,00 x 25%) / (100% - 25%) = 3,33 Importo imponibile (importo origine): Importo riga di transazione = 10,00



<a name="see-also"></a>Vedere anche
--------

[Determinare le aliquote IVA in base ai campi Imponibile marginale e Metodo di calcolo](marginal-base-field.md)

[Opzioni Importo totale e Intervallo per i codici IVA](whole-amount-interval-options-sales-tax-codes.md)




