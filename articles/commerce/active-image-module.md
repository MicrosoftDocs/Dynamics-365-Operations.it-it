---
title: Modulo dell'immagine attiva
description: In questo argomento vengono descritti i moduli delle immagini attive e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 36b7d6dea87c7f309c07608794d443a0ae19be211847d2cddcad95f2d933a8db
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716910"
---
# <a name="active-image-module"></a>Modulo dell'immagine attiva

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli delle immagini attive e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

Un modulo dell'immagine attiva può essere utilizzato per incorporare i tag del prodotto in un'immagine. Gli utenti del sito di e-commerce possono quindi passare con il mouse sui tag per visualizzare in anteprima i prodotti mostrati nell'immagine. Le anteprime vengono visualizzate in finestre popup. Selezionando una finestra popup di anteprima, gli utenti possono andare direttamente alla pagina dei dettagli del prodotto (PDP) per il prodotto corrispondente.

I tag sono definiti utilizzando le coordinate X e Y sull'immagine. Ciascun punto contrassegnato deve essere configurato con l'ID prodotto del prodotto mostrato nell'immagine.

L'illustrazione seguente mostra un esempio di una finestra popup di anteprima su un'immagine hero nella home page di Adventure Works.

![Esempio di una finestra popup di anteprima in un modulo dell'immagine attiva](./media/Active_image.PNG)

> [!IMPORTANT]
> - Il modulo immagine attivo è disponibile a partire dalla versione Dynamics 365 Commerce 10.0.20.
> - Il modulo dell'immagine attiva è mostrato nel tema Adventure Works.

## <a name="active-image-module-properties"></a>Proprietà del modulo dell'immagine attiva

| Nome proprietà      | Valori | descrizione |
|--------------------|--------|-------------|
| Immagine              | File di immagine | Un'immagine può essere utilizzata per presentare uno o più prodotti. L'immagine può essere caricata nella libreria multimediale in Creazione di siti di Commerce oppure è possibile utilizzare un'immagine esistente. |
| Larghezza              | Numero di pixel | Questa proprietà definisce la larghezza dell'immagine. Le coordinate attive vengono calcolate in base alla larghezza dell'immagine.|
| Coordinate attive | Coordinate X e Y e un numero ID del prodotto | Ciascun array dell'immagine attiva è costituito dalle coordinate X e Y e da un numero ID del prodotto.|
| Intestazione            | Testo e tag di intestazione (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Per impostazione predefinita, viene utilizzato il tag di intestazione **H2**, ma è possibile utilizzare un altro tag per soddisfare i requisiti di accessibilità. |
| Paragrafo          | Testo paragrafo | Il modulo supporta testo di paragrafo in formato RTF. Alcune funzionalità RTF di base sono supportate, ad esempio collegamenti ipertestuali e testo in grassetto, sottolineato e in corsivo. Alcune funzionalità possono essere sostituite dal tema di pagina applicato al modulo. |
| Collega               | Testo del collegamento, URL del collegamento, etichetta ARIA e selettore **Apri collegamento in una nuova scheda** | Il modulo supporta uno o più collegamenti "invito all'azione". Se un collegamento viene aggiunto, il testo del collegamento, un URL e un'etichetta ARIA sono necessari. Le etichette ARIA devono essere descrittive per soddisfare i requisiti di accessibilità. I collegamenti possono essere configurati di modo che siano aperti in una nuova scheda. |
| Sottotesto           | Intestazione, testo e collegamenti | È possibile aggiungere un contesto aggiuntivo per l'immagine, ad esempio un nome di autore o designer o collegamenti a blog personali.|
| Tema testo         | **Chiaro** o **Scuro** | Questa proprietà consente a un utente di impostare il testo su chiaro o scuro, in base all'immagine di sfondo. È disponibile come estensione del tema nel tema Adventure Works. |

## <a name="add-an-active-image-module-to-a-new-page"></a>Aggiunta di un modulo dell'immagine attiva a una nuova pagina

Per aggiungere un modulo dell'immagine attiva a una nuova pagina e impostare le proprietà necessarie, effettuare le seguenti operazioni.

1. Andare a **Modelli** e aprire il modello di marketing per la home page del sito (o creare un nuovo modello di marketing).
1. Nello slot **Principale** della pagina predefinita, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Immagine attiva**, quindi scegliere **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.
1. Andare in **Pagine** e aprire la home page del sito (o creare una nuova home page utilizzando il modello di marketing).
1. Nello slot **Principale** della pagina predefinita, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Immagine attiva**, quindi scegliere **OK**.
1. Nel riquadro delle proprietà del modulo dell'immagine attiva aggiungere un'immagine e impostare la larghezza del canvas in base alle dimensioni dell'immagine.
1. Imposta le coordinate X e Y e aggiungi il numero ID prodotto appropriato.
1. Aggiungere e configurare ulteriori moduli dell'immagine attiva in base alle esigenze.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina.
1. Selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria moduli](starter-kit-overview.md)

[Tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
