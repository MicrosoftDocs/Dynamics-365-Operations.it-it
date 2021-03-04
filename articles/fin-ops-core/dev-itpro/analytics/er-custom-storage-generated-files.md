---
title: Specificare percorsi di archiviazione personalizzati per i documenti generati
description: In questo argomento viene descritto come estendere l'elenco di percorsi di archiviazione per documenti generati con i formati per la creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 362ac7f10cc61e26be89dfbae0e84745d42588a3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680760"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>Specificare percorsi di archiviazione personalizzati per i documenti generati

[!include[banner](../includes/banner.md)]

L'API del framework per la creazione di report elettronici (ER) consente di estendere l'elenco di percorsi di archiviazione per i documenti generati con i formati ER. Questo argomento spiega come aggiungere una posizione di archiviazione personalizzata per i documenti generati delegando l'attività di creazione di destinazioni ER alla factory di destinazione predefinita e quindi implementando una classe personalizzata che ha la propria logica di destinazione.

## <a name="prerequisites"></a>Prerequisiti

Distribuire una topologia che supporta la compilazione continua. Per ulteriori informazioni, vedere [Distribuire topologie che supportano la compilazione continua e l'automazione dei test](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). È inoltre necessario avere accesso a questa topologia per uno dei seguenti ruoli:

- Sviluppatore per la creazione di report elettronici
- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

È inoltre necessario avere accesso all'ambiente di sviluppo per questa topologia.

argomentoTutte le attività in questo argomento possono essere completate nella società **USMF**.

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>Importare il formato ER roll forward dei cespiti

Per generare i documenti per i quali prevedi di aggiungere una posizione di archiviazione personalizzata, [importare](er-download-configurations-global-repo.md) la **configurazione del formato ER roll forward dei cespiti** nella topologia corrente.

![Configurazione della pagina dell'archivio](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>Eseguire il report roll forward dei cespiti

1. Vai a **Cespiti** \> **Richieste e report** \> **Report sulle transazioni** \> **Roll forward dei cespiti**.
2. Nel campo **Dal**, immettere **01/01/2017** (1° gennaio 2017).
3. Nel campo **Al**, immettere **31/01/2017** (31 gennaio 2017).
4. Nel campo **Valuta**, selezionare **Valuta di contabilizzazione**.
5. Nel campo **Mapping formato**, selezionare **Roll forward dei cespiti**.
6. Selezionare **OK**.

![Finestra di dialogo Runtime per il report roll forward dei cespiti](./media/er-custom-storage-generated-files-runtime-dialog.png)

In Microsoft Excel, esaminare il documento in uscita generato e disponibile per il download. Questo comportamento è il [comportamento predefinito](electronic-reporting-destinations.md#default-behavior) per un formato ER per cui non sono state configurate [destinazioni](electronic-reporting-destinations.md) e che è in esecuzione in modalità interattiva.

## <a name="review-the-source-code"></a>Esaminare il codice sorgente

Esaminare il codice del metodo `generateReportByGER()` della classe `AssetRollForwardService`. Si noti che il metodo `Run()` viene utilizzato per chiamare il framework ER e generare il report **Roll forward dei cespiti**.

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

## <a name="modify-the-source-code"></a>Modificare il codice sorgente

1. Nel progetto Visual Studio, aggiungere una nuova classe (`AssetRollForwardDestination` in questo esempio) e scrivere il codice per implementare la destinazione personalizzata per i report **Roll forward dei cespiti** generati.

    - Il metodo `new()` è progettato per ottenere l'oggetto di destinazione ER originale e il parametro basato sulla logica dell'applicazione che specifica la posizione personalizzata in cui devono essere archiviati i rapporti generati. In questo esempio, il percorso personalizzato è il nome di una cartella del file system locale del server che viene eseguito sul server oggetti applicativi (AOS).
    - Il metodo `saveFile()` è progettato per salvare un documento generato in una cartella del file system locale del server che esegue il servizio AOS.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. Nel progetto Visual Studio, aggiungere una nuova classe (`AssetRollForwardDestinationFactory` in questo esempio) e scrivere il codice per impostare una factory di destinazione personalizzata che delega la creazione di una destinazione alla factory di destinazione predefinita e per racchiudere una destinazione di file con la propria destinazione.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. Modificare la classe `AssetRollForwardService` esistente e scrivere il codice per impostare una factory di destinazione personalizzata per l'esecutore del report. Si noti che quando viene creata una factory di destinazione personalizzata, viene passato il parametro basato sull'applicazione che specifica una cartella di destinazione. In questo modo, quella cartella di destinazione viene utilizzata per memorizzare i file generati.

    > [!NOTE] 
    > Assicurarsi che la cartella specificata (**c:\\0** in questo esempio) è presente nel file system locale del server che esegue il servizio AOS. Altrimenti, verrà lanciata un'eccezione [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) in fase di esecuzione.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
                        formatMappingRun.run();
                    }
                }
                catch
                {
                    // An error occurred while exporting data.
                    error("@SYP4861341");
                }
            }
            else
            {
                // There is no data available.
                info("@SYS300117");
            }
        }
    }
    ```

4. Ricompilare il progetto.

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>Rieseguire il report roll forward dei cespiti

1. Vai a **Cespiti** \> **Richieste e report** \> **Report sulle transazioni** \> **Roll forward dei cespiti**.
2. Nel campo **Da**, immettere **01/01/2017**.
3. Nel campo **A**, immettere **31/01/2017**.
4. Nel campo **Valuta**, selezionare **Valuta di contabilizzazione**.
5. Nel campo **Mapping formato**, selezionare **Roll forward dei cespiti**.
6. Selezionare **OK**.
7. Selezionare la cartella locale **C:\\0** per trovare il file generato.

> [!NOTE]
> Perché l'oggetto `originDestination` non è utilizzato nell'oggetto `AssetRollForwardDestination` in questo esempio, le configurazioni per le [destinazioni](electronic-reporting-destinations.md) del formato ER verranno ignorate in fase di esecuzione.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)
- [Estendibilità home page](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]