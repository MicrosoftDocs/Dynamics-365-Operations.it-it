---
title: Impostare autorità di ritenuta d'acconto per il tipo di imposta TDS
description: Questo argomento descrive come impostare autorità per l'imposta dedotta all'origine (TDS).
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
ms.openlocfilehash: 5375363a9b1383a83e80fc3c4b841780adab4172
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023350"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a>Impostare autorità di ritenuta d'acconto per il tipo di imposta TDS

[!include [banner](../includes/banner.md)]

Questo argomento descrive come impostare autorità per l'imposta dedotta all'origine (TDS).

1. Seleziona **Imposta \> Imposte indirette \> Uffici ritenuta d'acconto**.

    [![Pagina Uffici ritenuta d'acconto](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)

2. Nel campo **Tipo di imposta**, seleziona **TDS** per impostare gli uffici di ritenuta d'acconto per il tipo di imposta TDS.
3. Nel riquadro azioni seleziona **Nuova** per creare una riga.
4. Nel campo **Uffici ritenuta d'acconto**, immetti il nome dell'autorità TDS.
5. Nel campo **Descrizione** immettere una descrizione.
6. Nella Scheda dettaglio **Generale**, nel campo **COnto fornitore**, seleziona il conto fornitore per l'autorità TDS.

    > [!NOTE]
    > Devi definire il nome della banca in cui verranno depositati i fondi dovuti al fornitore dell'autorità TDS. Il nome della banca è definito nella pagina **Conti bancari** (**Contabilità fornitori \> Tutti i fornitori \> Fornitore \> Configura \> Conti bancari**).

7. Chiudi la pagina.
