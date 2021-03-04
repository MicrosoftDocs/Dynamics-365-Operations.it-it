---
title: Utilizzare i moduli
description: In questo argomento viene descritto come e quando utilizzare moduli in Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 301eb6206fb9e02c3aa7d3c07cf368ba800a1ab9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413473"
---
# <a name="work-with-modules"></a>Utilizzare i moduli

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come e quando utilizzare moduli in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

I moduli sono blocchi predefiniti logici che costituiscono la struttura della pagina e hanno scopi e finalità. Alcuni moduli sono contenitori di alto livello e il loro solo scopo è di contenere e organizzare altri moduli (moduli figlio). Altri moduli, ad esempio un modulo Posizionamento immagine semplice, hanno uno scopo molto specifico. Altri moduli, come il modulo Sequenza, non rientrano in nessuna di queste due categorie.

Per impostazione predefinita, il sito di Dynamics 365 Commerce include una libreria di moduli che consente di ottenere la maggior parte degli scenari di e-Commere di base. Dovrebbe essere possibile poter creare un sito di e-Commerce end-to-end utilizzando questi moduli. Tuttavia, è anche possibile che si intenda personalizzare tali moduli o creare nuovi moduli personalizzati per specifiche esigenze. Se si desidera creare moduli personalizzati, un kit SDK di progettazione di moduli è disponibile per creare una libreria di moduli personalizzati.

## <a name="container-modules-and-slots"></a>Moduli contenitore e slot

Come indicato in precedenza, alcuni moduli sono progettati per contenere moduli figlio. Questi moduli sono noti come *contenitori* e consentono l'utilizzo di gerarchie di moduli nidificati. I moduli contenitore includono *slot*. Gli slot sono utilizzati per gestire il layout e lo scopo dei moduli figlio nel contenitore. Un esempio è un modulo contenitore pagina di base (un modulo di livello superiore per qualsiasi pagina) che definisce vari slot importanti:

- Uno slot di intestazione
- Uno slot di intestazione secondaria
- Uno slot principale
- Uno slot piè di pagina
- Uno slot di piè di pagina secondario

Lo sviluppatore del modulo definisce tali slot e determina quali e quanti moduli figlio possono essere inseriti direttamente all'interno di tale modulo. Ad esempio, lo slot intestazione potrebbe supportare solo un modulo di tipo **modulo Intestazione**, mentre lo slot corpo potrebbe supportare un numero illimitato di moduli di qualsiasi tipo (tranne altri moduli contenitore pagina).

Negli strumenti di creazione, gli autori di pagine non devono sapere in anticipo quali moduli possono e non possono essere inseriti in ogni slot. Quando gli autori di pagine selezionano uno slot e quindi tentano di selezionare un modulo da aggiungere allo slot, vedono una visualizzazione filtrata dei tipi di modulo supportati per quello slot.

## <a name="content-modules"></a>Moduli contenuto

I moduli contenuto contengono contenuto ed elementi multimediali, come testo (ad esempio, titoli, paragrafi e collegamenti) o riferimenti ad asset (ad esempio, immagini, video e PDF). Tipici tipi di moduli di contenuto includono blocchi di contenuto, blocchi di testo e moduli banner promozionali. I moduli di questi tre tipi possono contenere testo o elementi multimediali e non richiedono moduli figlio per rendere qualcosa visibile in una pagina.

La maggior parte delle attività di creazione di pagine e contenuto quotidiane tipiche comporta moduli contenuto, in particolare perché questi moduli definiscono il contenuto effettivo di cui viene eseguito il rendering nei moduli contenitore padre. Molti moduli contenuto sono disponibili e questi moduli sono in genere gli ultimi pezzi che saranno aggiunti alla gerarchia di moduli nidificati di una pagina.

Nella figura seguente viene illustrato come i moduli sono nidificati negli slot di moduli contenitore padre.

![Moduli nidificati](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Aggiungere o rimuovere moduli

Nelle procedure riportate di seguito viene descritto come aggiungere e rimuovere moduli.

### <a name="add-a-module"></a>Aggiungere un modulo

Per aggiungere un modulo a uno slot o contenitore in una pagina, effettuare le seguenti operazioni.

1. Nel riquadro a sinistra o direttamente nel canvas principale, selezionare un contenitore o uno slot a cui un modulo figlio può essere aggiunto.

    > [!NOTE]
    > Lo strumento di progettazione di moduli definisce l'elenco dei tipi di modulo che possono essere aggiunti a uno slot di modulo specifico. Gli autori di modelli possono quindi affinare le opzioni per moduli consentite per garantire un'ottimizzazione del motore di ricerca coerente e l'efficacia di creazione per tutte le pagine generate da un modello specifico. Durante l'aggiunta di un modulo a uno slot, la finestra di dialogo **Aggiungi modulo** viene automaticamente filtrata in modo da visualizzare solo i moduli che sono supportati nel contenitore o nello slot selezionato. L'elenco di moduli consentiti viene determinato dal modello della pagina o dalla definizione del modulo contenitore.

1. Se si utilizza il riquadro di contorno, selezionare i puntini di sospensione (**...**) accanto al nome del modulo, quindi selezionare **Aggiungi modulo**. Se si utilizzano i controlli direttamente nel canvas, selezionare il simbolo più (**+**) in uno slot vuoto o adiacente al modulo attualmente selezionato, quindi selezionare **Aggiungi modulo**.

    > [!NOTE]
    > Se un contenitore o uno slot non supporta nuovi moduli figlio, l'opzione **Aggiungi modulo** non è disponibile.

1. Nella finestra di dialogo **Aggiungi modulo**, selezionare un modulo da aggiungere alla pagina.

    > [!TIP]
    > **Blocco di contenuto** è un buon tipo di modulo con cui i principianti possono lavorare.

1. Selezionare **OK** per aggiungere il modulo selezionato al contenitore o allo slot selezionato nella pagina.

### <a name="remove-a-module"></a>Rimuovere un modulo

Per rimuovere un modulo da uno slot o un contenitore in una pagina, effettuare le seguenti operazioni.

1. Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione (**...**) accanto al nome del modulo da rimuovere e quindi selezionare il simbolo del cestino. In alternativa, nel canvas principale è possibile selezionare il simbolo del cestino sulla barra degli strumenti di un modulo selezionato.
1. Quando viene richiesto di confermare la rimozione del modulo, selezionare **OK**.

## <a name="move-a-module-to-a-new-position"></a>Spostare un modulo in una una posizione

Per spostare un modulo in una nuova posizione all'interno della pagina, utilizzare uno dei seguenti metodi.

### <a name="move-a-module-using-the-outline-pane"></a>Spostare un modulo utilizzando il riquadro struttura

Per spostare un modulo utilizzando il riquadro struttura, attenersi alla seguente procedura.

1. Selezionare e tenere premuto il modulo che si desidera spostare nel riquadro struttura, quindi trascinare il modulo in una nuova posizione nella struttura. La linea blu nel contorno e nel canvas indica dove è possibile posizionare il modulo.
1. Rilasciare il modulo per inserirlo nella nuova posizione.

### <a name="move-a-module-directly-within-the-canvas"></a>Spostare un modulo direttamente nel canvas

Per spostare un modulo direttamente nel canvas, attenersi alla seguente procedura.

1. Selezionare il modulo che si desidera spostare nel canvas. 
1. Selezionare un simbolo di freccia rivolta verso l'alto o verso il basso nella barra degli strumenti del modulo, quindi trascinare la freccia in una nuova posizione sulla pagina. La linea blu nel contorno e nel canvas indica dove è possibile posizionare il modulo. Se un modulo non può essere spostato verso l'alto o verso il basso, quel simbolo di freccia verrà disattivato. 
1. Rilasciare il modulo per inserirlo nella nuova posizione.

### <a name="move-a-module-using-the-ellipsis-menu"></a>Spostare un modulo utilizzando il menu dei puntini di sospensione

Per spostare un modulo utilizzando il menu dei puntini di sospensione, attenersi alla seguente procedura.

1. Selezionare un modulo nella struttura o nel canvas.
1. Selezionare i puntini di sospensione (**...**) accanto al nome del modulo nel riquadro struttura o nella barra degli strumenti del modulo nel canvas.
1. Se il modulo può essere spostato verso l'alto o verso il basso all'interno del contenitore o dello slot, verranno visualizzate le opzioni per **Sposta su** o **Sposta giù**. Selezionare l'opzione di spostamento desiderata per spostare il modulo verso l'alto o verso il basso rispetto ai suoi elementi di pari livello.

## <a name="configure-modules"></a>Configurare moduli

Nelle procedure riportate di seguito viene descritto come configurare moduli contenuto e contenitore.

### <a name="configure-a-content-module"></a>Configurare un modulo contenuto

Per configurare un modulo contenuto in una pagina, effettuare le seguenti operazioni.

1. Nella riquadro a sinistra, espandere la struttura e selezionare qualsiasi modulo contenuto (ad esempio **Blocco di contenuto**). In alternativa, è possibile selezionare il modulo nel canvas principale.
1. Nel riquadro delle proprietà del modulo sulla destra, immettere le proprietà per tutti i controlli del modulo desiderati.
1. Selezionare **Salva** nella barra dei comandi. Ciò aggiornerà anche la canvas di anteprima.

### <a name="edit-module-text-properties"></a>Modificare le proprietà del testo del modulo

Le proprietà del testo del modulo che non sono di sola lettura possono essere modificate direttamente nel canvas.

Per modificare le proprietà del testo del modulo, attenersi alla seguente procedura.

1. Selezionare il controllo del testo nel canvas, quindi posizionare il cursore nel punto in cui desideri modificare il testo.
1. Immettere il contenuto del testo.
1. Selezionare un punto qualsiasi al di fuori del contenuto del testo per continuare a modificare altro contenuto.

### <a name="inline-image-selection"></a>Selezione immagine in linea

Le immagini del modulo che non sono di sola lettura possono essere modificate direttamente dal canvas.

Per scegliere una nuova immagine per un modulo di contenuto, effettuare le seguenti operazioni.

1. Nel canvas, fare doppio clic sull'immagine. Questo farà apparire la finestra di selezione dei file multimediali.
1. Trovare e selezionare una nuova immagine da utilizzare, quindi selezionare **OK**. Il rendering della nuova immagine viene ora effettuato nel canvas.

### <a name="configure-a-container-module"></a>Configurare un modulo contenitore

Per configurare un modulo contenitore in una pagina, effettuare le seguenti operazioni.

1. Selezionare un modulo contenitore nella pagina (ad esempio un modulo contenitore fluido o Sequenza).
1. Nel riquadro delle proprietà a destra, espandere i controlli nidificati selezionando le intestazioni e impostare tutti i valori di controllo necessari.
1. Nel riquadro a sinistra, selezionare il pulsante con i puntini di sospensione accanto al nome del contenitore o di qualsiasi slot nel contenitore e quindi selezionare **Aggiungi modulo**. Aggiungere quindi i moduli figlio al contenitore selezionato. Per ulteriori informazioni, vedere la sezione [Utilizzare i moduli](#add-a-module) descritta precedentemente in questo argomento.
1. Se molteplici moduli figlio esistono come elementi di pari livello in un contenitore padre, è possibile modificarne l'ordine di visualizzazione nel contenitore padre. Selezionare il pulsante con i puntini di sospensione per un modulo e quindi utilizzare i tasti freccia GIÙ o SU.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica modelli e layout](templates-layouts-overview.md)

[Utilizzare i modelli](work-with-templates.md)

[Utilizzare i layout preimpostati](work-with-layouts.md)

[Utilizzare i frammenti](work-with-fragments.md)

[Aggiungere un modulo contenitore a una pagina](add-container-module.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]