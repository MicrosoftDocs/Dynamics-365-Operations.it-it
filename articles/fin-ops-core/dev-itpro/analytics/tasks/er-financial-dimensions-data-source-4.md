---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 4: eseguire il report)'
description: In questo argomento viene descritto come configurare un modello di Creazione di report elettronici (ER) per utilizzare le dimensioni finanziarie come origine dati per i report ER. (Parte 4)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f14be560ab014224e32169b4ac97682a669249b4
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605307"
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
![Pagina configurazioni ER.](../media/er-financial-dimensions-guides-run1.png)
5. Nel campo Nome dimensione immettere o selezionare un valore.
    * Per selezionare tutte le dimensioni della società corrente, immettere le seguenti informazioni: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![I parametri del rapporto elettronico scorrono verso l'esterno, menu a discesa Nome dimensione.](../media/er-financial-dimensions-guides-run2.png)
6. Espandere la sezione Record da includere.
7. Fare clic su Filtro.
8. Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.
9. Nel campo Criteri digitare '00057'.
10. Fare clic su OK.
11. Fare clic su OK.
![I parametri del rapporto elettronico scorrono verso l'esterno, rapporti includono la sezione.](../media/er-financial-dimensions-guides-run3.png)
    * Esaminare l'output generato. Per ciascuna transazione del batch selezionato, le dimensioni finanziarie del set di dimensioni corrispondente vengono presentate. Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per questa istanza.  
![Le configurazioni ER hanno generato l'output.](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
