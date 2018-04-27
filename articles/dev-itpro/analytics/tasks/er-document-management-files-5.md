--- 
title: Modificare ed eseguire il formato per utilizzare i file per la gestione dei documenti negli output di formato
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.openlocfilehash: b38f69fc169367aa56468b2c8f06b65fd1291c79
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="modify-and-run-format-to-use-document-management-files-in-format-outputs"></a>Modificare ed eseguire il formato per utilizzare i file per la gestione dei documenti negli output di formato

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici. Queste operazioni possono essere eseguite nella società DEMF.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare i file di gestione documenti negli output di formato (parte 4: eseguire il formato)'.

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>Modificare il formato per popolare gli allegati nella generazione di messaggi in formato binario
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere 'Modello fattura cliente'.
3. Nella struttura espandere 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.
4. Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)\Messaggio di esempio fattura elettronica'.
5. Fare clic su Progettazione.
    * Popolerete il messaggio della fattura nell'output di generazione come file XML tramite codifica UNICODE.  
6. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
7. Nella struttura selezionare "Comune\File".
8. Nel campo Nome digitare 'Messaggio Xml'.
    * Messaggio Xml  
9. Nel campo Codifica digitare "UTF-8".
    * UTF-8  
10. Fare clic su OK.
    * Configurare l'output di generazione come file compresso.  
11. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
12. Nella struttura selezionare 'Comune\Cartella'.
13. Nel campo Nome digitare 'Output ZIP'.
    * Output ZIP  
14. Fare clic su OK.
15. Nella struttura selezionare 'Output ZIP'.
    * Aggiungere allegati al file compresso di generazione come file con i nomi e le estensioni originali.  
16. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
17. Nella struttura selezionare "Comune\File".
18. Digitare 'File allegato' nel campo Nome.
    * File allegato  
19. Fare clic su OK.
20. Nella struttura selezionare 'Output ZIP\File allegato'.
21. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
22. Nella struttura selezionare  'Testo\Base64'.
23. Fare clic su OK.

## <a name="map-new-format-elements-to-data-model"></a>Mappare gli elementi del nuovo formato al modello dati
1. Fare clic sulla scheda Mapping.
2. Nella struttura , espandere il "modello".
3. Nella struttura espandere 'modello\Allegati fattura'.
4. Nella struttura selezionare 'Output ZIP\File allegato\Base64'.
5. Nella struttura selezionare 'modello\Allegati fattura\Contenuto file'.
6. Fare clic su Associa.
7. Nella struttura selezionare 'Output ZIP\File allegato'.
8. Fare clic su Modifica nome del file.
9. Nella struttura , espandere il "modello".
10. Nella struttura espandere 'modello\Allegati fattura'.
11. Nella struttura selezionare 'modello\Allegati fattura\Nome file'.
12. Fare clic su Aggiungi origine dati.
13. Fare clic su Salva.
14. Chiudere la pagina.
15. Nella struttura selezionare 'modello\Allegati fattura'.
16. Fare clic su Associa.
17. Fare clic su Salva.
18. Chiudere la pagina.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Eseguire il report progettato per la fattura selezionata
1. Fare clic su Esegui.
2. Espandere la sezione Record da includere ().
3. Fare clic su Filtro.
4. Selezionare la riga del giornale di registrazione fatture cliente e il campo Ordine cliente.
5. Nel campo Criterim nel campo "Ordine cliente" di criteri, digitare il numero di ordine 000148.
    * 000148  
6. Fare clic su OK.
7. Fare clic su OK.
    * Esaminare l'output generato. Si noti che, oltre al messaggio della fattura in formato XML, un singolo file è stato creato per ciascun allegato. I file degli allegati vengono popolati con l'output compresso in formato binario.  


