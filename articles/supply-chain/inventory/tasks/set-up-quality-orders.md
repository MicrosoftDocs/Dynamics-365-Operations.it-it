---
title: Impostare ordini di controllo qualità
description: In questa procedura viene illustrato come abilitare il processo di gestione della qualità in in cui le scorte in ingresso devono essere controllate subito dopo la registrazione degli arrivi.
author: perlynne
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, InventTestTable, DefaultDashboard, InventTestVariable, InventTestVariableOutcome, InventItemSampling, InventTestQualityGroup, InventTestItemQualityGroupAdd, SysQueryForm, InventTestItemQualityGroup, InventTestGroup, InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4577b8b189403b3d71eb634e159d51d2fa53ce12
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431403"
---
# <a name="set-up-quality-orders"></a>Impostare ordini di controllo qualità

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come abilitare il processo di gestione della qualità in in cui le scorte in ingresso devono essere controllate subito dopo la registrazione degli arrivi. La procedura in genere verrà eseguita da un responsabile della qualità. Il processo comprende la creazione di un gruppo di controllo qualità per definire gli articoli che verranno campionati e un gruppo di test per raggruppare i test da eseguire sugli articoli nel gruppo di controllo qualità. È possibile eseguire questa guida nella società di dati dimostrativi USMF.


## <a name="enable-quality-management"></a>Abilitare la gestione qualità
1. Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazione > Parametri di gestione articoli e magazzino**.
2. Fare clic sulla scheda **Gestione qualità**.
3. Impostare l'opzione **Usa Gestione qualità** su 'Sì'.
4. Fare clic su **Impostazione report**. In USMF, l'impostazione dei report per la gestione della qualità già è definita. Se così non fosse, aggiungereste le nuove righe qui per i tipi differenti di report e selezionereste il tipo di documento da usare per ogni report.  
5. Chiudere la pagina.
6. Chiudere la pagina.

## <a name="create-a-test"></a>Creare un test
1. Andare a **Gestione articoli > Impostazioni > Controllo qualità > Test**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Test**.
4. Digitare un valore nel campo **Descrizione**
5. Selezionare 'Opzione' nel campo **Tipo** In questo esempio, verrà selezionato "Opzione" che permetterà di assegnare i risultati del test in base ai valori predefiniti.  
6. Fare clic su **Salva**.
7. Chiudere la pagina.

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a>Creare variabili di test per definire la modalità in cui i risultati del test vengono registrati
1. Andare a **Gestione articoli > Impostazioni > Controllo qualità > Variabili di test**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Variabile**.
4. Digitare un valore nel campo **Descrizione**
5. Fare clic su **Salva**.
6. Fare clic su **Risultati**.
7. Fare clic su **Nuovo**.
8. Digitare un valore nel campo **Risultato**
9. Digitare un valore nel campo **Descrizione**
10. Selezionare 'Superato' nel campo **Stato risultato**.
11. Fare clic su **Salva**.
12. Fare clic su **Nuovo**.
13. Digitare un valore nel campo **Risultato**
14. Digitare un valore nel campo **Descrizione**
15. Fare clic su **Salva**.
16. Chiudere la pagina.
17. Chiudere la pagina.

## <a name="set-up-item-sampling"></a>Imposta il campionamento articoli
1. Andare a **Gestione articoli > Impostazioni > Controllo qualità > Campionamento articoli**.
2. Fare clic su **Nuovo**.
3. Nel campo **Campionamento articoli**, digitare un valore.
4. Digitare un valore nel campo **Descrizione**
5. Nel campo **Valore** immettere un numero. Questo valore è correlato alla specifica della quantità selezionata nel campo adiacente.  
6. Espandere o comprimere la sezione **Elaborazione**.
7. Selezionare o deselezionare la casella di controllo **Bloccaggio totale**. Se si seleziona questa opzione, l'intera quantità del lotto o d della riga ordine viene bloccata se un test ha esito negativo. Se tale opzione non viene selezionata, solo gli articoli nell'ordine di controllo qualità sono bloccati.  
8. Fare clic su **Salva**.
9. Chiudere la pagina.

> [!NOTE]
> La funzionalità *Gestione della qualità per i processi di magazzino* fornisce ulteriori funzionalità di campionamento degli articoli. Aggiunge un concetto di *ambito di campionamento dell'articolo* e la capacità di definire una targa completa come specifica della quantità. Se è stata abilitata questa funzione, vedere [Gestione della qualità per i processi di magazzino](../quality-management-for-warehouses-processes.md) per dettagli.

## <a name="create-a-quality-group"></a>Creare un gruppo di controllo qualità
1. Andare a **Gestione articoli > Impostazioni > Controllo qualità > Gruppi di controllo qualità**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Gruppo di controllo qualità**. Utilizzare un nome descrittivo per identificare il tipo di articoli che conterrà il gruppo (i criteri di campionamento).  
4. Digitare un valore nel campo **Descrizione**
5. Fare clic su **Salva**.
6. Fare clic su **Aggiungi articoli**.
7. Selezionare la riga **Numero articolo**. In questo esempio il filtro verrà eseguito in base al numero di articolo.  
8. Digitare un valore nel campo **Criteri**. Ad esempio, digitare T* per filtrare i numeri di articolo che iniziano con T.  
9. Fare clic su **OK**.
10. Fare clic su **OK**.
11. Fare clic su **Gruppi di controllo qualità articoli**.
12. Chiudere la pagina.
13. Chiudere la pagina.

## <a name="create-a-test-group"></a>Creazione di un gruppo di test
1. Andare a **Gestione articoli > Impostazioni > Controllo qualità > Gruppi di test**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Gruppo di test**. Assegnare al **gruppo di test** un nome che consente di ricordare il tipo di test eseguiti e il gruppo di controllo qualità a cui deve essere associato. Ad esempio, se deve essere utilizzato con un gruppo di controllo qualità che seleziona gli articoli che iniziano con "T" è possibile chiamarlo "Test articoli con la T".  
4. Digitare un valore nel campo **Descrizione**
5. Nel campo **Campionamento articoli**, selezionare la riga di campionamento articoli creata prima.
6. Nell'elenco trovare e selezionare il record desiderato.
7. Scegliere **Aggiungi**.
8. Immettere un numero nel campo **Numero progressivo**.
9. Nel campo **Test** selezionare il test creato in precedenza.
10. Trovare e selezionare il record desiderato nell'elenco.
11. Fare clic sulla scheda **Test**.
12. Nel campo **Variabile** selezionare la variabile creata in precedenza.
13. Trovare e selezionare il record desiderato nell'elenco.
14. Nel campo **Risultato predefinito** fare clic sul pulsante a discesa per aprire la ricerca.
15. Nell'elenco fare clic sul collegamento nella riga selezionata.
16. Fare clic su **Salva**.
17. Chiudere la pagina.

## <a name="define-when-quality-orders-will-be-created"></a>Definire quando gli ordini di controllo qualità verranno creati
1. Andare a **Gestione articoli > Impostazioni > Controllo qualità > Associazioni di controllo qualità**.
2. Fare clic su **Nuovo**.
3. Selezionare un'opzione nel campo **Tipo di riferimento**
4. Selezionare 'Gruppo' nel campo **Codice articolo**. In questo esempio verrà selezionato "Gruppo" e utilizzato il gruppo di controllo qualità creato prima. È inoltre possibile impostare il gruppo su "Tabella" per specificare gli articoli manualmente oppure selezionare "Tutti" per aggiungere tutti gli articoli all'ordine di controllo qualità.  
5. Nel campo **Articolo** selezionare il gruppo di controllo qualità creato prima. Le opzioni disponibili nel campo Articolo dipendono dall'opzione impostata nel campo Codice articolo.  
6. Nell'elenco trovare e selezionare il record desiderato.
7. Espandere o comprimere la sezione Elaborazione.
8. Nel campo **Tipo di evento** selezionare un'opzione. Si tratta dell'evento che attiva il test. Le opzioni disponibili in questo campo dipendono dal processo selezionato nel campo del Tipo di riferimento.  
9. Selezionare un'opzione nel campo **Esecuzione**.
10. Espandere o comprimere la sezione **Processo ordine di controllo qualità**.
11. Nel campo **Bloccaggio evento** fare clic sul pulsante a discesa per aprire la ricerca. In questo campo viene visualizzato l'elenco dei processi che è possibile bloccare se l'ordine di controllo qualità è ancora aperto. Le opzioni disponibili dipendono dall'opzione selezionata nel campo Tipo di evento.  
12. Nell'elenco fare clic sul collegamento nella riga selezionata. Tale opzione dipenderà dai valori selezionati precedenti. Selezionare se i seguenti processi devono essere bloccati mentre si hanno ordini di controllo qualità aperti collegati a una riga documento di origine.  
13. Espandere o comprimere la sezione **Specifiche**.
14. Nel campo **Gruppo di test** selezionare il gruppo di test creato in precedenza.
15. Nell'elenco trovare e selezionare il record desiderato.
16. Fare clic su **Salva**.
17. Chiudere la pagina.

> [!NOTE]
> La funzione *Gestione della qualità per i processi di magazzino* fornisce opzioni aggiuntive per l'impostazione di associazioni di qualità. Aggiunge una nuova condizione (**Tipo di magazzino applicabile**) e una nuova impostazione (**Criteri di elaborazione della qualità**). Se è stata abilitata questa funzione, vedere [Gestione della qualità per i processi di magazzino](../quality-management-for-warehouses-processes.md) per dettagli.