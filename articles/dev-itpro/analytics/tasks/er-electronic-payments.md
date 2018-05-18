--- 
title: Generare documenti elettronici per i pagamenti utilizzando una configurazione di formato per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può utilizzare una nuova configurazione del formato per la creazione di report elettronici (ER) per generare documenti elettronici per l'elaborazione dei pagamenti."
author: NickSelin
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a5d958d3b55bfa76f3cfbb3c1a289e4e89c49146
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="generate-electronic-documents-for-payments-using-a-format-configuration-for-electronic-reporting-er"></a>Generare documenti elettronici per i pagamenti utilizzando una configurazione di formato per la creazione di report elettronici (ER)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può utilizzare una nuova configurazione del formato per la creazione di report elettronici (ER) per generare documenti elettronici per l'elaborazione dei pagamenti. Questi passaggi possono essere eseguiti nella società campione.

Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un documento per una configurazione con formato di pagamento".


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


