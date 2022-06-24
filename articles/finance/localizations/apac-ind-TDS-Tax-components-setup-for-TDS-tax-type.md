---
title: Configurare componenti di imposta per il tipo di imposta TDS
description: In questo articolo viene illustrato come impostare i componenti di ritenuta d'acconto per il tipo di imposta TDS. Descrive inoltre come definire il limite di soglia utilizzato per calcolare la TDS per ogni componente TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: df2eb10ce9e372bb1e984f6ae1a2e889bbd90ad0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871159"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a>Configurare componenti di imposta per il tipo di imposta TDS

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come impostare i componenti di ritenuta d'acconto per il tipo di imposta TDS. I componenti TDS sono TDS, supplemento, PE-Cess e SHE Cess. Questo articolo descrive inoltre come definire il limite utilizzato per calcolare la TDS per ogni componente TDS. Inoltre, è possibile definire una soglia di eccezione utilizzata per calcolare la TDS per ogni componente TDS.

Per impostare i componenti TDS, procedi come segue:

1. Seleziona **Imposta \> Impostazione \> Ritenuta d'acconto \> Componenti ritenuta d'acconto**.

    [![Pagina Componenti ritenuta d'acconto.](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)

2. Nel campo **Tipo di imposta**, seleziona **TDS** per impostare i componenti di ritenuta d'acconto per il tipo di imposta TDS.
3. Nel riquadro azioni seleziona **Nuova** per creare una riga.
4. Nel campo **Componente ritenuta d'acconto**, immetti un nome per il componente TDS.
5. Nel campo **Gruppo componenti ritenuta d'acconto** seleziona il gruppo di componenti di ritenuta d'acconto TDS a cui associare il componente TDS.
6. Nella Scheda dettaglio **Generale**, nel campo **Descrizione** immetti una descrizione del componente TDS.
7. Nel riquadro Azioni, seleziona **Soglia** per aprire la pagina **Soglia**, in modo da poter definire il limite utilizzato per calcolare la TDS per il componente TDS.
8. Usa i campi **Data iniziale** e **Data finale** per definire il periodo a cui si applica la soglia.
9. Nella Scheda dettaglio **Generale**, in **Soglia**, immetti l'importo della soglia utilizzato per calcolare la TDS per il componente TDS. L'imposta verrà dedotta all'origine solo quando l'importo cumulativo delle fatture supera la soglia.

    Ad esempio, se l'importo della soglia è 10.000, la TDS viene calcolata dopo che l'importo cumulativo delle fatture supera 10.000 (in altre parole, quando è 10.001 o più).

10. Nel campo **Soglia eccezione**, immetti l'importo della soglia di eccezione utilizzato per calcolare la TDS per il componente TDS. L'imposta su una riga di fattura verrà dedotta all'origine solo quando l'importo supera la soglia.

    Ad esempio, se l'importo della soglia di eccezione è 5.000, la TDS viene calcolata su una specifica riga di fattura se l'importo della riga di fattura supera 5.000 (in altre parole, è 5.001 o più).

    [![Pagina Soglia.](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)

    > [!NOTE]
    > L'importo della soglia di eccezione deve essere inferiore o uguale all'importo della soglia.
    >
    > L'imposta viene dedotta per una transazione se l'importo della transazione supera la soglia di eccezione, anche se l'importo cumulativo delle fatture non supera la soglia specificata nel campo **Soglia**.

11. Chiudi la pagina **Soglia** per tornare alla pagina **Componenti ritenuta d'acconto**.
12. Nel riquadro Azioni seleziona **Copia** per aprire la finestra di dialogo **Copia componenti ritenuta d'acconto**, in modo da poter copiare i componenti TDS impostati per un gruppo di componenti TDS in un altro gruppo di componenti TDS.
13. Nel campo **Da** seleziona il gruppo di componenti TDS da cui copiare i componenti TDS. Nel campo **A** seleziona il gruppo di componenti di ritenuta d'acconto in cui copiare i componenti TDS.

    > [!NOTE]
    > I componenti TDS comuni associati a entrambi i gruppi di componenti TDS non vengono copiati.

14. Seleziona **OK** per copiare e creare componenti TDS per l'altro gruppo di componenti TDS nella pagina **Componenti ritenuta d'acconto**.

    [![Finestra di dialogo Copia componenti ritenuta d'acconto.](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)

15. Chiudere la pagina.
