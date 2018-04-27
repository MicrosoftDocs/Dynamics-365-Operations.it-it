--- 
title: Progettare il modello di dati per utilizzare le dimensioni finanziarie come origine dati
description: "I passaggi seguenti descrivono come un amministratore di sistema o uno sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3e55eedba1955ae79733afee1a0b3c7072147bb5
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="design-data-model-to-use-financial-dimensions-as-a-data-source"></a>Progettare il modello di dati per utilizzare le dimensioni finanziarie come origine dati 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un amministratore di sistema o uno sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici. Questi passaggi possono essere eseguiti in qualsiasi società.

Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".


## <a name="create-a-new-data-model"></a>Creare un nuovo modello dati
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Assicurarsi che il provider Litware, Inc. sia disponibile e contrassegnato come attivo.  
2. Fare clic su Configurazioni report.
3. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
4. Nel campo Nome digitare 'Modello di esempio dimensioni finanziarie'.
5. Fare clic su Crea configurazione.
6. Fare clic su Progettazione.
7. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
8. Digitare 'Voce' nel campo Nome.
9. Scegliere Aggiungi.
10. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
11. Nel campo Nome digitare "Società".
12. Scegliere Aggiungi.
    * Aggiungeremo al modello un nuovo elenco di record. Questo elenco esporrà (per qualsiasi report ER che usa questo modello come origine dati) le impostazioni delle dimensioni finanziarie selezionate. Ogni dimensione finanziaria verrà presentata in questo elenco come record con campi appropriati che rappresentano l'impostazione della dimensione.  
13. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
14. Digitare un 'Impostazione dimensioni' nel campo Nome.
15. Nel campo Tipo di articolo selezionare "Elenco di record".
16. Scegliere Aggiungi.
17. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
18. Digitare 'Codice' nel campo Nome.
19. Nel campo Tipo di articolo selezionare "Stringa".
20. Scegliere Aggiungi.
21. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
22. Nel campo Nome digitare "Nome".
23. Scegliere Aggiungi.
24. Nella struttura selezionare 'Voce'.
25. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
26. Digitare 'Giornale di registrazione' nel campo Nome.
27. Nel campo Tipo di articolo selezionare "Elenco di record".
28. Scegliere Aggiungi.
29. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
30. Digitare 'Batch'. nel campo Nome.
31. Nel campo Tipo di articolo selezionare "Stringa".
32. Scegliere Aggiungi.
33. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
34. Nel campo Nome digitare 'Transazione'.
35. Nel campo Tipo di articolo selezionare "Elenco di record".
36. Scegliere Aggiungi.
37. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
38. Digitare 'Data' nel campo Nome.
39. Nel campo Tipo di articolo selezionare "Data".
40. Scegliere Aggiungi.
41. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
42. Digitare 'Dare' nel campo Nome.
43. Nel campo Tipo di articolo selezionare "Reale".
44. Scegliere Aggiungi.
45. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
46. Nel campo Nome digitare 'Avere'.
47. Scegliere Aggiungi.
48. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
49. Nel campo Nome digitare "Valuta".
50. Nel campo Tipo di articolo selezionare "Stringa".
51. Scegliere Aggiungi.
52. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
53. Digitare 'Giustificativo' nel campo Nome.
54. Scegliere Aggiungi.
55. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
56. Digitare 'Dati dimensioni' nel campo Nome.
57. Nel campo Tipo di articolo selezionare "Elenco di record".
58. Scegliere Aggiungi.
    * Abbiamo aggiunto al modello un nuovo elenco di record. Questo elenco esporrà (per qualsiasi report ER che usa questo modello come origine dati) i valori delle dimensioni finanziarie selezionate. Ogni dimensione finanziaria verrà presentata in questo elenco come record con campi appropriati che rappresentano i valori della dimensione. Anche il nome della dimensione verrà presentato in questo record come campo da utilizzare, se necessario, per facilitare la selezione.  
59. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
60. Digitare 'Codice' nel campo Nome.
61. Nel campo Tipo di articolo selezionare "Stringa".
62. Scegliere Aggiungi.
63. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
64. Nel campo Nome digitare "Descrizione".
65. Scegliere Aggiungi.
66. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
67. Nel campo Nome digitare "Nome".
68. Scegliere Aggiungi.
69. Fare clic su Salva.
70. Chiudere la pagina.


