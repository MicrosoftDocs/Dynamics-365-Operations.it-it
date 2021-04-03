---
title: Risoluzione dei problemi relativi agli aggiornamenti delle app Finance and Operations
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi agli aggiornamenti delle app Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ae54ffc9f7a97793dfaddc29f5aae66e5b06c931
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561204"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>Risoluzione dei problemi relativi agli aggiornamenti delle app Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi agli aggiornamenti delle app Finance and Operations.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="database-synchronization-errors"></a>Errori di sincronizzazione del database

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato un messaggio di errore simile al seguente esempio quando si tenta di utilizzare la tabella **DualWriteProjectConfiguration** per aggiornare un'app Finance and Operations al Platform update 30.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
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
7. Nel menu **Dynamics 365**, selezionare **Sincronizza database**.
8. Selezionare **Sincronizza** per eseguire una sincronizzazione completa del database.
9. Una volta che la sincronizzazione completa del database ha esito positivo, rieseguire il passaggio di sincronizzazione del database in Microsoft Dynamics Lifecycle Services (LCS) e utilizzare gli script di aggiornamento manuale come applicabile, in modo da poter procedere con l'aggiornamento.

## <a name="missing-table-columns-issue-on-maps"></a>Problema di colonne di tabella mancanti sulle mappe

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

Nella pagina **Doppia scrittura** è possibile che venga visualizzato un messaggio di errore simile al seguente esempio:

*Campo di origine mancante \<field name\> nello schema.*

![Esempio del messaggio di errore della colonna di origine mancante](media/error_missing_field.png)

Per risolvere il problema, seguire innanzitutto questi passaggi per assicurarsi che le colonne siano nella tabella.

1. Accedere alla macchina virtuale per l'app Finance and Operations.
2. Andare a **Aree di lavoro \> Gestione dei dati**, selezionare il riquadro **Parametri framework** e quindi nella scheda **Impostazioni tabella**, selezionare **Aggiorna elenco tabelle** per aggiornare le tabelle.
3. Andare a **Aree di lavoro \> Gestione dei dati**, selezionare la scheda **Tabelle dati** e assicurarsi che la tabella sia elencata. Se la tabella non è elencata, accedere alla macchina virtuale per l'app Finance and Operations e assicurarsi che la tabella sia disponibile.
4. Aprire la pagina **Mapping della tabella** dalla pagina **Doppia scrittura** nell'app Finance and Operations.
5. Selezionare **Aggiorna elenco tabelle** per completare automaticamente le colonne nei mapping della tabella.

Se il problema persiste, attenersi alla seguente procedura.

> [!IMPORTANT]
> Questi passaggi guidano l'utente attraverso il processo di eliminazione di una tabella e quindi l'aggiunta di una nuova. Per evitare problemi, assicurarsi di seguire esattamente i passaggi.

1. Nell'app Finance and Operations, andare a **Aree di lavoro \> Gestione dei dati** e selezionare il riquadro **Tabelle dati**.
2. Trovare la tabella in cui manca l'attributo. Fare clic su **Modifica mapping di destinazione** nella barra degli strumenti.
3. Nel riquadro **Mappa gestione temporanea a destinazione**, fare clic si **Genera mapping**.
4. Aprire la pagina **Mapping della tabella** dalla pagina **Doppia scrittura** nell'app Finance and Operations.
5. Se l'attributo non viene popolato automaticamente sulla mappa, aggiungerlo manualmente facendo clic sul pulsante **Aggiungi attributo** e quindi su **Salva**. 
6. Selezionare la mappa e fare clic su **Esegui**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]