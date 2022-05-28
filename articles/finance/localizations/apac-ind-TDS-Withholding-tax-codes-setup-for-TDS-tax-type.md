---
title: Impostare codici di ritenuta d'acconto per il tipo di imposta TDS
description: Questo argomento descrive come impostare codici di ritenuta d'acconto per l'imposta dedotta all'origine (TDS).
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
ms.openlocfilehash: ced5902b5a2e822f84a40da8149bc319c94973ba
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724729"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>Impostare codici di ritenuta d'acconto per il tipo di imposta TDS

[!include [banner](../includes/banner.md)]

Questo argomento descrive come impostare codici di ritenuta d'acconto per l'imposta dedotta all'origine (TDS).

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
