---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 4: eseguire il report)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9a6f07d6c665097fabab4d3ec6d7fa5ba80b65d
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406476"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER Utilizzare le dimensioni finanziarie come origine dati (Parte 4: eseguire il report)

[!include [banner](../../includes/banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici. Queste operazioni possono essere eseguite nella società DEMF.

Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura "ER Usare dimensioni finanziarie come origine dati (parte 3: progettare il report)". È inoltre necessario configurare i tipi di documento predefiniti nella pagina Parametri per la creazione di report elettronici. I tipi di documento predefiniti vengono impostati anche quando si scarica e importa qualsiasi configurazione ER. 


## <a name="run-report"></a>Eseguire un report
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere 'Modello di esempio dimensioni finanziarie'.
3. Nella struttura selezionare 'Modello di esempio dimensioni finanziarie\Report dei giornali di registrazione di contabilità generale'.
4. Fare clic su Esegui.
![Pagina delle configurazioni ER](../media/er-financial-dimensions-guides-run1.png)
5. Nel campo Nome dimensione immettere o selezionare un valore.
    * Per selezionare tutte le dimensioni della società corrente, immettere le seguenti informazioni: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![Pagina delle configurazioni ER](../media/er-financial-dimensions-guides-run2.png)
6. Espandere la sezione Record da includere.
7. Fare clic su Filtro.
8. Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.
9. Nel campo Criteri digitare '00057'.
10. Fare clic su OK.
11. Fare clic su OK.
![Pagina delle configurazioni ER](../media/er-financial-dimensions-guides-run3.png)
    * Esaminare l'output generato. Per ciascuna transazione del batch selezionato, le dimensioni finanziarie del set di dimensioni corrispondente vengono presentate. Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per questa istanza.  
![Pagina delle configurazioni ER](../media/er-financial-dimensions-guides-run4.png)
