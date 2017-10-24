--- 
title: Definire il mapping di modello e selezionare le origini dati per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può selezionare origini dati per un modello dati per la creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 512e24b5d0e20f00890e2a9abfe45b660a913913
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="define-model-mapping-and-select-data-sources-for-electronic-reporting-er"></a>Definire il mapping di modello e selezionare le origini dati per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può selezionare origini dati per un modello dati per la creazione di report elettronici. Le origini dati verranno associate ai singoli componenti del modello dati selezionato in fase di progettazione e popolare i dati aziendali nel modello dati in fase di esecuzione. In questo esempio vengono selezionate le origini dati per un modello dati esistente creato per la società di esempio Litware, Inc. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Creare un nuovo modello dati".


## <a name="open-the-electronic-reporting-configurations-tree"></a>Aprire la struttura Configurazioni creazione di report elettronici
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Configurazioni report.

## <a name="insert-a-new-model-mapping"></a>Inserire un nuovo mapping di modello
1. Nella struttura selezionare "Pagamenti (modello semplificato)".
2. Fare clic su Progettazione.
3. Fare clic su Mappa modello a origine dati.
4. Fare clic su Nuovo.
    * Verrà creato un nuovo record che eseguirà il mapping del modello dati alle origini dati. In questo esempio, il modello dati verrà mappato alle origini dati per il tipo di pagamento desiderato, ovvero bonifico.     È possibile progettare più di un mapping per un modello dati specifico. Ad esempio, è possibile creare un mapping per i diversi tipi di pagamento, quali addebito diretto o bonifici. In questo esempio verrà creato un mapping per i bonifici.  
5. Nel campo Nome digitare "Mapping bonifico".
    * Mapping bonifico  
6. Nel campo Descrizione immettere "Mapping modello di pagamento per bonifico".
    * Mapping modello di pagamento per bonifico  
7. Nel campo Definizione digitare 'CustomerCreditTransferInitiation'.
    * CustomerCreditTransferInitiation  
8. ResolveChanges della definizione.
9. Fare clic su Salva.

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>Definire le origini dati richieste per il mapping di modello corrente
1. Fare clic su Progettazione.
2. Nella struttura selezionare "Dynamics 365 for Operations\Table records".
3. Fare clic su Aggiungi radice.
    * Immettere questa origine dati per accedere alle transazioni di pagamento.  
4. Nel campo Nome digitare "Transazioni".
    * Transazioni  
5. Nel campo Etichetta immettere "Transazioni".
    * Transazioni  
6. Nel campo Guida immettere "Righe giornale di registrazione contabile".
    * Righe giornale di registrazione contabile  
7. Selezionare Sì nel campo Chiedi query.
    * Selezionare Sì.  
8. Nel campo Tabella digitare "LedgerJournalTrans".
    * LedgerJournalTrans  
9. Fare clic su OK.
    * Selezionare la tabella LedgerJournalTrans come origine dati per il modello dati corrente.  
10. Nella struttura selezionare "Funzioni\Campo calcolato".
11. Scegliere Aggiungi.
    * Fare clic su Aggiungi per aggiungere un nuovo campo calcolato.  
12. Nel campo Nome digitare "$EndToEndID".
    * $EndToEndID  
13. Fare clic su Modifica formula.
14. Nella struttura selezionare "Stringa\CONCATENATE".
15. Fare clic su Aggiungi funzione.
16. Nella struttura espandere "Transazioni".
17. Nella struttura espandere "Transazioni\Giustificativo".
18. Fare clic su Aggiungi origine dati.
19. Nel campo Formula immettere 'CONCATENATE(Transactions.Voucher, "-", '.
    * Digitare [ , “-“, ] alla fine della formula.  
20. Nella struttura selezionare "Stringa\TEXT".
21. Fare clic su Aggiungi funzione.
22. Nella struttura selezionare "Transazioni\ID record(RecId)".
23. Fare clic su Aggiungi origine dati.
24. Nel campo Formula immettere 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.
    * Digitare [))] alla fine della formula.  
25. Fare clic su Salva.
    * Assicurarsi che non sia stato rilevato alcun errore per la formula creata. Vedere la scheda ERRORI sotto il controllo dell'editor della formula.  
26. Chiudere la pagina.
27. Fare clic su OK.
    * Aggiungere il campo calcolato all'origine dati.  
28. Scegliere Aggiungi.
    * Fare clic su Aggiungi per aggiungere un nuovo campo calcolato.  
29. Nel campo Nome digitare "$Amount".
    * $Amount  
30. Fare clic su Modifica formula.
31. Nella struttura espandere "Transazioni".
32. Nella struttura selezionare "Transazioni\Dare(AmountCurDebit)".
33. Fare clic su Aggiungi origine dati.
34. Nel campo Formula immettere 'Transactions.AmountCurDebit - '.
    * Digitare [ - ] alla fine della formula.  
35. Nella struttura selezionare "Transazioni\Avere(AmountCurCredit)".
36. Fare clic su Aggiungi origine dati.
37. Fare clic su Salva.
38. Chiudere la pagina.
39. Fare clic su OK.
    * Il campo calcolato $Amount verrà aggiunto all'origine dati selezionata per il modello dati corrente.  
40. Nella struttura selezionare "Transazioni\$Amount".
41. Nella struttura espandere "Transazioni".
42. Nella struttura espandere o comprimere 'Transazioni\$Amount'.
43. Nella struttura espandere o comprimere 'Transazioni'.
44. Nella struttura selezionare "Dynamics 365 for Operations\Table records".
45. Fare clic su Aggiungi radice.
    * Immettere l'origine dati per accedere ai dettagli del conto bancario della società.  
46. Nel campo Nome digitare "BankAccount".
    * BankAccount  
47. Nel campo Etichetta immettere "Conto bancario".
    * Conto bancario  
48. Nel campo Guida immettere "Conto bancario".
    * Conto bancario  
49. Selezionare Sì nel campo Chiedi query.
    * Selezionare Sì.  
50. Nel campo Tabella digitare "BankAccountTable".
    * BankAccountTable  
51. Fare clic su OK.
    * Selezionare la tabella BankAccountTable come origine dati per il modello dati corrente.  
52. Fare clic su Aggiungi radice.
    * Immettere l'origine dati per accedere ai requisiti della società.  
53. Nel campo Nome digitare "Società".
    * Società  
54. Nel campo Etichetta digitare un valore.
    * Informazioni società  
55. Nel campo Guida immettere "Informazioni società".
    * Informazioni società  
56. Selezionare Sì nel campo Chiedi query.
    * Selezionare Sì.  
57. Nel campo Tabella digitare "CompanyInfo".
    * CompanyInfo  
58. Fare clic su OK.
    * Selezionare la tabella CompanyInfo come origine dati per il modello dati corrente.  
59. Nella struttura selezionare "Funzioni\Campo calcolato".
60. Fare clic su Aggiungi radice.
    * Inserire un campo calcolato come nuova origine dati.  
61. Nel campo Nome digitare "ProcessingDateTime".
    * ProcessingDateTime  
62. Nel campo Etichetta immettere "Data e ora di elaborazione".
    * Data e ora di elaborazione  
63. Fare clic su Modifica formula.
64. Nella struttura selezionare 'Data/ora\SESSIONNOW'.
65. Fare clic su Aggiungi funzione.
66. Fare clic su Salva.
67. Chiudere la pagina.
68. Fare clic su OK.
    * Aggiungere il campo calcolato ProcessingDateTime come origine dati per il modello dati corrente.  
69. Fare clic su Salva.
70. Chiudere la pagina.
71. Chiudere la pagina.
72. Chiudere la pagina.


