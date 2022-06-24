---
title: Impostare codici reporting di ritenuta d'acconto per il tipo di imposta TDS
description: I codici reporting di ritenuta d'acconto sono utilizzati per generare dichiarazioni con modulo 26Q e modulo 27Q per l'imposta dedotta all'origine (TDS). In questo articolo viene illustrato come impostare i passaggi dei codici reporting di ritenuta d'acconto in modo da poter impostare i codici reporting TDS.
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
ms.openlocfilehash: bdd2e89d29807dc31d8f2d4684ee413470b1dbde
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907800"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Impostare codici reporting di ritenuta d'acconto per il tipo di imposta TDS

[!include [banner](../includes/banner.md)]

I codici reporting di ritenuta d'acconto sono utilizzati per generare dichiarazioni con modulo 26Q e modulo 27Q per l'imposta dedotta all'origine (TDS). In questo articolo viene illustrato come impostare i passaggi dei codici reporting di ritenuta d'acconto in modo da poter impostare i codici reporting TDS.

1. Seleziona **Imposta \> Impostazione \> Ritenuta d'acconto \> Codici reporting ritenuta d'acconto**.

    [![Pagina Codici reporting ritenuta d'acconto.](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)

2. Nel campo **Tipo di imposta**, seleziona **TDS** per definire i codici reporting di ritenuta d'acconto per il tipo di imposta TDS.
3. Nel campo **Componente ritenuta d'acconto** seleziona il componente TDS per il quale stai definendo il codice reporting di ritenuta d'acconto. Il campo **Gruppo componenti ritenuta d'acconto** mostra il gruppo di componenti TDS definito per il componente TDS che stai definendo.

    Il campo **Codice sezione** nella Scheda dettaglio **Generale** mostra il codice sezione associato al gruppo di componenti TDS.

4. Nella Scheda dettaglio **Generale**, nel campo **Codice reporting**, seleziona un codice reporting TDS:

    - TDS
    - TCS
    - Supplemento
    - PE\_Cess
    - SHE\_Cess

5. Chiudi la pagina.
