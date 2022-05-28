---
title: Calcolo della TDS su pagamenti ed effetti passivi
description: In questo argomento vengono fornite informazioni di riferimento sulle diverse transazioni di pagamento su cui viene calcolata l'imposta dedotta all'origine (TDS, Tax Deducted at Source).
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
ms.openlocfilehash: 7f38a8c4b0416abb10bfdaf95c3379e964e9a41e
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726464"
---
# <a name="tds-calculation-on-payments-and-promissory-notes"></a>Calcolo della TDS su pagamenti ed effetti passivi

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni di riferimento sulle diverse transazioni di pagamento su cui viene calcolata l'imposta dedotta all'origine (TDS, Tax Deducted at Source).

| Numero di serie | Tipo di transazione | Importo transazione | Nome pagina e percorso | Tipo di conto e tipo di conto di contropartita |
|---------------|------------------|--------------------|--------------------|--------------------------------------|
| 1             | Pagamento anticipato/Pagamento contro fattura (TDS a debito) | Dare o Avere | <ul><li>Giornale di registrazione generale (**Contabilità generale \> Inserimenti nel giornale di registrazione \> Giornali di registrazione generale**)</li><li>Giornale di registrazione fatture (**Contabilità fornitori \> Fatture \> Giornale di registrazione fatture**)</li><li>Giornale di registrazione pagamenti (**Contabilità fornitori \> Pagamenti \> Giornale di registrazione pagamenti fornitore**)</li></ul> | Fornitore (Dare), Banca (Avere) |
| 2             | Pagamento anticipato/Pagamento contro fattura (Acquisto effettuato dal cliente - TDS a debito) | Dare o Avere | <ul><li>Giornale di registrazione generale (**Contabilità generale \> Inserimenti nel giornale di registrazione \> Giornali di registrazione generale**)</li><li>Giornale di registrazione fatture (**Contabilità fornitori \> Fatture \> Giornale di registrazione fatture**)</li><li>Giornale di registrazione pagamenti (**Contabilità fornitori \> Pagamenti \> Giornale di registrazione pagamenti fornitore**)</li></ul> | Cliente (Dare), Banca (Avere) |
| 3             | Effetti passivi | Dare | Giornale di registrazione effetti passivi emessi (**Contabilità fornitori \> Pagamenti \> Effetti passivi \> Giornale di registrazione effetti passivi emessi**) | Fornitore (Dare), CoGe (Avere) |
| 4             | Entrate varie (TDS a credito) | Dare o Avere | Giornale di registrazione generale (**Contabilità generale \> Inserimenti nel giornale di registrazione \> Giornali di registrazione generale**) | Banca (Dare), CoGe (Avere) |
| 5             | Altre spese (TDS a debito) | Dare o Avere | Giornale di registrazione generale (**Contabilità generale \> Inserimenti nel giornale di registrazione \> Giornali di registrazione generale**) | Banca (Dare), CoGe (Avere) |

Segui questi passaggi per calcolare la TDS su pagamenti e effetti passivi.

1. Nelle pagine del giornale di registrazione, crea le righe del giornale di registrazione. Seleziona il tipo di conto e il tipo di conto di contropartita.
2. Seleziona **Funzioni \> Liquidazione** per aprire la pagina **Modifica transazione aperta**. Quindi seleziona una fattura specifica che deve essere liquidata. Se la TDS è già stata calcolata a livello di fattura, il campo **Imponibile** mostra l'importo di base su cui la TDS è stata calcolata. Il campo **Importo TDS** mostra l'importo TDS calcolato per la transazione. Il campo **Importo** mostra l'importo netto del pagamento (ovvero l'importo del pagamento dopo la detrazione della TDS).

    > [!NOTE]
    > Per un pagamento effettuato contro fattura, si applicano le seguenti condizioni:
    >
    > - Se l'importo del pagamento e l'importo della fattura sono uguali, la TDS non viene calcolata se è già stata calcolata a livello di fattura.
    > - Se l'importo della fattura dopo la detrazione dell'importo TDS è superiore all'importo del pagamento, la TDS non viene calcolata.
    > - Se l'importo della fattura dopo la detrazione dell'importo TDS è inferiore all'importo del pagamento, la TDS viene calcolata sull'importo che supera l'importo della fattura.

3. Nella pagina **Giustificativo giornale di registrazione**, nella scheda **Panoramica**, nel campo **Gruppi TDS**, esamina o modifica il gruppo TDS predefinito definito per il fornitore o il cliente. La TDS calcolata sulle righe del giornale di registrazione si basa sulla formula definita per i codici imposta TDS nel gruppo TDS.

    > [!NOTE]
    > La TDS viene calcolata solo se l'opzione **Calcola ritenuta d'acconto** è impostata su **Sì** per il fornitore nella pagina **Fornitori**.

4. Nella scheda **Informazioni fiscali**, nella sezione **Informazioni società**, nel campo **Nome**, puoi selezionare il nome di una società per gli indirizzi alternativi impostati per la società.

    Nella sezione **Ritenuta d'acconto**, il campo **Natura soggetto valutato** mostra la natura della categoria di soggetto valutato del fornitore o del cliente. Il campo **Numero conto imposta (TAN)** mostra il numero di conto imposta (TAN) della società selezionata.

5. Seleziona il **pulsante Ritenuta d'acconto \> Ritenuta d'acconto** per aprire la pagina **Transazioni ritenuta d'acconto temporanee**. La parte superiore di questa pagina ha i seguenti campi:

    - **Importo ritenuta d'acconto in totale** - La TDS totale calcolata per la transazione per il gruppo TDS.
    - **Valore** - La percentuale totale utilizzata per calcolare la TDS per la transazione. La percentuale totale si basa sulla formula definita per i codici imposta TDS e associata al gruppo TDS.
    - **Importo ritenuta d'acconto rettificato in totale** - L'importo TDS rettificato totale per tutti i codici imposta nel gruppo TDS.
    - **TDS** - Una casella di controllo selezionata indica che un gruppo TDS è associato alla transazione.

    I campi nelle schede **Panoramica**, **Generale** e **Rettifica** mostrano l'importo TDS calcolato ei dettagli dell'importo TDS rettificato per ogni codice imposta TDS associato al gruppo TDS.

6. Seleziona **Soglia** per aprire la pagina **Soglia**, in cui è possibile esaminare il limite di soglia definito per il componente fiscale TDS associato a un codice fiscale TDS specifico.
7. Seleziona **Designer formula** per aprire la pagina **Designer formula**, in cui è possibile esaminare la formula definita per uno specifico codice imposta TDS.
8. Chiudi le pagine **Designer formula** e **Transazioni ritenuta d'acconto temporanee** per tornare alla pagina **Giustificativo giornale di registrazione**.
9. Convalida e registra il giornale di registrazione. L'importo TDS calcolato viene registrato nel conto fornitori definito per ogni codice imposta TDS nel gruppo TDS. I conti clienti per i codici imposta TDS sono definiti nella pagina **Codici ritenuta d'acconto**.
10. Seleziona **Ritenuta d'acconto registrata** per aprire la pagina **Transazioni ritenuta d'acconto**. Il campo **Valore** mostra la percentuale totale utilizzata per calcolare la TDS per la transazione.

    I campi nelle schede **Panoramica**, **Generale** e **Importo** mostrano gli importi TDS calcolati per il gruppo TDS associato alla transazione.

11. Esamina le informazioni sul calcolo della TDS per ogni codice imposta TDS associato al gruppo TDS.

## <a name="generate-payments"></a>Genera pagamenti

Per generare i pagamenti, segui questi passaggi.

1. Eseguire uno dei passaggi riportati di seguito.

    - Vai a **Contabilità fornitori \> Pagamenti \> Giornale di registrazione pagamenti fornitore**.
    - Vai a **Contabilità clienti \> Pagamenti \> Giornale di registrazione pagamenti cliente**.
    - Vai a **Contabilità fornitori \> Pagamenti \> Effetti passivi \> Giornale di registrazione effetti passivi emessi**.
    - Vai a **Contabilità clienti \> Pagamenti \> Effetto attivo \> Giornale di registrazione effetti attivi emessi**.
    - Vai a **Contabilità clienti \> Pagamenti \> Effetto attivo \> Giornale di registrazione effetti attivi riemessi**.

2. Selezionare **Righe**.
3. Seleziona **Funzioni \> Genera pagamenti**.
