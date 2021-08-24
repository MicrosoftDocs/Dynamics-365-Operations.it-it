---
title: Associare codici imposta TDS a gruppi di imposte TDS e definire la formula per il calcolo della TDS
description: In questo argomento viene illustrato come impostare gruppi di imposte TDS e associare codici imposta TDS a gruppi di imposte TDS. Per calcolare la TDS per un gruppo di imposte TDS, devi definire la formula per i codici imposta TDS ad essa associati.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 81aac53cca91a75cde811c314bd6f7039852d32505fe6540921e17f3d1bbc7ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739312"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a>Associare codici imposta TDS a gruppi di imposte TDS e definire la formula per il calcolo della TDS

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come impostare gruppi di imposte TDS e associare codici imposta TDS a gruppi di imposte TDS. Per calcolare la TDS per un gruppo di imposte TDS, devi definire la formula per i codici imposta TDS ad essa associati.

Attieniti alla seguente procedura per impostare un gruppo di imposte TDS, associarvi codici imposta TDS e definire la formula per il calcolo della TDS.

1. Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Gruppi ritenute d'acconto**.

    [![Pagina Gruppi ritenute d'acconto.](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)

2. Nel riquadro Azioni seleziona **Nuovo** per creare un gruppo di ritenute d'acconto per la TDS e immetti i dettagli necessari.
3. Nel campo **Tipo di imposta** seleziona **TDS**.
4. Nella Scheda dettaglio **Imposta** seleziona **Aggiungi** per creare una riga.
5. Nel campo **Codice ritenuta d'acconto**, seleziona il codice imposta TDS per il gruppo di imposte TDS. Il campo **Nome ritenuta d'acconto** mostra il nome del codice imposta TDS e il campo **Valore** mostra il valore.
6. Per ignorare il limite di soglia e il limite di soglia di eccezione definiti per il componente fiscale TDS associato al codice imposta TDS nelle transazioni TDS, seleziona la casella di controllo **Ignora soglia**.
7. Per impedire il calcolo del gruppo di imposte nelle transazioni, seleziona la casella di controllo **Esente**.
8. Nel riquadro Azioni, seleziona **Designer** per aprire il designer formula, in modo da poter definire la formula per il calcolo della TDS per il gruppo di imposte TDS. Nella pagina **Designer**, la scheda **Imposte** mostra i codici imposta TDS che sono stati selezionati per il gruppo di imposte TDS.

    [![Pagina Designer.](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)

9. Nella scheda **Calcolo**, seleziona **ALT + N** per creare una riga. Il campo **ID** mostra l'ID priorità generato automaticamente per il calcolo della TDS.
10. Nel campo **Codice imposta**, seleziona il codice imposta TDS per cui definire la formula. Tutti i codici imposta TDS che sono stati selezionati per il gruppo di imposte TDS sono disponibili per la selezione in questo campo.
11. Nel campo **Base imponibile** seleziona la base per il calcolo della TDS:

    - **Importo lordo** - Calcola la TDS in base all'importo lordo della transazione (ovvero l'importo della fattura) utilizzando l'espressione di calcolo definita per il codice imposta.
    - **Importo lordo escluso** - Calcola la TDS in base all'espressione di calcolo definita per il codice imposta.

    > [!NOTE]
    > Il campo **Base imponibile** non può essere impostato su **Importo lordo escluso** per il codice imposta TDS il cui ID priorità è **1**.

12. Il calcolo TDS si basa sulla formula definita nel campo **Espressione di calcolo** per ogni codice imposta associato al gruppo di imposte TDS. Seleziona il segno più (**+**), il segno meno (**-**), il segno di moltiplicazione (**\**_) o il segno di divisione (_*/**) per immettere l'espressione di calcolo per il codice imposta TDS selezionato nel campo **Espressione di calcolo**.

    > [!NOTE]
    > Nessuna espressione di calcolo può essere definita per il codice imposta TDS il cui ID priorità è **1**.

13. Per definire l'espressione di calcolo per il codice imposta TDS nel campo **Espressione di calcolo**, aggiungi i codici imposta TDS disponibili nella scheda **Imposte**. Per aggiungere codici imposta TDS nel campo **Espressione di calcolo**, puoi utilizzare uno dei seguenti metodi:

    - Trascina il codice imposta richiesto dalla scheda **Imposte** al campo **Espressione di calcolo**.
    - Tocca due volte (o fai doppio clic) sul codice imposta necessario nella scheda **Imposte**.
    - Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) sul codice imposta necessario nella scheda **Imposte**, quindi seleziona **Aggiungi codice imposta**.

    > [!NOTE]
    > Inserisci un'espressione di calcolo prima di ogni codice imposta TDS. I codici imposta TDS aggiunti all'espressione di calcolo vengono visualizzati tra parentesi (\[...\]).

14. Per cancellare l'espressione di calcolo definita per un codice imposta nel campo **Espressione di calcolo**, seleziona il pulsante **C**.
15. Per eliminare un record nella scheda **Calcolo**, seleziona **Elimina**.
16. Chiudi la pagina.
