---
title: Sviluppare una struttura di retribuzione
description: In questo argomento viene illustrato come creare un piano di retribuzione fissa e iscrivere i dipendenti al piano in base alle regole di idoneità.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f069d4e982a9c02070c2010b894b2ec7a9c7f6ab
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693089"
---
# <a name="develop-a-compensation-structure"></a>Sviluppare una struttura di retribuzione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

In questo argomento viene descritto come creare un piano di retribuzione fissa e iscrivere i dipendenti al piano in base alle regole di idoneità. Questo argomento utilizza i dati dimostrativi USMF e si applica ai responsabili retribuzione e benefit.

## <a name="create-a-fixed-compensation-plan"></a>Creare un piano di retribuzione fissa

1. Selezionare **Gestione retribuzioni**.

2. Selezionare **Piani di retribuzione fissa**.

3. Selezionare **Nuovo**.

4. Nel campo **Piano** immettere un valore.

5. Nel campo **Descrizione** immettere un valore.

6. Nel campo **Data di validità**, immettere una data.

7. Nel campo **Tipo**, selezionare se il piano di retribuzione fissa è un piano di tipo **Fascia**, **Scala** o **Fase**.

8. La casella di controllo **Suggerimento consentito** è il valore predefinito per tutte le azioni aggiunte al piano in un evento di processo. L'autorizzazione di consigli consente di ignorare l'importo di riferimento calcolato quando si elabora la retribuzione.

9. Il campo **Tolleranza non compresa nell'intervallo** consente di specificare la modalità di gestione degli importi di retribuzione che non rientrano nell'intervallo specificato nella struttura retributiva per il livello specificato. L'impostazione del campo **Tolleranza non compresa nell'intervallo** su **Nessuno** consente di utilizzare qualsiasi importo di retribuzione. Una **tolleranza flessibile** consentirà di avvisare l'utente se l'importo di retribuzione è inferiore all'importo del punto di riferimento minimo per il livello o superiore all'importo massimo per tale livello. Gli utenti possono ignorare l'avviso e continuare. Nella **tolleranza rigida** viene generato un errore se la retribuzione di un dipendente viene stabilita all'esterno dei punti di riferimento minimo e massimo per il livello e la retribuzione del dipendente verrà automaticamente modificata perché rientri nell'intervallo.

10. Il campo **Regola di assunzione** calcola la retribuzione di un dipendente durante un evento di processo. Una **regola di assunzione** **Percentuale** consente di calcolare un aumento che viene ripartito per la la durata dell'intervallo di tempo in cui il lavoratore è stato assunto nel ciclo di lavorazione.

11. Digitare un valore nel campo **Valuta**.

12. Nel campo **Conversione retribuzione** immettere o selezionare un valore.

13. Espandere la sezione **Matrice utilizzo range retributivo**. Facoltativamente, aggiungere i record di utilizzo del range retributivo per velocizzare il raggiungimento da parte dei dipendenti del punto intermedio e per rallentare il raggiungimento da parte loro del massimo del range.

14. Selezionare **Salva**. Questo abilita il pulsante **Imposta retribuzione** per continuare a definire la struttura di retribuzione per il piano.

15. Selezionare **Imposta retribuzione**. È possibile creare una struttura di retribuzione utilizzando uno dei tre metodi seguenti:

    - Creare una struttura completamente nuova selezionando un set di punti di riferimento e aggiungendo i livelli per creare una struttura personalizzata.
    - Copiare una struttura retributiva da un piano esistente come un punto di inizio e modificarlo per il nuovo piano.
    - Selezionare una griglia retributiva esistente. Se la griglia retributiva è già utilizzata per un altro piano, tutte le modifiche apportate alla griglia vengono riflesse anche nell'altro piano.

16. Selezionare **Crea nuova matrice da matrice di incremento retributivo esistente**.

17. Nel campo **Copia da griglia** immettere o selezionare un valore. Facoltativamente è possibile modificare il nome della nuova griglia retributiva che viene creata come copia della griglia selezionata.

18. Selezionare **OK**.

19. Selezionare **Modifica in massa**. La **modifica in massa** consente di gestire gli importi della matrice di incremento retributivo applicando una percentuale o un aumento dell'importo fisso a uno o più livelli o punti di riferimento.

20. Nel campo **Importo di rettifica** immettere un numero.

21. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.

22. Fare clic su **Applica alla griglia**.

23. Chiudere la pagina. Una volta creata la struttura retributiva, è possibile selezionare i punti di riferimento da utilizzare come punto di controllo per il piano di retribuzione fissa. Il punto di controllo viene utilizzato per calcolare il Rapporto di comparazione di un dipendente.

24. Nel campo **Punto di controllo** immettere o selezionare un valore.

25. Chiudere la pagina.

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a>Creare una regola di idoneità per il piano di retribuzione fissa

Un piano di retribuzione fissa non può essere assegnato a un dipendente fino a quando non sono state definite le regole di idoneità per il piano.  

1. Selezionare **Regole di idoneità**.

2. Selezionare **Nuovo**.

3. Nel campo **Idoneità** immettere un valore.

4. Nel campo **Descrizione** immettere un valore.

5. Nel campo **Data di validità**, immettere una data. Le regole di idoneità vengono utilizzate per i piani di retribuzione fissa e variabile. Nel campo **Tipo** selezionare il tipo di piano.

6. Nel campo **Piano** immettere o selezionare un valore. Selezionare i criteri che un dipendente deve soddisfare per essere idoneo per il piano di retribuzione. I criteri possono includere:

    - **Reparto**
    - **Sindacato**
    - **Ubicazione** (**Paese di retribuzione**)
    - **Mansione**
    - **Funzione**
    - **Tipo di posizione**
    - **Livello retributivo**
    
    Il dipendente deve soddisfare tutti i criteri specificati per essere idoneo per il piano di retribuzione. Se non viene specificato alcun criterio, tutti i dipendenti sono idonei per il piano di retribuzione. Se un dipendente non soddisfa i criteri specificati nella regola di idoneità o non è stata specificata una regola di idoneità per un piano di retribuzione, il piano di retribuzione non viene visualizzato nella ricerca quando viene creato un record di retribuzione fissa per un dipendente.

7. Chiudere la pagina.

8. Chiudere la pagina.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
