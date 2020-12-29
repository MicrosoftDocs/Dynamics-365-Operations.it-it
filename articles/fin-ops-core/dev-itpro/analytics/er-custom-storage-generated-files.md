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
# <a name="specify-custom-storage-locations-for-generated-documents"></a><span data-ttu-id="78d0a-103">Specificare percorsi di archiviazione personalizzati per i documenti generati</span><span class="sxs-lookup"><span data-stu-id="78d0a-103">Specify custom storage locations for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="78d0a-104">L'API del framework per la creazione di report elettronici (ER) consente di estendere l'elenco di percorsi di archiviazione per i documenti generati con i formati ER.</span><span class="sxs-lookup"><span data-stu-id="78d0a-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="78d0a-105">Questo argomento spiega come aggiungere una posizione di archiviazione personalizzata per i documenti generati delegando l'attività di creazione di destinazioni ER alla factory di destinazione predefinita e quindi implementando una classe personalizzata che ha la propria logica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="78d0a-105">This topic explains how to add a custom storage location for generated documents by delegating the task of creating ER destinations to the default destination factory and then implementing a custom class that has its own destination logic.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78d0a-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="78d0a-106">Prerequisites</span></span>

<span data-ttu-id="78d0a-107">Distribuire una topologia che supporta la compilazione continua.</span><span class="sxs-lookup"><span data-stu-id="78d0a-107">Deploy a topology that supports continuous build.</span></span> <span data-ttu-id="78d0a-108">Per ulteriori informazioni, vedere [Distribuire topologie che supportano la compilazione continua e l'automazione dei test](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span><span class="sxs-lookup"><span data-stu-id="78d0a-108">For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span></span> <span data-ttu-id="78d0a-109">È inoltre necessario avere accesso a questa topologia per uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="78d0a-109">You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="78d0a-110">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="78d0a-110">Electronic reporting developer</span></span>
- <span data-ttu-id="78d0a-111">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="78d0a-111">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="78d0a-112">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="78d0a-112">System administrator</span></span>

<span data-ttu-id="78d0a-113">È inoltre necessario avere accesso all'ambiente di sviluppo per questa topologia.</span><span class="sxs-lookup"><span data-stu-id="78d0a-113">You must also have access to the development environment for this topology.</span></span>

<span data-ttu-id="78d0a-114">argomentoTutte le attività in questo argomento possono essere completate nella società **USMF**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-114">All the tasks in this topic can be completed in the **USMF** company.</span></span>

## <a name="import-the-fixed-asset-roll-forward-er-format"></a><span data-ttu-id="78d0a-115">Importare il formato ER roll forward dei cespiti</span><span class="sxs-lookup"><span data-stu-id="78d0a-115">Import the Fixed asset roll forward ER format</span></span>

<span data-ttu-id="78d0a-116">Per generare i documenti per i quali prevedi di aggiungere una posizione di archiviazione personalizzata, [importare](er-download-configurations-global-repo.md) la **configurazione del formato ER roll forward dei cespiti** nella topologia corrente.</span><span class="sxs-lookup"><span data-stu-id="78d0a-116">To generate the documents that you plan to add a custom storage location for, [import](er-download-configurations-global-repo.md) the **Fixed asset roll forward** ER format configuration into the current topology.</span></span>

![Configurazione della pagina dell'archivio](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="78d0a-118">Eseguire il report roll forward dei cespiti</span><span class="sxs-lookup"><span data-stu-id="78d0a-118">Run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="78d0a-119">Vai a **Cespiti** \> **Richieste e report** \> **Report sulle transazioni** \> **Roll forward dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-119">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="78d0a-120">Nel campo **Dal**, immettere **01/01/2017** (1° gennaio 2017).</span><span class="sxs-lookup"><span data-stu-id="78d0a-120">In the **From date** field, enter **1/1/2017** (January 1, 2017).</span></span>
3. <span data-ttu-id="78d0a-121">Nel campo **Al**, immettere **31/01/2017** (31 gennaio 2017).</span><span class="sxs-lookup"><span data-stu-id="78d0a-121">In the **To date** field, enter **1/31/2017** (January 31, 2017).</span></span>
4. <span data-ttu-id="78d0a-122">Nel campo **Valuta**, selezionare **Valuta di contabilizzazione**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-122">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="78d0a-123">Nel campo **Mapping formato**, selezionare **Roll forward dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-123">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="78d0a-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-124">Select **OK**.</span></span>

![Finestra di dialogo Runtime per il report roll forward dei cespiti](./media/er-custom-storage-generated-files-runtime-dialog.png)

<span data-ttu-id="78d0a-126">In Microsoft Excel, esaminare il documento in uscita generato e disponibile per il download.</span><span class="sxs-lookup"><span data-stu-id="78d0a-126">In Microsoft Excel, review the outbound document that is generated and available for download.</span></span> <span data-ttu-id="78d0a-127">Questo comportamento è il [comportamento predefinito](electronic-reporting-destinations.md#default-behavior) per un formato ER per cui non sono state configurate [destinazioni](electronic-reporting-destinations.md) e che è in esecuzione in modalità interattiva.</span><span class="sxs-lookup"><span data-stu-id="78d0a-127">This behavior is the [default behavior](electronic-reporting-destinations.md#default-behavior) for an ER format that no [destinations](electronic-reporting-destinations.md) are configured for, and that is running in interactive mode.</span></span>

## <a name="review-the-source-code"></a><span data-ttu-id="78d0a-128">Esaminare il codice sorgente</span><span class="sxs-lookup"><span data-stu-id="78d0a-128">Review the source code</span></span>

<span data-ttu-id="78d0a-129">Esaminare il codice del metodo `generateReportByGER()` della classe `AssetRollForwardService`.</span><span class="sxs-lookup"><span data-stu-id="78d0a-129">Review the code of the `generateReportByGER()` method of the `AssetRollForwardService` class.</span></span> <span data-ttu-id="78d0a-130">Si noti che il metodo `Run()` viene utilizzato per chiamare il framework ER e generare il report **Roll forward dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-130">Notice that the `Run()` method is used to call the ER framework and generate the **Fixed asset roll forward** report.</span></span>

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

## <a name="modify-the-source-code"></a><span data-ttu-id="78d0a-131">Modificare il codice sorgente</span><span class="sxs-lookup"><span data-stu-id="78d0a-131">Modify the source code</span></span>

1. <span data-ttu-id="78d0a-132">Nel progetto Visual Studio, aggiungere una nuova classe (`AssetRollForwardDestination` in questo esempio) e scrivere il codice per implementare la destinazione personalizzata per i report **Roll forward dei cespiti** generati.</span><span class="sxs-lookup"><span data-stu-id="78d0a-132">In your Visual Studio project, add a new class (`AssetRollForwardDestination` in this example), and write code to implement your custom destination for **Fixed asset roll forward** reports that are generated.</span></span>

    - <span data-ttu-id="78d0a-133">Il metodo `new()` è progettato per ottenere l'oggetto di destinazione ER originale e il parametro basato sulla logica dell'applicazione che specifica la posizione personalizzata in cui devono essere archiviati i rapporti generati.</span><span class="sxs-lookup"><span data-stu-id="78d0a-133">The `new()` method is designed to get the original ER destination object and the application logic–driven parameter that specifies the custom location where generated reports should be stored.</span></span> <span data-ttu-id="78d0a-134">In questo esempio, il percorso personalizzato è il nome di una cartella del file system locale del server che viene eseguito sul server oggetti applicativi (AOS).</span><span class="sxs-lookup"><span data-stu-id="78d0a-134">In this example, the custom location is the name of a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    - <span data-ttu-id="78d0a-135">Il metodo `saveFile()` è progettato per salvare un documento generato in una cartella del file system locale del server che esegue il servizio AOS.</span><span class="sxs-lookup"><span data-stu-id="78d0a-135">The `saveFile()` method is designed to save a generated document to a folder of the local file system of the server that runs the AOS service.</span></span>

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

2. <span data-ttu-id="78d0a-136">Nel progetto Visual Studio, aggiungere una nuova classe (`AssetRollForwardDestinationFactory` in questo esempio) e scrivere il codice per impostare una factory di destinazione personalizzata che delega la creazione di una destinazione alla factory di destinazione predefinita e per racchiudere una destinazione di file con la propria destinazione.</span><span class="sxs-lookup"><span data-stu-id="78d0a-136">In your Visual Studio project, add a new class (`AssetRollForwardDestinationFactory` in this example), and write code to set up a custom destination factory that delegates the creation of a destination to the default destination factory, and to wrap a file destination with your own destination.</span></span>

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

3. <span data-ttu-id="78d0a-137">Modificare la classe `AssetRollForwardService` esistente e scrivere il codice per impostare una factory di destinazione personalizzata per l'esecutore del report.</span><span class="sxs-lookup"><span data-stu-id="78d0a-137">Modify the existing `AssetRollForwardService` class, and write code to set up a custom destination factory for the report runner.</span></span> <span data-ttu-id="78d0a-138">Si noti che quando viene creata una factory di destinazione personalizzata, viene passato il parametro basato sull'applicazione che specifica una cartella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="78d0a-138">Notice that when a custom destination factory is constructed, the application-driven parameter that specifies a target folder is passed.</span></span> <span data-ttu-id="78d0a-139">In questo modo, quella cartella di destinazione viene utilizzata per memorizzare i file generati.</span><span class="sxs-lookup"><span data-stu-id="78d0a-139">In this way, that target folder is used to store generated files.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="78d0a-140">Assicurarsi che la cartella specificata (**c:\\0** in questo esempio) è presente nel file system locale del server che esegue il servizio AOS.</span><span class="sxs-lookup"><span data-stu-id="78d0a-140">Make sure that the specified folder (**c:\\0** in this example) is present in the local file system of the server that runs the AOS service.</span></span> <span data-ttu-id="78d0a-141">Altrimenti, verrà lanciata un'eccezione [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="78d0a-141">Otherwise, a [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) exception will be thrown at runtime.</span></span>

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

4. <span data-ttu-id="78d0a-142">Ricompilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="78d0a-142">Rebuild your project.</span></span>

## <a name="re-run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="78d0a-143">Rieseguire il report roll forward dei cespiti</span><span class="sxs-lookup"><span data-stu-id="78d0a-143">Re-run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="78d0a-144">Vai a **Cespiti** \> **Richieste e report** \> **Report sulle transazioni** \> **Roll forward dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-144">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="78d0a-145">Nel campo **Da**, immettere **01/01/2017**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-145">In the **From date** field, enter **1/1/2017**.</span></span>
3. <span data-ttu-id="78d0a-146">Nel campo **A**, immettere **31/01/2017**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-146">In the **To date** field, enter **1/31/2017**.</span></span>
4. <span data-ttu-id="78d0a-147">Nel campo **Valuta**, selezionare **Valuta di contabilizzazione**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-147">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="78d0a-148">Nel campo **Mapping formato**, selezionare **Roll forward dei cespiti**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-148">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="78d0a-149">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="78d0a-149">Select **OK**.</span></span>
7. <span data-ttu-id="78d0a-150">Selezionare la cartella locale **C:\\0** per trovare il file generato.</span><span class="sxs-lookup"><span data-stu-id="78d0a-150">Browse the local **C:\\0** folder to find the generated file.</span></span>

> [!NOTE]
> <span data-ttu-id="78d0a-151">Perché l'oggetto `originDestination` non è utilizzato nell'oggetto `AssetRollForwardDestination` in questo esempio, le configurazioni per le [destinazioni](electronic-reporting-destinations.md) del formato ER verranno ignorate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="78d0a-151">Because the `originDestination` object isn't used in the `AssetRollForwardDestination` object in this example, the configurations for the ER format [destinations](electronic-reporting-destinations.md) will be ignored at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78d0a-152">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="78d0a-152">Additional resources</span></span>

- [<span data-ttu-id="78d0a-153">Destinazioni dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="78d0a-153">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="78d0a-154">Estendibilità home page</span><span class="sxs-lookup"><span data-stu-id="78d0a-154">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
