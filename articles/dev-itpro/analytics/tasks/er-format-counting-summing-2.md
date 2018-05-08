--- 
title: Configurare i calcoli per eseguire il conteggio e la somma
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.openlocfilehash: d41ce101c0b038627e2baf6b5eac2410095af7ce
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="configure-computations-to-do-counting-and-summing"></a>Configurare i calcoli per eseguire il conteggio e la somma

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato. Questi passaggi possono essere eseguiti in qualsiasi società.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella procedura  'ER Configurare il formato per eseguire conteggi e somme (parte 1: creare il formato)'.

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>Creare una configurazione di formato per aggiungere dettagli di conteggio e somma
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Configurazioni report.
3. Nella struttura espandere 'Modello Intrastat'.
4. Nella struttura, selezionare 'Modello Intrastat\Intrastat (DE)'.
    * Si supponga di dover personalizzare il formato fornito da Microsoft aggiungendo righe con dettagli di riepilogo alla fine del report Intrastat. A tale scopo si deve derivare la propria istanza della configurazione Intrastat dall'istanza di Microsoft per apportare le modifiche.  
5. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
6. Nel campo Nuovo, immettere 'Deriva da nome: Intrastat (DE), Microsoft'.
7. Nel campo Nome, digitare 'Intrastat (DE) con conteggi e somme'.
8. Fare clic su Crea configurazione.

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>Configurare questo report per eseguire il conteggio e la sommatoria in base ai dettagli di output
1. Fare clic su Progettazione.
2. Selezionare Sì nel campo Raccogli dettagli di output.
    * Il flag attiverà in fase di esecuzione il processo di raccolta dei dettagli di output  per la generazione del file Intrastat.  
    * È necessario eseguire il conteggio per le diverse direzioni Intrastat, quindi aggiungere un'enumerazione modello dedicata all'elenco delle origini dati di questa configurazione di formato.  
3. Fare clic sulla scheda Mapping.
4. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
5. Nella struttura selezionare 'Modello dati\Enumerazione'.
6. Digitare 'Direction' nel campo Nome.
7. Nel campo Enumerazione modello immettere o selezionare un valore.
    * Selezionare il valore Direction.  
8. Fare clic su OK.
9. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
10. Nella struttura selezionare "Funzioni\Campo calcolato".
11. Digitare '$BlockName' nel campo Nome.
12. Fare clic su Modifica formula.
13. Nel campo Formula immettere'"block"'.
14. Fare clic su Salva.
15. Chiudere la pagina.
16. Fare clic su OK.
17. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
18. Nella struttura selezionare "Funzioni\Campo calcolato".
19. Nel campo Nome digitare '$RecName'.
20. Fare clic su Modifica formula.
21. Nel campo Formula immettere '"record"'.
22. Fare clic su Salva.
23. Chiudere la pagina.
24. Fare clic su OK.
25. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
26. Nella struttura selezionare "Funzioni\Campo calcolato".
27. Nel campo Nome digitare '$InvName'.
28. Fare clic su Modifica formula.
29. Nel campo Formula immettere '"InvoicedAmountEUR"'.
30. Fare clic su Salva.
31. Chiudere la pagina.
32. Fare clic su OK.
33. Nella struttura selezionare 'Intrastat\Dati'.
34. Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'
35. Fare clic su Aggiungi origine dati.
    * $BlockName  
36. Fare clic su Salva.
37. Chiudere la pagina.
38. Fare clic sul pulsante Modifica per il campo Valore chiave dati raccolti.
39. Nel campo Formula immettere 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.
    * IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")  
40. Fare clic su Salva.
41. Chiudere la pagina.
    * Contare le righe della sequenza. I risultati verranno utilizzati con il nome 'block' separatamente per le diverse direzioni. Il valore 'Import' verrà utilizzato per tutte le transazioni Intrastat di arrivi. Il valore 'Export' verrà utilizzato per tutte le transazioni Intrastat di spedizioni. Considerare questo come un foglio di calcolo di Excel virtuale. Per ciascuna transazione una riga in cui la prima colonna 'block' viene compilata, di conseguenza, con i valori 'Import' ed 'Export'.  
42. Nella struttura espandere 'Intrastat\Dati: Sequenza'.
43. Nella struttura selezionare 'Intrastat\Dati: Sequenza\Arrivi?'.
44. Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'.
    * Contare le righe della sequenza. I risultati verranno memorizzati utilizzando il nome 'record'.  
45. Nella struttura selezionare '$RecName'.
46. Fare clic su Aggiungi origine dati.
47. Fare clic su Salva.
48. Chiudere la pagina.
49. Fare clic sul pulsante Modifica per il campo Valore chiave dati raccolti.
50. Nel campo Formula, immettere  'Intrastat.CommodityRecord.CommodityCode'.
51. Fare clic su Salva.
52. Chiudere la pagina.
    * Contare le righe della sequenza. I risultati verranno utilizzati con il nome 'record' separatamente per i diversi codici voce doganale. Considerare questo come un foglio di calcolo di Excel virtuale. Per ciascuna transazione una riga in cui la prima colonna 'block' viene compilata, di conseguenza, con i valori 'Import' ed 'Export' e il secondo blocco 'record' è compilato con il valore del codice di voce doganale.  
53. Nella struttura espandere 'Intrastat\Dati: Sequenza\Spedizioni?'.
54. Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'
55. Nella struttura selezionare '$RecName'.
56. Fare clic su Aggiungi origine dati.
57. Fare clic su Salva.
58. Chiudere la pagina.
59. Fare clic sul pulsante Modifica per il campo Valore chiave dati raccolti.
60. Nel campo Formula, immettere  'Intrastat.CommodityRecord.CommodityCode'.
61. Fare clic su Salva.
62. Chiudere la pagina.
63. Nella struttura espandere 'Intrastat\Dati: Sequenza\Spedizioni: Sequenza?'.
64. Nella struttura espandere 'Intrastat\Dati: Sequenza\Spedizioni: Sequenza?\Record =  Intrastat.CommodityRecord'.
65. Fare clic sulla scheda Formato.
66. Nella struttura selezionare 'Intrastat\Dati\Spedizioni\Record\Importo fattura EUR'.
67. Fare clic sulla scheda Mapping.
68. Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'.
69. Nella struttura selezionare '$InvName'.
70. Fare clic su Aggiungi origine dati.
71. Fare clic su Salva.
72. Chiudere la pagina.
    * Riepilogare i valori dell'importo fatturato per le righe della sequenza. I risultati verranno utilizzati con il nome 'InvoicedAmountEUR' separatamente per le diverse direzioni e i diversi codici voce doganale Intrastat. Considerare questa come una creazione virtuale nel foglio di calcolo di Excel. Per ciascuna transazione una riga in cui la prima colonna 'block' viene compilata, di conseguenza, con i valori 'Import' ed 'Export'. Il secondo blocco 'record' viene compilato con il valore del codice voce doganale e la terza colonna 'InvoicedAmountEUR' viene compilata con il valore dell'importo della fattura.  
73. Nella struttura espandere 'Intrastat\Dati\Arrivi?'.
74. Nella struttura espandere 'Intrastat\Dati\Arrivi?\Record =  Intrastat.CommodityRecord'.
75. Fare clic sulla scheda Formato.
76. Nella struttura selezionare 'Intrastat\Dati\Arrivi\Record\Importo fattura EUR'.
77. Fare clic sulla scheda Mapping.
78. Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'.
79. Nella struttura selezionare '$InvName'.
80. Fare clic su Aggiungi origine dati.
81. Fare clic su Salva.
82. Chiudere la pagina.
83. Fare clic su Salva.
84. Chiudere la pagina.


