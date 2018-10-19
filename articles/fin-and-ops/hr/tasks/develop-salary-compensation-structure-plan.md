--- 
title: Sviluppare una struttura e un piano di stipendi/retribuzioni
description: "In questa guida attività viene illustrato il processo di creazione di un piano di retribuzione fissa e di abilitazione dei dipendenti a iscriversi al piano in base alle regole di idoneità."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 28d044cedbcc9f483a4deb7739aef0f8e3abf9ec
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="develop-salarycompensation-structure-and-plan"></a>Sviluppare una struttura e un piano di stipendi/retribuzioni

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa guida attività viene illustrato il processo di creazione di un piano di retribuzione fissa e di abilitazione dei dipendenti a iscriversi al piano in base alle regole di idoneità. La società di dati dimostrativi utilizzata per creare questa attività è USMF e l'attività è destinata ai responsabili retribuzione e benefit.


## <a name="create-fixed-compensation-plan"></a>Consente di creare un piano di retribuzione fissa
1. Fare clic su Gestione retribuzioni.
2. Care clic su Piani di retribuzione fissa.
3. Fare clic su Nuovo.
4. Digitare un valore nel campo Piano.
5. Nel campo Descrizione digitare un valore.
6. Nel campo Data di validità, immettere una data.
7. Nel campo Tipo, selezionare se il piano di retribuzione fissa è un piano di tipo Fascia, Scala o Fase.
8. La casella di controllo Suggerimento consentito funge da valore predefinito per tutte le azioni aggiunte al piano in un evento di processo.  L'autorizzazione di consigli consente di ignorare l'importo di riferimento calcolato quando si elabora la retribuzione.
9. La tolleranza non compresa nell'intervallo consente di specificare la modalità di gestione degli importi di retribuzione che non rientrano nell'intervallo specificato nella struttura retributiva per il livello specificato.  Una tolleranza non compresa nell'intervallo impostata su Nessuno consentirà l'utilizzo di qualsiasi importo di retribuzione.  Una tolleranza flessibile consentirà di avvisare l'utente se l'importo di retribuzione è inferiore all'importo del punto di riferimento minimo per il livello o superiore all'importo massimo per tale livello. L'utente può ignorare l'avviso e continuare.  Nella tolleranza rigida verrà generato un errore se la retribuzione di un dipendente viene stabilita all'esterno dei punti di riferimento minimo e massimo per il livello e la retribuzione del dipendente verrà automaticamente modificata perché rientri nell'intervallo.
10. Il campo Regola di assunzione viene utilizzato quando viene eseguito un evento processo di retribuzione per calcolare la retribuzione di un dipendente.  Una regola di assunzione Percentuale consentirà di calcolare un aumento che viene ripartito per la la durata dell'intervallo di tempo in cui il lavoratore è stato assunto nel ciclo di lavorazione.
11. Digitare un valore nel campo Valuta.
12. Nel campo Conversione retribuzione immettere o selezionare un valore.
13. Espandere la sezione Matrice utilizzo range retributivo.
    * Facoltativamente, aggiungere i record di utilizzo del range retributivo per velocizzare il raggiungimento da parte dei dipendenti del punto intermedio e per rallentare il raggiungimento da parte loro del massimo del range.  
14. In questa fase, è necessario salvare il piano di retribuzione fissa per attivare il pulsante Imposta retribuzione e continuare a definire la struttura di retribuzione per il piano.  Fare clic su Salva.
15. Fare clic su Imposta retribuzione.
    * Esistono tre modi per creare una struttura retributiva. 1: Creare una struttura completamente nuova selezionando un set di punti di riferimento e aggiungendo i livelli per creare una struttura personalizzata. 2: Copiare una struttura retributiva da un piano esistente come un punto di inizio e modificarlo per il nuovo piano. 3: Selezionare una griglia retributiva esistente. Se la griglia retributiva è già utilizzata da un altro piano, tutte le modifiche apportate alla griglia verranno riflesse anche nell'altro piano.  
16. Selezionare l'opzione Crea nuova matrice da matrice di incremento retributivo esistente.
17. Nel campo Copia da griglia immettere o selezionare un valore.
    * Facoltativamente è possibile modificare il nome della nuova griglia retributiva che verrà creata come copia della griglia selezionata.  
18. Fare clic su OK.
19. Fare clic su Modifica in massa.
    * La modifica in massa consente di gestire gli importi della matrice di incremento retributivo applicando una percentuale o un aumento dell'importo fisso a uno o più livelli e/o punti di riferimento.  
20. Nel campo Importo di rettifica immettere un numero.
21. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
22. Fare clic su Applica alla griglia.
23. Chiudere la pagina.
    * Una volta che una struttura retributiva è stata creata o selezionata, è possibile selezionare i punti di riferimento da utilizzare come punto di controllo per il piano di retribuzione fissa.  Il punto di controllo viene utilizzato per calcolare il Rapporto di comparazione di un dipendente.  
24. Nel campo Punto di controllo immettere o selezionare un valore.
25. Chiudere la pagina.

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a>Crea una regola di idoneità per il nuovo piano di retribuzione fissa.
    * Il nuovo piano di retribuzione fissa non può essere assegnato a un dipendente fino a quando non sono state definite le regole di idoneità per il piano.  
1. Fare clic su Regole di idoneità.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Idoneità.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Data di validità, immettere una data.
    * Le regole di idoneità vengono utilizzate sia per i piani di retribuzione fissa che variabile.  Nel campo Tipo, selezionare il tipo di piano relativo a tale set di regole.  
6. Nel campo Piano immettere o selezionare un valore.
    * Selezionare i criteri che un dipendente deve soddisfare per essere idoneo per il piano di retribuzione. I criteri possono includere un reparto, un sindacato, una località (paese di retribuzione), una mansione, una funzione, un tipo di mansione o un livello retributivo. Il dipendente deve soddisfare tutti i criteri specificati per essere idoneo per il piano di retribuzione. Se non viene specificato alcun criterio, tutti i dipendenti sono idonei per il piano di retribuzione. Se un dipendente non soddisfa i criteri specificati nella regola di idoneità o non è stata specificata una regola di idoneità per un piano di retribuzione, il piano di retribuzione non verrà visualizzato nella ricerca quando viene creato un record di retribuzione fissa per un dipendente.  
7. Chiudere la pagina.
8. Chiudere la pagina.


