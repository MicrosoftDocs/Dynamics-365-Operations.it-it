---
title: Impostare codici reporting di ritenuta d'acconto per il tipo di imposta TDS
description: I codici reporting di ritenuta d'acconto sono utilizzati per generare dichiarazioni con modulo 26Q e modulo 27Q per l'imposta dedotta all'origine (TDS). In questo argomento viene illustrato come impostare i passaggi dei codici reporting di ritenuta d'acconto in modo da poter impostare i codici reporting TDS.
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
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023368"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Impostare codici reporting di ritenuta d'acconto per il tipo di imposta TDS

[!include [banner](../includes/banner.md)]

I codici reporting di ritenuta d'acconto sono utilizzati per generare dichiarazioni con modulo 26Q e modulo 27Q per l'imposta dedotta all'origine (TDS). In questo argomento viene illustrato come impostare i passaggi dei codici reporting di ritenuta d'acconto in modo da poter impostare i codici reporting TDS.

1. Seleziona **Imposta \> Impostazione \> Ritenuta d'acconto \> Codici reporting ritenuta d'acconto**.

    [![Pagina Codici reporting ritenuta d'acconto](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)

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
