---
title: Impostare periodi di liquidazione della ritenuta d'acconto per il tipo di imposta TDS
description: Questo argomento descrive come impostare i periodi di liquidazione dell'imposta dedotta all'origine (TDS, Tax Deducted at Source).
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
ms.openlocfilehash: 3fe6a21636b3d875ac1fd56370b8a5a848ac0256
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407357"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a>Impostare periodi di liquidazione della ritenuta d'acconto per il tipo di imposta TDS

[!include [banner](../includes/banner.md)]

Questo argomento descrive come impostare i periodi di liquidazione dell'imposta dedotta all'origine (TDS, Tax Deducted at Source).

1. Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Periodi liquidazione ritenuta d'acconto**.

    [![Pagina Periodi liquidazione ritenuta d'acconto.](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)

2. Nel campo **Tipo di imposta**, seleziona **TDS** per impostare i periodi di liquidazione della ritenuta d'acconto per il tipo di imposta TDS.
3. Seleziona **Nuovo** per creare una riga.
4. Nel campo **Periodo di liquidazione** immetti un nome per il periodo di liquidazione TDS.
5. Nel campo **Descrizione** immettere una descrizione.
6. Nel campo **Ufficio tributario ritenuta d'acconto**, seleziona l'autorità TDS per cui stai definendo il periodo di liquidazione TDS.
7. Nella Scheda dettaglio **Generale** nel campo **Intervallo periodico** seleziona il tipo di intervallo periodico per il periodo di liquidazione TDS.
8. Nel campo **Numero di unità**, specifica il numero di unità per il tipo di intervallo periodico.
9. Nella Scheda dettaglio **Periodi**, nel campo **Data iniziale** seleziona la data iniziale del periodo di liquidazione TDS. Nel campo **Data finale** seleziona una data di fine.
10. Per creare un periodo di liquidazione TDS successivo per un periodo esistente, in base all'intervallo periodico e alle unità del periodo, seleziona **Nuovo periodo**.
11. Per visualizzare i dettagli della liquidazione TDS periodica eseguita per uno specifico periodo di liquidazione, seleziona **Pagamento ritenuta d'acconto** per aprire la pagina **Pagamento ritenuta d'acconto**.

    > [!NOTE]
    > Per eseguire il processo di liquidazione TDS periodico, vai a **Contabilità generale \> Periodico \> Ritenuta d'acconto \> Pagamento ritenuta d'acconto**.

    [![Pagina Pagamento ritenuta d'acconto.](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)

12. Chiudere la pagina.
