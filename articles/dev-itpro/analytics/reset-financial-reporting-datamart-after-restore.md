---
title: Reimpostare il data mart dei report finanziari
description: Questo argomento descrive come reimpostare il data mart dei report finanziari.
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: it-it
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a>Reimpostare il data mart dei report finanziari

[!include[banner](../includes/banner.md)]

In questo argomento viene descritto come reimpostare il data mart dei report finanziari per le versioni seguenti:

- Creazione di report finanziari di Microsoft Dynamics 365 for Finance and Operations versione 7.2.6.0 e successiva
- Creazione di report finanziari di Microsoft Dynamics 365 for Finance and Operations versione 7.0.10000.4 e successiva
- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (locale)

Per ottenere Creazione di report finanziari di Finance and Operations versione 7.2.6.0, è possibile scaricare KB 4052514 da <https://support.microsoft.com/it-it/help/4052514>.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a>Reimpostare il data mart di report finanziari per Creazione report finanziari di Finance and Operations versione 7.2.6.0 e successiva

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a>Reimpostare il data mart di report finanziari da Progettazione report

> [!NOTE]
> I passaggi in questo processo sono supportati per Creazione report finanziari di Finance and Operations versione 7.2.6.0 e successive. Se si dispone di una versione precedente, contattare il team di Supporto per assistenza.

In scenari specifici, potrebbe essere necessario reimpostare il data mart per i report finanziari. È possibile completare questa attività nel client di Progettazione report. Di seguito sono descritti alcuni scenari in cui potrebbe essere necessario reimpostare il data mart:

- Il database di Finance and Operations è stato ripristinato, ma non è stato ripristinato il database data mart.
- Si vedono dati errati per un periodo.
- Il Supporto consiglia di reimpostare il data mart come parte di un passaggio della risoluzione dei problemi.

La reimpostazione del data mart deve essere eseguita solo nei periodi in cui la quantità di elaborazione è ridotta. La funzionalità di creazione di report finanziari non è disponibile durante il processo di reimpostazione.

#### <a name="reset-the-data-mart"></a>Reimpostare il data mart

Per reimpostare il data mart, in Progettazione report, nel menu **Strumenti** selezionare **Reimposta data mart**. La finestra di dialogo che viene visualizzata contiene due sezioni: **Statistiche** e **Reimpostazione**.

[![Reimpostare la finestra di dialogo Data mart](./media/Statistics.png)](./media/Statistics.png)

##### <a name="integration-attempts"></a>Tentativi di integrazione

La griglia **Tentativi di integrazione** visualizza il numero di volte che il sistema è tentato di integrare le transazioni. Il sistema continua a provare a integrare dati nell'arco di giorni se i primissimi tentativi non hanno esito positivo. Il data mart deve essere reimpostato se il numero di tentativo è pari a 8 o superiore e se vi sono molte combinazioni di dimensioni o record di transazioni. In questo caso, i dati non vengono inseriti nel report.

##### <a name="data-status"></a>Stato dati

La griglia **Stato dati** include uno snapshot delle transazioni, i tassi di cambio e valori di dimensione nel data mart. La presenza di un numero elevato di record non aggiornati indica che sono stati eseguiti numerosi aggiornamenti ai record. Questa situazione può allungare i tempi di generazione dei report.

##### <a name="misaligned-main-account-categories"></a>Categorie di conti principali non allineate

Se si utilizza una versione precedente a Creazione report finanziari di Microsoft Dynamics 365 for Finance and Operations versione 7.2.1, potrebbe essere necessario reimpostare il data mart se si rinominano i conti e li si sposta tra categorie di conti. Queste azioni possono determinare il disallineamento delle categorie di conti principali. Il campo **Categorie di conti principali non allineate** mostra se è presente questo problema.

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a>Reimpostare il data mart in Creazione report finanziari di Finance and Operations versione 7.2.6.0

Per reimpostare il data mart in Creazione report finanziari di Finance and Operations versione 7.2.6.0 e versioni precedenti, nella finestra di dialogo **Reimposta data mart** selezionare la casella di controllo **Reimposta data mart** e quindi selezionare **OK**. È consigliabile reimpostare il data mart solo durante il periodo di inattività programmata.

[![Casella di controllo Reimposta data mart](./media/Reset-72.jpg)](./media/Reset-72.jpg)

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a>Reimpostare il data mart e selezionare un motivo in Creazione report finanziari di Microsoft Dynamics 365 for Finance and Operations versione 7.3.0

Se si determina che è necessario reimpostare il data mart, selezionare la casella di controllo **Reimposta data mart** e quindi selezionare un motivo nel campo **Motivo**. Sono disponibili le opzioni seguenti:

- **Dati mancanti o non corretti** - In base alle statistiche è stato determinato che potrebbero mancare dei dati. Prima di continuare, si consiglia di collaborare con il Supporto per determinare la causa radice.
- **Ripristina database** - Il database di Finance and Operations è stato ripristinato, ma non è stato ripristinato il database data mart.
- **Altro** - Si reimposta il data mart per un altro motivo. Se si teme che vi sia un problema, contattare il Supporto per identificarlo.

> [!NOTE]
> Verificare che tutte le attività esistenti hanno finito l'integrazione prima completare i passaggi. È possibile visualizzare lo stato dell'integrazione selezionando **Strumenti** &gt;. **Stato integrazione**.

#### <a name="clear-users-and-companies"></a>Cancella utenti e società

Selezionare la casella di controllo **Cancella utenti e società** se è stato ripristinato il database, ma successivamente sono state apportate modifiche agli utenti o alle società. Raramente si dovrebbe selezionare questa casella di controllo.

Quando si è pronti per avviare il processo di reimpostazione, selezionare **OK**. Verrà richiesto di confermare che si è pronti ad avviare il processo. Tenere presente che Creazione report finanziari non sarà disponibile durante la reimpostazione e l'integrazione dei dati iniziali che avviene in un momento successivo.

Se si desidera esaminare lo stato dell'integrazione, selezionare **Strumenti** &gt; **Stato integrazione** per vedere l'ultima volta che è stata eseguita l'integrazione e lo stato.

[![Visualizzare lo stato dell'integrazione](./media/Integration.png)](./media/Integration.png)

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a>Reimpostare il data mart di report finanziari per Creazione report finanziari di Finance and Operations versione 7.0.10000.4 e successiva

Se si ripristina il database di Finance and Operations da un backup o si copia il database da un altro ambiente, è necessario completare i passaggi in questa sezione per assicurarsi che il data mart dei report finanziari utilizzi correttamente il database di Finance and Operations ripristinato.

> [!NOTE]
> I passaggi in questo processo sono supportati per l'applicazione Microsoft Dynamics AX versione 7.0.1 (maggio 2016) (build applicazione 7.0.1265.23014 e build Creazione report finanziari 7.0.10000.4) e successive. Se si dispone di una versione precedente di Finance and Operations, contattare il team del Supporto per assistenza.

### <a name="export-report-definitions"></a>Esportare definizioni di report

Innanzitutto, attenersi alla procedura seguente per esportare i progetti di report da Progettazione report.

1. In Progettazione report, selezionare **Società** &gt; **Gruppi di blocchi predefiniti**.
2. Selezionare il gruppo di blocchi predefiniti da esportare, quindi selezionare **Esporta**.

    > [!NOTE]
    > Per Finance and Operations, è supportato un solo gruppo di blocchi predefiniti, **Predefinito**.

3. Selezionare le definizioni di report da esportare:

    - Per esportare tutte le definizioni di report e i blocchi predefiniti associati, selezionare **Seleziona tutto**.
    - Per esportare specifici report, righe, colonne, alberi o set di dimensioni, selezionare la scheda appropriata e selezionare gli elementi da esportare. Per selezionare più elementi in una scheda, tenere premuto CTRL. Quando si selezionano i report da esportare, vengono selezionate le righe, le colonne, gli alberi e i set di dimensioni associati.

4. Selezionare **Esporta**.
5. Immettere un nome di file e selezionare un percorso protetto in cui si desidera salvare le definizioni di report esportate.
6. Selezionare **Salva**.

È possibile copiare o caricare il file in un percorso protetto. In questo modo, il file può essere importato in un ambiente diverso in un secondo momento. Per informazioni su come utilizzare un account di archiviazione di Microsoft Azure, vedere [Trasferire dati con l'utilità della riga di comando AzCopy](/azure/storage/storage-use-azcopy).

> [!NOTE]
> Microsoft non fornisce un account di archiviazione nel contratto di Finance and Operations. È necessario richiedere un account di archiviazione o impostarne uno da una sottoscrizione Azure separata.

> [!WARNING]
> Tenere presente il comportamento dell'unità D nelle macchine virtuali di Azure. Non archiviare in modo permanente i gruppi esportati di blocchi predefiniti nell'unità D. Per ulteriori informazioni sulle unità temporanee, vedere [Comprensione dell'unità temporanea in Macchine virtuali di Microsoft Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

### <a name="stop-services"></a>Interrompere i servizi

I seguenti servizi di Microsoft Windows hanno connessioni aperte al database di Finance and Operations. È pertanto necessario utilizzare Desktop remoto per collegarsi a tutti i computer nell'ambiente e quindi utilizzare services.msc per arrestare questi servizi.

- Servizio di pubblicazione World Wide Web (in tutti i computer Application Object Servers [AOS])
- Servizio di gestione dei batch di Microsoft Dynamics 365 for Finance and Operations (solo in computer AOS non privati)
- Servizio del processo Management Reporter 2012 (solo nei computer Business intelligence [BI])

### <a name="reset"></a>Reimpostazione

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a>Scaricare il pacchetto MinorVersionDataUpgrade.zip più recente

Scaricare il pacchetto MinorVersionDataUpgrade.zip più recente. Per istruzioni su come trovare e scaricare la versione corretta del pacchetto di aggiornamento dei dati, vedere [Scaricare il pacchetto distribuibile di aggiornamento dei dati più recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). Non è necessario eseguire un aggiornamento per scaricare il pacchetto MinorVersionDataUpgrade.zip. Di conseguenza, è sufficiente seguire i passaggi descritti nella sezione "Scaricare il pacchetto distribuibile di aggiornamento dei dati più recente" di questo argomento. È possibile ignorare tutti gli altri passaggi descritti nell'argomento.

#### <a name="run-scripts-against-the-finance-and-operations-database"></a>Eseguire gli script sul database di Finance and Operations

Eseguire i seguenti script sul database di Finance and Operations (non sul database dei report finanziari):

- DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
- DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Questi script garantiscono la correttezza degli utenti, dei ruoli e delle impostazioni di rilevamento delle modifiche.

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a>Eseguire un comando di Windows PowerShell per ripristinare il database

Nel computer AOS, avviare Microsoft Windows PowerShell come amministratore ed eseguire i comandi seguenti per reimpostare l'integrazione tra Finance and Operations e Creazione report finanziari.

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

Ecco la descrizione dei parametri del comando **Reset-DatamartIntegration**:

- I valori validi per **-Reason** sono **SERVICING**, **BADDATA** e **OTHER**.
- Il parametro **-ReasonDetail** è testo libero.
- Il motivo e il dettaglio del motivo vengono registrati nel monitoraggio dell'ambiente/telemetria.

> [!NOTE]
> Dopo avere eseguito i comandi, viene chiesto di immettere **S** per confermare che si desidera reimpostare il database.

#### <a name="restart-services"></a>Avviare i servizi

Utilizzare services.msc per riavviare i servizi interrotti in precedenza:

- Servizio di pubblicazione World Wide Web (in tutti i computer AOS)
- Servizio di gestione dei batch di Microsoft Dynamics 365 for Finance and Operations (solo in computer AOS non privati)
- Servizio dei processi dello strumento di creazione report di gestione 2012 (solo in computer BI)

#### <a name="import-report-definitions"></a>Importare definizioni di report

Importare i progetti di report da Progettazione report utilizzando il file creato durante l'esportazione.

1. In Progettazione report, selezionare **Società** &gt; **Gruppi di blocchi predefiniti**.
2. Selezionare il gruppo di blocchi predefiniti da esportare, quindi selezionare **Esporta**.

    > [!NOTE]
    > Per Finance and Operations, è supportato un solo gruppo di blocchi predefiniti, **Predefinito**.

3. Selezionare il blocco **Predefinito** e selezionare **Importa**.
4. Selezionare il file che contiene le definizioni di report esportate e fare clic su **Apri**.
5. Nella finestra di dialogo **Importa** selezionare le definizioni di report da importare:

    - Per importare tutte le definizioni di report e i blocchi predefiniti associati, selezionare **Seleziona tutto**.
    - Per importare report, righe, colonne, alberi o set di dimensioni specifici, selezionare gli elementi da importare.

6. Selezionare **Importa**.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a>Reimpostare il data mart di Creazione report finanziari per Finance and Operations (locale)

1. Chiedere a tutti gli utenti di uscire da Progettazione report e dall'area Creazione report finanziari di Finance and Operations.
2. Eseguire lo script seguente sul database dei report finanziari (MRDB).

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. Troncare o eliminare tutti i record dalla tabella FINANCIALREPORTS nel database di Finance and Operations (AXDB).
4. Troncare o eliminare tutti i record dalla tabella FINANCIALREPORTVERSION, se questa tabella è presente nel database di Finance and Operations. Se la tabella non è presente nel database di Finance and Operations, ignorare questo passaggio.
5. Eseguire lo script **ResetDatamart.sql** sul database dei report finanziari. Questo script disattiva l'integrazione del data mart, elimina tutti i dati del data mart e quindi riattiva l'integrazione del data mart.

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. Dopo la reimpostazione, è possibile verificare manualmente il ricaricamento dei dati eseguendo la query seguente sul database dei report finanziari.

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    Verificare che tutte le righe abbiano un valore **LastRunTime** e che **StateType** sia impostato su **5**. **StateType** impostato su **5** indica il corretto ricaricamento dei dati. Il valore **7** indica uno stato di errore. Talvolta, la mappa della gerarchia organizzativa ha questo stato la prima volta che viene eseguita. Tuttavia, lo stato di errore dovrebbe essere risolto automaticamente.

