---
title: Modificare i modelli e i mapping per generare documenti che contengono dati dell'applicazione
description: Questo articolo descrive come progettare le configurazioni di creazione di report per generare un documento elettronico e aggiornare i dati dell'applicazione. (Parte 2 - Generare documenti).
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 797057112e9476389655b870fd729acd33d57e43
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908299"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a>Modificare i modelli e i mapping per generare documenti che contengono dati dell'applicazione

[!include [banner](../../includes/banner.md)]

Per completare i passaggi di questa procedura, è necessario completare la procedura "ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 2: Generare documenti)". 

I passaggi di questa procedura descrivono come progettare le configurazioni ER per generare un documento elettronico e aggiornare i dati dell'applicazione. In questa procedura verranno modificate le configurazioni ER per iniziare a utilizzarle per generare i documenti elettronici e per aggiornare i dati dell'applicazione. Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Tali passaggi possono essere completati mediante il set di dati DEMF.


## <a name="modify-data-model"></a>Modificare il modello dati
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura selezionare "Intrastat (model)".
    * A questo punto verranno estese le modalità di utilizzo del modello dati. Oltre a utilizzarlo come origine dati per generare il report Intrastat, il modello dati verrà utilizzato per raccogliere informazioni dettagliate sul processo di dichiarazione Intrastat. I dettagli verranno utilizzati per aggiornare i dati dell'applicazione.   
3. Fare clic su Progettazione.
4. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
5. Nel campo Nuovo nodo come immettere 'Radice modello'.
6. Nel campo Nome digitare "Per l'aggiornamento dei dati dell'applicazione".
    * Per l'aggiornamento dei dati dell'applicazione  
7. Scegliere Aggiungi.
8. Nella struttura selezionare "For application data update".
    * Il nuovo elemento radice viene aggiunto per specificare il flusso di dati per lo spostamento dei dati dal report Intrastat (utilizzato come origine dati) alle tabelle dell'applicazione (destinazione dell'aggiornamento). Si noti che è necessario utilizzare elementi radice diversi per ottenere i dati registrati nel documento in uscita e per ottenere i dati del documento utilizzato per aggiornare i dati dell'applicazione.   
9. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
10. Nel campo Nome digitare "Intestazione archivio".
    * Intestazione archivio  
11. Nel campo Tipo di articolo selezionare "Elenco di record".
12. Scegliere Aggiungi.
    * Poiché verrà creato un record per ogni report Intrastat generato, è necessario creare un nuovo articolo per il record.  
13. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
14. Nel campo Nome digitare 'Nome file'.
    * Nome file  
15. Nel campo Tipo di articolo selezionare "Stringa".
16. Scegliere Aggiungi.
17. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
18. Nel campo Nome digitare "Numero di righe".
    * Numero di righe  
19. Nel campo Tipo di articolo selezionare "Intero".
20. Scegliere Aggiungi.
    * Aggiungere tale articolo per rappresentare il numero di transazioni Intrastat dichiarate durante il processo di dichiarazione corrente.  
21. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
22. Nel campo Nome digitare "Righe archivio".
    * Righe archivio  
23. Nel campo Tipo di articolo selezionare "Elenco di record".
24. Scegliere Aggiungi.
    * Aggiungere tale articolo per rappresentare l'elenco di transazioni Intrastat dichiarate durante il processo di dichiarazione corrente.  
25. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
26. Nel campo Nome digitare "Importo".
    * Importo  
27. Nel campo Tipo di articolo selezionare "Reale".
28. Scegliere Aggiungi.
29. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
30. Nel campo Nome digitare "ID record voce doganale".
    * ID record voce doganale  
31. Nel campo Tipo di articolo selezionare "Int64".
32. Scegliere Aggiungi.
33. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
34. Nel campo Nome digitare "Numero articolo".
    * Numero articolo  
35. Nel campo Tipo di articolo selezionare "Stringa".
36. Scegliere Aggiungi.
37. Fare clic su Salva.
38. Chiudere la pagina.

## <a name="modify-model-mapping"></a>Modificare il mapping di modello
1. Nella struttura espandere "Intrastat (model)".
2. Nella struttura selezionare "Intrastat (model)\Intrastat (mapping)".
    * Modificare il mapping di modello esistente per iniziare a utilizzarlo per l'aggiornamento dei dati dell'applicazione e per archiviare i dettagli di dichiarazione Intrastat.  
3. Fare clic su Progettazione.
4. Fare clic su Nuovo.
5. Nel campo Nome digitare "Aggiorna archivio".
    * Aggiorna archivio  
6. Nel campo Direzione selezionare "A destinazione".
7. Fare clic su Salva.
    * Questo nuovo mapping specifica il flusso di dati per lo spostamento dei dati (dettagli dichiarazione Intrastat) dal modello dati alle tabelle dell'applicazione (destinazione dell'aggiornamento). Si noti che è necessario utilizzare elementi radice del modello diversi per ottenere i dati dall'applicazione per il processo di dichiarazione e quindi utilizzare i dati dal modello dati per l'aggiornamento dei dati dell'applicazione.   
8. Fare clic su Progettazione.
9. Nella struttura selezionare "Data model\Data model".
    * Aggiungere l'origine dati necessaria. Si tratta del modello dati che contiene i dettagli delle transazioni Intrastat dichiarate che devono essere archiviate.  
10. Fare clic su Aggiungi radice.
11. Nel campo Nome digitare "modello".
    * modello  
12. Nel campo Definizione immettere o selezionare il valore "Per l'aggiornamento dei dati dell'applicazione".
    * Per l'aggiornamento dei dati dell'applicazione  
13. Fare clic su OK.
14. Nella struttura , espandere il "modello".
15. Nella struttura selezionare "Funzioni\Campo calcolato".
16. Nella struttura selezionare "model\Archive header".
17. Scegliere Aggiungi.
    * Poiché si desidera enumerare le transazioni Intrastat dichiarate per l'archiviazione, è necessario aggiungere l'origine dati appropriata.  
18. Nel campo Nome digitare "Righe enumerate".
    * Righe enumerate  
19. Fare clic su Modifica formula.
20. Nella struttura selezionare "List\ENUMERATE".
21. Fare clic su Aggiungi funzione.
22. Nella struttura , espandere il "modello".
23. Nella struttura espandere "model\Archive header".
24. Nella struttura selezionare "model\Archive header\Archive lines".
25. Fare clic su Aggiungi origine dati.
26. Nel campo Formula immettere "ENUMERATE(model.'Archive header'.'Archive lines')".
    * ENUMERATE(model.'Archive header'.'Archive lines')  
27. Fare clic su Salva.
28. Chiudere la pagina.
29. Fare clic su OK.
30. Fare clic su Aggiungi destinazione.
    * Aggiungere le tabelle dell'applicazione come destinazioni necessarie che richiedono che gli aggiornamenti archivino dettagli delle transazioni Intrastat dichiarate.  
31. Nel campo Nome digitare "Archivio".
    * Archivia  
32. Nel campo Nome tabella digitare "IntrastatArchiveGeneral".
    * IntrastatArchiveGeneral  
    * Mantenere l'azione record "Inserisci" in modo da poter aggiungere record durante l'archiviazione dei dettagli di ogni processo di dichiarazione Intrastat.  
33. Selezionare Sì nel campo Registro informazioni record.
    * Selezionare Sì per ottenere informazioni sui problemi relativi all'aggiornamento dei dati dell'applicazione.  
34. Selezionare Sì nel campo Ignora convalida azione record.
    * Selezionare Sì per eliminare gli errori di convalida sul campo "ID archivio Intrastat" vuoto. Questa operazione verrà eseguita dopo l'aggiunta dei record, in base alle impostazioni del numero progressivo configurate per la tabella nel modulo Parametri per il commercio estero.  
35. Fare clic su OK.
    * Associare elementi dell'origine dati aggiunta (il modello filtrato in base all'elemento radice selezionato) con elementi dalla destinazione aggiunta.  
36. Nella struttura espandere "Archive".
37. Nella struttura espandere "Archive\<Relations".
38. Nella struttura espandere "Archive\<Relations\IntrastatArchiveDetail".
39. Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)".
40. Nella struttura espandere "model\Archive header\Enumerated lines".
41. Nella struttura espandere "model\Archive header\Enumerated lines\Value".
42. Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Amount".
43. Fare clic su Associa.
44. Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)".
45. Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Commodity rec id".
46. Fare clic su Associa.
47. Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)".
48. Nella struttura selezionare "model\Archive header\Enumerated lines\Value\Item number".
49. Fare clic su Associa.
50. Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)".
51. Nella struttura selezionare "model\Archive header\Enumerated lines\Number".
52. Fare clic su Associa.
53. Nella struttura selezionare "Archive\<Relations\IntrastatArchiveDetail".
54. Nella struttura selezionare "model\Archive header\Enumerated lines".
55. Fare clic su Associa.
56. Nella struttura selezionare "Archive\File name(FileName)".
57. Nella struttura selezionare "model\Archive header\File name".
58. Fare clic su Associa.
59. Nella struttura selezionare "Archive\Number of lines(NumberOfLines)".
60. Nella struttura selezionare "model\Archive header\Number of lines".
61. Fare clic su Associa.
62. Nella struttura selezionare "Archive".
63. Nella struttura selezionare "model\Archive header".
64. Fare clic su Associa.
65. Fare clic su Salva.
66. Chiudere la pagina.
67. Chiudere la pagina.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]