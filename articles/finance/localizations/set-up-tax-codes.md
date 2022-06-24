---
title: Impostare i codici di imposta
description: Questo articolo spiega come impostare i codici imposta nel servizio Calcolo imposte.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 1bc250716763ce9d8e25c8850c8a3676bf65fb0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862930"
---
# <a name="set-up-tax-codes"></a>Impostare i codici di imposta

[!include [banner](../includes/banner.md)]

Questo articolo spiega come impostare i codici imposta nel servizio Calcolo imposte. Include l'impostazione di uno scenario semplice per usare il codice imposta e informazioni su alcune funzionalità avanzate del codice imposta per scenari complessi.

> [!IMPORTANT]
> L'impostazione dei codici imposta nel servizio Calcolo imposte è indipendente dalla persona giuridica. È possibile completare questa configurazione in Regulatory Configuration Service (RCS) solo una volta. I codici imposta vengono sincronizzati automaticamente con Microsoft Dynamics 365 Finance quando abiliti il servizio Calcolo imposte per una persona giuridica selezionata in Finance.

## <a name="simple-setup"></a>Impostazione semplice

Segui questi passaggi per utilizzare un codice imposta in uno scenario semplice, ad esempio uno scenario in cui è presente una sola aliquota fiscale.

1. Accedi a [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Vai a **Aree di lavoro** \> **Funzionalità di globalizzazione** \> **Calcolo imposte**.
3. Seleziona la funzionalità e la versione che vuoi impostare, quindi seleziona **Modifica**.
4. Nella scheda **Generale** seleziona **Versione configurazione**.
5. Nella scheda **Codici imposta** seleziona **Aggiungi** e inserisci il codice imposta e una descrizione.
6. Seleziona **Origine calcolo**. Un'origine di calcolo è un gruppo di metodi definiti nella versione di configurazione dell'imposta selezionata. Per questo semplice scenario, seleziona **Per importo netto**.
7. Seleziona **Salva**. Diventano disponibili più campi, in base all'origine del calcolo selezionata.
8. Nella scheda dettaglio **Aliquote** seleziona **Aggiungi** per aggiungere un'aliquota per questo codice imposta.
9. Seleziona **Salva**.

## <a name="calculation-origin"></a>Origine calcolo

L'origine del calcolo definisce come vengono calcolati l'importo della base imponibile e l'importo dell'imposta. Si configura tramite la configurazione delle imposte nell'area di lavoro **Creazione di report elettronici**. I valori seguenti sono disponibili nel campo **Origine calcolo**:

- Per importo netto
- Per importo lordo
- Per quantità
- Per margine
- Imposta sull'imposta

### <a name="by-net-amount"></a>Per importo netto

Se selezioni **Per importo netto** nel campo **Origine calcolo**, l'importo dell'imposta viene calcolato come percentuale dell'importo dell'acquisto o della vendita, escludendo qualsiasi altro codice imposta.

Ad esempio, l'aliquota fiscale è del 25%, la riga della fattura mostra una quantità di 10 articoli a 1,00 ciascuno e al cliente è consentito uno sconto di riga del 10%. In questo caso, gli importi vengono calcolati nele seguente modo:

- **Importo netto:** (10 × 1,00) – 10% = 9,00 
- **IVA:** 9,00 × 25% = 2,25 
- **Importo fattura totale:** 9,00 + 2,25 = 11,25

### <a name="by-gross-amount"></a>Per importo lordo

Se selezioni **Per importo lordo** nel campo **Origine calcolo**, l'importo dell'imposta viene calcolato come percentuale dell'importo delle vendite lordo. L'importo lordo è l'importo netto della riga più eventuali imposte e commissioni per la riga tranne l'imposta dove il campo **Origine calcolo** è impostato su **Per importo lordo**.

Ad esempio, l'ufficio tributario richiede il versamento di imposte speciali su un articolo. Gli importi delle imposte vengono aggiunti all'importo netto prima del calcolo dell'imposta. Vengono utilizzati i codici imposta seguenti:

- **Imposta 1** – L'aliquota è del 10% e il metodo di calcolo **Per importo netto** viene utilizzato.
- **Imposta 2** – L'aliquota è del 20% e il metodo di calcolo **Per importo netto** viene utilizzato.
- **Aliquota imposta** – L'aliquota è del 25% e il metodo di calcolo **Per importo lordo** viene utilizzato.

Se l'importo netto è 10,00, l'importo dell'imposta 1 è 1,00 (10,00 × 10%) e l'importo dell'imposta 2 è 2,00 (10,00 × 20%). In questo caso, gli importi vengono calcolati nele seguente modo: 

- **Importo lordo:** Importo netto + Importo Imposta 1 + Importo Imposta 2 = 10,00 + 1,00 + 2,00 = 13,00 
- **Importo imposta:** 13,00 × 25% = 3,25 
- **Totale imposte:** 1,00 + 2,00 + 3,25 = 6,25 
- **Importo fattura totale:** 10,00 + 6,25 = 16,25

### <a name="by-quantity"></a>Per quantità

Quando selezioni **Per quantità** nel campo **Origine calcolo**, l'importo imposta viene calcolato come importo fisso per unità e moltiplicato per la quantità immessa nella riga del documento. L'importo per unità è specificato nella scheda dettaglio **Aliquote**.

Ad esempio, il codice imposta è impostato come 1,20 per unità. In una riga della fattura di vendita vengono vendute 25 unità di un articolo. In questo caso, l'importo delle imposte viene calcolato come 25 × 1,20 = 30,00.

### <a name="by-margin"></a>Per margine

Se selezioni **Per margine** nel campo **Origine calcolo**, l'importo dell'imposta viene calcolato come percentuale del margine delle vendite. Il margine delle vendite è l'importo delle vendite meno l'importo dei costi. Questo metodo di calcolo si applica solo alle transazioni di vendita.

Ad esempio, l'aliquota fiscale è del 25%, la riga della fattura mostra una quantità di 10 articoli a 10,00 ciascuno e il costo per articolo è 6. In questo caso, gli importi vengono calcolati nele seguente modo:

- **Margine vendite:** 10 × ( 10,00 – 6,00) = 40,00
- **Importo imposta:** 40,00 × 25% = 10,00
- **Importo fattura totale:** 100,00 + 10,00 = 110,00

### <a name="tax-on-tax"></a>Imposta sull'imposta

Se selezioni **Imposte su imposte** nel campo **Origine calcolo**, l'IVA viene calcolata come percentuale di tutti gli altri importi imposte nella stessa riga del documento.

Ad esempio, vengono utilizzati i codici imposta seguenti:

- **Imposta 1** – L'aliquota è del 10% e il metodo di calcolo **Per importo netto** viene utilizzato.
- **Imposta 2** – L'aliquota è del 20% e il metodo di calcolo **Per importo netto** viene utilizzato.
- **Imposta su imposta** – L'aliquota è del 25% e il metodo di calcolo **Imposta su imposta** viene utilizzato.

In questo caso, gli importi vengono calcolati nele seguente modo:

- **Importo netto:** 10,00 
- **Imposta 1:** 10,00 × 10% = 1,00 
- **Imposta 2:** 10,00 × 20% = 2,00 
- **Imposta su imposta:** 3,00 × 25% = 0,75
- **Totale imposta:** 1,00 + 2,00 + 0,75 = 3,75 
- **Importo fattura totale:** 10,00 + 3,75 = 13,75

## <a name="advanced-functionality"></a>Funzionalità avanzate

In questa sezione vengono illustrate alcune funzionalità avanzate dell'impostazione del codice imposta per scenari complessi.

### <a name="tax-exemption"></a>Esenzione da imposte

Se imposti l'opzione **Esenzione** su **sì** nella scheda dettaglio **Generale** l'importo dell'imposta verrà sempre impostato su 0 (zero), indipendentemente dall'aliquota fiscale effettiva.

Puoi impostare il campo **Codice esenzione** per specificare il motivo dell'esenzione. 

È possibile abilitare la ricerca dei dati master per il campo **Codice esenzione**. In questo modo è possibile selezionare tra i valori del codice esenzione definiti in Finance. Per informazioni su come abilitare la ricerca dei dati mater, vedi [Abilitare la ricerca dei dati master per la configurazione del calcolo delle imposte](tax-service-set-up-environment-master-data-lookup.md).

Ad esempio, l'aliquota fiscale è del 25% e l'opzione **Esenzione** è impostata su **sì** nel codice imposta. Nella riga della fattura è indicata una quantità pari a 10 articoli al prezzo di 1,00 ciascuno e al cliente viene concesso uno sconto riga del 10%. In questo caso, gli importi vengono calcolati nele seguente modo:

- **Importo netto:** (10 × 1,00) – 10% = 9,00 
- **IVA:** 0,00 
- **Importo fattura totale:** 9,00 + 0,00 = 9,00

### <a name="use-tax"></a>IVA intracomunitaria

Se imposti l'opzione **Imposta d'uso** su **sì** nella scheda dettaglio **Generale** l'importo dell'imposta verrà registrato nel conto **Imposta d'uso a debito** invece del conto **Riepilogo fornitore**.

Ad esempio, l'aliquota fiscale è del 25% e l'opzione **Imposta d'uso** è impostata su **sì** nel codice imposta. Nella riga della fattura è indicata una quantità pari a 10 articoli al prezzo di 1,00 ciascuno e al cliente viene concesso uno sconto riga del 10%. In questo caso, gli importi vengono calcolati nele seguente modo:

- **Importo netto:** (10 × 1,00) – 10% = 9,00 
- **Imposta d'uso:** 9,00 × 25% = 2,25
- **Importo fattura totale:** 9,00 + 0,00 = 9,00

> [!IMPORTANT]
> Se le opzioni **Esenzione** e **Imposta d'uso** sono entrambe impostate su **sì** in un codice imposta, il codice verrà riconosciuto come esente da imposta per le operazioni di vendita e come imposta d'uso per le operazioni di acquisto.

### <a name="reverse-charges"></a>Reverse charge

Se imposti l'opzione **Reverse charge** su **sì** nella scheda dettaglio **Generale** l'aliquota fiscale può essere configurata come negativa. Per uno scenario di reverse charge, consigliamo di configurare due codici imposta, uno dei quali ha un'aliquota fiscale positiva e l'altro ha un'aliquota fiscale negativa. Entrambi i codici imposta devono avere lo stesso valore di aliquota e l'opzione **Reverse Charge** deve essere impostata su **sì** nel codice imposta con aliquota negativa. Per ulteriori informazioni sulla soluzione di reverse charge in Finance, vedi [Meccanismo di reverse charge per lo schema IVA/GST](emea-reverse-charge.md).

Ad esempio, vengono determinati due codici imposta su una riga di fattura. Un'aliquota d'imposta è del 25%. L'altra aliquota fiscale è del -25% e l'opzione **Reverse Charge** è impostata su **sì** nel secondo codice imposta. La riga della fattura mostra una quantità di 10 articoli a 1,00 ciascuno. In questo caso, gli importi vengono calcolati nele seguente modo:

- **Importo netto:** (10 × 1,00) = 10,00 
- **Codice imposta 1:** 10,00 × 25% = 2,50
- **Codice imposta 2:** 10 × -25% = -2,50
- **Importo fattura totale:** 10,00 + 2,50 -2,50 = 10,00

### <a name="exclusion-from-base-amount-calculations"></a>Esclusione dal calcolo dell'importo di base

Se imposti l'opzione **Escludi dal calcolo dell'importo di base** su **sì** nella scheda dettaglio **Generale** l'importo dell'imposta calcolato del codice imposta è escluso dall'importo della base imponibile per altri calcoli del codice imposta nello scenario comprensivo di prezzo.

Per altre informazioni vedi [Calcolare le imposte da aggiungere al prezzo quando l'opzione per i prezzi con le imposte è abilitata](global-exclude-from-tax-base-amount-calculation.md).

### <a name="rates"></a>Tassi

Nella scheda dettaglio **Aliquota** puoi definire diverse aliquote d'imposta per diversi intervalli di importi imponibili. Per calcolare l'importo dell'imposta, il servizio Calcolo imposte utilizza sempre l'aliquota che corrisponde all'importo della base imponibile.

Ad esempio, le aliquote fiscali potrebbero essere configurate come mostrato nella tabella seguente.

| Importo minimo | Quantità massima | Aliquota IVA   |
| -------------- | -------------- | ---------- |
| 0              | 1.000          | 10 per cento |
| 1.000          | 5.000          | 15 per cento |
| 5.000          | 10,000         | 20 per cento |
| 10,000         | 0              | 30 per cento |

In questo caso, l'importo dell'imposta viene calcolato nele seguente modo:

- Se l'importo della base imponibile è 300,00, l'aliquota fiscale è del 10% e l'importo dell'imposta è 300,00 × 10% = 30,00.
- Se l'importo della base imponibile è 3.000,00, l'aliquota fiscale è del 15% e l'importo dell'imposta è 3.000,00 × 15% = 450,00.
- Se l'importo della base imponibile è 6.000,00, l'aliquota fiscale è del 20% e l'importo dell'imposta è 6.000,00 × 10% = 1.200,00.
- Se l'importo della base imponibile è 20.000,00, l'aliquota fiscale è del 30% e l'importo dell'imposta è 20.000,00 × 30% = 6.000,00.

> [!NOTE]
> Se l'importo della base imponibile può corrispondere sia all'importo massimo su una riga che all'importo minimo sull'altra riga, la base utilizzerà l'aliquota fiscale che corrisponde all'importo base minimo. Ad esempio, se l'importo della base imponibile è 1000,00, l'aliquota fiscale è del 15% e l'importo dell'imposta è 1.000,00 × 15% = 150,00.

### <a name="limits"></a>Limiti

Nella scheda dettaglio **Limiti** puoi definire i limiti di imposta per sostituire l'importo dell'imposta calcolato se l'importo dell'imposta rientra nell'intervallo minimo/massimo.

- Se l'importo dell'imposta calcolato è maggiore o uguale all'importo massimo dell'imposta configurato nella scheda dettaglio **limiti** l'importo dell'imposta finale è uguale all'importo massimo dell'imposta.
- Se l'importo dell'imposta calcolato è inferiore all'importo minimo dell'imposta configurato nella scheda dettaglio **limiti** l'importo dell'imposta finale è 0 (zero).

Ad esempio, i limiti di imposta sono configurati nel modo seguente:

- **Importo imposta minimo:** 100 
- **Importo imposta massimo:** 1.000

Se l'importo dell'imposta calcolato è 2.000, l'importo dell'imposta finale è 1.000.

Se l'importo dell'imposta calcolato è 500, l'importo dell'imposta finale è 500.

Se l'importo dell'imposta calcolato è 80, l'importo dell'imposta finale è 0 (zero).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
