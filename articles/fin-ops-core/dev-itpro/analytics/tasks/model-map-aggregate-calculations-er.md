---
title: Utilizzare configurazioni del mapping di modelli per calcoli aggregati a livello di database
description: Questa procedura fornisce informazioni per progettare una nuova configurazione di mapping di modello (ER) per la creazione di report elettronici e usare le funzioni ER incorporate per i calcoli aggregati efficienti.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f1c4ddf0fac5ba962c3dab545bfa7e0df4afa948
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684117"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a>Utilizzare configurazioni del mapping di modelli per calcoli aggregati a livello di database

[!include [banner](../../includes/banner.md)]

Questa procedura fornisce informazioni per progettare una nuova configurazione di mapping di modello (ER) per la creazione di report elettronici e usare le funzioni ER incorporate per i calcoli aggregati efficienti. In questa procedura verrà creata una configurazione per la società di esempio Litware, Inc. 

Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Tali passaggi possono essere completati mediante un set di dati.

 Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura "ER migliora l'efficienza dei calcoli di aggregazione eseguendoli a livello di database (Parte 1: Preparazione le configurazioni)".

1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere 'Modello Intrastat'.
3. Nella struttura selezionare 'Modello Intrastat\Mapping di esempio Intrastat'.
4. Fare clic su Progettazione.
5. Fare clic su Progettazione.
6. Nella struttura selezionare 'Dynamics 365 for Operations\Record di tabella'.
7. Fare clic su Aggiungi radice.
    * Aggiungere una nuova origine dati che rappresenta i record da raggruppare.  
8. Nel campo Nome digitare "Transazioni".
    * Transazioni  
9. Nel campo Tabella digitare "Intrastat".
    * Intrastat  
10. Fare clic su OK.
11. Nella struttura selezionare "Funzioni\Raggruppa per".
    * Questo tipo di origine dei dati viene utilizzato per immettere una nuova origine dati in fase di esecuzione nei record di gruppo e per calcolare le aggregazioni richieste.  
12. Fare clic su Aggiungi radice.
13. Digitare 'TransactionsGroups' nel campo Nome.
    * TransactionsGroups  
14. Fare clic su Modifica gruppo per.
15. Nella struttura selezionare "Transazioni".
    * Selezionare l'origine dati aggiunta di tipo "Elenco di record" che rappresenta i record da raggruppare.  
16. Fare clic su Aggiungi campo a.
17. Fare clic su Informazioni da raggruppare.
18. Nella struttura espandere "Transazioni".
19. Nella struttura, selezionare "Transazioni\Direzione".
20. Fare clic su Aggiungi campo a.
21. Fare clic su Campi raggruppati.
    * Selezionare il campo per specificare il livello di raggruppamento. In base a questa selezione, l'origine dati restituisce in fase di esecuzione tutti i gruppi di transazioni quanti sono i codici di direzione soddisfatti nella tabella Intrastat.  
22. Nella struttura selezionare "Transazioni\Importo fattura(AmountMST)".
    * Selezionare il campo per specificare l'origine per il calcolo di aggregazione.  
23. Fare clic su Aggiungi campo a.
24. Fare clic su Campi di aggregazione.
25. Nell'elenco contrassegnare la riga selezionata.
26. Selezionare "Somma" nel campo Metodo.
    * Selezionare il tipo di aggregazione.  
27. Digitare 'SumOfAmountMST' nel campo Nome.
    * Specificare il nome dell'aggregazione nell'origine dati configurata.  
28. Fare clic su Salva.
    * Tenere presente che il campo "Esecuzione in" indica che il raggruppamento verrà eseguito in fase di esecuzione nel database SQL.  
29. Chiudere la pagina.
30. Fare clic su OK.
31. Nella struttura espandere 'Totali'.
32. Nella struttura espandere 'TransactionsGroups'.
33. Nella struttura espandere 'TransactionsGroups\aggregated'.
34. Nella struttura selezionare 'TransactionsGroups\aggregated\SumOfAmountMST'.
35. Nella struttura selezionare 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.
36. Fare clic su Associa.
    * In base a questa impostazione, l'origine dati calcolerà la somma dei valori del campo "AmountMST" per ogni gruppo di transazioni. Questo calcolo di aggregazione sarà disponibile come elemento TransactionsGroups.aggregated.TotalAmount.  
37. Nella struttura espandere 'TransactionsGroups'.
38. Nella struttura selezionare 'TransactionsGroups'.
39. Fare clic su Modifica.
40. Fare clic su Modifica gruppo per.
41. Nella struttura espandere "Transazioni".
42. Nella struttura selezionare "Transazioni\Importo fattura(AmountMST)".
43. Fare clic su Aggiungi campo a.
44. Fare clic su Campi di aggregazione.
45. Nell'elenco contrassegnare la riga selezionata.
46. Selezionare "Max" nel campo Metodo.
47. Digitare 'MaxOfAmountMST' nel campo Nome.
48. Fare clic su Salva.
    * Attualmente, l'esecuzione delle origini dati GROUPBY può essere convertita a livello del database SQL con alcune limitazioni. La conversione può essere effettuata per le origini dati di tipo "Elenco record" o per le origini dati rappresentate come espressione utilizzando la funzione FILTER. Può inoltre essere eseguita quando l'unica aggregazione viene configurata per un singolo campo dei record del raggruppamento.  
    * Tenere presente che anche se più di un'aggregazione è stata configurata per il campo AmountMST, il campo "Esecuzione in" indica che il raggruppamento verrà eseguito in fase di esecuzione nel database SQL. Ciò accade perché solo un'aggregazione viene limitata all'elemento del modello dati e verrà utilizzata in fase di esecuzione per estrarre dati dall'origine dati.  
49. Chiudere la pagina.
50. Fare clic su OK.
51. Nella struttura espandere 'TransactionsGroups'.
52. Nella struttura espandere 'TransactionsGroups\aggregated'.
53. Nella struttura selezionare 'TransactionsGroups\aggregated\MaxOfAmountMST'.
54. Nella struttura selezionare 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.
55. Fare clic su Associa.
56. Nella struttura espandere 'TransactionsGroups'.
57. Nella struttura selezionare 'TransactionsGroups'.
58. Fare clic su Modifica.
59. Fare clic su Modifica gruppo per.
    * Tenere presente che il campo "Esecuzione in" indica che il raggruppamento verrà eseguito in fase di esecuzione nel memoria in quanto entrambe le aggregazioni dello stesso campo sono associate agli elementi del modello dati.   
60. Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.
61. Fare clic su Elimina.
62. Fare clic su Sì.
63. Fare clic su Elimina.
64. Fare clic su Sì.
65. Fare clic su Aggiungi campo a.
66. Fare clic su Informazioni da raggruppare.
67. Nella struttura espandere 'Record voce doganale(Intrastat)'.
68. Fare clic su Salva.
    * Tenere presente che il campo "Esecuzione in" indica che il raggruppamento verrà eseguito in fase di esecuzione in memoria anche se non sono presenti aggregazioni definite e l'origine dati selezionata di tipo "Record di tabella" fa riferimento alla stessa tabella "Intrastat". Ciò accade perché l'origine dati contiene alcuni campi calcolati che non possono essere convertiti a livello del database SQL.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]