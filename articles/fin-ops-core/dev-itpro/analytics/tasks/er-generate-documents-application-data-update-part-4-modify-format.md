---
title: Modificare i formati per generare documenti che contengono dati dell'applicazione
description: Questo argomento descrive come progettare le configurazioni di creazione di report per generare un documento elettronico e aggiornare i dati dell'applicazione.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e820e909bcd80b4747c06ccaaeb05c03f52b6963
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129399"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>Modificare i formati per generare documenti che contengono dati dell'applicazione

[!include [banner](../../includes/banner.md)]

Per completare i passaggi di questa procedura, è necessario completare la procedura "ER Generare documenti con l'aggiornamento dei dati dell'applicazione (Parte 3: Modificare modello e mapping)".

I passaggi di questa procedura descrivono come progettare le configurazioni ER per generare un documento elettronico e aggiornare i dati dell'applicazione. In questa procedura verranno modificate le configurazioni ER non solo per iniziare a utilizzarle per generare i documenti elettronici, ma anche per aggiornare i dati dell'applicazione. Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Tali passaggi possono essere completati mediante il set di dati DEMF.


## <a name="modify-format-to-collect-details-of-reporting"></a>Modificare il formato per raccogliere i dettagli del report
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere "Intrastat (model)".
3. Nella struttura selezionare "Intrastat (model)\Intrastat (format)".
4. Fare clic su Progettazione.
5. Nella struttura espandere "File".
6. Nella struttura espandere "File\Declaration".
7. Nella struttura selezionare "File\Declaration\Data".
8. Nel campo Molteplicità selezionare "Uno molti".
    * Configurare l'elemento di formato per archiviare i dettagli del processo di dichiarazione Intrastat. Questo elemento rappresenta il record di intestazione dell'archivio.  
9. Nella struttura espandere "File\Declaration\Data".
10. Nella struttura selezionare "File\Declaration\Data\Item".
11. Nel campo Molteplicità selezionare "Nessuno molti".
    * Configurare l'elemento di formato per archiviare i dettagli del processo di dichiarazione Intrastat. Questo elemento rappresenterà l'elenco delle righe archiviate.  
12. Nella struttura espandere "File\Declaration\Data\Item".
13. Nella struttura selezionare "File\Declaration\Data\Item\Dim1".
14. Selezionare Sì nel campo Escluso.
    * Tali dati non verranno archiviati, pertanto è possibile escludere l'elemento di formato dall'origine dati dai dettagli della dichiarazione Intrastat.  
15. Nella struttura espandere "File\Declaration\Data\Item\Dim1".
16. Nella struttura selezionare "File\Declaration\Data\Item\Dim1\property".
17. Selezionare Sì nel campo Escluso.
18. Nella struttura selezionare "File\Declaration\Data\Item\Dim1\date".
19. Selezionare Sì nel campo Escluso.
20. Nella struttura selezionare "File\Declaration\Data\Item\Dim2".
21. Selezionare Sì nel campo Escluso.
22. Nella struttura espandere "File\Declaration\Data\Item\Dim2".
23. Nella struttura selezionare "File\Declaration\Data\Item\Dim2\property".
24. Selezionare Sì nel campo Escluso.
25. Nella struttura selezionare "File\Declaration\Data\Item\Dim2\code".
26. Selezionare Sì nel campo Escluso.
27. Nella struttura selezionare "File\Declaration\Data\Item\Dim3".
    * Diversi elementi di formato possono avere lo stesso nome, ad esempio Dim. Non è possibile riconoscerli esplicitamente quando si utilizza il formato come origine dati per l'archiviazione dei dettagli di dichiarazione Intrastat, quindi è necessario definire i nomi alternativi per questi elementi di formato.   
28. Nel campo Nome digitare "Importo".
    * Importo  
29. Nel campo Molteplicità selezionare "Uno e solo uno".
30. Nella struttura selezionare "File\Declaration\Data\Item\Dim4".
31. Nel campo Nome digitare "Articolo".
    * Articolo  
32. Nel campo Molteplicità selezionare "Uno e solo uno".
    * Oltre agli elementi di formato di progettazione, è necessario archiviare i seguenti dettagli di dichiarazione Intrastat: ID record univoco di ogni articolo di voce doganale dichiarato e nome di file generato. Poiché questi dati non verranno inseriti nel report Intrastat, è necessario aggiungere il formato correlato a questi elementi di dettaglio di articoli come origine dati.  
33. Nella struttura selezionare "File\Declaration\Data".
34. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
35. Nella struttura selezionare "Data source\Item".
36. Nel campo Nome digitare 'Nome file'.
    * Nome file  
37. Nel campo Tipo di dati selezionare "Stringa".
38. Fare clic su OK.
39. Nella struttura selezionare "File\Declaration\Data\Item".
40. Fare clic su Aggiungi articolo.
41. Nel campo Nome digitare "ID record voce doganale".
    * ID record voce doganale  
42. Nel campo Tipo di dati selezionare "Int64".
43. Fare clic su OK.
44. Fare clic sulla scheda Mapping.
45. Nella struttura selezionare "File\Declaration\Data\File name".
46. Fare clic su Associa.
47. Nella struttura , espandere il "modello".
48. Nella struttura espandere "model\Transactions".
49. Nella struttura selezionare "File\Declaration\Data\Item = model.Transactions\Commodity rec id".
50. Nella struttura selezionare "model\Transactions\Commodity rec id".
51. Fare clic su Associa.
52. Fare clic su Salva.

## <a name="modify-format-to-memorize-details-of-reporting"></a>Modificare il formato per memorizzare i dettagli del report

1. Fare clic su Mapping formato a modello.
2. Fare clic su Nuovo.
3. Nel campo Definizione immettere o selezionare l'elemento radice "Per l'aggiornamento dei dati dell'applicazione".
    * Per l'aggiornamento dei dati dell'applicazione.
4. Nel campo Nome digitare "Mapping per aggiornare i dati".
    * Mapping per aggiornare i dati  
5. Fare clic su Salva.
    * Questo mapping definisce come i dettagli del report Intrastat vengono raccolti nel modello dati, la cui struttura è specificata dall'elemento radice selezionato "Per l'aggiornamento dei dati dell'applicazione". Tali dettagli, il mapping di modello con lo stesso elemento radice "Per l'aggiornamento dei dati dell'applicazione" e la direzione "A destinazione" verranno utilizzati per l'aggiornamento dei dati dell'applicazione. L'aggiornamento dei dati dell'applicazione inizia immediatamente dopo la generazione del report Intrastat in uscita. L'aggiornamento dei dati dell'applicazione può essere ignorato in fase di esecuzione, ma il modello dati deve essere vuoto (deve contenere un elenco di record vuoto).
6. Fare clic su Progettazione.
    * Il formato di report Intrastat in uscita viene aggiunto per impostazione predefinita come origine dei dati per il mapping di modello.  
    * Associare gli elementi del report progettato (visualizzati come origine dei dati) agli elementi del modello dati, che viene filtrato in base all'elemento radice del modello selezionato.  
7. Nella struttura espandere "Archive header".
8. Nella struttura espandere "Archive header\Archive lines".
9. Nella struttura espandere "format".
10. Nella struttura espandere "format\Declaration: XML Element(Declaration)".
11. Nella struttura espandere "format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)".
12. Nella struttura espandere "format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)".
13. Nella struttura espandere "format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)".
14. Nella struttura espandere "format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)".
15. Nella struttura selezionare "Archive header\Number of lines".
16. Fare clic su Modifica.
17. Nella struttura selezionare "List\COUNT".
18. Fare clic su Aggiungi funzione.
19. Nella struttura espandere "format".
20. Nella struttura espandere "format\Declaration: XML Element(Declaration)".
21. Nella struttura espandere `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`.
22. Nella struttura selezionare `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`.
23. Fare clic su Aggiungi origine dati.
24. Nel campo Formula immettere "COUNT(format.Declaration.Data.Item)".
    * COUNT(format.Declaration.Data.Item)  
25. Fare clic su Salva.
26. Chiudere la pagina.
27. Nella struttura selezionare "Archive header\File name".
28. Nella struttura selezionare "format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\File name: Item String(File name)".
29. Fare clic su Associa.
30. Nella struttura selezionare `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)`.
31. Nella struttura selezionare "Archive header\Archive lines\Item number".
32. Fare clic su Associa.
33. Nella struttura selezionare `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)`.
34. Nella struttura selezionare "Archive header\Archive lines\Amount".
35. Fare clic su Associa.
36. Nella struttura selezionare `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec ID: Item Int64(Commodity rec ID)`.
37. Nella struttura selezionare "Archive header\Archive lines\Commodity rec id".
38. Fare clic su Associa.
39. Nella struttura selezionare "Archive header\Archive lines".
40. Nella struttura selezionare `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`.
41. Fare clic su Associa.
42. Nella struttura selezionare "Archive header".
43. Nella struttura selezionare `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`.
44. Fare clic su Associa.
45. Fare clic su Salva.
46. Chiudere la pagina.
47. Chiudere la pagina.
48. Chiudere la pagina.
