---
title: Eseguire il processo di liquidazione TDS periodico
description: Questo argomento spiega come liquidare l'imposta dedotta all'origine (TDS, Tax Deducted at Source) periodica.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 5b4c3a83f3fed0907dacd415f5aff9fad3c10bc6
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408382"
---
# <a name="run-the-periodic-tds-settlement-process"></a>Eseguire il processo di liquidazione TDS periodico

[!include [banner](../includes/banner.md)]

Questo argomento spiega come liquidare l'imposta dedotta all'origine (TDS, Tax Deducted at Source) periodica.

1. Seleziona **Imposta \> Dichiarazioni \> Ritenuta d'acconto \> Pagamento ritenuta d'acconto**.

    [![Finestra di dialogo Pagamento ritenuta d'acconto.](./media/apac-ind-TDS-47.png)](./media/apac-ind-TDS-47.png)

2. Nella finestra di dialogo **Pagamento ritenuta d'acconto**, nel campo **Tipo di imposta**, seleziona **TDS**.
3. Nel campo **Numero conto imposta (TAN)** seleziona il numero di conto imposta (TAN) per cui eseguire il processo di liquidazione.
4. Nel campo **Gruppo componenti ritenuta d'acconto** seleziona il gruppo di componenti TDS per cui eseguire il processo di liquidazione.
5. Nel campo **Periodo di liquidazione** seleziona il periodo di liquidazione TDS per cui eseguire il processo di liquidazione.

    > [!NOTE]
    > Il processo di liquidazione TDS viene eseguito per tutti i periodi impostati per il periodo di liquidazione TDS nella scheda **Periodi** della pagina **Periodi liquidazione ritenuta d'acconto** (**Imposta \> Imposte indirette \> Ritenuta d'acconto \> Periodi liquidazione ritenuta d'acconto**).

6. Nel campo **Data iniziale** seleziona la data di inizio a partire dalla quale eseguire il processo di liquidazione TDS.

    Per un periodo specifico entro il periodo di liquidazione, la data di inizio definita per il periodo viene considerata come la data "da". Ad esempio, il periodo di liquidazione TDS ha due periodi: dal 1 aprile al 30 aprile 2009 e dal 1 maggio al 31 maggio 2009. Se selezioni **04/06/2009** (6 aprile 2009) come data di inizio nel campo **Data iniziale**, il processo di liquidazione comincerà sempre dal 1 aprile 2009.

    Se immetti un periodo successivo nel campo **Data iniziale**, ma senza liquidare un periodo precedente che rientra nel periodo di liquidazione, la liquidazione non avverrà per i periodi precedenti. Ad esempio, il periodo di liquidazione TDS ha tre periodi: dal 1 aprile al 30 aprile 2009, dal 1 maggio al 31 maggio 2009 e dal 1 giugno al 30 giugno 2009. Se selezioni **05/01/2009** (1 maggio 2009) come data di inizio nel campo **Data iniziale**, il processo di liquidazione verrà eseguito solo dal 1 al 31 maggio 2009. La liquidazione non avverrà per il periodo dal 1 al 30 aprile 2009.

7. Nel campo **Data transazione** seleziona la data per registrare la transazione di liquidazione TDS.
8. Nel campo **Versione pagamento ritenuta d'acconto**, seleziona la versione della liquidazione TDS:

     - **Originale** - Utilizza questa opzione per eseguire il processo di liquidazione TDS per la prima volta. La versione del pagamento originale viene utilizzata solo una volta per eseguire il processo di liquidazione TDS per una combinazione di TAN, un gruppo di componenti di ritenuta d'acconto e un periodo di liquidazione della ritenuta d'acconto.
    - **Ultime versioni** - Utilizza questa opzione se il processo di liquidazione TDS è già stato eseguito per il periodo specificato. Includi le transazioni retrodatate registrate dopo che il processo di liquidazione è stato eseguito in precedenza per il periodo. Puoi utilizzare questa opzione per eseguire il processo di liquidazione un numero qualsiasi di volte.

9. Seleziona la casella di controllo **Aggiorna** per eseguire il processo di liquidazione TDS e registrare gli importi nei conti CoGe. Se questa casella di controllo è deselezionata, il processo di liquidazione non verrà eseguito e i movimenti finanziari non verranno generati.
10. Seleziona **OK** per eseguire il processo di liquidazione TDS e generare il report sui pagamenti della ritenuta d'acconto. Lo stato delle transazioni TDS incluse nel processo di liquidazione è **Liquidato** nella pagina **Liquidazione** (vai a **Contabilità fornitori \> Pagamenti \> Giornale di registrazione pagamenti fornitore**, seleziona **Righe**, seleziona **Funzioni** e quindi seleziona **Liquidazione**).

### <a name="important-points"></a>Punti importanti

- Se un gruppo di componenti di ritenuta d'acconto non viene selezionato durante il processo di liquidazione, la liquidazione avviene per tutti i gruppi di componenti di ritenuta d'acconto per il TAN e il periodo di liquidazione selezionati. Viene creata una riga distinta per ogni gruppo di componenti di ritenuta d'acconto nella pagina **Modifica transazione aperta**.
- Il processo di regolamento si basa sulla natura della categoria di soggetto valutato per un periodo di liquidazione. Le transazioni per cui la natura della categoria di soggetto valutato è **Società** vengono liquidate e vengono visualizzate come riga nella pagina **Modifica transazione aperta**. Le transazioni per cui la natura della categoria di soggetto valutato è differente da **Società** vengono liquidate e vengono visualizzate come riga nella pagina **Modifica transazione aperta**.
- La data di scadenza delle righe di transazioni TDS liquidate nella pagina **Modifica transazione aperta** si basa sui termini di pagamento definiti per il fornitore dell'autorità TDS nella pagina **Fornitori**. Se i termini di pagamento non sono definiti per il fornitore dell'autorità TDS, l'ultimo giorno del periodo di liquidazione viene visualizzato come data di scadenza.
