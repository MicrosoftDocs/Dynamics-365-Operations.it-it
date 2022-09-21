---
title: Impostare un flusso di dati alternativo per i suggerimenti
description: In questo articolo viene descritto come configurare un ambiente usando un flusso di dati alternativo per fornire dati al servizio di suggerimenti.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: b507b9bb57c68aca9424b53f8ccc009efea733bc
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460163"
---
# <a name="set-up-an-alternate-dataflow-for-recommendations"></a>Impostare un flusso di dati alternativo per i suggerimenti

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come configurare un ambiente usando un flusso di dati alternativo per fornire dati al servizio di suggerimenti.

## <a name="comparison-of-out-of-the-box-dataflow-with-alternate-dataflow"></a>Confronto tra flusso di dati predefinito e flusso di dati alternativo

L'illustrazione seguente illustra il flusso di dati predefinito in un ambiente.

![Flusso di dati predefinito in un ambiente](media/reco-out-of-the-box-dataflow-2.png)

L'illustrazione seguente illustra un flusso di dati alternativo, in cui il processo batch di sincronizzazione dell'archivio entità viene sostituito con passaggi del flusso di dati alternativi.

![Flusso di dati alternativo in un ambiente](media/reco-alternate-dataflow-2.png)

## <a name="assumptions"></a>Presupposti

- Questo articolo presuppone che tu abbia già abilitato il servizio di suggerimenti per il tuo ambiente. Per ulteriori informazioni, vedi [Abilitare i suggerimenti sul prodotto](enable-product-recommendations.md).
- Quando lavori con file e cartelle nell'account Microsoft Azure Data Lake Storage:

    - È possibile usare l'interfaccia del portale Web di Azure o l'applicazione Esplora di Archiviazione di Azure.
    - I punti di partenza per lavorare con file e cartelle sono nel contenitore **dynamics365-financeandoperations** che si trova nella cartella denominata in modo che corrisponda all'URL dell'ambiente.
    - Se il nome del tuo ambiente sandbox è **MyUAT**, l'URL di base dell'ambiente sarà `myuat.sandbox.operations.dynamics.com`.
    - Se più di un ambiente è connesso allo stesso account di archiviazione, ogni ambiente avrà la propria cartella radice.

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere soddisfatti prima di poter implementare l'approccio del flusso di dati alternativo.

### <a name="set-up-microsoft-power-platform"></a>Imposta Microsoft Power Platform

Per impostare Microsoft Power Platform, segui le istruzioni in [Abilitare l'integrazione di Microsoft Power Platform](../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

### <a name="install-the-export-to-data-lake-add-in"></a>Installare il componente aggiuntivo Esporta in Data Lake

Per installare il componente aggiuntivo Esporta in Data Lake, segui le istruzioni in [Installare il componente aggiuntivo Esporta in Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

> [!NOTE]
> Prendi nota dei valori di configurazione, perché ti serviranno per alcuni dei passaggi che seguono.

### <a name="configure-tables-to-export-in-dynamics-365"></a>Configurare le tabelle da esportare in Dynamics 365

La sincronizzazione delle tabelle da Dynamics 365 ad Azure Data Lake Storage è gestita nella pagina **Esporta in Data Lake**. Poiché quella pagina non ha attualmente una voce di menu, solo gli utenti nel ruolo di sicurezza **Amministratore di sistema** possono aprirla.

Per configurare le tabelle da esportare in Dynamics 365, segui questi passaggi.

1. Per aprire la pagina **Esporta in Data Lake** aggiungi la stringa `?mi=DataFeedsDefinitionWorkspace` all'URL di base dell'ambiente, come mostrato nell'esempio seguente:

    `https://<environment-URL>/?mi=DataFeedsDefinitionWorkspace`

1. Sulla pagina **Esporta in Data Lake** copia le tabelle elencate nella sezione [Elenco delle tabelle dei cubi RetailSales](#list-of-retailsales-cube-tables) di questo articolo.
1. Nella colonna **Nome di sistema** espandi l'elenco delle opzioni di filtro.
1. Per il tipo di filtro, seleziona **è uno di**. Quindi posiziona il cursore nella casella di testo e incolla l'elenco di tabelle che hai copiato dalla pagina **Esporta in Data Lake**.
1. Nella parte inferiore dell'elenco delle opzioni di filtro, seleziona **Applica**.
1. Seleziona tutte le righe nella griglia, quindi seleziona **Attiva**.

> [!NOTE]
> Prima di passare al passaggio successivo, tutte le righe devono essere aggiornate allo stato di **In esecuzione**. Risolvi i problemi e correggi eventuali errori come richiesto.

### <a name="create-a-synapse-workspace"></a>Creare un'area di lavoro Synapse

Per creare un'area di lavoro Synapse se non ne hai già una, segui le istruzioni in [Avvio rapido: creare un'area di lavoro Synapse](/azure/synapse-analytics/quickstart-create-workspace).

Per mantenere organizzate le risorse di Azure, ti consigliamo di mettere insieme l'account Data Lake Storage e l'area di lavoro Synapse in un gruppo di risorse in Azure. È possibile riutilizzare l'account di archiviazione creato durante l'installazione del componente aggiuntivo Esporta in Data Lake.

## <a name="create-a-database-in-synapse-for-recommendation-data-processing"></a>Creare un database in Synapse per l'elaborazione dei dati dei suggerimenti

Utilizza l'applicazione console dell'utilità Common Data Model (CDMUtil_ConsoleApp) per creare un database nell'area di lavoro Synapse e popolarlo dalle tabelle Common Data Model in Data Lake Storage. Si consiglia di utilizzare l'utilità Common Data Model con il database in un ambiente di sviluppo, nel caso in cui siano presenti estensioni.

> [!NOTE]
> I passaggi seguenti presuppongono che nessun dato dell'estensione sia stato aggiunto al cubo RetailSales.

Per creare un database in Synapse, attieniti alla seguente procedura.

1. Vai al [GitHub Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Analytics/CDMUtilSolution#2-cdmutil-console-app) e segui i passaggi per scaricare il file **CDMUtilConsoleApp.zip**.
1. Estrai il file zip in una cartella locale.
1. Apri il file **CDMUtil_ConsoleApp.dll.config** in un editor di testo e aggiorna i seguenti valori:

    1. Imposta il valore **ID tenant** (ID tenant di Azure).
    1. Imposta il valore **Chiave di accesso** (la chiave di accesso per l'account Data Lake Storage).

        1. Nel portale di Azure, apri il tuo account di archiviazione.
        1. Nel menu sul lato sinistro della pagina, seleziona **Chiavi di accesso**.
        1. Seleziona **Mostra chiavi** nella parte superiore della pagina.
        1. Seleziona il pulsante copia per uno dei due campi chiave, quindi incolla il valore tra virgolette doppie nel file di configurazione.

    1. Imposta il valore **ManifestURL** sull'URL del tuo file **Tables.manifest.cdm.json** in Azure Data Lake Storage. Per ottenere l'URL, accedi al file nel portale di Azure, seleziona i puntini di sospensione (**...**) sul lato destro della vista, quindi seleziona **Proprietà**. L'URL è la prima proprietà mostrata nella scheda **Panoramica**.
    1. Imposta il valore **TargetDbConnectionString** sulla stringa di connessione per il pool SQL serverless integrato dell'area di lavoro Synapse.

        1. Nell'area di lavoro Synapse, seleziona la scheda **Gestisci**.
        1. Nel sottomenu, seleziona **Pool SQL**.
        1. Seleziona il nome **Incorporato** per visualizzare le proprietà del pool.
        1. Nella finestra di dialogo delle proprietà, seleziona il tipo di connessione ADO.NET che desideri utilizzare. Copia quindi il valore della stringa di connessione e incollalo tra le virgolette doppie nel file di configurazione.

        > [!NOTE]
        > È necessario avere le autorizzazioni per creare database. Per facilità d'uso, potresti voler utilizzare l'account amministratore **sqladminuser** incorporato.

    1. Decommenta il nodo **ProcessEntities** e impostane il valore su **true** (per esempio `<add key="ProcessEntities" value ="true"/>`).

1. Salva e chiudi il file **CDMUtil_ConsoleApp.dll.config**.
1. Copia il file **EntityList.json** nella directory **/Manifest**.
1. In una finestra del prompt dei comandi, esegui **cdmutil_consoleapp.exe**.

> [!NOTE]
> Quando si esamina l'output, dovrebbero esserci 35 entità/viste, almeno 75 tabelle e nessun errore.

## <a name="prepare-the-data-lake-retailsales-aggregate-measurements-directory"></a>Preparare la directory delle misurazioni aggregate di Data Lake RetailSales

### <a name="back-up-your-current-retailsales-cube-data-from-data-lake-storage"></a>Eseguire il backup dei dati attuali del cubo RetailSales da Data Lake Storage

Il modo più semplice per eseguire il backup dei dati del cubo RetailSales corrente è rinominare la directory **RetailSales** in Data Lake Storage **RetailSales-backup** o qualcosa di simile. Questo metodo conserva i dati esistenti nel caso in cui sia necessaria la risoluzione dei problemi in un secondo momento.

La cartella del cubo **/RetailSales** può essere trovata nel seguente percorso:

`<storage-account>/dynamics365-financeandoperations/<environment-url (for example, myuat.sandbox.operations.dynamics.com)>/AggregateMeasurements/RetailSales`

### <a name="create-a-new-retailsales-folder-and-upload-the-model-file"></a>Creare una nuova cartella RetailSales e caricare il file del modello

Per creare una nuova directory **RetailSales** e carica il file **model.json** in Data Lake Storage, attieniti alla seguente procedura.

1. Crea una nuova directory vuota allo stesso livello della directory precedente e denominala **RetailSales**.
1. Carica il file **model.json** nella nuova directory.

## <a name="create-a-pipeline-to-copy-the-retailsales-cube-data"></a>Creare una pipeline per copiare i dati del cubo RetailSales

La pipeline leggerà le visualizzazioni del cubo RetailSales ed esporterà i dati in file CSV in Data Lake Storage.

Per creare una pipeline per copiare i dati del cubo RetailSales, segui questi passaggi.

1. Nell'area di lavoro Synapse, seleziona la scheda **Integra**.
1. Seleziona il segno più (**+**), quindi seleziona **Importa da modello di pipeline**.
1. Scarica e quindi seleziona il [file ExportRetailSalesCubeViews.zip](https://aka.ms/reco-alternate-dataflow-files).
1. Seleziona il servizio collegato al database SQL.
1. Seleziona il servizio collegato all'account di archiviazione.
1. Apri lo strumento **Copia dati** e cambia la proprietà **Percorso della cartella** in **\<environment_name\>/...**.

### <a name="test-execution-of-the-pipeline"></a>Esecuzione dei test della pipeline

Si consiglia di testare la pipeline utilizzando una sola vista. La vista **RetailSales_RetailMediaTemplateView** funziona bene perché di solito contiene meno di 10 righe.

## <a name="schedule-the-pipeline-to-run-on-a-recurring-schedule"></a>Pianificare l'esecuzione della pipeline in base a una pianificazione ricorrente

Ogni volta che viene eseguita la pipeline, si verifica il consumo di Azure. Ti consigliamo di pianificare le esecuzioni a intervalli di 48 ore o maggiore. Puoi sempre eseguire la pipeline manualmente se devi sincronizzare i dati immediatamente. 
 
## <a name="table-list-for-synchronization-from-dynamics-365-to-data-lake-storage"></a>Elenco tabelle per la sincronizzazione da Dynamics 365 a Data Lake Storage

Il seguente elenco di tabelle è un sottoinsieme di tutte le tabelle necessarie per l'intero cubo RetailSales. Solo 15 delle viste nel cubo RetailSales vengono utilizzate dal servizio di suggerimenti e l'elenco delle tabelle richieste è stato filtrato di conseguenza.

### <a name="list-of-retailsales-cube-tables"></a>Elenco delle tabelle dei cubi RetailSales

- BICalendarOffsets
- BIDateDimension
- BIDateDimensionValue
- Catalogo
- CatalogProduct
- CatalogProductCategory
- CustInvoiceJour
- CustInvoiceTrans
- CustTable
- DataArea
- DimensionAttributeValueCombination
- DimensionAttributeValueSet
- DirPartyTable
- EcoResCategory
- EcoResCategoryHierarchy
- EcoResCategoryHierarchyRole
- EcoResColor
- EcoResConfiguration
- EcoResProduct
- EcoResProductCategory
- EcoResProductTranslation
- EcoResSize
- EcoResStyle
- HcmWorker
- InventDim
- InventDimCombination
- InventItemGroup
- InventItemGroupItem
- InventItemSetupSupplyType
- InventTable
- InventTrans
- LogisticsAddressCountryRegion
- LogisticsAddressCountryRegionTranslation
- LogisticsLocation
- LogisticsPostalAddress
- OMHIERARCHYPURPOSE
- RetailAssortmentLookup
- RetailAssortmentLookupChannelGroup
- RetailChannelProfile
- RetailChannelProfileProperty
- RetailChannelTable
- RetailChannelTableExt
- RetailConnDatabaseProfile
- RetailCustInvoiceJourTable
- RetailCustTable
- RetailMediaTemplate
- RetailOfflineProfile
- RetailPeriodicDiscount
- RetailRecoListConfigurationParameters
- RetailSalesTaxOverrideGroup
- RetailSharedParameters
- RetailSpecialCategoryMember
- RetailTenderTypeCardTable
- RetailTenderTypeTable
- RetailTerminalTable
- RetailTmpProductMedia
- RetailTransactionDiscountTrans
- RetailTransactionPaymentTrans
- RetailTransactionPaymentTransExt
- RetailTransactionSalesTrans
- RetailTransactionSalesTransExt
- RetailTransactionTable
- SalesLine
- SalesTable
- SystemParameters
- RETAILCATALOGINTERNALORG
- RETAILGROUPMEMBERLINE
- RETAILINTERNALORGANIZATION
- RETAILSPECIALCATEGORYPRODUCT
- RETAILPRODUCTCATEGORY
- ECORESCONFIGURATION
- DIMENSIONATTRIBUTE
- DIMENSIONATTRIBUTEVALUESET
- DIMENSIONHIERARCHY
- DIMENSIONHIERARCHYINTEGRATION
- DIMENSIONHIERARCHYLEVEL
- DIMENSIONPARAMETER
- OMExplodedOrganizationSecurityGraph

### <a name="view-list-for-the-parameter-to-pass-to-the-synapse-pipeline"></a>Visualizzare l'elenco per il parametro da passare alla pipeline Synapse

L'elenco separato da virgole seguente contiene le visualizzazioni del cubo RetailSales su cui la pipeline eseguirà un'operazione di "selezione". Quindi copierà i risultati in Data Lake Storage.

RetailSales_RetailAssortmentRulesView,RetailSales_RetailChannelNavigationHierarchiesView,RetailSales_RetailChannelNavigationHierarchyCatalogProductsView,RetailSales_RetailChannelNavigationHierarchyCategoryNodesView,RetailSales_RetailChannelNavigationHierarchyCategoryProductsView,RetailSales_RetailMediaBaseUrlChannelView,RetailSales_RetailMediaRelativeUrlProductView,RetailSales_RetailMediaTemplateView,RetailSales_RetailOptOutCustomersView,RetailSales_RetailProductCategory,RetailSales_RetailProductTransaction,RetailSales_RetailProductVariantDimensionsView,RetailSales_RetailRecoListConfigurationParametersView,RetailSales_RetailRecoListsSharedParametersView,RetailSales_RetailEcoResProductTranslation

> [!IMPORTANT]
> Il parametro pipeline deve essere un elenco di nomi di visualizzazione separati da virgole singole. Non devono esserci spazi o avanzamenti di riga.

## <a name="environment-specific-fixes"></a>Correzioni specifiche per l'ambiente

### <a name="retailchannelview-fix"></a>Correzione di RETAILCHANNELVIEW

La vista **RETAILCHANNELVIEW** contiene un intero hardcoded che rappresenta un'organizzazione del tipo "canale di vendita al dettaglio". Il valore effettivo del tipo può cambiare da ambiente a ambiente o da tenant a tenant.

```SQL
CREATE OR ALTER   VIEW [dbo].[RETAILCHANNELVIEW]
AS
SELECT T1.RECID AS RECID1,
       T1.STOREAREA AS STOREAREA,
       T1.OMOPERATINGUNITID AS OMOPERATINGUNITID,
       T1.DEFAULTCUSTACCOUNT AS DEFAULTCUSTOMER,
       T1.RETAILCHANNELID AS RETAILCHANNELID,
       T1.CHANNELTYPE AS CHANNELTYPE,
       T1.PARTITION AS PARTITION,
       T1.RECID AS RECID,
       T2.OMOPERATINGUNITNUMBER AS OMOPERATINGUNITNUMBER,
       T3.NAME AS NAME
FROM   dbo.RETAILCHANNELTABLE AS T1 CROSS JOIN dbo.DIRPARTYTABLE AS T2 CROSS JOIN dbo.DIRPARTYTABLE AS T3
WHERE  ((((T1.OMOPERATINGUNITID = T2.RECID)
          )
         AND ((T2.RECID = T3.RECID)
              ))
        AND T2.INSTANCERELATIONTYPE IN (8363));
```

Segui questi passaggi per aggiornare l'intero hardcoded.

1. In Dynamics 365, cerca il valore **ChannelID** per il tuo canale online.
1. In un'istanza di SQL Server Management Studio (SSMS) collegata al database Synapse, esegui la query seguente.

    ```SQL
    select INSTANCERELATIONTYPE, NAME, NAMEALIAS, * from dbo.DIRPARTYTABLE where RECID IN (select OMOPERATINGUNITID from dbo.RETAILCHANNELTABLE where RETAILCHANNELID =     <channelID>)
    ```

1. Copia il valore dalla prima colonna (**INSTANCERELATIONTYPE**) e incollalo nella definizione della vista.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="pipeline-task-fails"></a>L'attività della pipeline non riesce

Dovrebbero esserci 15 esecuzioni di attività della pipeline per l'attività **CopyData**. Se un'esecuzione non riesce, è necessario verificare che tutti gli oggetti SQL dipendenti esistano e che le query vengano eseguite. Il modo più semplice per accedere a tutte le dipendenze è utilizzare SSMS per connettersi al database. È quindi possibile selezionare e tenere premuta (o fare clic con il pulsante destro del mouse) una vista e selezionare **Genera CREA come in una nuova finestra**.

Il messaggio di errore potrebbe includere il seguente testo:

- Errore: si è verificato un errore sul lato "Origine"
- Errore nella gestione del file esterno: "Numero massimo di errori".
- /RetailSales/RetailSales_xxxxxx

#### <a name="example-scenario"></a>Scenario di esempio

In questo esempio, l'attività **RetailSales_RetailProductCategory** non riesce e viene visualizzato l'errore "Numero massimo di errori".

Per eseguire il debug dell'errore, effettua le operazioni seguenti.

1. Apri il file **EntityList.json** in un editor di testo (ad esempio, Visual Studio Code).
1. Trova la definizione della vista per **RetailSales_RetailProductCategory**.

    ```SQL
    CREATE  VIEW [dbo].[RetailSales_RetailProductCategory] AS SELECT 0 AS ROW_UNIQUEKEY ,CATEGORY AS CATEGORYID ,PRODUCT AS PRODUCTID ,PRODUCTNAME ,CATEGORYNAME     ,PARENTCATEGORY AS PARENTCATEGORYID ,PARTITION ,RECID FROM RetailProductCategoryView
    ```

1. Questa vista dipende solo da un'altra vista: **RetailProductCategoryView** _. Trova la definizione della vista per _*RetailProductCategoryView**.

    ```SQL
    CREATE VIEW [DBO].[RETAILPRODUCTCATEGORYVIEW] AS SELECT T1.CATEGORY AS CATEGORY, T1.PRODUCT AS PRODUCT, T1.PARTITION AS PARTITION, T1.RECID AS RECID, T2.PRODUCTNAME AS PRODUCTNAME, T2.PARTITION AS PARTITION#2, T3.NAME AS CATEGORYNAME, T3.PARENTCATEGORY AS PARENTCATEGORY, T3.PARTITION AS PARTITION#3 FROM RETAILPRODUCTCATEGORY T1 CROSS JOIN ECORESPRODUCTTRANSLATIONS T2 CROSS JOIN RETAILCATEGORYEXPANDED T3 WHERE((( T1.PRODUCT = T2.PRODUCT) AND ( T1.PARTITION = T2.PARTITION)) AND (( T1.CATEGORY = T3.RECID) AND ( T1.PARTITION = T3.PARTITION)))
    ```

1. Questa vista dipende da altre tre viste: **RETAILPRODUCTCATEGORY**, **ECORESPRODUCTTRANSLATIONS**, e **RETAILCATEGORYEXPANDED**. Trova la definizione per ciascuna di queste viste ed elenca le sue dipendenze. Continua fino a trovare tutte le viste dipendenti.

    Ecco l'intero elenco nell'ordine dell'albero delle dipendenze. È necessario convalidare tredici visualizzazioni.

    - RetailSales_RetailProductCategory

        - RetailProductCategoryView

            - RETAILPRODUCTCATEGORY

                - ECORESPRODUCTCATEGORY
                - ECORESCATEGORYHIERARCHYROLE
                - RETAILSPECIALCATEGORYPRODUCT

                    - ECORESPRODUCT
                    - RETAILGROUPMEMBERLINE
                    - RETAILSPECIALCATEGORYMEMBER

            - ECORESPRODUCTTRANSLATIONS

                - ECORESPRODUCT
                - ECORESPRODUCTTRANSLATION
                - SYSTEMPARAMETERS

            - RETAILCATEGORYEXPANDED

                - ECORESCATEGORY
                - ECORESCATEGORYHIERARCHYROLE

1. In Excel, crea le seguenti 13 istruzioni **select count(\*) from \<view_name\>**. Esegui queste istruzioni in SSMS e invia i risultati in formato testo. Quindi scorri i risultati per vedere se una delle visualizzazioni non è riuscita. L'errore iniziale suggerisce che almeno una delle visualizzazioni avrà esito negativo.

    ```SQL
    select count(*) from RetailProductCategoryView
    select count(*) from RETAILPRODUCTCATEGORY
    select count(*) from ECORESPRODUCTCATEGORY
    select count(*) from ECORESCATEGORYHIERARCHYROLE
    select count(*) from RETAILSPECIALCATEGORYPRODUCT
    select count(*) from ECORESPRODUCT
    select count(*) from RETAILGROUPMEMBERLINE
    select count(*) from RETAILSPECIALCATEGORYMEMBER
    select count(*) from ECORESPRODUCTTRANSLATIONS
    select count(*) from ECORESPRODUCTTRANSLATION
    select count(*) from SYSTEMPARAMETERS
    select count(*) from RETAILCATEGORYEXPANDED
    select count(*) from ECORESCATEGORY
    ```

1. Un modo per convalidare ciò che stai guardando è creare una vista dipendente dalla radice per generare la definizione della vista in SSMS. Verifica quindi che sia presente una colonna di file di Azure Data Lake denominata **r.filepath**. La presenza di questa colonna indicherà che la vista che stai esaminando sta leggendo i dati da Data Lake Storage.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica suggerimenti sul prodotto](product-recommendations.md)

[Abilitare Azure Data Lake Storage in un ambiente Dynamics 365 Commerce](enable-adls-environment.md)

[Abilitare i suggerimenti personalizzati](personalized-recommendations.md)

[Abilitare gli elementi consigliati "acquista prodotti simili"](shop-similar-looks.md)

[Rifiuto esplicito dei suggerimenti personalizzati](personalization-gdpr.md)

[Aggiungere suggerimenti sul prodotto su POS](product.md)

[Aggiungere suggerimenti alla schermata della transazione](add-recommendations-control-pos-screen.md)

[Regolare i risultati dei suggerimenti AI-ML](modify-product-recommendation-results.md)

[Creare manualmente suggerimenti mirati](create-editorial-recommendation-lists.md)

[Crea suggerimenti con dati dimostrativi](product-recommendations-demo-data.md)

[Domande frequenti su suggerimenti prodotto](faq-recommendations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
