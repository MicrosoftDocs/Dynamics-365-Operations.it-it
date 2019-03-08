---
title: "ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 3: usare i calcoli per creare l'output)"
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c870c134a9dae81cd619268bed7ce545bdd5f52
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "347079"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3-use-computations-to-make-the-output"></a>ER configurare il formato per eseguire il conteggio e la sommatoria (parte 3: usare i calcoli per creare l'output)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato. Questi passaggi possono essere eseguiti in qualsiasi società.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella procedura 'ER Configurare il formato per eseguire conteggi e somme (parte 2: configurare i calcoli)'.

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>Configurare questo report per utilizzare le informazioni di conteggio e somma
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Configurazioni report.
3. Nella struttura espandere 'Modello Intrastat'.
4. Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.
5. Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.
6. Fare clic su Progettazione.
7. Fare clic sulla scheda Mapping.
8. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
    * Aggiungere una nuova origine dati per ottenere l'elenco dei blocchi memorizzati.  
9. Nella struttura selezionare "Funzioni\Campo calcolato".
10. Digitare  '$BlocksList' nel campo Nome.
    * $BlocksList  
11. Fare clic su Modifica formula.
12. Nella struttura, selezionare 'Funzioni raccolta dati\COLLECTEDLIST'.
13. Fare clic su Aggiungi funzione.
14. Fare clic su Aggiungi origine dati.
15. Nel campo Formula immettere 'COLLECTEDLIST('$BlockName', '.
    * COLLECTEDLIST('$BlockName',  
16. Nel campo Formula immettere 'COLLECTEDLIST('$BlockName', "*")'.
    * COLLECTEDLIST('$BlockName', "*")  
17. Fare clic su Salva.
    * Il modello "*" indica che tutti i blocchi verranno inclusi nell'elenco per il record.  
18. Chiudere la pagina.
19. Fare clic su OK.
20. Fare clic sulla scheda Formato.
21. Nella struttura selezionare 'Intrastat\Dati'.
22. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
23. Nella struttura selezionare 'Testo\Sequenza'.
24. Nel campo Nome digitare 'Totali per blocchi'.
    * Totali per blocchi  
25. Nel campo Caratteri speciali, selezionare 'Nuova riga - Windows (CR LF)'.
26. Fare clic su OK.
27. Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi'.
28. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
29. Nella struttura selezionare "Testo\Stringa".
30. Digitare 'Codice blocco' nel campo Nome.
    * Codice blocco  
31. Fare clic su OK.
32. Fare clic su Aggiungi stringa.
33. Nel campo Nome digitare 'Conteggio righe'.
    * Conteggio righe  
34. Fare clic su OK.
35. Fare clic su Aggiungi stringa.
36. Nel campo Nome digitare 'Importo totale'.
    * Importo totale  
37. Fare clic su OK.
38. Fare clic sulla scheda Mapping.
39. Nella struttura selezionare '$BlocksList'.
40. Fare clic su Associa.
    * Creare una riga di riepilogo per ciascun blocco memorizzato.  
41. Fare clic sulla scheda Formato.
42. Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Codice blocco'.
43. Fare clic sulla scheda Mapping.
44. Fare clic su Modifica formula.
45. Nel campo Formula immettere '"Block id: " & '.
    * "Block id: " &  
46. Nella struttura espandere '$BlocksList'.
47. Nella struttura selezionare '$BlocksList\Value'.
48. Fare clic su Aggiungi origine dati.
49. Fare clic su Salva.
50. Chiudere la pagina.
51. Fare clic sulla scheda Formato.
52. Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Conteggio righe'.
53. Fare clic sulla scheda Mapping.
54. Fare clic su Modifica formula.
    * Creare l'output per il numero di righe per ciascun blocco presentato nel report.  
55. Nel campo Formula, immettere '"Numero di righe in questo blocco: " & '.
    * "Numero di righe in questo blocco: " &  
56. Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT('.
    * "Numero di righe in questo blocco: " & TEXT(  
57. Nella struttura, selezionare 'Funzioni raccolta dati\COUNTIFS'.
58. Fare clic su Aggiungi funzione.
59. Fare clic su Aggiungi origine dati.
60. Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '.
    * "Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName',  
61. Nella struttura espandere '$BlocksList'.
62. Nella struttura selezionare '$BlocksList\Value'.
63. Fare clic su Aggiungi origine dati.
64. Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.
    * "Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,  
65. Nella struttura selezionare '$RecName'.
66. Fare clic su Aggiungi origine dati.
67. Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.
    * "Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
68. Fare clic su Salva.
69. Chiudere la pagina.
70. Fare clic sulla scheda Formato.
71. Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Importo totale'.
72. Fare clic sulla scheda Mapping.
73. Fare clic su Modifica formula.
    * Creare l'output che costituirà il totale dell'importo fatturato per ciascun blocco presentato nel report.  
74. Nel campo Formula immettere '"Somma dell'importo fatturato: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.
    * "Somma dell'importo fatturato: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
75. Fare clic su Salva.
76. Chiudere la pagina.
77. Fare clic su Salva.
78. Chiudere la pagina.

