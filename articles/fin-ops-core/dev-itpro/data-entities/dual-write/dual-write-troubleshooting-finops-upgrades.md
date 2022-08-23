---
title: Risoluzione dei problemi degli aggiornamenti delle app per la finanza e le operazioni
description: Questo articolo fornisce informazioni che possono aiutarti a risolvere i problemi relativi agli aggiornamenti delle app per la finanza e le operazioni.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 7ab75c3a7b6c53982a32658f376a9fd148c023e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289546"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>Risoluzione dei problemi degli aggiornamenti delle app per la finanza e le operazioni

[!include [banner](../../includes/banner.md)]





In questo articolo vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app per la finanza e le operazioni e Dataverse. In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi agli aggiornamenti delle app per la finanza e le operazioni.

> [!IMPORTANT]
> Alcuni problemi che questo articolo tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="database-synchronization-errors"></a>Errori di sincronizzazione del database

**Ruolo richiesto per risolvere il problema:** amministratore di sistema

È possibile che venga visualizzato un messaggio di errore simile al seguente esempio quando si tenta di utilizzare la tabella **DualWriteProjectConfiguration** per aggiornare un'app per la finanza e le operazioni al Platform update 30.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Per risolvere il problema, procedere come segue.

1. Accedere alla macchina virtuale (VM) per l'app per la finanza e le operazioni.
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

![Esempio del messaggio di errore della colonna di origine mancante.](media/error_missing_field.png)

Per risolvere il problema, seguire innanzitutto questi passaggi per assicurarsi che le colonne siano nella tabella.

1. Accedere alla macchina virtuale (VM) per l'app per la finanza e le operazioni.
2. Andare a **Aree di lavoro \> Gestione dei dati**, selezionare il riquadro **Parametri framework** e quindi nella scheda **Impostazioni tabella**, selezionare **Aggiorna elenco tabelle** per aggiornare le tabelle.
3. Andare a **Aree di lavoro \> Gestione dei dati**, selezionare la scheda **Tabelle dati** e assicurarsi che la tabella sia elencata. Se la tabella non è elencata, accedere alla macchina virtuale per l'app per la finanza e le operazioni e assicurarsi che la tabella sia disponibile.
4. Aprire la pagina **Mapping della tabella** dalla pagina **Doppia scrittura** nell'app per la finanza e le operazioni.
5. Selezionare **Aggiorna elenco tabelle** per completare automaticamente le colonne nei mapping della tabella.

Se il problema persiste, attenersi alla seguente procedura.

> [!IMPORTANT]
> Questi passaggi guidano l'utente attraverso il processo di eliminazione di una tabella e quindi l'aggiunta di una nuova. Per evitare problemi, assicurarsi di seguire esattamente i passaggi.

1. Nell'app per la finanza e le operazioni, andare a **Aree di lavoro \> Gestione dei dati** e selezionare il riquadro **Tabelle dati**.
2. Trovare la tabella in cui manca l'attributo. Fare clic su **Modifica mapping di destinazione** nella barra degli strumenti.
3. Nel riquadro **Mappa gestione temporanea a destinazione**, fare clic si **Genera mapping**.
4. Aprire la pagina **Mapping della tabella** dalla pagina **Doppia scrittura** nell'app per la finanza e le operazioni.
5. Se l'attributo non viene popolato automaticamente sulla mappa, aggiungerlo manualmente facendo clic sul pulsante **Aggiungi attributo** e quindi su **Salva**. 
6. Selezionare la mappa e fare clic su **Esegui**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
