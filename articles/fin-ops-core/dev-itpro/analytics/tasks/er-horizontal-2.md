---
title: 'ER Utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel (Parte 2: eseguire il formato)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: ec81aba054718452dac3c10253dcd87091414fb5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182280"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2-run-format"></a>ER utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel (parte 2: eseguire il formato)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la generazione di report come file di fogli di lavoro (Excel) OPENXML in cui le colonne richieste possono essere create in modo dinamico come intervalli espandibili orizzontalmente. Queste operazioni possono essere eseguite nella società DEMF.

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura 'ER Usare intervalli espandibili orizzontalmente per aggiungere colonne in modo dinamico in report di Excel (parte 1: progettare il formato)'.

Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.


## <a name="find-created-format"></a>Trovare il formato creato
1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
2. Nella struttura espandere 'Modello di esempio dimensioni finanziarie'.
3. Nella struttura selezionare 'Modello di esempio dimensioni finanziarie\Report di esempio con intervalli espandibili orizzontalmente'.

## <a name="execute-format-to-create-excel-output"></a>Eseguire il formato per creare l'output di Excel
1. Fare clic su Esegui.
2. Nel campo Nome dimensione, digitare 'BusinessUnit;CostCenter;Department'.
    * Nel campo Nome dimensione immettere o selezionare un valore.  Per selezionare tutte le dimensioni della società corrente, immettere quanto segue: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
3. Espandere la sezione Record da includere.
4. Fare clic su Filtro.
5. Selezionare la riga relativa alla tabella Giornale di registrazione contabile e il campo Numero batch giornale di registrazione.
6. Nel campo Criteri digitare '00057..00058'.
    * 00057..00058  
7. Fare clic su OK.
8. Fare clic su OK.
    * Esaminare l'output generato. Si noti che il file di Excel appena creato contiene lo stesso numero di colonne selezionate per le dimensioni finanziarie. L'intestazione del report nelle colonne rappresenta i nomi delle dimensioni finanziarie. Le righe delle transazioni nelle colonne rappresentano le dimensioni finanziarie. Eseguire questo report e selezionare dimensioni diverse per vedere che il report non dipende dal numero di dimensioni selezionate o dal numero di dimensioni configurate per questa istanza.  

