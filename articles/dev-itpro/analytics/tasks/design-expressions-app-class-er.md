--- 
title: Progettare espressioni per chiamare i metodi delle classi dell'applicazione (ER)
description: In questo manuale sono disponibili informazioni su come riutilizzare la logica dell'applicazione esistente nelle configurazioni dei report elettronici (ER) chiamando i metodi richiesti delle classi dell'applicazione nelle espressioni ER.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 631fa7bae808856efb8b95700fd2a85e6d5f8725
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---
# <a name="design-expressions-to-call-application-class-methods-er"></a>Progettare espressioni per chiamare i metodi delle classi dell'applicazione (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

In questo manuale sono disponibili informazioni su come riutilizzare la logica dell'applicazione esistente nelle configurazioni dei report elettronici (ER) chiamando i metodi richiesti delle classi dell'applicazione nelle espressioni ER. I valori degli argomenti per la chiamata delle classi possono essere definiti in modo dinamico in fase di esecuzione: ad esempio, in base alle informazioni nel documento di analisi per garantirne la correttezza. In questa guida verranno create le configurazioni ER necessarie per la società di esempio Litware, Inc. Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. 

Tali passaggi possono essere completati mediante un set di dati. È inoltre necessario scaricare e salvare il file seguente localmente: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.

Per completare questi passaggi, è necessario completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Verificare che il provider di configurazione per la società di esempio Litware Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".   
    * Supponiamo che si sta creando un processo per l'analisi dei rendiconti bancari in entrata per un aggiornamento dei dati dell'applicazione. I rendiconti bancari verranno ricevuti come file TXT contenenti codici IBAN. Durante il processo di importazione dei rendiconti bancari, è necessario convalidare la correttezza dei codici IBAN utilizzando la logica già disponibile in Dynamics 365 for Finance and Operations.   

## <a name="import-a-new-er-model-configuration"></a>Importare una nuova configurazione del modello ER
1. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il riquadro Provider Microsoft.  
2. Fare clic su Archivi.
3. Fare clic su Mostra filtri.
4. Aggiungere un campo di filtro "Nome del tipo". Immettere il valore "risorse" nel campo Nome, selezionare l'operatore di filtro "contiene" e fare clic su Applica.
5. Fare clic su Apri.
6. Nella struttura selezionare "Modello di pagamento".
    * Se il pulsante Importa della scheda dettaglio Versioni non è abilitato, è già stata importata la versione 1 di una configurazione ER "modello di pagamento". È possibile ignorare i passaggi rimanenti della sottoattività.   
7. Fare clic su Importa.
8. Fare clic su Sì.
9. Chiudere la pagina.
10. Chiudere la pagina.

## <a name="add-a-new-er-format-configuration"></a>Aggiungere una nuova configurazione di formato ER
1. Fare clic su Configurazioni report.
    * Aggiungere un nuovo formato ER per analizzare i rendiconti bancari in entrata nel formato TXT.  
2. Nella struttura selezionare "Modello di pagamento".
3. Fare clic su Crea configurazione per aprire il menu della finestra di dialogo.
4. Nel campo Nuovo immettere "Formato in base al modello dati PaymentModel".
5. Nel campo Nome digitare "Formato di importazione per rendiconto bancario (esempio)".
    * Formato di importazione per rendiconto bancario (esempio)  
6. Selezionare Sì nel campo Supporta importazione dati.
7. Fare clic su Crea configurazione.

## <a name="design-the-er-format-configuration---format"></a>Progettare la configurazione di formato ER - Formato
1. Fare clic su Progettazione.
    * Il formato progettato rappresenta la struttura prevista del file esterno nel formato TXT.  
2. Fare clic su Aggiungi radice per aprire il menu della finestra di dialogo.
3. Nella struttura selezionare 'Testo\Sequenza'.
4. Digitare 'Nodo principale' nel campo Nome.
    * Nodo principale  
5. Nel campo Caratteri speciali, selezionare 'Nuova riga - Windows (CR LF)'.
    * Nel campo "Caratteri speciali" è stata selezionata l'opzione 'Nuova riga - Windows (CR LF)'. In base a questa impostazione, ogni riga del file di analisi viene considerata come record separato.  
6. Fare clic su OK.
7. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
8. Nella struttura selezionare 'Testo\Sequenza'.
9. Nel campo Nome digitare 'Righe'.
    * Righe  
10. Nel campo Molteplicità selezionare "Uno molti".
    * L'opzione "Uno molti" è stata selezionata nel campo "Molteplicità". In base a questa impostazione, si prevede che almeno una riga verrà presentata nel file di analisi.  
11. Fare clic su OK.
12. Nella struttura selezionare 'Root\Rows'.
13. Fare clic su Aggiungi sequenza.
14. Nel campo Nome digitare "Campi"
    * Campi  
15. Nel campo Molteplicità selezionare "Uno e solo uno".
16. Fare clic su OK.
17. Nella struttura selezionare Root\Rows\Fields'.
18. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
19. Nella struttura selezionare "Testo\Stringa".
20. Nel campo nome digitare "IBAN".
    * IBAN  
21. Fare clic su OK.
    * È stato configurato che ogni riga del file di analisi contiene solo il numero IBAN.  
22. Fare clic su Salva.

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a>Progettare la configurazione di formato ER - Mapping al modello dati
1. Fare clic su Mapping formato a modello.
2. Fare clic su Nuovo.
3. Nel campo Definizione digitare 'BankToCustomerDebitCreditNotificationInitiation'.
    * BankToCustomerDebitCreditNotificationInitiation  
4. ResolveChanges della definizione.
5. Nel campo Nome digitare "Mapping a modello di dati".
    * Mapping a modello di dati  
6. Fare clic su Salva.
7. Fare clic su Progettazione.
8. Nella struttura selezionare 'Dynamics 365 for Operations\Class'.
9. Fare clic su Aggiungi radice.
    * Aggiungere una nuova origine dati per chiamare la logica dell'applicazione esistente per la convalida dei codici IBAN.  
10. Digitare 'check_codes' nel campo Nome.
    * verificare codici  
11. Nel campo Classe digitare 'ISO7064'.
    * ISO7064  
12. Fare clic su OK.
13. Nella struttura espandere "format".
14. Nella struttura espandere 'format\Root: Sequence(Root)'.
15. Nella struttura selezionare 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)'.
16. Fare clic su Associa.
17. Nella struttura espandere 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)'.
18. Nella struttura espandere 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)'.
19. Nella struttura selezionare 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)'.
20. Nella struttura espandere 'Payments = format.Root.Rows'.
21. Nella struttura espandere 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)'.
22. Nella struttura espandere 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification'.
23. Nella struttura selezionare 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification\IBAN'.
24. Fare clic su Associa.
25. Fare clic sulla scheda Convalide.
26. Fare clic su Nuovo.
    * Aggiungere una nuova regola di convalida che visualizza un errore per ogni riga del file di analisi contenente un codice IBAN non valido.  
27. Fare clic su Modifica condizione.
28. Nella struttura espandere "check_codes".
29. Nella struttura selezionare 'check_codes\verifyMOD1271_36'.
30. Fare clic su Aggiungi origine dati.
31. Nel campo Formula immettere 'check_codes.verifyMOD1271_36('.
    * check_codes.verifyMOD1271_36(  
32. Nella struttura espandere "format".
33. Nella struttura espandere 'format\Root: Sequence(Root)'.
34. Nella struttura espandere 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)'.
35. Nella struttura espandere 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)'.
36. Nella struttura selezionare 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)'.
37. Fare clic su Aggiungi origine dati.
38. Nel campo Formula, immettere 'check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)'.
    * check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)  
39. Fare clic su Salva.
40. Chiudere la pagina.
    * La condizione di convalida è stata configurata per restituire FALSE per qualsiasi codice IBAN non valido chiamando il metodo esistente 'verifyMOD1271_36' della classe di applicazione 'ISO7064'. Si noti che il valore del codice IBAN è definito in modo dinamico in fase di esecuzione come argomento del metodo di chiamata in base al contenuto del file TXT di analisi.   
41. Fare clic su Modifica messaggio.
42. Nel campo Formula immettere 'CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)'.
    * CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)  
43. Fare clic su Salva.
44. Chiudere la pagina.
45. Fare clic su Salva.
46. Chiudere la pagina.

## <a name="run-the-format-mapping"></a>Eseguire il mapping di formato
Per scopi di verifica, eseguire il mapping di formato utilizzando il file SampleIncomingMessage.txt scaricato. L'output generato include i dati che verranno importati dal file TXT selezionato e popolati nel modello dati personalizzati al momento dell'importazione effettiva.   
1. Fare clic su Esegui.
    * Fare clic su Sfoglia e trovare il file SampleIncomingMessage.txt in precedenza scaricato.  
2. Fare clic su OK.
    * Esaminare l'output in formato XML, che rappresenta i dati che sono stati importati dal file selezionato e trasferiti nel modello dati. Tenere presente che solo le righe 3 del file TXT importato sono state elaborate. Nella riga 4 il codice IBAN non valido è stato ignorato e un messaggio di errore viene inviato nel Registro informazioni.  


