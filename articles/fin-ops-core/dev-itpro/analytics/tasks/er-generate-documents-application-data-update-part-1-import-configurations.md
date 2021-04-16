---
title: Importare le configurazioni per generare documenti che contengono dati dell'applicazione
description: Per completare i passaggi in questa procedura, è necessario prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".
author: NickSelin
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 96f636b19f9babc9a7893c12233d67fb2f044638
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751108"
---
# <a name="import-configurations-to-generate-documents-that-have-application-data"></a>Importare le configurazioni per generare documenti che contengono dati dell'applicazione

[!include [banner](../../includes/banner.md)]

Per completare i passaggi in questa procedura, è necessario prima completare i passaggi della procedura "ER Creare un provider di configurazione e contrassegnarlo come attivo".

I passaggi di questa procedura descrivono come progettare le configurazioni ER per generare un documento elettronico. In questa procedura, le configurazioni ER necessarie create per la società di esempio Litware, Inc. saranno importate e utilizzate per generare documenti elettronici. Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Tali passaggi possono essere completati mediante il set di dati DEMF. Prima di iniziare, scarichiate e salvare i file elencati nell'argomento della Guida "Generare documenti elettronici e aggiornare i dati dell'applicazione mediante lo strumento di creazione di report elettronici" (generate-electronic-documents-update-application-data/). I file sono Intrastat (model).xml, Intrastat (mapping).xml e Intrastat (format).xml.

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".  
    * I passaggi di questa procedura descrivono come utilizzare le funzionalità ER per completare un aggiornamento dei dati dell'applicazione e come generare un report Intrastat. I dettagli del processo di creazione del report vengono archiviati nelle tabelle dell'applicazione. Attualmente, quando il processo di dichiarazione Intrastat viene attivato dal modulo Intrastat, l'archiviazione viene eseguita in base alla logica programmata nel codice sorgente esistente. In questa procedura verrà configurata una logica simile, ma semplificata, dei dati dell'applicazione utilizzando solo il framework ER. Al codice sorgente non verrà apportata alcuna modifica.   

## <a name="import-er-configurations"></a>Importare configurazioni ER
1. Fare clic su Configurazioni report.
2. Fare clic su Scambia.
3. Fare clic su Carica da file XML.
    * Viene importata la configurazione del modello ER contenente un modello dati progettato per essere utilizzato come origine dati per la generazione del report Intrastat. Successivamente, estendere la definizione di modello dati per utilizzarla per l'aggiornamento dei dati dell'applicazione per archiviare dettagli del processo di dichiarazione Intrastat.   
    * Fare clic su Sfoglia e selezionare il file Intrastat (model).xml.  
4. Fare clic su OK.
5. Nella struttura selezionare "Intrastat (model)".
6. Fare clic su Progettazione.
7. Nella struttura espandere "For outgoing document".
8. Nella struttura espandere "For outgoing document\Transactions".
    * Verificare la struttura del modello dati importato. Si noti che l'elemento radice relativo al "documento in uscita" è definito per specificare il flusso di dati per ottenere i dati dall'applicazione e viene utilizzato come origine dati per generare il report Intrastat. L'elemento "Transazioni (elenco record)" consente di rappresentare l'elenco delle transazioni Intrastat che devono essere dichiarate. Poiché verranno archiviati i codici di voce doganale, nel flusso di dati è necessario l'identificatore univoco di un unico codice di voce doganale "ID record voce doganale (Int64)".   
9. Chiudere la pagina.
10. Fare clic su Scambia.
11. Fare clic su Carica da file XML.
    * Importare la configurazione di mapping ER che specifica il flusso di dati per ottenere i dati dall'applicazione e quindi utilizzarli per generare il report Intrastat. Successivamente, estendere la definizione di mapping di modello per ottenere i dati dal report Intrastat e utilizzarla per l'aggiornamento dei dati dell'applicazione per archiviare dettagli del processo di dichiarazione Intrastat.   
    * Fare clic su Sfoglia e selezionare il file Intrastat (mapping).xml.  
12. Fare clic su OK.
13. Nella struttura espandere "Intrastat (model)".
14. Nella struttura selezionare "Intrastat (model)\Intrastat (mapping)".
15. Fare clic su Progettazione.
    * Si noti che il mapping corrente del modello contiene il valore "A modello" nel campo Direzione. Ciò significa che il mapping di modello è stato progettato per ottenere i dati dall'applicazione e archiviarli nel modello dati.  
16. Fare clic su Progettazione.
17. Nella struttura espandere "List".
18. Nella struttura espandere "Transactions= List".
    * Verificare la struttura del mapping di modello che utilizza il modello dati che viene filtrato in base all'elemento radice relativo al "documento in uscita". Si noti che l'origine dati aggiunta "Elenco" consente di accedere ai dati dell'applicazione richiesti, ovvero all'elenco dei record della tabella Intrastat.  
19. Chiudere la pagina.
20. Chiudere la pagina.
21. Fare clic su Scambia.
22. Fare clic su Carica da file XML.
    * Importare la configurazione del formato ER che specifica il layout del report Intrastat e il processo di popolamento dei dati nel report. Successivamente, estendere la definizione del formato per inserire i dati dal report Intrastat nel modello dati e per utilizzarli per l'aggiornamento dei dati dell'applicazione per archiviare i dettagli del processo di dichiarazione Intrastat.   
    * Fare clic su Sfoglia e selezionare il file Intrastat (format).xml.  
23. Fare clic su OK.
24. Nella struttura selezionare "Intrastat (model)\Intrastat (format)".
25. Fare clic su Progettazione.
26. Fare clic su Espandi/Comprimi.
27. Nella struttura selezionare "File\Declaration".
28. Fare clic sulla scheda Mapping.
29. Nella struttura selezionare "File".
    * Verificare la struttura del formato utilizzato per generare il report Intrastat. Si noti che è progettata per generare un file XML popolando i dati dal modello dati, basato sull'elemento radice relativo al "documento in uscita". Verificare che il nome del file generato sia definito nel modulo di dialogo utente (viene utilizzata l'origine dati "fn").   
30. Chiudere la pagina.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]