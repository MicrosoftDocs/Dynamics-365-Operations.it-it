--- 
title: Mappare un modello dati alle origini dati selezionate per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può mappare un modello dati per la creazione di report elettronici a origini dati di Dynamics 365 for Finance and Operations, Enterprise edition selezionate."
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
ms.openlocfilehash: 96974d7c1597db4ac31168be40cecbc7e12d6edd
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="map-a-data-model-to-selected-data-sources-for-electronic-reporting-er"></a>Mappare un modello dati alle origini dati selezionate per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo amministratore di sistema o sviluppatore per la creazione di report elettronici può mappare un modello dati per la creazione di report elettronici a origini dati di Dynamics 365 for Finance and Operations, Enterprise edition selezionate. Il mapping di modello verrà utilizzato in seguito come origine dati in un formato di configurazione da utilizzare per gestire i documenti di pagamento elettronico. In questo esempio si esegue il mapping di modello dati per la società di esempio, Litware, Inc. alle origini dati. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Selezionare le origini dati per il mapping di modello".


## <a name="open-er-configurations-tree"></a>Consente di aprire la struttura di configurazioni per la creazione di report elettronici
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic Configurazioni:

## <a name="select-created-model-mapping"></a>Selezionare il mapping del modello creato
1. Nella struttura selezionare "Pagamenti (modello semplificato)".
    * Verificare che la configurazione del modello "Pagamenti (modello semplificato)" sia stata creata in anticipo. In caso contrario, arrestare ora e tornare al termine della guida attività 'Creare una nuova configurazione con il modello dati del dominio selezionato'.  
2. Fare clic su Progettazione modello.
3. Fare clic su Mappa modello a origine dati.
4. Selezionare il record "Mapping bonifico".
    * Mapping bonifico  

## <a name="bind-created-data-sources-to-data-model-elements"></a>Associare le origini dati create a elementi del modello dati
1. Fare clic su Progettazione.
2. Nella struttura selezionare "Data e ora di elaborazione(ProcessingDateTime)".
3. Nella struttura selezionare "Data di elaborazione(ProcessingDateTime)".
4. Fare clic su Associa.
5. Nella struttura selezionare "Identificazione messaggio di pagamento(MessageIdentification)".
6. Nella struttura espandere "Transazioni".
7. Nella struttura selezionare "Transazioni\Numero batch giornale di registrazione(JournalNum)".
8. Fare clic su Associa.
9. Nella struttura selezionare "Pagamenti".
10. Nella struttura selezionare "Transazioni".
11. Fare clic su Associa.
12. Nella struttura espandere "Pagamenti= Transazioni".
13. Nella struttura espandere "Pagamenti= Transazioni\Creditore".
14. Nella struttura espandere "Pagamenti= Transazioni\Creditore\Conto".
15. Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Conto\Codice valuta(Currency)".
16. Nella struttura espandere "Transazioni\vendBankAccountInTransactionCompany()".
17. Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Valuta(CurrencyCode)".
18. Fare clic su Associa.
19. Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Conto\Codice IBAN(IBAN)".
20. Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)".
21. Fare clic su Associa.
22. Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Conto\Numero".
23. Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Numero conto bancario(AccountNum)".
24. Fare clic su Associa.
25. Nella struttura espandere "Pagamenti= Transazioni\Creditore\Agente".
26. Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Agente\Nome".
27. Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Nome".
28. Fare clic su Associa.
29. Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Agente\Numero di registrazione(RoutingNumber)".
30. Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Numero di registrazione(RegistrationNum)".
31. Fare clic su Associa.
32. Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Agente\Codice SWIFT(SWIFT)".
33. Nella struttura selezionare "Transazioni\vendBankAccountInTransactionCompany()\Codice SWIFT(SWIFTNo)".
34. Fare clic su Associa.
35. Nella struttura selezionare "Pagamenti= Transazioni\Creditore\Nome".
36. Nella struttura espandere "Transazioni\findVendTable()".
37. Nella struttura selezionare "Transazioni\findVendTable()\name()".
38. Fare clic su Associa.
39. Nella struttura selezionare "Pagamenti= Transazioni\Codice valuta(Currency)".
40. Nella struttura, espandere "Transazioni\>Relazioni".
41. Nella struttura, espandere "Transazioni\>Relazioni\Tabella valute(Currency)".
42. Nella struttura, selezionare "Transazioni\>Relazioni\Tabella valute(Currency)\Codice valuta(CurrencyCodeISO)".
43. Fare clic su Associa.
44. Nella struttura espandere "Pagamenti= Transazioni\Debitore".
45. Nella struttura espandere "Pagamenti= Transazioni\Debitore\Conto".
46. Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Conto\Codice valuta(Currency)".
47. Nella struttura selezionare "Conto bancario(BankAccount)".
48. Nella struttura espandere "Conto bancario(BankAccount)".
49. Nella struttura selezionare "Conto bancario(BankAccount)\Valuta(CurrencyCode)".
50. Fare clic su Associa.
51. Nella struttura selezionare "Conto bancario(BankAccount)\IBAN".
52. Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Conto\Codice IBAN(IBAN)".
53. Fare clic su Associa.
54. Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Conto\Numero".
55. Nella struttura selezionare "Conto bancario(BankAccount)\Numero conto bancario(AccountNum)".
56. Fare clic su Associa.
57. Nella struttura espandere "Pagamenti= Transazioni\Debitore\Agente".
58. Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Agente\Nome".
59. Nella struttura selezionare "Conto bancario(BankAccount)\Nome".
60. Fare clic su Associa.
61. Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Agente\Numero di registrazione(RoutingNumber)".
62. Nella struttura selezionare "Conto bancario(BankAccount)\Numero di registrazione(RegistrationNum)".
63. Fare clic su Associa.
64. Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Agente\Codice SWIFT(SWIFT)".
65. Nella struttura selezionare "Conto bancario(BankAccount)\Codice SWIFT(SWIFTNo)".
66. Fare clic su Associa.
67. Nella struttura selezionare "Pagamenti= Transazioni\Debitore\Nome".
68. Nella struttura selezionare "Informazioni società(Company)".
69. Nella struttura espandere "Informazioni società(Company)".
70. Nella struttura selezionare "Informazioni società(Company)\Nome".
71. Fare clic su Associa.
72. Nella struttura selezionare "Pagamenti= Transazioni\Descrizione".
73. Nella struttura selezionare "Transazioni\Descrizione(Txt)".
74. Fare clic su Associa.
75. Nella struttura selezionare "Pagamenti= Transazioni\Codice di identificazione end-to-end(End2EndID)".
76. Nella struttura, selezionare "Transazioni\$EndToEndID".
77. Fare clic su Associa.
78. Nella struttura selezionare "Pagamenti= Transazioni\Importo istruito(InstructedAmount)".
79. Nella struttura selezionare "Transazioni\$Amount".
80. Fare clic su Associa.
81. Nella struttura selezionare "Pagamenti= Transazioni\Data della transazione(TransactionDate)".
82. Nella struttura selezionare "Transazioni\Data(TransDate)".
83. Fare clic su Associa.

## <a name="validate-created-mapping"></a>Convalida il mapping creato
1. Fare clic su Convalida.
    * Convalidare il nuovo mapping per assicurarsi che tutte le associazioni siano corrette.  
2. Fare clic sulla freccia per espandere o comprimere la sezione Elenco errori.
3. Fare clic su Salva.
4. Chiudere la pagina.
5. Chiudere la pagina.
6. Chiudere la pagina.

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>Modificare lo stato della versione corrente della configurazione del modello
1. Fare clic su Cambia stato.
    * Modificare lo stato della configurazione designata del modello da Bozza a Completato per renderla disponibile per la progettazione del formato di pagamento.  
2. Fare clic su Completa.
    * Seleziona Completa.  
3. Nel campo Descrizione digitare un valore.
    * Ad esempio, 'versione 1'.  
4. Fare clic su OK.
5. Selezionare la versione completata della configurazione corrente.
    * Si noti che la configurazione creata viene salvata come versione completata 1.  


