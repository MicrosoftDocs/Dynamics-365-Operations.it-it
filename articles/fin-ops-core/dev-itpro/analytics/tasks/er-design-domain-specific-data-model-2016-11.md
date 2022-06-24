---
title: RE Progettare il modello dati specifico di dominio
description: Questo articolo descrive come creare una nuova configurazione di reporting elettronico (ER) che contiene un modello di dati per i documenti di pagamento elettronico.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c923ed6ec817d1f4ae6cd956c06b2156a6a61311
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908444"
---
# <a name="er-design-domain-specific-data-model"></a>RE Progettare il modello dati specifico di dominio

[!include [banner](../../includes/banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una nuova configurazione per la creazione di report elettronici che contiene un modello dati per i documenti di pagamento elettronico. Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.

In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni per la creazione di report elettronici sono condivise tra tutte le società. Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.

    Selezionare il provider di configurazione per la società di esempio "Litware, Inc." Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".  
    
2. Fare clic su Configurazioni report.

    Verrà creata una configurazione che contiene un modello dati per i documenti di pagamento elettronico. Questo modello dati verrà utilizzato successivamente come origine dati quando si crea il formato dei documenti di pagamento.  

## <a name="create-a-new-data-model-configuration"></a>Crea una nuova configurazione di modello dati
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
2. Nel campo Nome digitare "Pagamenti (modello semplificato)".
3. Nel campo Descrizione digitare "Configurazione modello di pagamento".

    Il provider di configurazione attiva viene inserito automaticamente in questo punto. Tale provider potrà gestire la configurazione. Altri provider possono utilizzare la configurazione, ma non potranno gestirla.  

4. Fare clic sul pulsante "Crea configurazione" per completare l'attività di creazione della configurazione

## <a name="create-a-data-model"></a>Creare un modello dati
Si sta creando un nuovo modello dati per la configurazione selezionata. Questa versione di configurazione avrà lo stato di bozza.  
1. Fare clic su Progettazione.

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a>Definire la struttura di una parte che partecipa a un processo di pagamento
1. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
2. Digitare 'Party' nel campo Nome.
3. Scegliere Aggiungi.
4. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
5. Nel campo Nome digitare "Nome".
6. Nel campo Tipo di articolo selezionare "Stringa".
7. Scegliere Aggiungi.
8. Digitare 'Party' nel campo Trova.
9. Fare clic su Trova precedente.

## <a name="define-the-bank-structure-for-this-model"></a>Definire la struttura della banca per il modello
1. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
2. Nel campo Nome digitare "Agente".
3. Nel campo Tipo di articolo selezionare "Record".
4. Scegliere Aggiungi.
5. Nel campo Descrizione immettere 'Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).'.

    Istituto finanziario, ad esempio una banca, responsabile di un conto per la parte (debitore/creditore).  

6. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
7. Nel campo Nome digitare "Nome". 
8. Nel campo Tipo di articolo selezionare "Stringa".
9. Scegliere Aggiungi.
10. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
11. Nel campo Nome digitare "SWIFT".
12. Scegliere Aggiungi.
13. Nel campo Descrizione immettere 'Codice di identificazione bancario'. 
14. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
15. Nel campo Nome digitare "RoutingNumber".
16. Scegliere Aggiungi.
17. Nel campo Descrizione immettere 'Numero di registrazione'.
18. Fare clic su Trova precedente.

## <a name="define-the-bank-account-structure-for-this-model"></a>Definire la struttura del conto bancario per il modello
1. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
2. Nel campo Nome digitare "Conto". 
3. Nel campo Tipo di articolo selezionare "Record".
4. Scegliere Aggiungi.
5. Nel campo Descrizione, immettere 'Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.'.

    Identificazione di un conto di una parte di un istituto finanziario, ad esempio una banca.  

6. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
7. Nel campo Nome digitare "Valuta". 
8. Nel campo Tipo di articolo selezionare "Stringa".
9. Scegliere Aggiungi.
10. Nel campo Descrizione immettere 'Codice valuta'.
11. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
12. Nel campo Nome digitare "Numero". 
13. Scegliere Aggiungi.
14. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
15. Nel campo nome digitare "IBAN". 
16. Scegliere Aggiungi.
17. Nel campo Descrizione immettere 'International Bank Account Number (numero di conto bancario internazionale)'.

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a>Definire la struttura del messaggio di pagamento per il tipo di pagamento con bonifico
1. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
2. Nel campo Nuovo nodo come immettere 'Radice modello'.
3. Nel campo Nome digitare "CustomerCreditTransferInitiation".
4. Scegliere Aggiungi.
5. Nel campo Trova digitare 'CustomerCreditTransferInitiation'. 
6. Fare clic su Trova precedente.
7. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
8. Nel campo Nome digitare "MessageIdentification". 
9. Scegliere Aggiungi.
10. Nel campo Descrizione immettere 'Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio'.

    Riferimento punto a punto assegnato dalla parte che impartisce le istruzioni e inviato alla parte successiva per identificare un messaggio.  

11. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
12. Nel campo Nome digitare "ProcessingDateTime".
13. Nel campo Tipo di articolo selezionare "DateTime".
14. Scegliere Aggiungi.
15. Nel campo Descrizione immettere 'Data e ora di creazione del messaggio di pagamento.'. 
16. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.

    Definire la struttura della transazione di pagamento per il modello.  

17. Nel campo Nome digitare "Pagamenti".
18. Nel campo Tipo di articolo selezionare "Elenco di record".
19. Scegliere Aggiungi.
20. Nel campo Descrizione immettere "Righe pagamento del messaggio corrente".
21. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
22. Nel campo Nome digitare "Creditore". 
23. Nel campo Tipo di articolo selezionare "Record".
24. Scegliere Aggiungi.
25. Nel campo Descrizione immettere 'Parte a cui è dovuta una somma di denaro.'. 
26. Fare clic su Cambia riferimento articolo.
27. Digitare 'Party' nel campo Trova.
28. Fare clic su Trova successivo.
29. Fare clic su OK.
30. Nel campo Trova digitare 'Pagamenti'.
31. Fare clic su Trova successivo.
32. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
33. Nel campo nome digitare "Debitore". 
34. Scegliere Aggiungi.
35. Nel campo Descrizione immettere 'Parte che deve una somma di denaro al creditore (finale).'.
36. Fare clic su Cambia riferimento articolo.
37. Digitare 'Party' nel campo Trova.
38. Fare clic su Trova successivo.
39. Fare clic su OK.
40. Fare clic su Trova successivo.
41. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
42. Nel campo Nome digitare "Descrizione".
43. Nel campo Tipo di articolo selezionare "Stringa".
44. Scegliere Aggiungi.
45. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
46. Nel campo Nome digitare "Valuta".
47. Scegliere Aggiungi.
48. Nel campo Descrizione immettere 'Codice valuta'.
49. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
50. Nel campo Nome digitare "TransactionDate". 
51. Nel campo Tipo di articolo selezionare "Data".
52. Scegliere Aggiungi.
53. Nel campo Descrizione immettere 'Data della transazione'. 
54. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
55. Nel campo Nome digitare "InstructedAmount".  
56. Nel campo Tipo di articolo selezionare "Reale".
57. Scegliere Aggiungi.
58. Nel campo Descrizione immettere 'Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri. L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione".

    Somma di denaro da trasferire tra il debitore e il creditore al lordo delle detrazione di oneri. L'importo deve essere espresso nella valuta indicata dalla parte che inizia la transazione.  

59. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
60. Nel campo Nome digitare "End2EndID". 
61. Nel campo Tipo di articolo selezionare "Stringa".
62. Scegliere Aggiungi.
63. Nel campo Descrizione immettere 'Identificazione univoca assegnata dalla parte che inizia la transazione. L'identificazione viene passata senza modifiche lungo l'intera catena end-to-end". 
64. Nel campo Nome digitare "PaymentModel".

    Il nome PaymentModel è in linea con le interfacce predefinite delle forme di pagamento.  

65. Fare clic su Salva.
66. Chiudere la pagina.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
