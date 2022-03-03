---
title: Generare varianti per prodotti di progettazione
description: Questo argomento descrive come generare varianti per prodotti di progettazione
author: t-benebo
ms.date: 06/08/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7921983a965af5557f54f608418c8ec922256ba6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103640"
---
# <a name="generate-variants-for-engineering-products"></a>Generare varianti per prodotti di progettazione

[!include [banner](../includes/banner.md)]

Questo argomento descrive come generare varianti per prodotti di progettazione.

## <a name="turn-variant-generation-for-engineering-products-on-or-off"></a>Attivare o disattivare la funzionalità Generazione di varianti per prodotti di progettazione

La funzionalità descritta in questo argomento richiede che entrambe le funzionalità *Gestione modifiche di progettazione* e *Generazione di varianti per prodotti di progettazione* siano attivate per il sistema. Per dettagli su come attivare o disattivare queste funzionalità, vedere [Panoramica della gestione delle modifiche di progettazione](product-engineering-overview.md).

## <a name="generate-one-or-more-new-variants-of-an-engineering-product"></a>Generare una o più nuove varianti di un prodotto di progettazione

Puoi creare una o più nuove varianti di un prodotto senza copiare le informazioni da un prodotto esistente. Ciò è utile quando è necessario creare più varianti di prodotto contemporaneamente.

La procedura seguente fornisce un esempio di come creare diverse varianti che includono la dimensione del colore.

1. Apri la pagina **Prodotti rilasciati** (ad esempio, vai in **Gestione modifiche di progettazione \> Comune \> Prodotti rilasciati**).
1. Nel riquadro azioni, apri la scheda **Prodotto** e nel gruppo **Nuovo** seleziona **Prodotto di progettazione**.
1. Verrà visualizzata la finestra di dialogo **Nuova prodotto**. Seleziona l'appropriata **Categoria di progettazione**.
1. Se la categoria di progettazione selezionata include le dimensioni della variante, puoi impostarne i valori. Per questo esempio, se la categoria ha una dimensione **Colore** puoi impostarla su *Blu*.
1. Effettua altre impostazioni secondo necessità. Seleziona **OK** per creare il prodotto.
1. Il prodotto e la variante blu V-1 vengono creati e il nuovo prodotto si apre.
1. Aggiungi una distinta base (DBA) e indirizzala alla variante secondo necessità.
1. Nel riquadro azioni, apri la scheda **Prodotto** e nel gruppo **Rappresentazione generale prodotto**, seleziona **Dimensioni prodotto**.
1. Si apre la pagina **Dimensioni prodotto**. Questa pagina include una scheda per ogni dimensione disponibile. In ogni scheda, aggiungi una riga per ogni valore che supporterai per ogni dimensione pertinente. (Per questo esempio, potresti aggiungere righe nella scheda **Colore** per *Bianco*, *Giallo*, e *Verde*).
1. Chiudere la pagina, quindi selezionare **Varianti prodotti rilasciati**. Viene visualizzata la prima variante creata (V-1 blu).
1. Nel riquadro Azioni, nella scheda **Variante prodotto**, selezionare **Suggerimenti variante**.
1. Nella finestra di dialogo **Suggerimenti variante**, effettuare uno dei seguenti passaggi:

    - Nella parte superiore della finestra di dialogo è presente una sezione per ogni dimensione disponibile. Per ogni dimensione, selezionare la casella di controllo per ogni valore per il quale si desidera generare un suggerimento di variante, quindi selezionare **Suggerisci** sulla barra degli strumenti. I suggerimenti pertinenti vengono aggiunti alla sezione **Varianti suggerite**.
    - Selezionare **Suggerisci tutto** sulla barra degli strumenti per generare suggerimenti di varianti per tutte le combinazioni disponibili di valori di dimensione. I suggerimenti vengono aggiunti alla sezione **Varianti suggerite**.

1. Nella sezione **Varianti suggerite**, selezionare la casella di controllo per ogni variante che si desidera creare. Quindi, selezionare **Crea** per generare e rilasciare le varianti selezionate alla società di progettazione. Vengono applicate le seguenti condizioni:

    - Nessuna delle varianti create avrà una DBA o un ciclo di lavorazione.
    - Gli attributi per queste varianti saranno quelli predefiniti della categoria di progettazione e non verranno copiati dalla variante precedente.

## <a name="generate-a-variant-as-a-copy-of-another-product-variant"></a>Generare una variante come copia di un'altra variante di prodotto

Puoi creare una variante di un prodotto in base a un'altra variante di prodotto. La distinta base (DBA) e il ciclo di lavorazione della variante di prodotto di origine vengono copiati nella nuova variante. Ciò può essere di aiuto per i prodotti di produzione discreti in cui può essere utile creare la distinta base basata su una distinta base iniziale e tenere traccia delle modifiche rispetto alla variante precedente. Per mantenere la tracciabilità, il sistema registra quale variante è stata copiata per creare una nuova copia.

La seguente procedura fornisce un esempio di come creare una nuova variante che includa la dimensione del colore creando una copia di una variante esistente

1. Apri la pagina **Prodotti rilasciati** (ad esempio, vai in **Gestione modifiche di progettazione \> Comune \> Prodotti rilasciati**).
1. Nel riquadro azioni, apri la scheda **Prodotto** e nel gruppo **Nuovo** seleziona **Prodotto di progettazione**.
1. Verrà visualizzata la finestra di dialogo **Nuova prodotto**. Seleziona l'appropriata **Categoria di progettazione**.
1. Se la categoria di progettazione selezionata include le dimensioni della variante, puoi impostarne i valori. Per questo esempio, se la categoria ha una dimensione **Colore** puoi impostarla su *Blu*.
1. Effettua altre impostazioni secondo necessità. Seleziona **OK** per creare il prodotto.
1. Il prodotto e la variante blu V-1 vengono creati e il nuovo prodotto si apre.
1. Aggiungi una distinta base e indirizzala alla variante secondo necessità.
1. Aggiungi gli attributi alla variante di prodotto secondo necessità.
1. Aggiungi la variante di prodotto blu V-1 a un ordine di modifica tecnica.
1. Imposta **Impatto** su *Nuova variante*.
1. Seleziona il nuovo valore del colore (ad esempio, *bianco*). Nota che si applicano le seguenti condizioni: 
    - La nuova variante ha una distinta base e un ciclo di lavorazione che sono stati copiati dalla variante precedente.
    - La nuova variante ha gli attributi copiati dalla variante precedente.
1. Approva l'ordine di modifica.
1. Elabora l'ordine di modifica. Dopo che l'ordine è stato elaborato, la nuova variante V-1 verrà creata e rilasciata alla società di progettazione.
