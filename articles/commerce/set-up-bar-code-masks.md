---
title: Impostare maschere codici a barre
description: In questo articolo viene descritto come impostare i caratteri di maschera codice a barre e come assegnare le maschere codice a barre ai codici a barre.
author: BrianShook
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 97b490384cff27c60191a87dc623eb6a2ef868f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853714"
---
# <a name="set-up-bar-code-masks"></a>Impostare maschere codici a barre

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come impostare i caratteri di maschera codice a barre e come assegnare le maschere codice a barre ai codici a barre.

## <a name="set-up-bar-code-mask-characters"></a>Impostare caratteri di maschera codice a barre

Le maschere codice a barre sono utilizzate per creare i codici a barre e identificare rapidamente i codici a barre sottoposti a scansione nel POS. Le maschere sono costituite da caratteri con la funzione di segnaposto che indicano il formato per i codici a barre che verranno creati. Per configurare una maschera codice a barre, è necessario impostare i caratteri di maschera codice a barre. Andare a **Retail e Commerce** &gt; **Gestione inventario** &gt; **Codici a barre ed etichette** &gt; **Caratteri maschera**. Fare clic su **Nuovo** per creare nuovi caratteri di maschera codice a barre. I caratteri di maschera possono essere creati per indicare i seguenti dati di codice a barre.

| Campo            | Descrizione |
|------------------|-------------|
| Prodotto          | Segnaposto per ID prodotto. |
| Qualsiasi numero       | Utilizzato specificare un numero che verrà hardcoded in codici a barre. |
| Cifra di controllo      | Indica che il formato del codice a barre in una maschera di codice a barre utilizza una cifra di controllo per confermare la validità di un codice a barre. |
| Cifra dimensioni       | Indica le dimensioni in un codice a barre creato per una variante prodotto che include le dimensioni. |
| Cifra colore      | Indica il colore in un codice a barre creato per una variante prodotto che include il colore. |
| Cifra stile      | Indica lo stile in un codice a barre creato per una variante prodotto che include uno stile. |
| Codice di licenza EAN | Segnaposto per la licenza EAN emessa per codici di licenza EAN. |
| Prezzo            | Indica il prezzo per i codici a barre con prezzo incorporato. |
| Quantità         | Indica la quantità nei codici a barre con quantità/peso casuale incorporato. |
| Dipendente         | Indica il segmento del codice a barre per il numero ID dipendente utilizzato per l'accesso al POS del codice a barre. |
| Cliente         | Indica il segmento di ID cliente. |
| Immissione dati       | *Non ancora implementato.* |
| Codice sconto    | *Obsoleto* dalla versione Dynamics 365 for Retail della primavera 2017. Precedentemente: indica il codice sconto per un codice a barre utilizzato per aggiungere uno sconto a una transazione del POS. |
| Codice buono sconto      | Indica il codice buono sconto per un codice a barre utilizzato per aggiungere uno sconto a un ordine. Sostituisce il codice sconto. |
| Gift card        | Indica il numero della gift card quando si emette o si effettua il pagamento tramite gift card. |
| Carta fedeltà     | Aggiunge un cliente del programma fedeltà alla transazione e può essere utilizzato quando si paga mediante il programma fedeltà. |

## <a name="define-bar-code-masks"></a>Definire le maschere codice a barre

Una volta specificati i caratteri di maschera codice a barre per le maschere codice a barre necessarie, passare a **Retail e Commerce** &gt; **Gestione inventario** &gt; **Codici a barre ed etichette** &gt; **Impostazione maschera codice a barre**. In questa pagina è possibile definire le maschere codice a barre che utilizzano i caratteri specificati in precedenza. Queste maschere codice a barre verranno utilizzate quando vengono generati i codici a barre e consentono inoltre di identificare i codici a barre sottoposti a scansione presso il POS.

1. Fare clic su **Nuovo** per creare una nuova maschera codice a barre.
2. Immettere i valori nei campi **ID maschera** e **Descrizione**, quindi selezionare una maschera codice a barre nel campo **Tipo**.
3. Nella sezione **Generale**, selezionare un valore nel campo **Codice a barre standard**, quindi specificare il prefisso del codice a barre, se necessario.
4. Nella sezione **Segmento maschera codice a barre**, aggiungere i segmenti del codice a barre che verranno utilizzati nel codice a barre da creare.

Ad esempio, per creare una maschera codice a barre con ID maschera "Prodotto", è necessario effettuare le seguenti operazioni:

1. Creare una nuova maschera codice a barre e selezionare il tipo "Prodotto".
2. Selezionare un codice a barre standard, ad esempio "Code 39".
3. Immettere un prefisso da utilizzare per identificare facilmente il codice a barre. Ad esempio, "22".
4. Aggiungere un segmento maschera. Il segmento maschera "Prodotto" verrà selezionato.
5. Immettere una lunghezza per il segmento del prodotto, ad esempio "10". La lunghezza deve corrispondere alla lunghezza di un ID prodotto generalmente utilizzato nel punto vendita. La maschera verrà visualizzata come anteprima nella sezione **Generale** in **Maschera**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Assegnare maschere codice a barre a codici a barre

Le maschere codice a barre devono essere assegnate ai codici a barre prima di poter essere utilizzate. In base all'esempio precedente, per assegnare la maschera codice a barre a un codice a barre, effettuare le seguenti operazioni:

1. Passare ad **Amministrazione organizzazione** &gt; **Impostazioni** &gt; **Codici a barre**. Fare clic su **Nuovo** per creare un nuovo codice a barre.
2. Immettere i valori nei campi **Impostazione** e **codice** **a barre**.
3. Nella sezione **Generale**, nel campo **Tipo di codice a barre**, selezionare "Code 39". Nel campo **ID** **maschera**, selezionare la maschera "Prodotto" creata in precedenza.
4. In **Dimensioni**, immettere "12".
5. Fare clic su **Salva**.

La maschera codice a barre può ora essere utilizzata per creare codici a barre per prodotti. I passaggi precedenti sono esempi che illustrano come creare maschere codice a barre per prodotti, ma descrivono anche come creare maschere codice a barre per qualsiasi altro tipo di codice a barre supportato. Le maschere, i tipi e le lunghezze dei codici a barre devono essere modificati in base all'utilizzo nell'ambiente specifico.


[!INCLUDE[footer-include](../includes/footer-banner.md)]