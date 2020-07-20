---
title: Conto lavoro
description: In questo argomento vengono fornite le informazioni dettagliate per creare un conto lavoro nella produzione in Dynamics 365 Supply Chain Management.
author: christophernread
manager: tfehr
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1cc1040393d843f39ca8c741a7c51435c7169c00
ms.sourcegitcommit: edb46dce498df42b09e8f5ad6de00f86c8022dfa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2020
ms.locfileid: "3346424"
---
# <a name="subcontracting"></a>Conto lavoro

[!include [banner](../includes/banner.md)]

In questo argomento vengono fornite le informazioni dettagliate per creare un conto lavoro nella produzione in Microsoft Dynamics 365 Supply Chain Management. La prima parte di questo argomento descrive l'impostazione dei dati. La seconda parte descrive la procedura.

## <a name="target-audience"></a>Destinatari

Questo argomento descrive come impostare il conto lavoro nella produzione. Verranno usati i dati esistenti nella persona giuridica HQUS per eseguire l'impostazione di base di un flusso di attività conto lavoro. I dati dimostrativi nella persona giuridica HQUS includono i parametri di impostazione che sono stati prestabiliti per supportare i passaggi della procedura. Anche se la procedura risolve i punti critici e le sfide per vari ruoli, può essere completata dall'amministratore di sistema.

## <a name="demo-scenario"></a>Scenario dimostrativo

Nella persona giuridica HQUS vengono prodotti alto parlanti di fascia alta. Durante il processo di produzione gli altoparlanti subiscono tre operazioni.

- **Preassemblaggio** - Viene assemblato il cabinet dell'altoparlante. Il materiale per il cabinet viene prelevato dal magazzino prima che abbia inizio l'operazione.
- **Rivestimento** - Dopo l'assemblaggio, il cabinet viene rivestito. Questa operazione viene completata da un fornitore (terzista). Il cabinet dell'altoparlante preassemblato viene spedito al terzista che si occupa del rivestimento insieme a due materiali.
- **Finitura** - Dopo essere stato assemblato e rivestito dal terzista, il cabinet torna alla persona giuridica HQUS per completare l'assemblaggio finale dell'altoparlante.

La figura seguente mostra le tre operazioni e i materiali impiegati.

![Operazioni di preassemblaggio, rivestimento e finitura e i materiali impiegati](./media/subcontract01_operations-materials.png)

## <a name="setup"></a>Imposta

Prima di iniziare la procedura, è necessario impostare i dati.

### <a name="set-up-the-finished-product"></a>Impostare il prodotto finito

Questa procedura illustra l'impostazione del prodotto rilasciato D8100, "Cabinet rivestito".

1. Selezionare **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati** per aprire la pagina **Dettagli prodotto rilasciato**.
2. Nel campo del filtro rapido, immettere **D8100** per trovare il prodotto rilasciato esistente.

    ![Filtro per il prodotto rilasciato D8100 nella pagina dei dettagli del prodotto rilasciato](./media/subcontract02_filtering-released-products.png)

3. Nel riquadro azioni, nella scheda **Progetta** selezionare **Ciclo** per aprire la pagina **Ciclo di lavorazione**.

    La pagina **Ciclo di lavorazione** mostra le otto versioni del ciclo per il prodotto rilasciato D8100. Le otto versioni del ciclo di lavorazione sono suddivise in quattro cicli di lavorazione nel sito 1 e nel sito 5. Il ciclo di lavorazione 000400 viene utilizzato per la determinazione dei costi, il ciclo 00041 viene utilizzato quando l'operazione di rivestimento avviene internamento e il ciclo 00042 viene utilizzando quando tale operazione avviene esternamente.

    ![Otto versioni del ciclo di lavorazione nella pagina Ciclo di lavorazione](./media/subcontract03_route-page.png)

4. Nel riquadro superiore, nella griglia **Versioni** selezionare la versione **00042** per il sito **5**.
5. Nel riquadro inferiore, nella scheda **Panoramica** selezionare l'operazione **20** (**Cbnt CtSc**) nella griglia.

    ![Operazione 20 per la versione 00042 del sito 5 selezionata](./media/subcontract04_route-version-operation.png)

6. Selezionare la scheda **Generale**.

    Notare che il campo **Tipo ciclo di lavorazione** è impostato su **Fornitore**. Questo valore indica che l'operazione 20 (Cbnt CtSc) costituisce un'operazione in conto lavoro.

    ![Campo Tipo di lavorazione impostato su Fornitore nella scheda Generale](./media/subcontract05_general-tab.png)

7. Selezionare la scheda **Requisiti risorsa**.

    Le funzionalità verranno utilizzate per trovare una risorsa valida durante la programmazione della produzione. Per l'operazione 20 (Cbnt CtSc), notare che è necessaria una risorsa che abbia due funzionalità, **Rivestimento** e **Cabinet rivestiti**.

    ![Funzionalità Rivestimento e Cabinet rivestiti nella scheda dei requisiti di risorsa](./media/subcontract06_resource-requirements-tab.png)

8. Selezionare **Risorse applicabili** per aprire la finestra di dialogo **Risorse applicabili**.

    Tre risorse sono disponibili che soddisfano i requisiti di risorsa per l'operazione. Notare che le risorse 8851 e 8852 sono di tipo **Fornitore**.

    ![Tre risorse appropriate nella finestra di dialogo Risorse applicabili](./media/subcontract07_applicable-resources-dialog.png)

9. Selezionare **OK** per chiudere la finestra di dialogo **Risorse applicabili** e tornare alla pagina **Ciclo di lavorazione**.
10. Chiudere la pagina **Ciclo di lavorazione** per tornare alla pagina **Dettagli prodotto rilasciato**.

    ![Pagina Dettagli prodotto rilasciato](./media/subcontract08_released-product-details-page.png)

11. Nel riquadro azioni, nella scheda **Progetta** selezionare **Versioni DBA** per aprire la pagina **Versioni DBA**.

    La pagina **Versioni DBA** mostra le quattro versioni di distinta base (DBA) per il prodotto rilasciato D8100. La DBA 000040 viene utilizzata per la determinazione dei costi e la pianificazione, la DBA 000041 viene utilizzata se l'operazione Rivestimento viene effettuata internamente e le DBA 000042 e 000043 vengono utilizzate se l'operazione Rivestimento è in conto lavoro.

    Si noti che l'articolo S8050 è un prodotto di tipo **Servizio**. Questo articolo rappresenta il lavoro in conto lavoro.

    ![Quattro versioni di DBA nella pagina Versioni DBA](./media/subcontract09_bom-versions-page.png)

12. Nella Scheda dettaglio **Righe della distinta base** selezionare **Modifica** per aprire la finestra di dialogo **Modifica riga DBA**.

    Quando viene creato e stimato un ordine di produzione per il prodotto rilasciato D8100, viene generato automaticamente un ordine fornitore per l'articolo S8050. L'ordine fornitore verrà collegato all'ordine di produzione. Affinché gli ordini fornitore vengano generati automaticamente, è necessario impostare il campo **Tipo di riga** su **Fornitore** e selezionare il conto fornitore per il terzista. In questo caso il conto fornitore è US-801.

    Notare che la riga DBA è collegata all'operazione Rivestimento tramite il numero di operazione, in questo caso 20.

    ![Finestra di dialogo Modifica riga DBA](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a>Creare una password per gli addetti magazzino

È necessario definire una password per gli addetti magazzino che utilizzano il dispositivo palmare.

1. Selezionare **Gestione magazzino \> Impostazioni \> Lavoratore** per aprire la pagina **Utenti di lavoro**.
2. Nella Scheda dettaglio **Utenti** selezionare la riga per l'utente **51**.

    ![Pagina Utenti di lavoro](./media/subcontract11_work-users-page.png)

3. Selezionare **Reimposta password**.
4. Nei campi **Password** e **Conferma password** immettere **1**.
5. Selezionare **Imposta password**.

## <a name="step-by-step-walkthrough"></a>Procedura

**Scenario e sfondo**

Viene creato un ordine di produzione di 10 pezzi per il prodotto D8100, "Cabinet rivestito". Il rivestimento dei cabinet è un'operazione in conto lavoro che viene eseguita presso il fornitore US-801, Perfect Coating Solutions. L'ordine di produzione è costituito da tre operazioni. Nella prima operazione il gabinetto viene preassemblato internamente. Il materiale per il pre-assemblaggio viene rilasciato per essere prelevato nel magazzino delle materie prime. Dopo l'assemblaggio, il cabine viene inviato a Perfect Coating Solutions insieme a due materiali che sono necessari per l'operazione di rivestimento. Quando il cabinet rivestito viene restituito dal fornitore, viene sottoposto internamente a un'operazione di assemblaggio finale prima di essere segnalato come finito.

1. Selezionare **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** per aprire la pagina **Tutti gli ordini di produzione**.
2. Nel riquadro azioni selezionare **Nuovo ordine di produzione** per aprire la finestra di dialogo **Crea ordine di produzione**.

    ![Finestra di dialogo Crea ordine di produzione](./media/subcontract12_create-production-order-dialog.png)

3. Nel campo **Numero articolo** selezionare **D8100**.
4. Dopo avere selezionare il numero articolo, vengono visualizzati i campi per le dimensioni inventariali. Nel campo **Colore** selezionare **Cromato**.

    Verrà visualizzata una finestra di messaggio per chiedere se è necessario inserire le versioni attive della DBA e del ciclo di lavorazione.

    ![Finestra di messaggio](./media/subcontract13_message-box.png)

5. Selezionare **Sì**. 

    Nella finestra di dialogo **Crea ordine di produzione** le versioni attive della DBA e del ciclo di lavorazione per il prodotto D8100 vengono automaticamente selezionate nei rispettivi campi **Numero DBA** e **Numero ciclo di lavorazione**. In questo caso vengono selezionati la DBA **000040** e il ciclo di lavorazione **000040**.
    
    > [!NOTE]
    > Sia per la DBA che per il ciclo di lavorazione, viene utilizzata la versione 000040 per la determinazione dei costi e la pianificazione.

6. Nel campo **Sito** selezionare **5**.
7. Nel campo **Magazzino** selezionare **51**.
8. Nei campi **Numero DBA** e **Numero ciclo di lavorazione** modificare il valore selezionato automaticamente in **000042**.

    > [!NOTE]
    > Sia per la DBA che per il ciclo di lavorazione, viene utilizzata la versione 000042 per subappaltare l'operazione di rivestimento del cabinet al fornitore US-801.

    ![Valori impostati nella finestra di dialogo Crea ordine di produzione](./media/subcontract14_create-production-order-dialog-set.png)

9. Selezionare **Crea** per creare l'ordine di produzione e tornare alla pagina **Tutti gli ordini di produzione**.

    ![Nuovo ordine di produzione nella pagina Tutti gli ordini di produzione](./media/subcontract15_new-production-order.png)

10. Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **Stima** per aprire la finestra di dialogo **Stima**.

    ![Finestra di dialogo Stima](./media/subcontract16_estimate-dialog.png)

11. Selezionare **OK** per confermare la stima e tornare alla pagina **Tutti gli ordini di produzione**.

    > [!NOTE]
    > Dopo la stima dell'ordine di produzione, viene generato l'ordine fornitore per l'articolo di tipo Assistenza S8050 per il fornitore US-801.

12. Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **DBA** per aprire la pagina **DBA**, dove è possibile visualizzare le righe DBA per l'ordine di produzione.

    Per l'articolo di tipo Assistenza S8050, notare che è presente un riferimento all'ordine fornitore generato quando l'ordine di produzione è stato stimato.

    ![Righe DBA dell'ordine di produzione nella pagina DBA](./media/subcontract17_production-order-bom-lines.png)

13. Chiudere la pagina **DBA** per tornare alla pagina **Tutti gli ordini di produzione**.
14. Nel riquadro azioni, nella scheda **Programma** selezionare **Programma processi** per aprire la finestra di dialogo **Programmazione processo**.
15. Specificare i valori seguenti:

    - Nel campo **Direzione programmazione** selezionare **Avanti da domani**.
    - Impostare l'opzione **Capacità limitata** su **Sì**.

    ![Finestra di dialogo Programmazione processi](./media/subcontract18_job-scheduling-dialog.png)

16. Selezionare **OK** per chiudere la finestra di dialogo **Programmazione processi** e tornare alla pagina **Tutti gli ordini di produzione**.
17. Nel riquadro azioni, nella scheda **Programma** scegliere **Gantt** per aprire la pagina **Diagramma di Gantt - visualizzazione risorse**.

    Il diagramma di Gantt fornisce una panoramica visiva del modo in cui i processi di produzione vengono programmati sulle risorse. Notare che l'operazione esterna di rivestimento consiste in tre processi: un processo di lavorazione, un processo di trasporto e un processo con tempo di attesa.

    ![Pagina Diagramma di Gantt - Visualizzazione risorse](./media/subcontract19_gantt-chart.png)

18. Chiudere la pagina **Diagramma di Gantt - Visualizzazione risorse** per tornare alla pagina **Tutti gli ordini di produzione**.
19. Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **Rilascio** per aprire la finestra di dialogo **Rilascio**.

    ![Finestra di dialogo Rilascio](./media/subcontract20_release-dialog.png)

20. Selezionare **OK** per chiudere la finestra di dialogo **Rilascio**.
21. Selezionare **Controllo produzione \> Attività periodiche \> Rilascia in magazzino \> Rilascio automatico di righe di DBA e di formula** per aprire la finestra di dialogo **Rilascio automatico di righe di DBA e di formula**.

    ![Finestra di dialogo Rilascio automatico di righe di DBA e di formula](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. Selezionare **OK** per eseguire il processo Rilascio automatico di righe di DBA e di formula.

    Questo processo rilascia il lavoro di prelievo delle materie prime al magazzino.

23. Selezionare **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** per aprire la pagina **Tutti gli ordini di produzione**.
24. Utilizzare il campo di filtro rapido per selezionare l'ordine di produzione a cui si sta lavorando.
25. Nel riquadro azioni, nella scheda **Magazzino** selezionare **Dettagli lavoro** per aprire la pagina **Lavoro**.

    Notare che la pagina mostra due set di lavoro per il prelievo della materia prima. Il primo lavoro riguarda i materiali M8100 e M8101. Questi materiali vengono utilizzati nell'operazione 10. Il secondo lavoro riguarda i materiali M8202 e M8250. Questi materiali vengono utilizzati dall'operazione 20, che corrisponde all'operazione in conto lavoro.

    ![Due set di lavoro per il prelievo della materia prima nella pagina Lavoro.](./media/subcontract22_work-page.png)

26. Avviare l'app di magazzino per elaborare il lavoro di magazzino per l'operazione 10.

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. Selezionare **Controllo produzione \> Ordini di produzione \> Tutti gli ordini di produzione** per aprire la pagina **Tutti gli ordini di produzione**.
28. Utilizzare il campo di filtro rapido per selezionare l'ordine di produzione a cui si sta lavorando.
29. Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **Avvio** per aprire la finestra di dialogo **Avvio**.
30. Nella scheda **Generale** specificare i valori seguenti:

    - Nel campo **Da oper. n.** selezionare **10**.
    - Nel campo **A oper. n.** selezionare **10**.

    ![Valori impostati nella scheda Generale](./media/subcontract23_start-dialog.png)

31. Selezionare **OK** per chiudere la finestra di dialogo **Avvio** e tornare alla pagina **Tutti gli ordini di produzione**.

    Notare che lo stato dell'ordine di produzione è ora impostato su **Avviato**. I materiali per l'operazione 10 vengono consumati da una registrazione automatica del giornale di registrazione distinte di prelievo. Il consumo di tempo per l'operazione 10 viene considerato da una registrazione automatica di un giornale di registrazione schede cicli di lavorazione.

32. Avviare l'app di magazzino per elaborare il lavoro di magazzino per l'operazione 20.

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. Nel riquadro azioni, nella scheda **Ordine di produzione** selezionare **Avvio** per aprire la finestra di dialogo **Avvio**.
34. Nella scheda **Generale** specificare i valori seguenti:

    - Nel campo **Da oper. n.** selezionare **20**.
    - Nel campo **A oper. n.** selezionare **20**.
    - Nel campo **Quantità** immettere **10**.
    - Impostare l'opzione **Registra distinta di prelievo ora** su **No**.

    ![Valori impostati nella scheda Generale](./media/subcontract24_general-tab.png)

35. Selezionare **OK** per chiudere la finestra di dialogo **Avvio** e tornare alla pagina **Tutti gli ordini di produzione**.

    Verrà creata una distinta di prelievo per i materiali utilizzati per l'operazione di rivestimento e per l'articolo di tipo Assistenza. L'articolo di tipo Assistenza rappresenta il costo dell'operazione in conto lavoro.

36. Nel riquadro azioni, nella scheda **Visualizza** scegliere **Distinta di prelievo** per aprire la pagina **Distinta di prelievo**.
37. Selezionare la distinta di prelievo che non è registrata e selezionare il numero del giornale di registrazione per visualizzare le righe del giornale di registrazione.

    ![Righe del giornale di registrazione nella pagina Distinta di prelievo](./media/subcontract25_picking-list.png)

38. Nel riquadro azioni, selezionare **Stampa** \> **Report distinte di prelievo** per aprire la finestra di dialogo **Report distinte di prelievo**.
39. Impostare l'opzione **Utilizza layout bolla di consegna** su **Sì**.

    ![Finestra di dialogo Report distinte di prelievo](./media/subcontract26_picking-list-report-dialog.png)

40. Selezionare **OK** per generare un report **Distinta di prelievo**.

    In questo caso viene stampata una bolla di consegna fornitore dal giornale di registrazione distinte di prelievo produzione. La bolla di consegna specifica i materiali che devono essere spediti al fornitore che si occupa dell'operazione di rivestimento.

    ![Report distinte di prelievo](./media/subcontract27_picking-list-report.png)

41. Chiudere il report **Distinta di prelievo** per tornare alla pagina **Distinta di prelievo**.
42. Nel riquadro azioni, scegliere **Registra** per aprire la finestra di dialogo **Registra giornale**.

    ![Finestra di dialogo Registra giornale](./media/subcontract28_post-journal-dialog.png)

43. Selezionare **OK** per chiudere la finestra di dialogo **Registra giornale**.
44. Aprire l'ordine fornitore.

    ![Pagina Ordine fornitore](./media/subcontract29_purchase-order-page.png)

45. Nel riquadro azioni, nella scheda **Acquisti** selezionare **Conferma**.
46. Selezionare **Registra** per aprire la finestra di dialogo **Registra giornale**.
47. Selezionare **OK** per chiudere la finestra di dialogo **Registra giornale** e tornare alla pagina **Ordine fornitore**.
48. Modificare il prezzo unitario da **33** a **40**.

    ![Prezzo unitario modificato nella pagina Ordine fornitore](./media/subcontract30_unit-price.png)

49. Confermare di nuovo l'ordine fornitore.
50. Entrata prodotti.

    ![Finestra di dialogo Registrazione entrata prodotti](./media/subcontract31_posting-product-receipt-dialog.png)

51. Fattura acquisto.
52. Aggiornare lo stato di abbinamento.

    ![Pagina Fattura fornitore](./media/subcontract32_vendor-invoice-page.png)

53. Dichiarato finito.

    ![Finestra di dialogo Dichiarazione di finito](./media/subcontract33_report-as-finished-dialog.png)

54. Fine.

    ![Finestra di dialogo Fine](./media/subcontract34_end-dialog.png)

55. Confronto costi.

    ![Grafici di confronto costi](./media/subcontract35_cost-comparison-charts.png)

Mancata impostazione nei dati.
