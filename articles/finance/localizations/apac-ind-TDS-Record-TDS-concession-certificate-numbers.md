---
title: Registrare numeri di certificati di concessione TDS
description: In questo argomento viene illustrato come registrare i numeri di certificati di concessione dell'imposta dedotta all'origine (TDS) rilasciati ai fornitori.
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
ms.openlocfilehash: f543adc8bab5ca224bdb672d6b3c282c2d8531d8
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023346"
---
# <a name="record-tds-concession-certificate-numbers"></a>Registrare numeri di certificati di concessione TDS

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come registrare i numeri di certificati di concessione dell'imposta dedotta all'origine (TDS) rilasciati ai fornitori.

1. Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Concessioni ritenuta d'acconto**.
2. Nel campo **Tipo di imposta**, seleziona **TDS** per registrare certificati di concessione per il tipo di imposta TDS.
3. Nella scheda **Panoramica**, seleziona **ALT+N** per creare una riga.

    [![Intestazione della nuova riga](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. Nel campo **Codice ritenuta d'acconto**, seleziona il codice imposta TDS per il quale vengono emessi certificati di concessione. Il campo **Nome codice ritenuta d'acconto** mostra il nome del codice imposta TDS.
5. Nei campo **Data iniziale** e **Data finale**, definisci il periodo di validità del certificato di concessione che utilizza il codice imposta TDS per calcolare la TDS per il fornitore sulla base di una concessione.
6. Nel campo **Osservazioni**, immetti eventuali commenti.
7. Nel campo **Sezione** immetti il codice sezione giuridica del certificato di concessione TDS.

    Se il codice sezione è 197, il valore "A" appare sia nella colonna "Motivo per non detrazione/detrazione ridotta" nel modulo 26Q che nella colonna "Motivo per non detrazione/detrazione ridotta/calcolo del lordo (se presente)" nel Modulo 27Q. Se il codice sezione è 197A, il valore "B" appare in entrambe le colonne.

8. Seleziona la Scheda dettaglio **Certificato** per registrare i numeri di certificati di concessione TDS per i fornitori.
9. Nel campo **Conto fornitore** seleziona il conto fornitore per cui viene emesso il certificato di concessione TDS.
10. Nei campi **Data iniziale** e **Data finale**, definisci il periodo di validità del certificato di concessione TDS.

    Il calcolo del TDS sulla base di una concessione si basa sul periodo in cui il certificato viene creato per il fornitore.

11. Nel campo **Certificato**, immetti il numero di certificato di concessione TDS.

    [![Scheda dettaglio Certificato](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. Chiudi la pagina.
