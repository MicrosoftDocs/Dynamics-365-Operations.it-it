---
title: Calcoli per il modello di configurazione prodotto
description: In questo argomento viene descritto come creare i calcoli per gli attributi in un modello di configurazione prodotto
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 349fed3ca75b94db2f421a1ff3c3553c96c202c37d59857a3d973f3de8f995ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755253"
---
# <a name="product-configuration-model-calculations"></a>Calcoli per il modello di configurazione prodotto

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come creare i calcoli per gli attributi in un modello di configurazione prodotto.

## <a name="prerequisites"></a>Prerequisiti

I calcoli vengono utilizzati nel modello di configurazione prodotto per calcolare i valori di configurazione per un prodotto. Prima di poter iniziare a impostare i calcoli, è necessario che esista il modello di configurazione prodotto correlato. Per una panoramica del processo di configurazione per i modelli di configurazione e le attività correlate, vedi [Impostare un modello di configurazione prodotto](set-up-maintain-product-configuration-model.md).

## <a name="create-a-calculation"></a>Creare un calcolo

Un calcolo è costituito da un'espressione e da un attributo di destinazione. Per ulteriori informazioni vedi, [Domande frequenti sui calcoli per i modelli di configurazione prodotto](calculate-product-configuration-models.md).

Per creare un calcolo per un modello di prodotto esistente, attieniti alla seguente procedura.

1. Vai a **Gestione informazioni sul prodotto \> Comune \> Modelli di configurazione prodotto**.
1. Apri un modello di configurazione prodotto e seleziona **Modifica**.
1. Nella Scheda dettaglio **Calcoli**, seleziona **Aggiungi** per aggiungere un calcolo e quindi imposta i campi seguenti:

    - **Nome** - Immetti un nome per il calcolo.
    - **Descrizione** - Immetti una descrizione del calcolo.
    - **Attributo di destinazione** - Seleziona l'attributo per il quale stai effettuando il calcolo.

1. Seleziona **Modifica espressione**.
1. Nella finestra di dialogo **Immettere un calcolo**, aggiungi gli attributi, gli operatori e i valori richiesti all'espressione. Per ulteriori informazioni su come utilizzare questi elementi, vedi [Vincoli di espressione e vincoli di tabella nei modelli di configurazione del prodotto](expression-constraints-table-constraints-product-configuration-models.md).
1. Quando la tua espressione è pronta, seleziona **OK**.

## <a name="calculation-examples"></a>Esempi di calcolo

Questa sezione fornisce alcuni esempi che mostrano come funzionano i calcoli.

### <a name="example-1"></a>Esempio 1

L'attributo di destinazione è booleano e il calcolo utilizza la seguente espressione condizionale:

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

Tale espressione restituisce un valore *True* all'attributo di destinazione se `decimalAttribute2` è maggiore o uguale a `decimalAttribute1`. In caso contrario, restituisce il valore *False*.

### <a name="example-2"></a>Esempio 2

Questo esempio utilizza l'attributo di testo `textFixedList` come attributo di destinazione. Questo attributo contiene il seguente elenco fisso.

| Valore | Valore risolutore |
|---|---|
| A | 1a |
| B | 2b |
| C | 2c |

Lo screenshot seguente mostra come potrebbero apparire le impostazioni per questo attributo nel sistema.

![Impostazioni del tipo di attributo per l'esempio 2.](media/model-calculations-example2.png "Impostazioni del tipo di attributo per l'esempio 2")

L'attributo viene utilizzato nella seguente istruzione condizionale:

`If[integerAttribute < 150, 0, 2]`

Se `integerAttribute` è inferiore a 150, questa istruzione restituisce il valore di testo del primo record nell'elenco fisso, *A*. In caso contrario, restituisce il valore di testo del terzo record nell'elenco fisso, *C*.

> [!NOTE]
> L'elenco fisso è equivalente a un'enumerazione in base zero (enum) e ai suoi valori si accede tramite il valore intero appropriato. Pertanto, il primo valore di elenco fisso (*A*) è abbinato a *0*, il secondo valore (*B*) è abbinato a *1* e il terzo valore (*C*) è abbinato a *2*.

### <a name="example-3"></a>Esempio 3

Questo esempio utilizza l'attributo di destinazione `textFixedList` dell'esempio precedente. Utilizza anche un altro attributo di testo, `textAttribute`, che contiene il seguente elenco fisso.

| Valore | Valore risolutore |
|---|---|
| AA | 1aa |
| BB | 2bb |

Lo screenshot seguente mostra come potrebbero apparire le impostazioni per questo attributo nel sistema.

![Impostazioni del tipo di attributo per l'esempio 3.](media/model-calculations-example3.png "Impostazioni del tipo di attributo per l'esempio 3")

Il valore per l'attributo `textFixedList` viene calcolato utilizzando la seguente istruzione condizionale:

`If[textAttribute == "1aa", 0, 2]`

Se il valore di `textAttribute` ha un valore di soluzione pari a *1aa*, questa espressione restituisce il valore di testo del primo record nell'elenco fisso `textFixedList`, *A*. In caso contrario, restituisce il valore di testo del terzo record nell'elenco fisso `textFixedList`, *C*.

> [!NOTE]
> - L'istruzione condizionale deve utilizzare il valore di soluzione dell'attributo.
> - Solo gli attributi di testo a elenco fisso possono essere utilizzati nei calcoli.

## <a name="see-also"></a>Vedere anche

- [Domande frequenti sui calcoli per i modelli di configurazione prodotto](calculate-product-configuration-models.md)
- [Aggiungere un vincolo di espressione a un modello di configurazione prodotto](tasks/add-expression-constraint-product-configuration-model.md)
- [Panoramica sui modelli di configurazione prodotto](product-configuration-models.md)
