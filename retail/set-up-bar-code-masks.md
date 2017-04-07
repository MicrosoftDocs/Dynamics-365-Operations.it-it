---
title: Impostare le maschere codice a barre
description: "In questo argomento viene descritto come impostare i caratteri maschera codice a barre, maschere codice a barre e la modalità di allocazione delle maschere codice a barre ai codici a barre."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fe598799d52cacd84da775ac7ace8cf9a30ae5fe
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-code-masks"></a>Impostare le maschere codice a barre

In questo argomento viene descritto come impostare i caratteri maschera codice a barre, maschere codice a barre e la modalità di allocazione delle maschere codice a barre ai codici a barre.

<a name="set-up-bar-code-mask-characters"></a>Impostare caratteri di maschera codice a barre
-------------------------------

Le maschere codici a barre sono utilizzate per creare i codici a barre e per identificare rapidamente i codici a barre per quelle personalizzate vengono esaminate nel POS (POS). Le maschere sono incluse caratteri che funziona come segnaposto che indicano il formato dei codici a barre che verranno creati. Per configurare una maschera codice a barre, è necessario impostare i caratteri maschera codice a barre. ** Va al dettaglio e il commercio ** &gt; ** su Gestione articoli ** &gt; ** codici a barre e etichette ** &gt; ** caratteri maschera **. Fare clic su ** nuovo ** per creare i caratteri maschera codice a barre. I caratteri maschera possono essere creati per indicare i seguenti dati di codice a barre.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Field**            | **Description**                                                                                                 |
| **Product**          | Segnaposto per l'identificazione del prodotto.                                                                                     |
| **Any number**       | Consente di specificare un numero che verrà codificato definitivo i codici a barre.                                                  |
| **Check digit**      | Indica che il formato del codice a barre in una maschera codice a barre viene utilizzata una cifra di controllo per verificare la validità di un codice a barre. |
| **Size digit**       | Indica le dimensioni di un codice a barre creato per una variante prodotto che include la dimensione.                                 |
| **Color digit**      | Indica il colore di un codice a barre creato per una variante prodotto che include il colore.                               |
| **Style digit**      | Indica lo stile di immettere un codice a barre creato per una variante prodotto che include uno stile.                             |
| **EAN license code** | Segnaposto per la licenza EAN emessa per i codici di licenza EAN.                                                       |
| **Prezzo**            | Indica il prezzo per i codici a barre inclusi prezzo.                                                                   |
| **Quantity**         | Indica la quantità la quantità/i codici a barre inclusi peso casuale.                                                |
| **Employee**         | Indica il segmento di codice a barre per il numero di ID dipendente utilizzato per l'accesso a Retail POS di codice a barre.                                  |
| **Customer**         | Indica il segmento di identificazione cliente.                                                                                  |
| ** Inserimento di dati **       | *Not eppure implemented.*                                                                                          |
| **Discount code**    | Indica il codice sconto per un codice a barre utilizzato per aggiungere uno sconto a una transazione del POS             |
| **Gift card**        | Indica il numero della gift card o un'uscita quando il pagamento deve essere effettuato tramite gift card.                                               |
| **Loyalty card**     | Aggiunge un cliente programma fedeltà alla transazione e può essere utilizzato quando si paga dal programma fedeltà.                             |

## <a name="define-bar-code-masks"></a>Definire le maschere codice a barre
Dopo che i caratteri maschera codice a barre vengono specificati per le maschere necessarie ai codici a barre, spostarsi ** al dettaglio e il commercio ** &gt; ** su Gestione articoli ** &gt; ** codici a barre e contrassegna ** &gt; ** maschera codice a barre impostata **. In questa pagina, è possibile definire le maschere codice a barre che utilizzano caratteri specificati in precedenza. Le maschere codice a barre verranno utilizzate per la generazione di codici a barre e anche consentano di identificare i codici a barre scanditi al POS.

1.  Fare clic su ** nuovo ** per creare una nuova maschera codice a barre.
2.  Immettere i valori ** ID maschera ** e ** descrizione ** i campi e quindi selezionare una maschera codice a barre in ** tipo ** il campo.
3.  ** Generale ** nell'area, selezionare un valore in ** standard di codici a barre ** Sistemano quindi specificare il prefisso di codice a barre, se è obbligatorio.
4.  ** Segmento maschera codice a barre ** Nell'area, aggiungere i segmenti di codice a barre utilizzato nel codice a barre da creare.

Come esempio, creare una maschera codice a barre con l'ID "prodotto" maschera, fareste le seguenti operazioni:

1.  Creare una nuova maschera codice a barre e selezionare il tipo "" prodotto.
2.  Selezionare un valore predefinito del codice a barre, ad esempio, "Codice 39".
3.  Immettere un prefisso da utilizzare per identificare facilmente il codice a barre. Ad esempio, "22 ".
4.  Aggiungere un segmento maschera. Segmento maschera "prodotto" verrà selezionato.
5.  Immettere una lunghezza per il segmento del prodotto, ad esempio, "10 ". Lunghezza deve equivalere alla durata di un ID prodotto in genere utilizzata nel punto vendita. La maschera visualizzati come previsione ** dettagli relativi all'identificazione ** nella sezione in ** maschera **.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Assegnare le maschere codice a barre ai codici a barre
Le maschere codici a barre e devono essere assegnate ai codici a barre affinché possano essere utilizzate. In base all'esempio precedente, assegnare la maschera codice a barre a un codice a barre, effettuare le seguenti operazioni:

1.  Va ** Amministrazione organizzazione ** &gt; ** l'impostazione ** &gt; ** codici a barre **. Fare clic su ** nuovo ** per creare un nuovo codice a barre.
2.  Immettere i valori ** codice a barre ** ** impostazione ** e ** impostazione ** campi.
3.  In ** dettagli relativi all'identificazione ** aree, in ** tipo di codice a barre ** Sistemano, selezionare il "Codice 39". ** Maschera ** ** l'ID ** sistemi, selezionare la maschera "prodotto" creata in precedenza.
4.  In ** dimensione **, immettere "12 ".
5.  Click **Save**.

La maschera codice a barre possono ora essere utilizzata per creare i codici a barre per i prodotti. I passaggi precedenti sono riportati esempi della creazione delle maschere codice a barre per i prodotti, ma anche viene illustrato come creare le maschere codice a barre per tutti gli altri tipi di codice a barre supportati. Le maschere, i tipi e le lunghezze di codice a barre se devono essere registrati per ottenere utilizzare nell'ambiente specifico.


