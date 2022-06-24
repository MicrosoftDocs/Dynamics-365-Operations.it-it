---
title: Impostare codici di ritenuta d'acconto per il tipo di imposta TDS
description: Questo articolo descrive come impostare codici di ritenuta d'acconto per l'imposta dedotta all'origine (TDS).
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
ms.openlocfilehash: fabe14b74c445434c37cb6ee79597d37affb162d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904385"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>Impostare codici di ritenuta d'acconto per il tipo di imposta TDS

[!include [banner](../includes/banner.md)]

Questo articolo descrive come impostare codici di ritenuta d'acconto per l'imposta dedotta all'origine (TDS).

1. Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Codici ritenuta d'acconto**.

    [![Pagina Codici ritenuta d'acconto.](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. Nel riquadro Azioni seleziona **Nuovo** per creare un codice di ritenuta d'acconto per la TDS e immetti i dettagli necessari.
3. Nella Scheda dettaglio **Generale**, nel campo **Tipo di imposta**, seleziona **TDS** per categorizzare il codice imposta come codice imposta TDS.
4. Nel campo **Periodo di liquidazione** seleziona il periodo di liquidazione TDS per il codice imposta TDS.
5. Nel campo **Conto principale** seleziona il conto CoGe in cui registrare l'importo TDS.
6. Nel campo **Conto clienti**, seleziona il conto clienti in cui registrare l'importo TDS che viene detratto nelle transazioni di vendita.

    Il campo **Origine** viene impostato automaticamente su **Percentuale dell'importo lordo** e il valore non può essere modificato.

    > [!NOTE]
    > Non puoi impostare l'origine su **Percentuale dell'importo netto** per i codici imposta del tipo di imposta TDS.

7. Nel campo **Componente ritenuta d'acconto**, seleziona il componete imposta TDS per il codice imposta TDS.
8. Nel riquadro Azioni, seleziona **Valore** per aprire la pagina **Valori ritenuta d'acconto**.
9. Nel campo **Data iniziale** immetti la data di inizio per il valore TDS. Nel campo **Data finale** immetti una data di fine.

    > [!NOTE]
    > I campi **Limite minimo**, **Limite superiore** e **Escludi %** non sono disponibili per i codici imposta del tipo di imposta TDS.

10. Nel campo **Valore**, immetti la percentuale di TDS per il codice imposta TDS.
11. Chiudi la pagina **Valori ritenuta d'acconto** per tornare alla pagina **Codici ritenuta d'acconto**.

    > [!NOTE]
    > I pulsanti **Limiti** nella pagina **Codici ritenuta d'acconto** non sono disponibili per i codici imposta del tipo di imposta TDS.

12. Chiudi la pagina.
