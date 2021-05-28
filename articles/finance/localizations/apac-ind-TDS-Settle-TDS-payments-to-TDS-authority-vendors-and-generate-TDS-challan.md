---
title: Liquidare pagamenti TDS a fornitori dell'autorità TDS e generare un challan TDS
description: Questo argomento descrive come liquidare i pagamenti dell'imposta dedotta all'origine (TDS) ai fornitori dell'autorità TDS.
author: kailiang
ms.date: 03/12/2021
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
ms.openlocfilehash: 5b77985a75d2930267cf94d6f218d53b47e6e705
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023365"
---
# <a name="settle-tds-payments-to-tds-authority-vendors-and-generate-tds-challan"></a>Liquidare pagamenti TDS a fornitori dell'autorità TDS e generare un challan TDS

[!include [banner](../includes/banner.md)]

Questo argomento descrive come liquidare i pagamenti dell'imposta dedotta all'origine (TDS) ai fornitori dell'autorità TDS.

1. Vai a **Contabilità fornitori \> Pagamenti \> Giornale di registrazione pagamenti fornitore**.

    [![Pagina Giornale di registrazione pagamenti fornitore](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)

2. Nella pagina **Giornale di registrazione pagamenti fornitore**, seleziona **Nuovo** per creare una riga di giornale di registrazione.
3. Nel campo **Conto**, seleziona il fornitore dell'autorità TDS a cui liquidare i pagamenti TDS.
4. Seleziona **Transazioni liquidazione** per aprire la pagina **Transazioni liquidazione**, dove puoi visualizzare le transazioni TDS liquidate per il fornitore dell'autorità TDS.

    Le transazioni TDS liquidate per un periodo di liquidazione sono visualizzate nel modo seguente:

    - Le transazioni TDS per cui la natura della categoria di soggetto valutato è **Società** vengono visualizzate come un'unica riga di transazione.
    - Le transazioni TDS per cui la natura della categoria di soggetto valutato è **HUF**, **Ditta**, **Persona fisica**, **AOP**, **BOI**, **Autorità locale** o **Altri** vengono visualizzate come un'unica riga di transazione.
    - Il campo **Importo** mostra l'importo TDS totale che deve essere pagato al fornitore dell'autorità TDS.

5. Seleziona **Transazioni ritenuta d'acconto** per visualizzare le diverse transazioni TDS incluse per il record di liquidazione. In questa pagina puoi visualizzare la divisione di ciascuna transazione TDS inclusa nel processo di liquidazione per il periodo di liquidazione.
6. Nella scheda **Panoramica**, seleziona la casella di controllo **Contrassegna** per le transazioni TDS da liquidare al fornitore dell'autorità TDS.

    La scheda **Panoramica** mostra le seguenti informazioni per ciascuna transazione TDS aperta:

    - **Data** - La data della transazione TDS.
    - **Giustificativo** - Il numero di giustificativo.
    - **Origine** - Il modulo in cui viene registrata la transazione TDS.
    - **Fornitore/cliente** - Il numero di conto del fornitore o del cliente da cui viene detratta la TDS.
    - **Nome beneficiario/parte** - Il nome del fornitore o del cliente da cui viene detratta la TDS.
    - **Natura soggetto valutato** - La natura della categoria di soggetto valutato a cui appartiene il beneficiario.
    - **Importo** - L'importo della fattura su cui è stata calcolata la TDS.
    - **Importo imposta** - L'importo TDS calcolato per la transazione.

    > [!NOTE]
    > Deseleziona la casella di controllo **Contrassegna** per qualsiasi transazione TDS che non deve essere liquidata al fornitore dell'autorità TDS.

    Nella scheda **Generale**, il campo **PAN** mostra il numero di conto permanente (PAN) del beneficiario. Il campo **Data** mostra la data del calcolo TDS e il campo **Valore** mostra la percentuale totale utilizzata per il calcolo della TDS.

7. Seleziona **Giustificativo** per visualizzare le voci del giustificativo per la transazione TDS.
8. Chiudi la pagina.
10. Seleziona **Componenti ritenuta d'acconto** per aprire la pagina **Componenti ritenuta d'acconto** in cui puoi visualizzare la TDS calcolata per il componente fiscale TDS di uno specifico codice imposta TDS.

    Nella scheda **Panoramica**, il campo **Componente fiscale** mostra il componente fiscale TDS utilizzato per la transazione. Il campo **Importo** mostra l'importo TDS calcolato per il componente fiscale TDS, nella valuta di base. Il campo **Importo cumulato** mostra l'importo TDS totale calcolato per il componente fiscale TDS di tutte le transazioni liquidate.

    Nella scheda **Importo**, la sezione **Valuta predefinita** mostra l'importo TDS calcolato per la componente fiscale TDS, nella valuta predefinita. La sezione **Valuta secondaria** mostra l'importo nella valuta secondaria.

11. Chiudi la pagina **Componenti ritenuta d'acconto**.
12. Nella pagina **Modifica transazione aperta**, nel campo **Importo**, nota che l'importo totale da liquidare al fornitore dell'autorità TDS per il periodo di liquidazione viene aggiornato.
13. Per liquidare le transazioni TDS di diversi periodi di liquidazione TDS al fornitore dell'autorità TDS, seleziona la casella di controllo **Contrassegna** delle transazioni.
14. Chiudi la pagina **Modifica transazione aperta**.

    > [!NOTE]
    > Se vengono selezionate solo poche transazioni per la liquidazione nella pagina **Transazioni ritenuta d'acconto**, l'importo TDS totale delle transazioni selezionate viene aggiornato nel campo **Correzione** della pagina **Modifica transazione aperta**. L'importo della correzione viene aggiornato nella riga del giornale di registrazione nella pagina **Giustificativo giornale di registrazione** e la pagina **Modifica transazione aperta** viene chiusa.

    Nella pagina **Giustificativo giornale di registrazione**, il campo **Addebito** mostra l'importo totale da pagare al fornitore dell'autorità TDS.

15. Immetti i dettagli del conto di contropartita.

    > [!NOTE]
    > Se le transazioni TDS hanno diversi numeri di conto imposta (TAN), le righe del giornale di registrazione vengono create per TAN nella pagina **Giustificativo giornale di registrazione**.

16. Nella scheda **Commissione pagamento**, nel campo **ID commissione**, seleziona un ID commissione il cui tipo di commissione è **Interessi** o **Altri** per addebitare la commissione di pagamento per i pagamenti ritardati effettuati al fornitore dell'autorità TDS.

    Nella scheda **Informazioni fiscali**, nella sezione **Informazioni società**, il campo **Nome** mostra il nome della società. Nella sezione **Ritenuta d'acconto**, il campo **Numero conto imposta (TAN)** mostra il TAN associato alla riga di transazione.

17. Convalida e registra il giornale di registrazione.
18. Seleziona **Ritenuta d'acconto\> Informazioni challan** per immettere i dettagli dello challan per la transazione.

    Il campo **Giustificativo** mostra il numero di giustificativo della transazione.
    
19. Seleziona la casella di controllo **TDS depositato tramite registrazione contabile** se l'importo TDS viene depositato utilizzando la registrazione contabile.
20. Nel campo **Numero challan**, immetti il numero di challan utilizzato per effettuare il pagamento al fornitore dell'autorità TDS.
21. Immetti la data dello challan nel campo **Data**.
22. Nel campo **Nome banca** seleziona il nome della banca in cui deve essere depositato l'importo TDS pagabile al fornitore dell'autorità TDS. Questo campo elenca tutti i conti bancari impostati per il fornitore dell'autorità TDS in **Contabilità fornitori \> Tutti i fornitori \> Configura \> Conti bancari**.
23. Nel campo **Codice BSR** immetti il codice BSR (Basic Statistical Return) della banca.
24. Chiudi la pagina.

### <a name="example"></a>Esempio

Il periodo 04/01/2009 viene liquidato per il gruppo di componenti TDS **Affitto** utilizzando il processo di liquidazione TDS periodico. L'importo TDS totale di 141.625,00 viene registrato nel conto del fornitore dell'autorità TDS per il periodo di liquidazione TDS. Puoi visualizzare questo importo nel campo **Importo** nella pagina **Modifica transazione aperta** per il fornitore dell'autorità TDS.

Se selezioni **Transazioni ritenuta d'acconto** per visualizzare le diverse transazioni TDS liquidate per il periodo, vengono visualizzate le seguenti informazioni.

| Importo TDS |
|------------|
| 16,995.00  |
| 22,660.00  |
| 28,325.00  |
| 16,995.00  |
| 28,325.00  |
| 16,995.00  |
| 11,330.00  |

Per uno specifico importo TDS, puoi selezionare **Componenti ritenuta d'acconto** per visualizzare la TDS calcolata per componente fiscale TDS di uno specifico codice imposta TDS. Per questo esempio, seleziona **Componenti ritenuta d'acconto** per l'importo TDS di 16.995,00. Viene visualizzato l'importo imposta calcolato per componente della transazione.

| Componente fiscale | Periodo    | Importo cumulato |
|---------------|-----------|--------------------|
| TDS           | 1,5000.00 | 125,000.00         |
| Supplemento     | 1,500.00  | 12,500.00          |
| PE-Cess       | 330.00    | 2,750.00           |
| SHE Cess      | 165.00    | 1,375.00           |

Se hai selezionato solo gli importi TDS 16.995,00, 22.660,00 e 28.325,00 per la liquidazione nella pagina **Transazioni ritenuta d'acconto**, l'importo totale della liquidazione viene visualizzato come **67.980,00** nel campo **Correzione** della pagina **Modifica transazione aperta**. Se questa transazione è contrassegnata per la liquidazione e la pagina **Modifica transazione aperta** viene chiusa, l'importo **67.980,00** è visualizzato nel campo **Addebito** della pagina **Giustificativo giornale di registrazione**.

Ora puoi pubblicare il giornale di registrazione e generare lo challan TDS.

### <a name="adjustment-of-advance-payments-that-are-made-to-tds-authority-vendors"></a>Adeguamento dei pagamenti anticipati effettuati ai fornitori dell'autorità TDS

Per adeguare un pagamento anticipato effettuato al fornitore dell'autorità TDS a un pagamento effettivo, vai a **Contabilità fornitori \> Fornitori \> Tutti i fornitori \> Modifica transazioni**. Se il pagamento effettivo effettuato supera il pagamento anticipato, vengono generati due numeri di challan per la transazione. Tuttavia, solo il primo numero di challan è visualizzato nella richiesta TDS.
