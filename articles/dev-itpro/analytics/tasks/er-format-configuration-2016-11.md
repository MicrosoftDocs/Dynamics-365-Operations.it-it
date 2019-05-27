---
title: ER Creare una configurazione formato (novembre 2016)
description: I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 582e1a2baee805fe6770465edc7958954f638f1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544773"
---
# <a name="er-create-a-format-configuration-november-2016"></a>ER Creare una configurazione formato (novembre 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare una configurazione di formato per la creazione di report elettronici. Tale configurazione di formato definirà il formato dei documenti elettronici utilizzati per l'elaborazione dei pagamenti. In questo esempio verrà creata una configurazione di formato per la società di esempio Litware, Inc. Per completare questi passaggi, è necessario aver completato prima i passaggi della procedura "Mappare il modello alle origini dati selezionate".


## <a name="create-a-new-format-configuration"></a>Creare una nuova configurazione di formato
1. Andare ad **Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici**.
2. Fare clic su **Configurazioni report**.
3. Nella struttura selezionare **Pagamenti (modello semplificato)**.
4. Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa.

 > [!NOTE]
 > Se **Crea configurazione** non è visualizzato, necessario abilitare la modalità progettazione nella pagina **Parametri per la creazione di report elettronici**. 
 
5. Nel campo **Nuovo** immettere **Formato in base al modello dati PaymentModel**.
6. Nel campo **Nome** digitare **BACS (fittizio per il Regno Unito)**.
7. Nel campo **Descrizione** digitare **Formato di pagamento fornitore BACS (fittizio per il Regno Unito)**.
    * Il provider di configurazione attiva viene inserito automaticamente in questo punto. Tale provider potrà gestire la configurazione. Altri provider possono utilizzare la configurazione, ma non potranno gestirla.  
    * È possibile definire un formato specifico del documento elettronico. Lasciare vuoto il campo se si desidera selezionare un formato in fase di esecuzione.  
8. Nel campo **Definizione modello dati** immettere o selezionare un valore.
9. Fare clic su **Crea configurazione**. È stata creata una nuova configurazione. La versione bozza può essere utilizzata per archiviare il formato di progettazione per gestire i documenti elettronici.  

## <a name="design-the-format-of-an-electronic-document"></a>Progettazione del formato di un documento elettronico
1. Fare clic su **Progettazione**.
2. Fare clic su **Aggiungi radice** per aprire la finestra di dialogo a discesa.
3. Nella struttura selezionare **Comune\File**.
4. Nel campo **Nome** digitare **XML**.
5. Nel campo **Codifica** digitare **UTF-8**.
6. Fare clic su **OK**.
7. Fare clic su **Aggiungi**.
8. Nella struttura selezionare **XML\Elemento**.
9. Nel campo **Nome** digitare **Messaggio**.
10. Fare clic su **OK**.
11. Nella struttura selezionare **Xml\Messaggio**.
12. Fare clic su **Aggiungi elemento**.
13. Nel campo **Nome** digitare **ProcessingDate**.
14. Fare clic su **OK**.
15. Fare clic su **Aggiungi elemento**.
16. Nel campo Nome digitare **MessageId**.
17. Fare clic su **OK**.
18. Fare clic su **Aggiungi elemento**.
19. Nel campo **Nome** digitare **Pagamenti**.
20. Fare clic su **OK**.
21. Nella struttura selezionare **Xml\Messaggio\Pagamenti**.
22. Fare clic su **Aggiungi elemento**.
23. Nel campo **Nome** digitare **Articolo**.
24. Fare clic su **OK**.
25. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.
26. Fare clic su **Aggiungi**.
27. Nella struttura selezionare **XML\Attributo**.
28. Nel campo Nome digitare **ID**.
29. Fare clic su **OK**.
30. Fare clic su **Aggiungi**.
31. Nella struttura selezionare **XML\Elemento**.
32. Nel campo Nome digitare **Fornitore**.
33. Fare clic su **OK**.
34. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore**.
35. Fare clic su **Aggiungi elemento**.
36. Nel campo Nome digitare **Nome**.
37. Fare clic su **OK**.
38. Fare clic su **Aggiungi elemento**.
39. Nel campo **Nome** digitare **Banca**.
40. Fare clic su **OK**.
41. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca**.
42. Fare clic su **Aggiungi elemento**.
43. Nel campo **Nome** digitare **RoutingNumber**.
44. Fare clic su **OK**.
45. Fare clic su **Aggiungi elemento**.
46. Nel campo **Nome** digitare **AccountNumber**.
47. Fare clic su **OK**.
48. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore**.
49. Fare clic su **Copia**.
50. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.
51. Fare clic su **Incolla**.
52. Nel campo **Nome** digitare **Pagante**.
53. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo**.
54. Fare clic su **Aggiungi elemento**.
55. Nel campo **Nome** digitare **Valuta**.
56. Fare clic su **OK**.
57. Fare clic su **Aggiungi elemento**.
58. Nel campo **Nome** digitare **Descrizione**.
59. Fare clic su **OK**.
60. Fare clic su **Aggiungi elemento**.
61. Nel campo Nome digitare **TransDate**.
62. Fare clic su **OK**.
63. Fare clic su **Aggiungi elemento**.
64. Nel campo Nome digitare **Importo**.
65. Fare clic su **OK**.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Preparare i componenti del formato per eseguire il mapping a elementi del modello dati
1. Nella struttura selezionare **Xml\Messaggio\ProcessingDate**.
2. Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.
3. Nella struttura selezionare **Text\DateTime**.
4. Nel campo **Formato** digitare **gg-MM-aaaa**.
5. Fare clic su **OK**.
6. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\TransDate**.
7. Fare clic su **Aggiungi DateTime**.
8. Nel campo **Formato** digitare **gg-MM-aaaa**.
9. Nel campo **DateTime** selezionare **Date**.
10. Fare clic su **OK**.
11. Nella struttura selezionare **Xml\Messaggio\MessageId**.
12. Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.
13. Nella struttura selezionare **Testo\Stringa**.
14. Fare clic su **OK**.
15. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome**.
16. Fare clic su **Aggiungi stringa**.
17. Fare clic su **OK**.
18. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\RoutingNumber**.
19. Fare clic su **Aggiungi stringa**.
20. Fare clic su **OK**.
21. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\AccountNumber**.
22. Fare clic su **Aggiungi stringa**.
23. Fare clic su **OK**.
24. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Nome**.
25. Fare clic su **Aggiungi stringa**.
26. Fare clic su **OK**.
27. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\RoutingNumber**.
28. Fare clic su **Aggiungi stringa**.
29. Fare clic su **OK**.
30. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Pagante\Banca\AccountNumber**.
31. Fare clic su **Aggiungi stringa**.
32. Fare clic su **OK**.
33. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Valuta**.
34. Fare clic su **Aggiungi stringa**.
35. Fare clic su **OK**.
36. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Descrizione**.
37. Fare clic su **Aggiungi stringa**.
38. Fare clic su **OK**.
39. Nella struttura selezionare **Xml\Messaggio\Pagamenti\Articolo\Importo**.
40. Fare clic su **Aggiungi stringa**.
41. Fare clic su **OK**.
42. Fare clic su **Salva**.
43. Chiudere la pagina.

