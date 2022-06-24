---
title: Pagamenti anticipati dei clienti
description: Questo articolo spiega come impostare ed elaborare i pagamenti anticipati dei clienti (noti anche come depositi cliente).
author: twheeloc
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88773067c472471fb75167712268d1076c1738a5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861562"
---
# <a name="customer-prepayments"></a>Pagamenti anticipati dei clienti

[!include [banner](../includes/banner.md)]

I pagamenti anticipati dei clienti vengono utilizzati quando si riceve un pagamento da un cliente, ma non esiste alcuna fattura in base alla quale il pagamento può essere liquidato. Questi tipi di pagamenti sono anche denominati depositi cliente.

Il processo di impostazione e utilizzo dei pagamenti anticipati dei clienti consiste nei seguenti passaggi di base.

1. Crea un profilo di registrazione cliente per i pagamenti anticipati.
2. Imposta il parametro **Profilo registrazione con giustificativo giornale di registrazione per pagamento anticipato**.
3. Crea un giornale di registrazione pagamenti del cliente e seleziona la casella di controllo **Giustificativo giornale di registrazione per pagamento anticipato** in ogni riga.
4. Registra il giornale di registrazione pagamenti cliente.
5. Dopo aver generato una fattura, liquida il pagamento anticipato con la stessa utilizzando la pagina **Liquida transazioni aperte**.

## <a name="create-a-customer-posting-profile-for-prepayments"></a>Creare un profilo di registrazione cliente per i pagamenti anticipati

In genere, quando accetti pagamenti anticipati o depositi dai clienti prima della consegna di beni o servizi o prima dell'esistenza di una fattura nel tuo sistema, ti consigliamo di registrare il contante come passività anziché come cespite nel piano dei conti. Tuttavia, i requisiti per la registrazione di questi importi nella contabilità generale potrebbero differire, a seconda del paese. Pertanto, assicurati di consultare i contabili in merito a eventuali normative locali applicabili.

In generale, il processo per la creazione di un profilo di registrazione che può essere utilizzato per i pagamenti anticipati è lo stesso del processo per la creazione di altri profili di registrazione. La differenza principale è il conto principale selezionato nel campo **Conto riepilogativo**. Per ulteriori informazioni, vedi [Profili di registrazione cliente](customer-posting-profiles.md).

## <a name="define-parameters-for-customer-prepayments"></a>Definire parametri per i pagamenti anticipati dei clienti

Esistono due parametri di contabilità clienti principali che devi considerare quando configuri il sistema per i pagamenti anticipati dei clienti. Per configurare i parametri, procedi come descritto di seguito.

1. Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
2. Facoltativo: nella scheda **Contabilità generale e IVA**, nella Scheda dettaglio **Pagamento**, imposta l'opzione **IVA su giustificativo giornale di registrazione per pagamento anticipato** su **Sì**.
3. Nel campo **Profilo registrazione con giustificativo giornale di registrazione per pagamento anticipato** seleziona il profilo di registrazione cliente da utilizzare quando vengono registrati i pagamenti anticipati dei clienti.
4. Chiudi la pagina.

## <a name="create-customer-prepayment-vouchers"></a>Creare giustificativi di pagamenti anticipati dei clienti

Quando crei il giornale di registrazione pagamenti dei clienti, per ogni pagamento anticipato devi impostare l'opzione **Giustificativo giornale di registrazione per pagamento anticipato** su **Sì** nella pagina **Giornale di registrazione pagamenti cliente**. Per creare un pagamento anticipato dei clienti, completa i passaggi seguenti.

1. Vai a **Contabilità clienti \> Pagamenti \> Giornale di registrazione pagamenti cliente**.
2. Seleziona **Nuovo** per creare un giornale di registrazione.
3. Seleziona il nome del giornale di registrazione nel campo **Nome**.

    > [!IMPORTANT]
    > Se imposti l'opzione **IVA su giustificativo giornale di registrazione per pagamento anticipato** su **Sì** nella procedura precedente, devi selezionare un nome di giornale di registrazione in cui il parametro **L'importo include l'IVA** è selezionato. 

4. Facoltativo: nel campo **Descrizione**, immetti una descrizione dettagliata.
5. Selezionare **Righe**.
6. Se non esiste una riga vuota, seleziona **Nuovo** per creare una riga.
7. Nel campo **Data** immetti la data in cui il pagamento anticipato deve essere registrato.
8. Nel campo **Conto** seleziona il cliente per il pagamento anticipato.
9. Facoltativo: nel campo **Descrizione**, immetti una descrizione dettagliata della transazione.
10. Nel campo **Avere**, immetti l'importo del pagamento anticipato.
11. Nel campo **Conto di contropartita** seleziona il conto a cui applicare la contropartita per il pagamento. Ad esempio, seleziona la banca o il conto principale in cui registrare il pagamento.
12. Nel campo **Metodo di pagamento** seleziona il metodo di pagamento del cliente.
13. Nella scheda **Pagamento**, imposta l'opzione **Giustificativo giornale di registrazione per pagamento anticipato** su **Sì**.
14. Ripeti i passaggi da 7 a 13 per ogni pagamento anticipato aggiuntivo che deve essere registrato.
15. Seleziona **Registra** per finalizzare il giornale di registrazione.

## <a name="settle-prepayments-with-invoices"></a>Liquidare pagamenti anticipati con fatture

Puoi usare l'area di lavoro **Pagamenti clienti** per trovare e liquidare facilmente i pagamenti che non sono stati completamente liquidati.

1. Nel dashboard **Home**, seleziona il riquadro **Pagamenti clienti**.
2. Nella sezione **Transazioni cliente**, nella scheda **Pagamenti non liquidati**, cerca e seleziona il pagamento da liquidare.
3. Seleziona **Liquida transazioni**.
4. Seleziona la casella di controllo **Contrassegna** per la fattura e il pagamento che verrà liquidato.
5. Selezionare **Registra**.

Per ulteriori informazioni su come liquidare le transazioni aperte, vedi [Panoramica della liquidazione](/dynamics365/finance/cash-bank-management/settlement-overview).
