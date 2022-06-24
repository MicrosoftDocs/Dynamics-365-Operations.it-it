---
title: ER genera documenti elettronici per i pagamenti utilizzando una configurazione di formato
description: Questo articolo descrive come utilizzare una nuova configurazione di formato di report elettronico per generare documenti elettronici per l'elaborazione dei pagamenti.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a79c32372402fcd49f20c855cbfa8d9bcd8ba524
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864603"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>ER genera documenti elettronici per i pagamenti utilizzando una configurazione di formato

[!include [banner](../../includes/banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può utilizzare una nuova configurazione del formato per la creazione di report elettronici (ER) per generare documenti elettronici per l'elaborazione dei pagamenti. Questi passaggi possono essere eseguiti nella società campione.

Per completare questi passaggi, è necessario prima completare i passaggi della procedura "Creare un documento per una configurazione con formato di pagamento".


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>Modificare la configurazione del metodo di pagamento elettronico
1. Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.
2. Attivare/disattivare la sezione Formato file per espanderla, se necessario.
3. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro al campo Metodo di pagamento in base a un valore "Elettronico".
4. Fare clic su Modifica.
5. Impostare il campo Report elettronici generici su Sì.
    * Selezionare Sì per utilizzare il modello Report elettronici generici per la creazione dei file di pagamento.  
6. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
7. Selezionare la configurazione del formato BACS (fittizia per il Regno Unito).
8. Fare clic su Salva.
9. Chiudere la pagina.

## <a name="test-the-format-of-generated-payment-files"></a>Testare il formato dei file di pagamento generati
1. Andare a Contabilità fornitori > Pagamenti > Giornale di registrazione pagamenti.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Nel campo Nome fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare VendPay.  
6. Fare clic su Salva.
7. Fare clic su Righe.
8. Digitare "DEMF" nel campo Società.
    * DEMF  
9. Nel campo Account, specificare i valori desiderati "DE-01001".
    * DE - 01001  
10. Digitare "Pagamento" nel campo Descrizione.
    * Pagamento  
11. Nel campo Dare immettere un numero.
    * 1000  
12. Fare clic sulla scheda Pagamento.
13. Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.
14. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il valore elettronico.  
15. Nell'elenco fare clic sul collegamento nella riga selezionata.
16. Fare clic su Salva.
17. Fare clic su Genera pagamenti.
18. Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.
19. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il valore elettronico.  
20. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare il valore elettronico.  
21. Digitare un valore nel campo Nome file.
    * Ad esempio, digitare "pagamenti".  
22. Nel campo Conto bancario fare clic sul pulsante a discesa per aprire la ricerca.
23. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare il valore GBSI OPER.  
24. Fare clic su OK.
25. Fare clic su OK.
    * Analizzare il file di pagamento creato in formato XML. Confrontarlo con il layout del documento progettato e gli attributi di transazione del pagamento definiti.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]