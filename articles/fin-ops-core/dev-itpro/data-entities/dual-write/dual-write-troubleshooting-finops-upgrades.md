---
title: Risoluzione dei problemi relativi agli aggiornamenti delle app Finance and Operations
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi agli aggiornamenti delle app Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 07d6bd0bab796d7839daa2bad91f7e88c2e881b5
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997920"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a>Risoluzione dei problemi relativi agli aggiornamenti delle app Finance and Operations

[!include [banner](../../includes/banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Common Data Service. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi agli aggiornamenti delle app Finance and Operations.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="database-synchronization-errors"></a>Errori di sincronizzazione del database

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato un messaggio di errore simile al seguente esempio quando si tenta di utilizzare l'entità **DualWriteProjectConfiguration** per aggiornare un'app Finance and Operations al Platform update 30.

```console
Infolog diagnostic message: 'Cannot select a record in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Per risolvere il problema, procedere come segue.

1. Accedere alla macchina virtuale (VM) per l'app Finance and Operations.
2. Aprire Visual Studio come amministratore e aprire Application Object Tree (AOT).
3. Cercare **DualWriteProjectConfiguration**.
4. In AOT, fare clic con il tasto destro su **DualWriteProjectConfiguration** e selezionare **Aggiungi a nuovo progetto**. Selezionare **OK** per creare il nuovo progetto con le opzioni predefinite.
5. In Esplora soluzioni, fare clic con il tasto destro su **Proprietà progetto** e impostare **Sincronizza database su build** su **True**.
6. Compilare il progetto e verificare che la compilazione abbia esito positivo.
7. Nel menu **Dynamics 365** , selezionare **Sincronizza database**.
8. Selezionare **Sincronizza** per eseguire una sincronizzazione completa del database.
9. Una volta che la sincronizzazione completa del database ha esito positivo, rieseguire il passaggio di sincronizzazione del database in Microsoft Dynamics Lifecycle Services (LCS) e utilizzare gli script di aggiornamento manuale come applicabile, in modo da poter procedere con l'aggiornamento.

## <a name="missing-entity-fields-issue-on-maps"></a>Problema di campi di entità mancanti sulle mappe

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

Nella pagina **Doppia scrittura** è possibile che venga visualizzato un messaggio di errore simile al seguente esempio:

*Campo di origine mancante \<field name\> nello schema.*

![Esempio del messaggio di errore del campo di origine mancante](media/error_missing_field.png)

Per risolvere il problema, seguire innanzitutto questi passaggi per assicurarsi che i campi siano nell'entità.

1. Accedere alla macchina virtuale per l'app Finance and Operations.
2. Andare a **Aree di lavoro \> Gestione dei dati** , selezionare il riquadro **Parametri framework** e quindi nella scheda **Impostazioni entità** , selezionare **Aggiorna elenco entità** per aggiornare le entità.
3. Andare a **Aree di lavoro \> Gestione dei dati** , selezionare la scheda **Entità di dati** e assicurarsi che l'entità sia elencata. Se l'entità non è elencata, accedere alla macchina virtuale per l'app Finance and Operations e assicurarsi che l'entità sia disponibile.
4. Aprire la pagina **Mapping di entità** dalla pagina **Doppia scrittura** nell'app Finance and Operations.
5. Selezionare **Aggiorna elenco entità** per completare automaticamente i campi nei mapping delle entità.

Se il problema persiste, attenersi alla seguente procedura.

> [!IMPORTANT]
> Questi passaggi guidano l'utente attraverso il processo di eliminazione di un'entità e quindi l'aggiunta di una nuova. Per evitare problemi, assicurarsi di seguire esattamente i passaggi.

1. Nell'app Finance and Operations, andare a **Aree di lavoro \> Gestione dei dati** e selezionare il riquadro **Entità di dati**.
2. Trovare l'entità in cui manca l'attributo. Fare clic su **Modifica mapping di destinazione** nella barra degli strumenti.
3. Nel riquadro **Mappa gestione temporanea a destinazione** , fare clic si **Genera mapping**.
4. Aprire la pagina **Mapping di entità** dalla pagina **Doppia scrittura** nell'app Finance and Operations.
5. Se l'attributo non viene popolato automaticamente sulla mappa, aggiungerlo manualmente facendo clic sul pulsante **Aggiungi attributo** e quindi su **Salva**. 
6. Selezionare la mappa e fare clic su **Esegui**.
