---
title: Layout delle etichette di distribuzione documenti
description: Questo articolo descrive come utilizzare i metodi di formattazione per stampare i valori sulle etichette.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: a4e0c16b71c257cae832870ca58679884047ea16
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708647"
---
# <a name="document-routing-label-layout"></a>Layout delle etichette di distribuzione documenti

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come creare layout per etichette di targa, contenitore e ciclo. Fornisce inoltre le linee guida per l'utilizzo del linguaggio di programmazione Zebra (ZPL) utilizzato per creare i layout.

I layout delle etichette di distribuzione dei documenti definiscono il modo in cui le etichette vengono disposte e dei dati che vi vengono stampati. Configurare i punti di attivazione della stampa quando si impostano le voci di menu del dispositivo mobile e i modelli di lavoro.

Le informazioni in questo articolo si applicano a tutti i layout delle etichette di distribuzione dei documenti, inclusi i layout per [etichette di targa](tasks/license-plate-label-printing.md), [etichette dei contenitori](print-container-labels.md) e [etichette di ciclo](configure-wave-label-printing.md).

È possibile stampare etichette molto complesse, a condizione che il dispositivo di stampa sia in grado di interpretare il testo che viene inviato. Ad esempio, un layout ZPL che include un codice a barre potrebbe assomigliare al seguente esempio.

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

Come parte del processo di stampa delle etichette, il testo `$LicensePlateId$` in questo esempio verrà sostituito con un valore di dati. Diversi strumenti di generazione di etichette ampiamente disponibili possono aiutare a formattare il testo per il layout dell'etichetta. Molti di questi strumenti supportano il formato `$FieldName$`. Inoltre, Microsoft Dynamics 365 Supply Chain Management utilizza una logica di formattazione speciale come parte della mappatura dei campi per il layout della distribuzione del documento.

Per vedere i valori che verranno stampati, andare a **Gestione magazzino \> Richieste di informazioni e report \> Etichette della targa**.

## <a name="turn-on-this-feature-for-your-system"></a>Attivare questa funzionalità per il sistema

Se il sistema non include già le funzionalità descritte in questo articolo, vai a [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attiva la funzionalità *Layout etichette targa migliorati*. A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.25 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata.

## <a name="custom-number-formats"></a>Formati numerici personalizzati

È possibile personalizzare la formattazione dei valori dei campi numerici che vengono stampati utilizzando i codici che hanno il seguente formato.

```dos
$FieldName:FormatString$
```

Di seguito è riportata una spiegazione di questo formato:

- `FieldName` è il nome del campo dati (ad esempio **Quantità**).
- `FormatString` definisce come devono essere stampati i dati.

I seguenti esempi mostrano come personalizzare il campo della quantità di lavoro (**Quantità**):

- Per mostrare sempre quattro cifre (usando zeri come segnaposto) utilizzare `$Qty:0000$`. Ad esempio, se la quantità è 10, l'etichetta mostrerà "0010".
- Per mostrare sempre due cifre decimali, utilizzare `$Qty:0.00$`. Ad esempio, se la quantità è 10, l'etichetta mostrerà "10.00".

Per l'elenco completo delle stringhe di formato numerico disponibili, vedere [Stringhe di formato numerico personalizzate](/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="custom-string-formats"></a>Formati di stringa personalizzati

È possibile rimuovere i primi caratteri di una stringa utilizzando il campo e il codice di formato seguenti.

```dos
$FieldName:#..$
```

`#` specifica il numero di caratteri da ignorare. Ad esempio, per stampare un numero di targa Serial Shipping Container Code (SSCC) che non include i primi due caratteri, utilizzare `$LicensePlateId:2..$`. In questo caso, il numero di targa 0011111111111222221 verrà stampato come "11111111111222221".

## <a name="custom-datetime-formats"></a>Formati di data/ora personalizzati

L'esempio seguente mostra come è possibile controllare il formato utilizzato per stampare le date.

```dos
$PrintedDate:dd-MM-yyyy$
```

In questo esempio, la data del 30 aprile 2020 verrà stampata come "30-04-2020".

Per l'elenco completo dei formati data/ora disponibili, vedere [Stringhe di formato data/ora personalizzate](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="print-individual-lines-from-multiline-data"></a>Stampa di singole righe da dati multiriga

Se un campo dati contiene più righe (ovvero righe separate da interruzioni di riga) è possibile stampare una singola riga utilizzando il seguente formato.

```dos
$FieldName[#]$
```

`#` è il numero di riga che si desidera stampare. (Usare 1 per la prima riga.)

Ad esempio, il sistema ha un campo `AdditionalAddress` che memorizza il seguente indirizzo multiriga:

Contoso Inc.  
123 Street Name  
Some City, Some State

È possibile stampare questo indirizzo, una riga alla volta, utilizzando i seguenti codici.

| Codice | Testo stampato |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 Street Name |
| `$AdditionalAddress[3]$` | Some City, Some State |

## <a name="print-and-format-from-a-display-method"></a>Stampa e formattazione da un metodo di visualizzazione

È possibile stampare da un metodo di visualizzazione utilizzando il seguente formato.

```dos
$DisplayMethod()$
```

È possibile combinare questo formato con altri tipi descritti in precedenza in questo articolo. Ad esempio, è disponibile un metodo di visualizzazione chiamato `DisplayListOfItemsNumbers()` e si desidera stampare il primo numero di articolo di questo metodo. In questo caso, è possibile utilizzare il seguente codice.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>Ulteriori informazioni sulla stampa delle etichette

Per ulteriori informazioni su come impostare e stampare le etichette, vedi gli articoli seguenti.

- [Stampa di etichette di targa](tasks/license-plate-label-printing.md)
- [Stampa di etichette di contenitore](print-container-labels.md)
- [Stampa di etichette ciclo](configure-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
