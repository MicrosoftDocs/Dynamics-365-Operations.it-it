---
title: Esempi di definizioni di registrazione
description: L'articolo offre alcuni esempi che mostrano come utilizzare le definizioni di registrazione per gli impegni di spesa di ordini fornitore e le ripartizioni di budget.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 751be602b701ac7a5b593404bf655e1a9852f863
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990491"
---
# <a name="posting-definition-examples"></a>Esempi di definizioni di registrazione

[!include [banner](../includes/banner.md)]

L'articolo offre alcuni esempi che mostrano come utilizzare le definizioni di registrazione per gli impegni di spesa di ordini fornitore e le ripartizioni di budget.

Prima di leggere questo argomento, è consigliabile acquisire familiarità con le definizioni di registrazione e le definizioni di registrazione della transazione. Per ulteriori informazioni, vedere [Definizioni di registrazione](posting-definitions.md). Gli esempi seguenti possono essere impostati nella pagina **Definizioni di registrazione**. Ogni esempio contiene queste sezioni:

-   Definizione di registrazione – criteri di corrispondenza
-   Definizione di registrazione – voci generate
-   Transazioni con i conti, i valori di dimensione e gli importi
-   Voci di contabilità generale generate dalla definizione di registrazione

In caso di corrispondenza tra i conti e i valori di dimensione nel riquadro **Associa criteri** per la definizione di registrazione e i conti e i valori di dimensione sulla transazione, vengono generate voci di contabilità generale basate sul riquadro **Voci generate** per la definizione di registrazione. 
> [!NOTE]
> Per associare una definizione di registrazione a uno specifico tipo di transazione, utilizzare la pagina **Definizioni di registrazione transazioni**. Dopo aver associato una definizione di registrazione a un tipo di transazione e selezionato **Usa definizioni di registrazione** nella pagina **Parametri di contabilità generale**, tutte le transazioni del tipo selezionato devono utilizzare definizioni di registrazione.

## <a name="example-purchase-order-encumbrances"></a>Esempio: impegni di spesa ordini fornitore
Quando si abilita l'elaborazione degli impegni di spesa selezionando **Abilita processo di impegno di spesa** nella pagina **Parametri di contabilità generale**, è necessario utilizzare le definizioni di registrazione per registrare gli impegni di spesa nella contabilità generale per tutti i conti che devono essere prenotati. Nella maggior parte dei casi, tutti i conti spese vengono prenotati sullo stato patrimoniale. 

Le definizioni di registrazione per gli impegni di spesa vengono impostati per il modulo **Acquisto** nella pagina **Definizioni di registrazione**. Quindi, nell'area **Acquisto** della pagina **Definizioni di registrazione transazione**, è possibile selezionare il tipo di transazione **Ordine acquisto** per associare la definizione di registrazione agli ordini fornitore. 

Tutte le transazioni giustificativo per gli impegni di spesa degli ordini fornitore devono compensarsi (i debiti devono essere pari ai crediti) in ciascuna dimensione univoca su un giustificativo.

### <a name="posting-definition--match-criteria"></a>Definizione di registrazione – criteri di corrispondenza

| Struttura dei conti       | Associa numero di conto | Priorità  |
|-------------------------|----------------------|----------|
| Struttura dei conti - profitti e perdite | \*                   | 1        |

<em>Un valore vuoto nel campo **Numero di conto da associare</em>* implica che tutti i conti corrispondenti nella struttura dei conti definita faranno parte della regola di corrispondenza.

### <a name="posting-definition--generated-entries"></a>Definizione di registrazione – voci generate

| Struttura dei conti | Numero di conto generato                    | Dare/Avere generato |
|-------------------|---------------------------------------------|------------------------|
| Saldo           | 300143 - -(conto impegno di spesa)             | Uguali                   |
| Saldo           | 300144 - -(prenotazione conto impegno di spesa) | Stare in equilibrio              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transazioni con i conti, i valori di dimensione e gli importi

I conti e i valori di dimensione derivano dalle distribuzioni contabili immesse per una riga dell'ordine fornitore oppure derivano dai conti e dalle dimensioni generati automaticamente in base alle impostazioni predefinite per fornitori, articoli, categorie e modelli di dimensione.

| Conto + dimensioni           | Dare  | Avere | Commento |
|--------------------------------|--------|--------|---------|
| 606400-OU\_1-OU\_3566-Training | 250,00 |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Voci di contabilità generale generate dalla definizione di registrazione

Le voci di contabilità generale generate vengono create per registrare gli impegni di spesa.

| Conto + dimensioni           | Dare  | Avere | Commento |
|--------------------------------|--------|--------|---------|
| 300143-OU\_1-OU\_3566-Training | 250,00 |        |         |
| 300144-OU\_1-OU\_3566-Training |        | 250,00 |         |

In questo esempio, qualsiasi conto fa parte di Struttura conti - profitti e perdite corrispondono ai criteri delle definizioni di registrazione. Pertanto, quando viene valutato 606500-OU\_1-OU\_3566-Training, le voci generate vengono create per i conti definiti nel riquadro **Voci generate** per la definizione di registrazione.

## <a name="example-budget-appropriations"></a>Esempio: Ripartizioni di budget
Quando si abilita la ripartizione di budget selezionando **Abilita ripartizione budget** nella pagina **Parametri contabilità generale**, le definizioni di registrazione devono essere utilizzate per registrare le voci del registro di budget nella contabilità generale. Quando una configurazione del controllo del budget è attiva e abilitata, le definizioni di registrazione e le definizioni di registrazione delle transazioni possono essere utilizzate per sostenere la registrazione delle voci di ripartizione, revisione, trasferimento, progetto, cespite, e di previsione della domanda e dell'offerta nella contabilità generale. 

Una definizione di registrazione per voci del registro di budget del tipo di budget **Budget originale** e che ha abilitate le ripartizioni, può essere impostata selezionando il modulo **Budget** nella pagina **Definizioni di registrazione**. Quindi, nell'area **Budget** della pagina **Definizioni di registrazione transazioni**, è possibile utilizzare i codici budget per associare la definizione di registrazione a voci del registro di budget del tipo di budget **Budget originale**. 

Se sono abilitate le ripartizioni di budget e le definizioni di registrazione, le voci del registro di budget vengono registrate per il controllo del budget e nella contabilità generale.

### <a name="posting-definition--match-criteria"></a>Definizione di registrazione – criteri di corrispondenza

| Struttura dei conti       | Associa numero di conto | Priorità  |
|-------------------------|----------------------|----------|
| Struttura dei conti - profitti e perdite | \*                   | 1        |

<em>Un valore vuoto nel campo **Numero di conto da associare</em>* implica che tutti i conti corrispondenti nella struttura dei conti definita faranno parte della regola di corrispondenza.

### <a name="posting-definition--generated-entries"></a>Definizione di registrazione – voci generate

| Struttura dei conti | Numero di conto generato              | Dare/Avere generato |
|-------------------|---------------------------------------|------------------------|
| Struttura dei conti | 300145 - -(Conto ricavi stimati) | Uguali                   |
| Struttura dei conti | 300146 - -(Conto ripartizioni)     | Stare in equilibrio              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a>Transazioni con i conti, i valori di dimensione e gli importi

Nella pagina **Voce di registro budget** si immettono i conti, i valori di dimensione e gli importi per la voce contabile del budget.

| Conto + dimensioni           | Dare | Avere | Commento |
|--------------------------------|-------|--------|---------|
| 606400-OU\_1-OU\_3566-Training |       | 250,00 |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a>Voci di contabilità generale generate dalla definizione di registrazione

Le voci di contabilità generale generate vengono create per registrare il budget originale in ciascuna dimensione.

| Conto + dimensioni           | Dare  | Avere | Commento |
|--------------------------------|--------|--------|---------|
| 300145-OU\_1-OU\_3566-Training |        | 250,00 |         |
| 300146-OU\_1-OU\_3566-Training | 250,00 |        |         |

In questo esempio, qualsiasi conto fa parte di Struttura conti - profitti e perdite corrispondono ai criteri delle definizioni di registrazione. Pertanto, quando viene valutato 606400-OU\_1-OU\_3566-Training, vengono create le voci della contabilità generale generate.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]