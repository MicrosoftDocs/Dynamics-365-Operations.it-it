---
title: Impostare periodi di liquidazione della ritenuta d'acconto per il tipo di imposta TDS
description: Questo articolo descrive come impostare i periodi di liquidazione dell'imposta dedotta all'origine (TDS, Tax Deducted at Source).
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
ms.openlocfilehash: 855bda71f0967c53166cf0a7f5e7e465146f34a7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846557"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a>Impostare periodi di liquidazione della ritenuta d'acconto per il tipo di imposta TDS

[!include [banner](../includes/banner.md)]

Questo articolo descrive come impostare i periodi di liquidazione dell'imposta dedotta all'origine (TDS, Tax Deducted at Source).

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
