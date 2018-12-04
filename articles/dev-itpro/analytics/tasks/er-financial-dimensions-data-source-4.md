--- 
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 4: eseguire il report)'
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 917eae141bbb8792f02d3323054e2a4096dae551
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4-run-the-report"></a>ER utilizzare le dimensioni finanziarie come origine dati (parte 4: eseguire il report)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici. Queste operazioni possono essere eseguite nella società DEMF.

Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura 'ER Usare dimensioni finanziarie come origine dati (parte 3: progettare il report)'. È inoltre necessario configurare i tipi di documento predefiniti nella pagina Parametri per la creazione di report elettronici. I tipi di documento predefiniti vengono impostati anche quando si scarica e importa qualsiasi configurazione ER. 


## <a name="run-report"></a>Eseguire un report
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere 'Modello di esempio dimensioni finanziarie'.
3. Nella struttura selezionare 'Modello di esempio dimensioni finanziarie\Report dei giornali di registrazione di contabilità generale'.
4. Fare clic su Esegui.
5. Nel campo Nome dimensione, immettere o selezionare un valore.
    * Per selezionare tutte le dimensioni della società corrente, immettere quanto segue: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
6. Espandere la sezione Record da includere.
7. Fare clic su Filtro.
8. Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.
9. Nel campo Criteri digitare '00057'.
10. Fare clic su OK.
11. Fare clic su OK.
    * Esaminare l'output generato. Tenere presente che per ciascuna transazione del batch selezionato, le dimensioni finanziarie del set di dimensioni corrispondente vengono presentate. Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per l'istanza di Dynamics 365 for Finance and Operations, Enterprise edition.  


