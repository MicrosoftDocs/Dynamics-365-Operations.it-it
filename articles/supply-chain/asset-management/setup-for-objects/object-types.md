---
title: Tipi di cespite
description: Nell'articolo viene descritto come creare tipi di cespite in Gestione cespiti. Sono descritti inoltre gli elementi correlati ai tipi di cespite.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectJobType, EntAssetObjectType, EntAssetObjectTypeDefaultSparePart, EntAssetObjectTypeDefaultSparePartApprove, EntAssetObjectTypeDefaultCreateCombinations, EntAssetObjectTypeDefault, EntAssetObjectTypeDefaultCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3a51fdb55e9158e88e89549e3d0049e699c233e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887633"
---
# <a name="asset-types"></a>Tipi di cespite

[!include [banner](../../includes/banner.md)]



In questo articolo viene illustrato come creare tipi di cespite. Sono descritti inoltre gli elementi correlati ai tipi di cespite. I tipi di cespite vengono utilizzati come categorie generali per i cespiti. Alcuni esempi sono rappresentati dalle macchine CNC, attrezzature di misura e camion. I tipi di cespite vengono utilizzati per gestire i tipi di processo di manutenzione (attività di manutenzione), gli stati del ciclo di vita del cespite, i contatori, gli attributi del cespite, i modelli di valutazione delle condizioni e i modelli di cespite che è possibile selezionare per un cespite. Quando si crea un cespite, è necessario specificare il tipo di cespite.

Per ciascun tipo di cespite, variazioni di impostazione del tipo di cespite possono essere create. Ad esempio, se si dispone di un tipo di cespite **Camion**, è possibile creare le variazioni del tipo di cespite per diversi produttori e modelli del cespite. Per ciascuna impostazione di tipo di cespite, sarà possibile aggiungere i pezzi di ricambio e i piani di manutenzione necessari.

Innanzitutto, impostare i tipi di cespite necessari. A questo punto, è possibile creare i modelli di cespite che devono essere correlati ai tipi di cespite. Infine, nella pagina **Valori predefiniti tipo di cespite**, creare tutte le variazioni di tipi di cespite necessarie per la propria attrezzatura.

## <a name="create-an-asset-type"></a>Creare un tipo di cespite

1. Selezionare **Gestione cespiti** > **Impostazione** > **Tipi di cespite** > **Tipi di cespite**.
2. Selezionare **Nuovo** per creare un tipo di cespite.
3. Nel campo **Tipo di cespite**, immettere un ID tipo di cespite.
4. Nel campo **Nome** immettere un nome.
5. Selezionare un modello del ciclo di vita del cespite nel campo **Modello del ciclo di vita cespite**. Per ulteriori informazioni sugli stati del ciclo di vita del cespite e sui modelli del ciclo di vita del cespite, vedere [Stati del ciclo di vita del cespite](object-stages.md).
6. Impostare **Totale** su **Sì** se i valori degli indicatori di prestazioni chiave (KPI) devono essere calcolati per i cespiti con questo tipo di cespite.
7. Selezionare **Salva**.
8. Nella Scheda dettaglio **Tipi di processo di manutenzione**, selezionare i tipi di processo di manutenzione che devono essere associati al tipo di cespite:

    - Per selezionare un tipo di processo di manutenzione, selezionarlo nel campo **Tipi di processo di manutenzione rimanenti**, quindi fare clic sul pulsante freccia destra ![Pulsante freccia destra.](media/29-setup-for-objects.png) per spostarlo nella sezione **Tipi di processo di manutenzione selezionati**.
    - Per selezionare tutti i tipi di processo di manutenzione disponibili, selezionare il pulsante ![Freccia inoltra tutti](media/30-setup-for-objects.png) . Tutti i tipi di processo di manutenzione vengono trasferiti dal campo **Tipi di processo di manutenzione rimanenti** al campo **Tipi di processo di manutenzione selezionati**.
    - Per annullare la selezione di un tipo di processo di manutenzione, selezionarlo nel campo **Tipi di processo di manutenzione selezionati**, quindi fare clic sul pulsante freccia sinistra ![Pulsante freccia sinistra.](media/31-setup-for-objects.png) per spostarlo nel campo **Tipi di processo di manutenzione rimanenti**.

9. È anche possibile selezionare i contatori che devono essere correlati al tipo di cespite. Nella Scheda dettaglio **Contatori**, selezionare le opzioni desiderate utilizzando i metodi descritti per i tipi di processo di manutenzione nel passaggio 8. Per ulteriori informazioni su come impostare i contatori, vedere [Contatori](counters.md).
10. è anche possibile selezionare i tipi di attributo che devono essere correlati ai tipi di cespite. Nella Scheda dettaglio **Tipi di attributo**, selezionare le opzioni desiderate utilizzando i metodi descritti per i tipi di processo di manutenzione nel passaggio 8. Quindi, per creare la sequenza preferita dei tipi di attributi, selezionare un tipo di attributo nel campo **Tipi di attributo selezionati** e utilizzare i pulsanti freccia su e giù per spostarlo. La sequenza dei tipi di attributo verrà visualizzata sui cespiti che utilizzano questo tipo di cespite. Per ulteriori informazioni sugli attributi dei cespiti, vedere [Tipi di attributo di manutenzione](../setup-for-functional-locations/specification-types.md).

    > [!NOTE]
    > Quando si aggiungono nuovi tipi di attributo nella Scheda dettaglio **Tipi di attributo**, i cespiti esistenti viene aggiornati automaticamente con le informazioni.

11. è anche possibile selezionare i modelli di valutazione delle condizioni che devono essere correlati ai tipi di cespite. Nella Scheda dettaglio **Valutazioni della condizione**, selezionare le opzioni desiderate utilizzando i metodi descritti per i tipi di processo di manutenzione nel passaggio 8. Per ulteriori informazioni sui modelli e le registrazioni di valutazione delle condizioni, vedere [Valutazione delle condizioni](../setup-for-objects/condition-assessment.md).
12. La Scheda dettaglio **Modello cespite** mostra tutte le combinazioni di produttori e modelli del cespite impostati per il tipo di cespite selezionato. Per visualizzare le combinazioni suddivise in base al produttore, scegliere **Modello cespite** per aprire la pagina **Modello cespite**.

    Nella pagina **Modello cespite**, è possibile aggiungere relazioni modello di cespite-tipo di cespite. Inoltre, nella pagina **Tipi di cespite**, è possibile aggiungere le relazioni produttore del cespite-modello di cespite direttamente a un tipo di cespite. Infine, nella pagina **Modello cespite** (**Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Modello cespite**), è possibile creare nuove relazioni produttore del cespite-modello di cespite-tipo di cespite. Di conseguenza, sono disponibili tre modi di impostare e modificare le relazioni produttore del cespite-modello di cespite-tipo di cespite. Tutte le combinazioni disponibili sono mostrate da diverse prospettive ed è possibile selezionare il punto di ingresso preferito quando si lavora con le impostazioni.

> [!NOTE]
> - Se si selezionano i contatori per un tipo di cespite, le selezioni vengono aggiornate automaticamente nella pagina **Contatori** (**Gestione cespiti** > **Impostazione** > **Cespiti** > **Tipi di cespite** > **Contatori**).
> - I campi disponibili nella sezione **Dettagli** della Scheda dettaglio **Generale** indicano il numero di tipi di processi di manutenzione, contatori, attributi e così via, che sono impostati per il tipo di cespite selezionato.

In genere, gli ordini di lavoro creati manualmente sono correlati alla manutenzione correttiva, mentre gli ordini di lavoro creati automaticamente correlati alla preventiva. Quando si creano manualmente ordini di lavoro, solo i tipi di processo di manutenzione selezionati nella Scheda dettaglio **Tipi di processo di manutenzione** della pagina **Tipi di cespite** possono essere utilizzati. Tuttavia, gli ordini di lavoro automaticamente creati possono utilizzare tutti i tipi di processo di manutenzione creati nella pagina **Tipi di processo di manutenzione** (**Gestione cespiti** \> **Impostazione** \> **Processi** \> **Tipi di processo di manutenzione**).

## <a name="create-asset-type-setup-lines"></a>Creare righe di impostazione di tipo di cespite

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Tipi di cespite** \> **Impostazione tipo di cespite**. In alternativa, selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Tipi di cespite** \> **Tipi di cespite**, selezionare un tipo di cespite, quindi selezionare **Impostazione tipo di cespite**.
2. La prima volta che si utilizza la pagina **Impostazione tipo di cespite**, è possibile trovare il pulsante **Crea combinazioni** utile. È possibile utilizzare questo pulsante per creare rapidamente tutte le combinazioni di modello di cespite su un tipo di cespite. Selezionare **Crea combinazioni**, selezionare il tipo di cespite per cui creare combinazioni, quindi **OK**.

    > [!NOTE]
    > Se non si prevede di utilizzare tutte le combinazioni di impostazione del tipo di cespite create automaticamente, è possibile eliminare un'impostazione selezionandola e poi selezionano **Elimina**.

3. Selezionare **Nuovo** per creare manualmente un'impostazione di tipo di cespite.
4. A seconda di quanto specifica deve essere l'impostazione di tipo di cespite, selezionare le opzioni nei campi **Tipo di cespite**, **Produttore** e **Modello**.
5. Se un contratto di garanzia è associato al tipo di cespite, selezionare il contratto nei campi **Garanzia cliente** e **Garanzia fornitore**. 
6. Nella Scheda dettaglio **Pezzi di ricambio**, selezionare **Aggiungi** per aggiungere i pezzi di ricambio all'impostazione di tipo di cespite selezionata.
7. Per approvare un pezzo di ricambio, selezionare la riga del pezzo di ricambio, quindi **Approva**. È possibile selezionare più righe per l'approvazione.
8. Per verificare se un pezzo di ricambio viene utilizzato altrove in Gestione cespiti (ad esempio, in relazione a cespiti e ordini di lavoro) selezionare la riga del pezzo di ricambio quindi scegliere **Articolo utilizzato in** per aprire la pagina **Articolo utilizzato in**. Per visualizzare tutti i pezzi di ricambio attivi nell'elenco, selezionare la casella  controllo **Attivo**. Per visualizzare solo i pezzi di ricambio approvati, selezionare la casella di controllo **Approvato**.
9. Nella Scheda dettaglio **Piani di manutenzione**, selezionare **Aggiungi** per aggiungere i piani di manutenzione all'impostazione di tipo di cespite selezionata.
10. Per copiare un'impostazione di tipo di cespite in una diversa impostazione, è possibile utilizzare la funzione di copia. Selezionare l'impostazione di tipo di cespite in cui copiare l'impostazione, selezionare **Copia impostazione** e selezionare l'impostazione di tipo di cespite da cui copiare l'impostazione. Le impostazioni delle varie opzioni determinano la quantità di informazioni incluse. Al termine, scegliere **OK** per copiare l'impostazione.

> [!NOTE]
> Se sono presenti più righe dei pezzi di ricambio e righe di piani di manutenzione che riutilizzerete, la funzione di copia consente in modo semplice e rapido di impostare i dati per molte combinazioni di impostazioni di tipo di cespite.

## <a name="spare-parts-on-the-asset-type-setup"></a>Pezzi di ricambio nell'impostazione di tipo di cespite

Come è stato descritto nella sezione "Creare righe di impostazione di tipo di cespite", i pezzi di ricambio sono impostati sui modelli del cespite nella pagina **Impostazione tipo di cespite**. Pertanto, quando si apre la pagina **Impostazione tipo di cespite**, vengono visualizzati solo i pezzi di ricambio correlati alla combinazione selezionata di tipo di cespite, produttore del cespite e modello di cespite. Per visualizzare un elenco di tutti i record dei pezzi di ricambio, aprire la pagina **Pezzi di ricambio** (**Gestione cespiti** \> **Richieste di informazioni** \> **Pezzi di ricambio**).

Nella pagina **Pezzi di ricambio**, è possibile creare nuovi pezzi di ricambio per combinazioni esistenti di tipo cespite, produttore del cespite e modello di cespite. È possibile decidere se si preferisce creare record dei pezzi di ricambio nella pagina **Impostazione tipo di cespite** o **Pezzi di ricambio**. La pagina **Impostazione tipo di cespite** mostra una panoramica dei dati nella combinazione selezionata di tipo di cespite, produttore del cespite e modello di cespite, mentre la pagina **Pezzi di ricambio** mostra una panoramica completa di tutte le righe di impostazione tipo di cespite. Se la pagina **Pezzi di ricambio** contiene molti record, la pagina **Impostazione tipo di cespite** può fornire una panoramica migliore.

Per verificare se il pezzo di ricambio nella riga selezionata viene utilizzato altrove in Gestione cespiti (ad esempio, in relazione a cespiti e ordini di lavoro) selezionare la riga del pezzo di ricambio quindi scegliere **Articolo utilizzato in** per aprire la pagina **Articolo utilizzato in**. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]