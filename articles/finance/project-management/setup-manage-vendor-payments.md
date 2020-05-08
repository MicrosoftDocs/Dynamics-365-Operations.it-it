---
title: Configurare e utilizzare i pagamenti del fornitore con Retribuisci su retribuzione
description: Questo argomento spiega come creare termini di Retribuisci su retribuzione in modo da poter rilasciare pagamenti parziali del fornitore, in base ai pagamenti dei clienti.
author: RadhikaRS
manager: AnnBe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 390cec62d2790ed10892669e283f2283c6b8e686
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284115"
---
# <a name="set-up-and-use-pay-when-paid-vendor-payments"></a>Configurare e utilizzare i pagamenti del fornitore con Retribuisci su retribuzione

[!include [banner](../includes/banner.md)]

Quando si approva un fornitore a lavorare come subappaltatore, è possibile che si desideri trattenere il pagamento al fornitore fino a quando il cliente non paga per il progetto. Per supportare questo scenario, è possibile impostare termini pay-on-paid (Retribuisci su retribuzione) quando si imposta l'ordine fornitore (PO) con il fornitore.

Ad esempio, quando un cliente paga un importo in una fattura del progetto, è possibile rilasciare parte o tutto l'importo della fattura del fornitore. Basta impostare i termini Retribuisci su retribuzione che specificano che il fornitore verrà pagato dopo aver ricevuto una percentuale del relativo pagamento dal cliente. Quando si riceve il pagamento parziale da un cliente, è possibile rilasciare manualmente alcune fatture fornitore correlate per il pagamento.

L'esempio seguente descrive il processo quando vengono utilizzati i termini Retribuisci su retribuzione.

## <a name="example"></a>Esempio

L'organizzazione accetta di fornire a un cliente 100 computer con software installato, al prezzo di 150,00 dollari USA (USD) per computer. Quindi si assumerà un venditore per fornire i computer su cui è installato il software. In base all'accordo, il cliente deve approvare la qualità dei computer prima di pagare la propria organizzazione. La politica dell'organizzazione è quella di trattenere il pagamento ai fornitori fino a quando il cliente non effettua il pagamento. Pertanto, si imposta il progetto in modo che esso abbia una percentuale per il Retribuisci su retribuzione del 100 percento.

Il fornitore invia i 100 computer su cui è installato il software, insieme a una fattura per 10.000,00 USD. Poiché i termini Retribuisci su retribuzione sono impostati per il progetto, non si paga il fornitore al ricevimento dei computer. Invece, si inviano i computer al cliente, insieme a una fattura per 15.000,00. Il cliente controlla i computer e approva l'intero importo della fattura del progetto.

Dopo aver ricevuto il pagamento completo dal cliente, pagare al fornitore l'intero importo della fattura fornitore, 10.000,00.

## <a name="set-up-pwp-terms-for-a-project"></a>Impostare i termini dell'opzione Retribuisci su retribuzione per il progetto

Quando si impostano i termini Retribuisci su retribuzione per un progetto, è necessario specificare, in percentuale, l'importo minimo che un cliente deve pagare per il progetto prima di pagare il fornitore. L'importo della soglia viene calcolato automaticamente sulle fatture cliente create per il progetto. Seguire i seguenti passaggi per impostare la percentuale di soglia per i termini Retribuisci su retribuzione.

1. Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti**.
2. Trovare e aprire il progetto per il quale si desidera impostare i termini Retribuisci su retribuzione.
3. Nella Scheda dettaglio **Contratti fornitore** fare clic su **Aggiungi riga**.
3. Nel campo **Codice conto** selezionare una delle seguenti opzioni:

    - **Tabella** – i termini dell'opzione Retribuisci su retribuzione sono applicabili a un singolo venditore.
    - **Gruppo** – i termini dell'opzione Retribuisci su retribuzione si applicano a tutti i fornitori in un gruppo di fornitori.
    - **Tutti** – i termini dell'opzione Retribuisci su retribuzione vengono applicati a tutti i fornitori.

4. Se si è selezionato **Tabella** o **Gruppo** nel passaggio precedente, nel campo **Fornitore/Gruppo di fornitori**, selezionare il fornitore o il gruppo di fornitori a cui si applicano i termini Retribuisci su retribuzione. Se si è selezionato **Tutti** nel passaggio precedente, il campo **Fornitore/ Gruppo di fornitori** non può essere modificato.
5. Se i termini di conservazione del fornitore sono impostati per il fornitore nel progetto, nel campo **Termini di ritenuta fornitore**, selezionare l'ID regola per i termini di conservazione.
6. Nel campo **Percentuale soglia opzione Retribuisci su retribuzione** immettere la percentuale di soglia per il progetto. La percentuale immessa per il progetto imposta l'importo minimo che deve essere pagato dal cliente prima che venga pagato il fornitore.

## <a name="create-a-po-that-has-pwp-terms"></a>Creare un PO con termini Retribuisci su retribuzione

Quando si registra una fattura da un fornitore, se il venditore è soggetto ai termini Retribuisci su retribuzione, tali termini vengono visualizzati nelle righe PO. Per creare un PO con termini Retribuisci su retribuzione, effettuare le seguenti operazioni:

1. Andare a **Approvvigionamento** \> **Ordini fornitore** \> **Tutti gli ordini fornitore**.
2. Nel Riquadro azioni selezionare **Nuovo**. Quindi, nella finestra di dialogo **Crea ordine fornitore**, immettere le informazioni richieste e selezionare **OK**.

    In alternativa, aprire un PO esistente sulla pagina di elenco **Tutti gli ordini fornitore**.

4. Nella pagina **Ordine fornitore**, nella scheda dettaglio **Righe ordine fornitore** , rivedere i dettagli della riga PO per il fornitore. L'opzione **Retribuisci su retribuzione** è selezionata automaticamente, ed il valore nel campo **Percentuale soglia opzione Retribuisci su retribuzione** è automaticamente copiato dal campo **Percentuale soglia opzione Retribuisci su retribuzione** nella pagina **Progetti** .
6. Se non si desidera applicare termini Retribuisci su retribuzione al fornitore per una riga PO, deselezionare l'opzione **Retribuisci su retribuzione**. In questo caso, il campo **Percentuale soglia opzione Retribuisci su retribuzione** per la linea PO verrà resettato a 0 (zero).

## <a name="update-a-customer-payment-and-pay-the-vendor"></a>Aggiornare un pagamento cliente e pagare il fornitore

Quando un fornitore completa il suo lavoro su un progetto e invia una fattura, è necessario rivedere lo stato del progetto e le fatture del cliente per determinare se i termini Retribuisci su retribuzione sono stati rispettati per il progetto. Se i termini dell'opzione Retribuisci su retribuzione per il fornitore sono stati soddisfatti, è possibile determinare quali righe fattura fornitore pagare, in base ai pagamenti cliente del progetto. Se si decide di pagare il fornitore anche se i termini dell'opzione Retribuisci su retribuzione non vengono soddisfatti, è possibile sostituirli nel modulo **Fatture fornitore con Retribuisci su retribuzione**.

1. Vai a **Gestione progetti e contabilità** \> **Richieste di informazioni e report** \> **Richieste di informazioni conservazione** \> **Fattura fornitore con Retribuisci su retribuzione**.
2. Nella pagina **Fatture fornitore con Retribuisci su retribuzione**, nel campo di ricerca, immettere i valori per trovare la fattura fornitore che si desidera rivedere, quindi selezionare **Cerca**.
3. Nella scheda rapida **Righe fattura fornitore**, selezionare le righe che si desidera modificare.
4. Se le condizioni **Retribuisci su retribuzione** sono soddisfatte le condizioni per la riga della fattura, selezionare **Rilascia pagamento fornitore**. L'opzione **Retribuisci su retribuzione** viene deselezionata e il valore del campo **Pronto per pagamento** viene modificato in **Sì**.
