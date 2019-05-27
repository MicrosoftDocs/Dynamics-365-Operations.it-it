---
title: 'ER Usare file di gestione documenti in output di formato (Parte 2: Estendere il modello dati)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb4c58dc86a159a70634c05408a8db471ebcae4c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544809"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2-extend-data-model"></a>ER Usare file di gestione documenti in output di formato (parte 2: estendere il modello dati)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che utilizzi i file (allegati) di gestione documenti nell'output della creazione di report elettronici. Questi passaggi possono essere eseguiti in qualsiasi società.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della guida attività 'ER Usare i file di gestione documenti negli output di formato (parte 1: preparare il modello dati)'.

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>Estendere il modello dati per presentare i file di gestione documenti al suo interno
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Fare clic su Configurazioni report.
3. Nella struttura espandere 'Modello fattura cliente'.
4. Nella struttura selezionare 'Modello fattura cliente\Modello fattura cliente (personalizzato)'.
5. Fare clic su Progettazione.
6. Nella struttura selezionare 'Fattura cliente(InvoiceCustomer)'.
    * Estenderemo questo modello dati per esporvi qualsiasi file allegato a un ordine cliente correlato a una fattura elaborata elettronicamente.  
7. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
8. Nel campo Nome digitare 'Allegati fattura'.
    * Allegati fattura  
9. Nel campo Tipo di articolo selezionare "Elenco di record".
10. Scegliere Aggiungi.
11. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
12. Digitare 'Contenuto file' nel campo Nome.
    * Contenuto file  
13. Nel campo Tipo di articolo selezionare 'Contenitore'.
14. Scegliere Aggiungi.
15. Fare clic su Nuovo per aprire la finestra di dialogo a discesa.
16. Nel campo Nome digitare 'Nome file'.
    * Nome file  
17. Nel campo Tipo di articolo selezionare "Stringa".
18. Scegliere Aggiungi.

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a>Mappare gli elementi del nuovo modello dati alle origini dati di Dynamics 365 for Finance and Operations, edizione Enterprise
1. Fare clic su Mappa modello a origine dati.
2. Utilizzare il filtro rapido per filtrare in base al campo Definizione con un valore di 'InvoiceCustomer'.
    * InvoiceCustomer  
    * Mapperemo gli elementi del nuovo modello alle origini dati appropriate.  
3. Fare clic su Progettazione.
4. Nella struttura selezionare 'Allegati fattura'.
5. Nella struttura espandere 'Allegati fattura'.
6. Nella struttura selezionare 'Allegati fattura\Nome file'.
7. Fare clic su Modifica.
8. Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'  
9. Fare clic su Salva.
10. Chiudere la pagina.
11. Nella struttura selezionare 'Allegati fattura\Contenuto file'.
12. Fare clic su Modifica.
13. Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'  
14. Fare clic su Salva.
15. Chiudere la pagina.
16. Nella struttura selezionare 'Allegati fattura'.
17. Fare clic su Modifica.
18. Nel campo Formula immettere 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'  
19. Fare clic su Salva.
20. Chiudere la pagina.
21. Fare clic su Salva.
22. Chiudere la pagina.
23. Chiudere la pagina.
24. Chiudere la pagina.
25. Fare clic su Cambia stato.
26. Fare clic su Completa.
27. Fare clic su OK.

