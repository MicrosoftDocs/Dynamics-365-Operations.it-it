---
title: Creare i formati per utilizzare i file di gestione documenti nell'output di ER
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1815a0004eee6734b3c7d2c2f9e75ce5fe16af1c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "362949"
---
# <a name="create-formats-to-use-document-management-files-in-er-output"></a>Creare i formati per utilizzare i file di gestione documenti nell'output di ER

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici. Questi passaggi possono essere eseguiti in qualsiasi società.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare i file di gestione documenti negli output di formato (parte 2: estendere il modello dati)'.

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="create-a-format-to-process-invoices"></a>Creare un formato per l'elaborazione delle fatture
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Configurazioni report.
3. Nella struttura espandere 'Modello fattura cliente'.
4. Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.
    * Creerete un formato per generare i messaggi elettronici con informazioni su tutti i file che sono stati allegati a un ordine cliente correlato a una fattura elaborata elettronicamente.  
5. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
6. Nel campo Nuovo immettere 'Formato basato sul modello dati Modello fattura cliente (personalizzato)'.
7. Nel campo Nome digitare 'Messaggio di esempio fattura elettronica'.
    * Messaggio di esempio fattura elettronica  
8. Nel campo Definizione modello dati immettere o selezionare un valore.
    * InvoiceCustomer  
9. Fare clic su Crea configurazione.

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>Progettare un formato per popolare gli allegati nella generazione di un messaggio in formato MIME
1. Fare clic su Progettazione.
2. Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.
3. Nella struttura selezionare "XML\Elemento".
4. Digitare 'Fattura' nel campo Nome.
    * Fattura  
5. Fare clic su OK.
6. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
7. Nella struttura selezionare "XML\Attributo".
8. Digitare 'SalesOrder' nel campo Nome.
    * SalesOrder  
9. Fare clic su OK.
10. Fare clic su Aggiungi attributo.
11. Nel campo Nome digitare 'InvoiceNumber'.
    * InvoiceNumber  
12. Fare clic su OK.
13. Fare clic su Aggiungi attributo.
14. Nel campo Nome digitare 'InvoiceAmount'.
    * InvoiceAmount  
15. Fare clic su OK.
16. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
17. Nella struttura selezionare "XML\Elemento".
18. Nel campo Nome digitare 'EnclosedDocs'.
    * EnclosedDocs  
19. Fare clic su OK.
20. Nella struttura selezionare 'Fattura\EnclosedDocs'.
21. Fare clic su Aggiungi elemento.
22. Nel campo Nome digitare 'Documento'.
    * Documento  
23. Fare clic su OK.
24. Nella struttura selezionare 'Fattura\EnclosedDocs\Documento'.
25. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
26. Nella struttura selezionare "XML\Attributo".
27. Nel campo Nome digitare 'FileName'.
    * FileName  
28. Fare clic su OK.
29. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
30. Nella struttura selezionare "XML\Elemento".
31. Digitare 'FileContent' nel campo Nome.
    * FileContent  
32. Fare clic su OK.
33. Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileContent'.
34. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
35. Nella struttura selezionare  'Testo\Base64'.
36. Fare clic su OK.

## <a name="map-format-elements-to-data-model-as-data-source"></a>Mappare gli elementi di formato al modello dati come origine dati
1. Nella struttura selezionare 'Fattura\SalesOrder'.
2. Fare clic sulla scheda Mapping.
3. Nella struttura , espandere il "modello".
4. Nella struttura, selezionare 'modello\Numero ordine cliente(SalesId)'.
5. Fare clic su Associa.
6. Nella struttura selezionare 'Fattura\InvoiceNumber'.
7. Nella struttura espandere 'modello\Fattura base(InvoiceBase)'.
8. Nella struttura selezionare 'modello\Fattura base(InvoiceBase)\Numero fattura(Id)'.
9. Fare clic su Associa.
10. Nella struttura selezionare 'Fattura\InvoiceAmount'.
11. Nella struttura selezionare 'modello\Fattura base(InvoiceBase)\Importo fattura(Amount)'.
12. Fare clic su Associa.
13. Nella struttura espandere 'modello\Allegati fattura'.
14. Nella struttura selezionare 'modello\Allegati fattura\Contenuto file'.
15. Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileContent\Base64'.
16. Fare clic su Associa.
17. Nella struttura selezionare 'modello\Allegati fattura\Nome file'.
18. Nella struttura selezionare 'Fattura\EnclosedDocs\Documento\FileName'.
19. Fare clic su Associa.
20. Nella struttura selezionare 'modello\Allegati fattura'.
21. Nella struttura selezionare 'Fattura\EnclosedDocs\Documento'.
22. Fare clic su Associa.
23. Fare clic su Salva.
24. Chiudere la pagina.

