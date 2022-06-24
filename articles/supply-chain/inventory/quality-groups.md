---
title: Gruppi di controllo qualità articoli
description: In questo articolo viene descritto come utilizzare e creare gruppi di controllo qualità articoli per raggruppare logicamente i prodotti in modo che possano essere assegnati ad associazioni di controllo qualità per la generazione automatica di ordini di controllo qualità.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bf1ce49fa58fd1a8a5aa07636e0b2bd7e2fc10e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875367"
---
# <a name="item-quality-groups"></a>Gruppi di controllo qualità articoli

[!include [banner](../includes/banner.md)]

Un gruppo di controllo qualità rappresenta i requisiti di test comuni per gli articoli. In questo articolo viene descritto come utilizzare e creare gruppi di controllo qualità articoli per raggruppare logicamente i prodotti in modo che possano essere assegnati ad associazioni di controllo qualità per la generazione automatica di ordini di controllo qualità.

Per impostare, modificare e visualizzare gli articoli assegnati a un gruppo di controllo qualità o i gruppi di controllo qualità assegnati a un articolo, vai a **Gestione articoli \> Impostazioni \> Gruppi di controllo qualità**. Dopo la definizione dei requisiti di test nella pagine **Gruppi di test**, è possibile definire le regole per generare automaticamente gli ordini di controllo qualità. Per semplificare il processo, non si definiscono le regole per i singoli articoli. Invece, puoi definire le regole per un gruppo di controllo qualità nella pagina **Associazioni di controllo qualità**.

## <a name="example-of-an-item-quality-group"></a>Esempio di un gruppo di controllo qualità articoli

Una società di produzione acquista varie materie prime con gli stessi requisiti di test per quanto riguarda l'ispezione in entrata. Pertanto, la società definisce un gruppo di controllo qualità e vi assegna i numeri articolo associati alle materie prime. In seguito, la società acquista un nuovo tipo di materie prima con gli stessi requisiti di test. Invece di impostare nuovi requisiti di test per il nuovo materiale, la società aggiunge il relativo numero articolo al gruppo di controllo qualità esistente.

La stessa società produce inoltre articoli con gli stessi requisiti di test della produzione e spedisce articoli con gli stessi requisiti per quanto riguarda l'esecuzione di test prima della spedizione. Pertanto, la società definisce due ulteriori gruppi di controllo qualità e assegna a ognuno i numeri di articolo rilevanti.

## <a name="create-a-quality-group"></a>Creare un gruppo di controllo qualità

Per creare un gruppo di controllo qualità, eseguire i passaggi indicati di seguito:

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di controllo qualità**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Gruppo di controllo qualità** – Immetti un ID o nome univoco per il gruppo di controllo qualità.
    - **Descrizione** - Immettere una descrizione dettagliata del gruppo di controllo qualità.

1. Chiudere la pagina.

## <a name="manually-add-items-to-a-quality-group"></a>Aggiungere manualmente articoli a gruppo di controllo qualità

Per aggiungere manualmente articoli a un gruppo di controllo qualità, segui questi passaggi.

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di controllo qualità**.
1. Seleziona il gruppo di controllo qualità a cui desideri aggiungere gli articoli.
1. Nel riquadro azioni seleziona **Articoli**.
1. Nella pagina **Articoli in gruppi di controllo qualità**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia. Quindi, per la nuova riga, imposta il campo **Numero articolo** sul numero di articolo che si desidera aggiungere.
1. Ripeti il passaggio precedente per ogni articolo aggiuntivo che devi aggiungere.
1. Chiudere le pagine.

## <a name="add-multiple-items-to-a-quality-group"></a>Aggiungere più articoli a gruppo di controllo qualità

Per aggiungere più articoli a un gruppo di controllo qualità, segui questi passaggi.

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di controllo qualità**.
1. Crea o seleziona il gruppo di controllo qualità a cui desideri aggiungere gli articoli.
1. Nel riquadro azioni seleziona **Aggiungi articoli**.
1. Nella finestra di dialogo **Richiesta di informazioni**, immettere i criteri di filtro per gli articoli che si desidera aggiungere. Ad esempio, potresti filtrare tutti gli articoli in un gruppo di articoli specifico.
1. Selezionare **OK**.
1. Nella finestra di dialogo **Aggiungi articoli**, una griglia mostra tutti gli elementi che corrispondono alla tua query. Rivedi i risultati.

    Se sono necessarie modifiche, selezionare **Seleziona** per tornare alla finestra di dialogo **Richiesta di informazioni** e modificare la query.

1. Quando i risultati includono tutti gli articoli che desideri aggiungere, seleziona **OK**.
1. Chiudere la pagina.

## <a name="manually-associate-an-item-with-a-quality-group"></a>Associare manualmente un articolo a un gruppo di controllo qualità

Per associare manualmente un articolo a un gruppo di controllo qualità, segui questi passaggi.

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Gruppi di controllo qualità articoli**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Numero articolo** - Seleziona il numero dell'articolo da aggiungere.
    - **Gruppo di controllo qualità** - Seleziona il gruppo di controllo qualità da assegnare all'articolo.

1. Ripetere il passaggio precedente per ogni combinazione aggiuntiva di un articolo e un gruppo di controllo qualità che deve essere aggiunto.
1. Chiudere le pagine.

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a>Aggiungere manualmente un gruppo di controllo qualità dalla pagina Prodotti rilasciati

Per aggiungere manualmente un gruppo di controllo qualità dalla pagina **Prodotti rilasciati**, segui questi passaggi.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare il prodotto a cui si desidera assegnare un gruppo di controllo qualità.
1. Nel riquadro azioni, nella scheda **Gestione articoli**, nel gruppo **Qualità**, selezionare **Gruppi di controllo qualità articoli**.
1. Nella pagina **Articoli in gruppi di controllo qualità**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia. Quindi, per la nuova riga, imposta il campo **Gruppo di controllo qualità** sul gruppo di controllo qualità che si desidera assegnare al prodotto.
1. Ripetere il passaggio precedente per ogni gruppo di controllo qualità aggiuntivo che si desidera assegnare al prodotto.
1. Chiudere le pagine.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Strumenti di test di gestione qualità](quality-test-instruments.md)
- [Test di gestione qualità](quality-tests.md)
- [Gruppi di test di gestione qualità](quality-test-groups.md)
- [Variabili di test di gestione qualità](quality-test-variables.md)
- [Associazioni di controllo qualità](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
