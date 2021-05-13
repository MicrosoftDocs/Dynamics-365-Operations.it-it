---
title: Aggiungere campi dati nell'integrazione fiscale usando le estensioni
description: In questo argomento viene illustrato come usare le estensioni X++ per aggiungere campi dati nell'integrazione fiscale.
author: qire
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8e3573f9c9971d4a5af33ece08b7e0b43f2e813a
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921167"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>Aggiungere campi dati nell'integrazione fiscale usando l'estensione

[!include [banner](../includes/banner.md)]


In questo argomento viene illustrato come usare le estensioni X++ per aggiungere campi dati nell'integrazione fiscale. Questi campi possono essere estesi al modello di dati fiscali del servizio per le imposte e utilizzati per determinare i codici imposta. Per ulteriori informazioni, vedi [Aggiungere campi dati nelle configurazioni imposte](tax-service-add-data-fields-tax-configurations.md).

## <a name="data-model"></a>Modello dati

I dati nel modello di dati sono forniti dagli oggetti e implementati dalle classi.

Ecco un elenco degli oggetti principali:

* AxClass/TaxIntegration **Document** Object
* AxClass/TaxIntegration **Line** Object
* AxClass/TaxIntegration **TaxLine** Object

Nella figura seguente viene illustrato come questi oggetti sono correlati.

[![Relazione degli oggetti del modello di dati](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

Un oggetto **Documento** può contenere molti oggetti **Riga**. Ogni oggetto contiene metadati per il servizio per le imposte.

- `TaxIntegrationDocumentObject` contiene metadati `originAddress`, che contengono informazioni sull'indirizzo di origine, e metadati `includingTax`, che indicano se l'importo della riga include l'IVA.
- `TaxIntegrationLineObject` contiene i metadati `itemId`, `quantity` e `categoryId`.

> [!NOTE]
> `TaxIntegrationLineObject` implementa anche gli oggetti **Addebito**.

## <a name="integration-flow"></a>Flusso di integrazione

I dati nel flusso vengono gestiti dalle attività.

### <a name="key-activities"></a>Attività chiave

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

Le attività vengono eseguite nell'ordine seguente:

1. Recupero impostazione
2. Recupero dati
3. Servizio di calcolo
4. Cambio valuta
5. Persistenza dei dati

Ad esempio, estendi **Recupero dati** prima del **Servizio di calcolo**.

#### <a name="data-retrieval-activities"></a>Attività di recupero dati

Le attività di **recupero dati** recuperano i dati dal database. Adattatori per transazioni diverse sono disponibili per recuperare i dati da tabelle di transazioni diverse:

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

In queste attività di **recupero dati**, i dati vengono copiati dal database in `TaxIntegrationDocumentObject` e `TaxIntegrationLineObject`. Poiché tutte queste attività estendono la stessa classe di modelli astratta, hanno metodi comuni.

#### <a name="calculation-service-activities"></a>Attività del servizio di calcolo

L'attività **Servizio di calcolo** è il collegamento tra il servizio per le imposte e l'integrazione fiscale. Questa attività è responsabile delle seguenti funzioni:

1. Costruire la richiesta.
2. Registrare la richiesta nel servizio per le imposte.
3. Ottenere la risposta dal servizio per le imposte.
4. Analizzare la risposta.

Un campo dati aggiunto alla richiesta verrà inviato insieme agli altri metadati. 

## <a name="extension-implementation"></a>Implementazione dell'estensione

In questa sezione vengono descritti i passaggi dettagliati che spiegano come implementare l'estensione. Ad esempio, vengono utilizzate le dimensioni finanziarie **Centro di costo** e **Progetto**.

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>Passaggio 1. Aggiungere la variabile dati nella classe oggetto

La classe oggetto contiene la variabile di dati e i metodi getter/setter per i dati. Aggiungi il campo dati a `TaxIntegrationDocumentObject` o a `TaxIntegrationLineObject`, a seconda del livello del campo. L'esempio seguente utilizza il livello di riga e il nome del file è `TaxIntegrationLineObject_Extension.xpp`.

> [!NOTE]
> Se il campo dati che stai aggiungendo è a livello di documento, cambia il nome del file in `TaxIntegrationDocumentObject_Extension.xpp`.

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

**Centro di costo** e **Progetto** vengono aggiunti come variabili private. Crea metodi getter e setter per questi campi dati per manipolare i dati.

### <a name="step-2-retrieve-data-from-the-database"></a>Passaggio 2. Recuperare i dati dal database

Specifica la transazione ed estendi le classi dell'adattatore appropriate per recuperare i dati. Ad esempio, se utilizzi una transazione **Ordine fornitore**, è necessario estendere `TaxIntegrationPurchTableDataRetrieval` e `TaxIntegrationVendInvoiceInfoTableDataRetrieval`. 

> [!NOTE]
> `TaxIntegrationPurchParmTableDataRetrieval` è ereditato da `TaxIntegrationPurchTableDataRetrieval`. Non deve essere modificato a meno che la logica delle tabelle `purchTable` e `purchParmTable` è diversa.

Se il campo dati deve essere aggiunto per tutte le transazioni, estendi tutte le classi `DataRetrieval`.

Perché tutte le attività **Recupero dati** estendono la stessa classe modello, le strutture della classe, le variabili e i metodi sono simili.

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

L'esempio seguente mostra la struttura di base quando la tabella `PurchTable` viene utilizzata.

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

Quando il metodo `CopyToDocument` viene chiamato, il buffer `this.purchTable` è già esistente. Lo scopo di questo metodo è copiare tutti i dati richiesti da `this.purchTable` nell'oggetto `document` utilizzando il metodo setter creato nella classe `DocumentObject`.

Allo stesso modo, un buffer `this.purchLine` esiste già nel metodo `CopyToLine`. Lo scopo di questo metodo è copiare tutti i dati richiesti da `this.purchLine` nell'oggetto `_line` utilizzando il metodo setter creato nella classe `LineObject`.

L'approccio più semplice è estendere i metodi `CopyToDocument` e `CopyToLine`. Tuttavia, ti consigliamo di provare prima i metodi `copyToDocumentFromHeaderTable` e `copyToLineFromLineTable`. Se non funzionano come richiesto, implementa il tuo metodo e chiamalo in `CopyToDocument` e `CopyToLine`. Esistono tre situazioni comuni in cui potresti utilizzare questo approccio:

- Il campo obbligatorio è in `PurchTable` o `PurchLine`. In questa situazione, puoi estendere `copyToDocumentFromHeaderTable` e `copyToLineFromLineTable`. Ecco il codice di esempio.

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- I dati richiesti non sono nella tabella predefinita della transazione. Tuttavia, esistono alcune relazioni di join con la tabella predefinita e il campo è obbligatorio nella maggior parte delle righe. In questa situazione, sostituisci `getDocumentQueryObject` o `getLineObject` per eseguire query sulla tabella in base alla relazione di join. Nell'esempio seguente, il campo **Consegna ora** è integrato con l'ordine cliente a livello di riga.

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    In questo esempio, un buffer `mcrSalesLineDropShipment` viene dichiarato e la query viene definita in `getLineQueryObject`. La query utilizza la relazione `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`. In questa situazione, puoi sostituire `getLineQueryObject` con il tuo oggetto query costruito. Considera però i seguenti punti:

    * Perché il valore restituito del metodo `getLineQueryObject` è `SysDaQueryObject`, è necessario costruire questo oggetto utilizzando l'approccio SysDa.
    * Non è possibile rimuovere la tabella esistente.

- I dati richiesti sono correlati alla tabella delle transazioni da una complicata relazione di join, oppure la relazione non è uno a uno (1:1) ma uno a molti (1:N). In questa situazione, le cose diventano un po' più complicate. Questa situazione si applica all'esempio delle dimensioni finanziarie. 

    In questa situazione, puoi implementare il tuo metodo per recuperare i dati. Ecco il codice di esempio nel file `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a>Passaggio 3. Aggiungere dati alla richiesta

Estendi il metodo `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` o `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` per aggiungere dati alla richiesta. Ecco il codice di esempio nel file `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```

In questo codice, `_destination` è l'oggetto wrapper utilizzato per generare la richiesta di registrazione e `_source` è l'oggetto `TaxIntegrationLineObject`. 

> [!NOTE]
> * Definisci la chiave utilizzata nel modulo di richiesta come `private const str`.
> * Imposta il campo nel metodo `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` utilizzando il metodo `SetField`. Il tipo di dati del secondo parametro deve essere `string`. Se il tipo di dati non è `string`, convertilo in `string`.

## <a name="appendix"></a>Appendice

Questa appendice mostra il codice di esempio completo per l'integrazione delle dimensioni finanziarie (**Centro di costo** e **Progetto**) a livello di riga.

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
