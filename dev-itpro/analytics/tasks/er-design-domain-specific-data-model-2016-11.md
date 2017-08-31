--- 
title: Progettare un modello di dati specifico del dominio per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici che contiene un modello dati per i documenti di pagamento elettronico."
author: NickSelin
manager: AnnBe
ms.date: 12/21/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: bf727b63ed86e7cc26d4fca630d97af88abb1804
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="design-a-domain-specific-data-model-for-electronic-reporting-er"></a>Progettare un modello di dati specifico del dominio per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici che contiene un modello dati per i documenti di pagamento elettronico. Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.



In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società. Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Selezionare il provider di configurazione per la società di esempio Litware, Inc. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".  
2. Fare clic su Configurazioni report.
    * Verrà creata una configurazione che contiene un modello dati per i documenti di pagamento elettronico. Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.  

## <a name="create-a-new-data-model-configuration"></a>Crea una nuova configurazione di modello dati
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
2. Nel campo Nome digitare "Pagamenti (modello semplificato)".
    * Pagamenti (modello semplificato)  
3. Nel campo Descrizione digitare "Configurazione modello di pagamento".
    * Configurazione modello di pagamento  
    * Il provider di configurazione attiva viene inserito automaticamente in questo punto. Tale provider potrà gestire la configurazione. Altri provider possono utilizzare la configurazione, ma non potranno gestirla.  
4. Fare clic sul pulsante "Crea configurazione" per completare l'attività di creazione della configurazione

## <a name="create-a-data-model"></a>Creare un modello dati
    * Si sta creando un nuovo modello dati per la configurazione selezionata. Questa versione di configurazione avrà lo stato di bozza.  
1. Fare clic su Progettazione.

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a>Definire la struttura di una parte che partecipa a un processo di pagamento
1. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
2. Digitare 'Party' nel campo Nome.
    * Parte  
3. Scegliere Aggiungi.
4. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
5. Nel campo Nome digitare "Nome".
    * Nome  
6. Nel campo Tipo di articolo selezionare "Stringa".
7. Scegliere Aggiungi.
8. Digitare 'Party' nel campo Trova.
    * Parte  
9. Fare clic su Trova precedente.

## <a name="define-the-bank-structure-for-this-model"></a>Definire la struttura della banca per il modello
1. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
2. Nel campo Nome digitare "Agente".
    * Agente  
3. Nel campo Tipo di articolo selezionare "Record".
4. Scegliere Aggiungi.
5. Nel campo Descrizione immettere 'Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).'.
    * Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).  
6. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
7. Nel campo Nome digitare "Nome".
    * Nome  
8. Nel campo Tipo di articolo selezionare "Stringa".
9. Scegliere Aggiungi.
10. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
11. Nel campo Nome digitare "SWIFT".
    * SWIFT  
12. Scegliere Aggiungi.
13. Nel campo Descrizione immettere 'Codice di identificazione bancario'.
    * Codice di identificazione bancario  
14. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
15. Nel campo Nome digitare "RoutingNumber".
    * RoutingNumber  
16. Scegliere Aggiungi.
17. Nel campo Descrizione immettere 'Numero di registrazione'.
    * Numero di registrazione  
18. Fare clic su Trova precedente.

## <a name="define-the-bank-account-structure-for-this-model"></a>Definire la struttura del conto bancario per il modello
1. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
2. Nel campo Nome digitare "Conto".
    * Conto  
3. Nel campo Tipo di articolo selezionare "Record".
4. Scegliere Aggiungi.
5. Nel campo Descrizione, immettere 'Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.'.
    * Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.  
6. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
7. Nel campo Nome digitare "Valuta".
    * Valuta  
8. Nel campo Tipo di articolo selezionare "Stringa".
9. Scegliere Aggiungi.
10. Nel campo Descrizione immettere 'Codice valuta'.
    * Codice valuta  
11. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
12. Nel campo Nome digitare "Numero".
    * Numero  
13. Scegliere Aggiungi.
14. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
15. Nel campo nome digitare "IBAN".
    * IBAN  
16. Scegliere Aggiungi.
17. Nel campo Descrizione immettere 'International Bank Account Number (numero di conto bancario internazionale)'.
    * International Bank Account Number (numero di conto bancario internazionale)  

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a>Definire la struttura del messaggio di pagamento per il tipo di pagamento con bonifico
1. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
2. Nel campo Nuovo nodo come immettere 'Radice modello'.
3. Nel campo Nome digitare "CustomerCreditTransferInitiation".
    * CustomerCreditTransferInitiation  
4. Scegliere Aggiungi.
5. Nel campo Trova digitare 'CustomerCreditTransferInitiation'.
    * CustomerCreditTransferInitiation  
6. Fare clic su Trova precedente.
7. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
8. Nel campo Nome digitare "MessageIdentification".
    * MessageIdentification  
9. Scegliere Aggiungi.
10. Nel campo Descrizione immettere 'Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio'.
    * Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio.  
11. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
12. Nel campo Nome digitare "ProcessingDateTime".
    * ProcessingDateTime  
13. Nel campo Tipo di articolo selezionare "DateTime".
14. Scegliere Aggiungi.
15. Nel campo Descrizione immettere 'Data e ora di creazione del messaggio di pagamento.'.
    * Data e ora di creazione del messaggio di pagamento.  
16. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
    * Definire la struttura della transazione di pagamento per il modello.  
17. Nel campo Nome digitare "Pagamenti".
    * Pagamenti  
18. Nel campo Tipo di articolo selezionare "Elenco di record".
19. Scegliere Aggiungi.
20. Nel campo Descrizione immettere "Righe pagamento del messaggio corrente".
    * Righe pagamento del messaggio corrente  
21. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
22. Nel campo Nome digitare "Creditore".
    * Creditore  
23. Nel campo Tipo di articolo selezionare "Record".
24. Scegliere Aggiungi.
25. Nel campo Descrizione immettere 'Parte a cui è dovuta una somma di denaro.'.
    * Parte a cui è dovuta una somma di denaro.  
26. Fare clic su Cambia riferimento articolo.
27. Digitare 'Party' nel campo Trova.
    * Parte  
28. Fare clic su Trova successivo.
29. Fare clic su OK.
30. Nel campo Trova digitare 'Pagamenti'.
    * Pagamenti  
31. Fare clic su Trova successivo.
32. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
33. Nel campo nome digitare "Debitore".
    * Debitore  
34. Scegliere Aggiungi.
35. Nel campo Descrizione immettere 'Parte che deve una somma di denaro al creditore (finale).'.
    * Parte che deve una somma di denaro al creditore (finale).  
36. Fare clic su Cambia riferimento articolo.
37. Digitare 'Party' nel campo Trova.
    * Parte  
38. Fare clic su Trova successivo.
39. Fare clic su OK.
40. Fare clic su Trova successivo.
41. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
42. Nel campo Nome digitare "Descrizione".
    * descrizione  
43. Nel campo Tipo di articolo selezionare "Stringa".
44. Scegliere Aggiungi.
45. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
46. Nel campo Nome digitare "Valuta".
    * Valuta  
47. Scegliere Aggiungi.
48. Nel campo Descrizione immettere 'Codice valuta'.
    * Codice valuta  
49. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
50. Nel campo Nome digitare "TransactionDate".
    * TransactionDate  
51. Nel campo Tipo di articolo selezionare "Data".
52. Scegliere Aggiungi.
53. Nel campo Descrizione immettere 'Data della transazione'.
    * Data della transazione  
54. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
55. Nel campo Nome digitare "InstructedAmount".
    * InstructedAmount  
56. Nel campo Tipo di articolo selezionare "Reale".
57. Scegliere Aggiungi.
58. Nel campo Descrizione immettere 'Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri. L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione".
    * Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri. L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione.  
59. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
60. Nel campo Nome digitare "End2EndID".
    * End2EndID  
61. Nel campo Tipo di articolo selezionare "Stringa".
62. Scegliere Aggiungi.
63. Nel campo Descrizione immettere 'Identificazione univoca assegnata dalla parte che inizia la transazione. L'identificazione viene passata senza modifiche lungo l'intera catena end-to-end".
    * Identificazione univoca assegnata dalla parte che inizia la transazione. L'identificazione viene passata senza modifiche lungo l'intera catena end-to-end.  
64. Nel campo Nome digitare "PaymentModel".
    * Il nome PaymentModel è in linea con le interfacce predefinite delle forme di pagamento.  
65. Fare clic su Salva.
66. Chiudere la pagina.


