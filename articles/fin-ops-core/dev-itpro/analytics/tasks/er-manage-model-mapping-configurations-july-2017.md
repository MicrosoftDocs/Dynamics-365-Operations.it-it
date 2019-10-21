---
title: Gestire il mapping dei modelli di ER in configurazioni di ER separate
description: I passaggi seguenti illustrano come un utente assegnato con il ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può gestire mapping di modello ER in configurazioni ER separate.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcf322973ea5e4afd9c828c3cbd1ebbd9972a964
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182257"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a>Gestire il mapping dei modelli di ER in configurazioni di ER separate

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato con il ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può gestire mapping di modello ER in configurazioni ER separate. In questa guida attività verranno create le configurazioni ER necessarie per la società di esempio Litware, Inc. Per completare questa guida attività, è necessario prima completare i passaggi della guida attività "ER Creare un provider di configurazione e contrassegnarlo come attivo". 

Poiché le configurazioni ER sono condivise tra le società, è possibile completare questa guida attività utilizzando il set di dati della società scelta. La funzionalità della Guida di attività è disponibile se è stato installato uno dei seguenti hotfix: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 per Dynamics AX 7.0 o https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 per Dynamics 365 for Operations.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Verificare che il provider di configurazione per la società di esempio 'Litware, Inc.' sia disponibile e contrassegnato come attivo. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo" nella guida attività.   

## <a name="add-a-new-er-model-configuration"></a>Aggiungere una nuova configurazione del modello ER
1. Fare clic su Configurazioni report.
    * Aggiungere una nuova configurazione del modello. Il nome deve essere univoco nella struttura delle configurazioni.  
2. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
3. Nel campo Nome digitare "Modello dati di esempio".
    * Modello dati di esempio  
4. Fare clic su Crea configurazione.
5. Fare clic su Progettazione.
6. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
7. Digitare 'Nodo principale' nel campo Nome.
    * Nodo principale  
8. Scegliere Aggiungi.
9. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
10. Nel campo Nome digitare "Società".
    * Società  
11. Scegliere Aggiungi.
12. Nel campo Descrizione, immettere la descrizione della persona giuridica o della società in cui un utente ha eseguito l'accesso in fase di esecuzione. 
    * Descrizione della persona giuridica o della società a cui un utente ha eseguito l'accesso in fase di esecuzione.  
13. Fare clic su Riferimento radice.
14. Fare clic su OK.
15. Fare clic su Salva.
16. Chiudere la pagina.
17. Fare clic su Cambia stato.
18. Fare clic su Completa.
19. Fare clic su OK.

## <a name="add-a-new-er-model-mapping-configuration"></a>Aggiungere una nuova configurazione del mapping di modello ER
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
2. Nel campo Nuovo immettere "Mapping modello in base al modello dati di esempio".
3. Nel campo Nome digitare "Mapping di esempio".
    * Mapping di esempio  
4. Fare clic su Crea configurazione.
5. Espandere la sezione Prerequisiti.
    * Si noti che il gruppo di prerequisiti Implementazioni è stato aggiunto automaticamente. Questo gruppo include il componente di prerequisiti che fa riferimento alla configurazione del modello dati padre ed è contrassegnato come Implementazione. Ciò significa che la configurazione di mapping di modello Mapping di esempio viene considerata l'implementazione del modello dati Modello dati di esempio. Di conseguenza, questo componente comporterà il download da parte di ER della configurazione del mapping di modello da un archivio quando viene scaricata la configurazione del modello dati di esempio.   
6. Fare clic su Progettazione.
    * Si noti che la configurazione di mapping di modello creata contiene un nuovo mapping vuoto con lo stesso nome della configurazione creata. Tenere presente che quando una configurazione di modelli padre selezionata contiene mapping di modello, questi ultimi verranno copiati in una nuova configurazione di mapping di modello.   
7. Fare clic su Progettazione.
8. Nella struttura selezionare 'Dynamics 365 for Operations\Tabella'.
9. Fare clic su Aggiungi radice.
10. Nel campo Nome digitare "Società".
    * Società  
11. Nel campo Tabella digitare "CompanyInfo".
    * CompanyInfo  
12. Fare clic su OK.
13. Nella struttura espandere "Company".
14. Nella struttura espandere "Company\find()".
15. Nella struttura selezionare "Company\find()\Name".
16. Fare clic su Associa.
17. Fare clic su Salva.
18. Chiudere la pagina.
19. Chiudere la pagina.
20. Nel riquadro azioni, fare clic su Configurazioni.
21. Fare clic su Parametri utente.
22. Selezionare Sì nel campo Esegui impostazioni.
23. Fare clic su OK.
24. Fare clic su Modifica.
25. Selezionare Sì nel campo Esegui bozza.

## <a name="add-a-new-er-format-configuration"></a>Aggiungere una nuova configurazione di formato ER
1. Nella struttura selezionare "Sample data model".
2. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
3. Nel campo Nuovo immettere "Formato in base al modello dati Modello dati di esempio".
4. Nel campo Nome digitare "Formato di esempio".
    * Formato di esempio  
5. Fare clic su Crea configurazione.
6. Fare clic su Progettazione.
7. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
8. Nella struttura selezionare "Testo\Stringa".
9. Fare clic su OK.
10. Fare clic sulla scheda Mapping.
11. Nella struttura , espandere il "modello".
12. Nella struttura selezionare "model\Company".
13. Fare clic su Associa.
14. Fare clic su Salva.
15. Chiudere la pagina.
    * Eseguire la versione bozza del formato creato a scopo di verifica.  
16. Fare clic su Esegui.
    * Nella scheda dettaglio Versioni fare clic su Esegui.  
17. Fare clic su OK.
    * Verificare l'uscita che contiene il nome della società a cui l'utente che ha esegue questa configurazione di formato ha eseguito l'accesso. Si noti che la configurazione di mapping di modello creata viene utilizzata da questa configurazione di formato perché è presente una sola configurazione disponibile contenente i mapping di modello richiesti.   

## <a name="add-alternative-er-model-mapping-configuration"></a>Aggiungere una configurazione del mapping di modello ER alternativa
1. Nella struttura selezionare "Sample data model".
2. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
3. Nel campo Nuovo immettere "Mapping modello in base al modello dati di esempio".
4. Nel campo Nome digitare "Mapping di esempio (alternative)".
    * Mapping di esempio (alternativo)  
5. Fare clic su Crea configurazione.
6. Fare clic su Progettazione.
7. Fare clic su Progettazione.
8. Nella struttura selezionare 'Dynamics 365 for Operations\Tabella'.
9. Fare clic su Aggiungi radice.
10. Nel campo Nome digitare "Società".
    * Società  
11. Nel campo Tabella digitare "CompanyInfo".
    * CompanyInfo  
12. Fare clic su OK.
13. Fare clic su Modifica.
14. Nella struttura selezionare "Stringa\CONCATENATE".
15. Fare clic su Aggiungi funzione.
16. Nella struttura espandere "Company".
17. Nella struttura espandere "Company\find()".
18. Nella struttura selezionare "Company\find()\Name".
19. Fare clic su Aggiungi origine dati.
20. Digitare un valore nel campo Formula.
    * CONCATENATE(Company.'find()'.Name, ";",  
21. Nella struttura selezionare "Company\find()\Company(DataArea)".
22. Fare clic su Aggiungi origine dati.
23. Digitare un valore nel campo Formula.
    * CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)  
24. Fare clic su Salva.
25. Chiudere la pagina.
26. Fare clic su Salva.
27. Chiudere la pagina.
28. Chiudere la pagina.
29. Selezionare Sì nel campo Esegui bozza.

## <a name="use-an-existing-er-model-mapping-configuration"></a>Utilizzare una configurazione del mapping di modello ER esistente
1. Nella struttura selezionare "Sample data model\Sample format".
2. Fare clic su Esegui.
    * Si noti che la versione bozza della configurazione di formato ER non può essere eseguita perché è presente più di una configurazione di mapping di modello disponibile per il modello dati non definito selezionato come origine dati del formato ER in esecuzione.   
    * A questo punto verrà definita la configurazione del mapping di modello alternativo come un configurazione da cui i mapping di modello verranno utilizzati come origini dati per il formato ER in esecuzione.   
3. Nella struttura selezionare "Sample data model\Sample mapping (alternative)".
4. Selezionare Sì nel campo Impostazione predefinita per mapping di modello.
5. Nella struttura selezionare "Sample data model\Sample format".
6. Fare clic su Esegui.
7. Fare clic su OK.
    * Si noti che la configurazione del mapping di modello predefinita viene utilizzata da questa configurazione di formato per la generazione di documenti elettronici (l'output creato conterrà il codice della società).  

