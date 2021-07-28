---
title: Calcolo della TDS sulle fatture dalla pagina Fattura a testo libero
description: Questo argomento spiega come calcolare l'imposta dedotta all'origine (TDS) sulle fatture utilizzando la pagina Fattura a testo libero.
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
ms.openlocfilehash: 702fffa6b958e5cec26029bd5a12d01b0467ee6d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358292"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a>Calcolo della TDS sulle fatture dalla pagina Fattura a testo libero

[!include [banner](../includes/banner.md)]

Questo argomento descrive come calcolare l'imposta dedotta all'origine (TDS) sulle fatture utilizzando la pagina **Fattura a testo libero**.

1. Passa a **Contabilità clienti \> Fatture \> Tutte le fatture a testo libero**.

    [![Pagina Fattura a testo libero.](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)

2. Seleziona **Nuovo** per creare una fattura a testo libero e immetti i dettagli richiesti.
3. Seleziona la scheda **Fattura**. Nella sezione **Gruppo ritenute d'acconto**, il campo **Natura soggetto valutato** mostra la natura della categoria di soggetto valutato del cliente.
4. Nel campo **Gruppo TDS**, esamina o modifica il gruppo TDS predefinito definito per il cliente.

    > [!NOTE]
    > Quando selezioni un valore nel campo **Gruppo TCS**, il campo **Gruppo TCS** non è più disponibile. La TDS viene calcolata solo se l'opzione **Calcola ritenuta d'acconto** è impostata su **Sì** per il cliente nella pagina **Tutti i clienti**.

5. Nella scheda **Informazioni fiscali**, nella sezione **Informazioni società**, nel campo **Nome**, seleziona il nome della società per un indirizzo alternativo impostato per la società.

    Nella sezione **Ritenuta d'acconto**, il campo **Numero conto imposta (TAN)** mostra il numero di conto imposta (TAN) della società selezionata.

6. Nella scheda **Righe fattura**, crea righe fattura immetti i dettagli richiesti.

    Nella sezione **Gruppo ritenute d'acconto**, il campo **Numero conto imposta (TAN)** mostra il TAN e il campo **Gruppo TDS** mostra il gruppo TDS.

7. Seleziona **Ritenuta d'acconto** per aprire la pagina **Transazioni ritenuta d'acconto temporanee**. La parte superiore di questa pagina ha i seguenti campi:

    - **Importo ritenuta d'acconto in totale** - La TDS totale calcolata per la transazione per il gruppo TDS.
    - **Valore** - La percentuale totale utilizzata per calcolare la TDS per la transazione. La percentuale totale si basa sulla formula definita per i codici imposta TDS e associata al gruppo TDS.
    - **Importo ritenuta d'acconto rettificato in totale** - L'importo TDS rettificato totale per tutti i codici imposta nel gruppo TDS.
    - **TDS** - Una casella di controllo selezionata indica che un gruppo TDS è associato alla transazione.

    I campi nelle schede **Panoramica**, **Generale** e **Rettifica** mostrano l'importo TDS calcolato ei dettagli dell'importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.

8. Seleziona **Soglia** per aprire la pagina **Soglia**, in cui è possibile esaminare il limite di soglia definito per il componente fiscale TDS associato a un codice fiscale TDS specifico.
9. Seleziona **Designer formula** per aprire la pagina **Designer formula**, in cui è possibile esaminare la formula definita per uno specifico codice imposta TDS.
10. Registra la fattura a testo libero. L'importo TDS calcolato per la fattura a testo libero viene registrato nel conto clienti definito per ogni codice imposta TDS nel gruppo TDS. I conti clienti per i codici imposta TDS sono definiti nella pagina **Codici ritenuta d'acconto**.
11. Seleziona **Ritenuta d'acconto registrata** per aprire la pagina **Transazioni ritenuta d'acconto**. Il campo **Valore** mostra la percentuale totale utilizzata per calcolare la TDS per la transazione.

    I campi nelle schede **Panoramica**, **Generale** e **Importo** mostrano gli importi TDS calcolati sulle righe fattura.

12. Esamina le informazioni sul calcolo della TDS per ogni codice imposta TDS associato al gruppo TDS.
