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
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a><span data-ttu-id="c80fa-103">Aggiungere campi dati nell'integrazione fiscale usando l'estensione</span><span class="sxs-lookup"><span data-stu-id="c80fa-103">Add data fields in the tax integration by using extension</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c80fa-104">In questo argomento viene illustrato come usare le estensioni X++ per aggiungere campi dati nell'integrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="c80fa-104">This topic explains how to use X++ extensions to add data fields in the tax integration.</span></span> <span data-ttu-id="c80fa-105">Questi campi possono essere estesi al modello di dati fiscali del servizio per le imposte e utilizzati per determinare i codici imposta.</span><span class="sxs-lookup"><span data-stu-id="c80fa-105">These fields can be extended to the tax data model of the tax service and used to determine tax codes.</span></span> <span data-ttu-id="c80fa-106">Per ulteriori informazioni, vedi [Aggiungere campi dati nelle configurazioni imposte](tax-service-add-data-fields-tax-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="c80fa-106">For more information, see [Add data fields in tax configurations](tax-service-add-data-fields-tax-configurations.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="c80fa-107">Modello dati</span><span class="sxs-lookup"><span data-stu-id="c80fa-107">Data model</span></span>

<span data-ttu-id="c80fa-108">I dati nel modello di dati sono forniti dagli oggetti e implementati dalle classi.</span><span class="sxs-lookup"><span data-stu-id="c80fa-108">The data in the data model is carried by objects and implemented by classes.</span></span>

<span data-ttu-id="c80fa-109">Ecco un elenco degli oggetti principali:</span><span class="sxs-lookup"><span data-stu-id="c80fa-109">Here is a list of the major objects:</span></span>

* <span data-ttu-id="c80fa-110">AxClass/TaxIntegration **Document** Object</span><span class="sxs-lookup"><span data-stu-id="c80fa-110">AxClass/TaxIntegration **Document** Object</span></span>
* <span data-ttu-id="c80fa-111">AxClass/TaxIntegration **Line** Object</span><span class="sxs-lookup"><span data-stu-id="c80fa-111">AxClass/TaxIntegration **Line** Object</span></span>
* <span data-ttu-id="c80fa-112">AxClass/TaxIntegration **TaxLine** Object</span><span class="sxs-lookup"><span data-stu-id="c80fa-112">AxClass/TaxIntegration **TaxLine** Object</span></span>

<span data-ttu-id="c80fa-113">Nella figura seguente viene illustrato come questi oggetti sono correlati.</span><span class="sxs-lookup"><span data-stu-id="c80fa-113">The following illustration shows how these objects are related.</span></span>

<span data-ttu-id="c80fa-114">[![Relazione degli oggetti del modello di dati](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span><span class="sxs-lookup"><span data-stu-id="c80fa-114">[![Data model object relationship](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span></span>

<span data-ttu-id="c80fa-115">Un oggetto **Documento** può contenere molti oggetti **Riga**.</span><span class="sxs-lookup"><span data-stu-id="c80fa-115">A **Document** object can contain many **Line** objects.</span></span> <span data-ttu-id="c80fa-116">Ogni oggetto contiene metadati per il servizio per le imposte.</span><span class="sxs-lookup"><span data-stu-id="c80fa-116">Each object contains metadata for the tax service.</span></span>

- <span data-ttu-id="c80fa-117">`TaxIntegrationDocumentObject` contiene metadati `originAddress`, che contengono informazioni sull'indirizzo di origine, e metadati `includingTax`, che indicano se l'importo della riga include l'IVA.</span><span class="sxs-lookup"><span data-stu-id="c80fa-117">`TaxIntegrationDocumentObject` has `originAddress` metadata, which contains information about the source address, and `includingTax` metadata, which indicates whether the line amount includes sales tax.</span></span>
- <span data-ttu-id="c80fa-118">`TaxIntegrationLineObject` contiene i metadati `itemId`, `quantity` e `categoryId`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-118">`TaxIntegrationLineObject` has `itemId`, `quantity`, and `categoryId` metadata.</span></span>

> [!NOTE]
> <span data-ttu-id="c80fa-119">`TaxIntegrationLineObject` implementa anche gli oggetti **Addebito**.</span><span class="sxs-lookup"><span data-stu-id="c80fa-119">`TaxIntegrationLineObject` also implements **Charge** objects.</span></span>

## <a name="integration-flow"></a><span data-ttu-id="c80fa-120">Flusso di integrazione</span><span class="sxs-lookup"><span data-stu-id="c80fa-120">Integration flow</span></span>

<span data-ttu-id="c80fa-121">I dati nel flusso vengono gestiti dalle attività.</span><span class="sxs-lookup"><span data-stu-id="c80fa-121">The data in the flow is manipulated by activities.</span></span>

### <a name="key-activities"></a><span data-ttu-id="c80fa-122">Attività chiave</span><span class="sxs-lookup"><span data-stu-id="c80fa-122">Key activities</span></span>

* <span data-ttu-id="c80fa-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="c80fa-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span></span>
* <span data-ttu-id="c80fa-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="c80fa-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span></span>
* <span data-ttu-id="c80fa-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="c80fa-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span></span>
* <span data-ttu-id="c80fa-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="c80fa-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span></span>
* <span data-ttu-id="c80fa-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="c80fa-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span></span>

<span data-ttu-id="c80fa-128">Le attività vengono eseguite nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="c80fa-128">Activities are run in the following order:</span></span>

1. <span data-ttu-id="c80fa-129">Recupero impostazione</span><span class="sxs-lookup"><span data-stu-id="c80fa-129">Setting Retrieval</span></span>
2. <span data-ttu-id="c80fa-130">Recupero dati</span><span class="sxs-lookup"><span data-stu-id="c80fa-130">Data Retrieval</span></span>
3. <span data-ttu-id="c80fa-131">Servizio di calcolo</span><span class="sxs-lookup"><span data-stu-id="c80fa-131">Calculation Service</span></span>
4. <span data-ttu-id="c80fa-132">Cambio valuta</span><span class="sxs-lookup"><span data-stu-id="c80fa-132">Currency Exchange</span></span>
5. <span data-ttu-id="c80fa-133">Persistenza dei dati</span><span class="sxs-lookup"><span data-stu-id="c80fa-133">Data Persistence</span></span>

<span data-ttu-id="c80fa-134">Ad esempio, estendi **Recupero dati** prima del **Servizio di calcolo**.</span><span class="sxs-lookup"><span data-stu-id="c80fa-134">For example, extend **Data Retrieval** before **Calculation Service**.</span></span>

#### <a name="data-retrieval-activities"></a><span data-ttu-id="c80fa-135">Attività di recupero dati</span><span class="sxs-lookup"><span data-stu-id="c80fa-135">Data Retrieval activities</span></span>

<span data-ttu-id="c80fa-136">Le attività di **recupero dati** recuperano i dati dal database.</span><span class="sxs-lookup"><span data-stu-id="c80fa-136">**Data Retrieval** activities retrieve data from the database.</span></span> <span data-ttu-id="c80fa-137">Adattatori per transazioni diverse sono disponibili per recuperare i dati da tabelle di transazioni diverse:</span><span class="sxs-lookup"><span data-stu-id="c80fa-137">Adapters for different transactions are available to retrieve data from different transaction tables:</span></span>

- <span data-ttu-id="c80fa-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="c80fa-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span></span>
- <span data-ttu-id="c80fa-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="c80fa-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span></span>
- <span data-ttu-id="c80fa-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="c80fa-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span></span>
- <span data-ttu-id="c80fa-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="c80fa-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span></span>
- <span data-ttu-id="c80fa-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="c80fa-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span></span>
- <span data-ttu-id="c80fa-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="c80fa-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span></span>
- <span data-ttu-id="c80fa-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="c80fa-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span></span>

<span data-ttu-id="c80fa-145">In queste attività di **recupero dati**, i dati vengono copiati dal database in `TaxIntegrationDocumentObject` e `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-145">In these **Data Retrieval** activities, data is copied from the database to `TaxIntegrationDocumentObject` and `TaxIntegrationLineObject`.</span></span> <span data-ttu-id="c80fa-146">Poiché tutte queste attività estendono la stessa classe di modelli astratta, hanno metodi comuni.</span><span class="sxs-lookup"><span data-stu-id="c80fa-146">Because all these activities extend the same abstract template class, they have common methods.</span></span>

#### <a name="calculation-service-activities"></a><span data-ttu-id="c80fa-147">Attività del servizio di calcolo</span><span class="sxs-lookup"><span data-stu-id="c80fa-147">Calculation Service activities</span></span>

<span data-ttu-id="c80fa-148">L'attività **Servizio di calcolo** è il collegamento tra il servizio per le imposte e l'integrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="c80fa-148">The **Calculation Service** activity is the link between the tax service and the tax integration.</span></span> <span data-ttu-id="c80fa-149">Questa attività è responsabile delle seguenti funzioni:</span><span class="sxs-lookup"><span data-stu-id="c80fa-149">This activity is responsible for the following functions:</span></span>

1. <span data-ttu-id="c80fa-150">Costruire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c80fa-150">Construct the request.</span></span>
2. <span data-ttu-id="c80fa-151">Registrare la richiesta nel servizio per le imposte.</span><span class="sxs-lookup"><span data-stu-id="c80fa-151">Post the request to the tax service.</span></span>
3. <span data-ttu-id="c80fa-152">Ottenere la risposta dal servizio per le imposte.</span><span class="sxs-lookup"><span data-stu-id="c80fa-152">Get the response from the tax service.</span></span>
4. <span data-ttu-id="c80fa-153">Analizzare la risposta.</span><span class="sxs-lookup"><span data-stu-id="c80fa-153">Parse the response.</span></span>

<span data-ttu-id="c80fa-154">Un campo dati aggiunto alla richiesta verrà inviato insieme agli altri metadati.</span><span class="sxs-lookup"><span data-stu-id="c80fa-154">A data field that you add to the request will be posted together with other metadata.</span></span> 

## <a name="extension-implementation"></a><span data-ttu-id="c80fa-155">Implementazione dell'estensione</span><span class="sxs-lookup"><span data-stu-id="c80fa-155">Extension implementation</span></span>

<span data-ttu-id="c80fa-156">In questa sezione vengono descritti i passaggi dettagliati che spiegano come implementare l'estensione.</span><span class="sxs-lookup"><span data-stu-id="c80fa-156">This section provides detailed steps that explain how to implement the extension.</span></span> <span data-ttu-id="c80fa-157">Ad esempio, vengono utilizzate le dimensioni finanziarie **Centro di costo** e **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="c80fa-157">It uses the **Cost center** and **Project** financial dimensions as examples.</span></span>

### <a name="step-1-add-the-data-variable-in-the-object-class"></a><span data-ttu-id="c80fa-158">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="c80fa-158">Step 1.</span></span> <span data-ttu-id="c80fa-159">Aggiungere la variabile dati nella classe oggetto</span><span class="sxs-lookup"><span data-stu-id="c80fa-159">Add the data variable in the object class</span></span>

<span data-ttu-id="c80fa-160">La classe oggetto contiene la variabile di dati e i metodi getter/setter per i dati.</span><span class="sxs-lookup"><span data-stu-id="c80fa-160">The object class contains the data variable and getter/setter methods for the data.</span></span> <span data-ttu-id="c80fa-161">Aggiungi il campo dati a `TaxIntegrationDocumentObject` o a `TaxIntegrationLineObject`, a seconda del livello del campo.</span><span class="sxs-lookup"><span data-stu-id="c80fa-161">Add the data field to either `TaxIntegrationDocumentObject` or `TaxIntegrationLineObject`, depending on the level of the field.</span></span> <span data-ttu-id="c80fa-162">L'esempio seguente utilizza il livello di riga e il nome del file è `TaxIntegrationLineObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-162">The following example uses the line level, and the file name is `TaxIntegrationLineObject_Extension.xpp`.</span></span>

> [!NOTE]
> <span data-ttu-id="c80fa-163">Se il campo dati che stai aggiungendo è a livello di documento, cambia il nome del file in `TaxIntegrationDocumentObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-163">If the data field that you're adding is at the document level, change the file name to `TaxIntegrationDocumentObject_Extension.xpp`.</span></span>

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

<span data-ttu-id="c80fa-164">**Centro di costo** e **Progetto** vengono aggiunti come variabili private.</span><span class="sxs-lookup"><span data-stu-id="c80fa-164">**Cost center** and **Project** are added as private variables.</span></span> <span data-ttu-id="c80fa-165">Crea metodi getter e setter per questi campi dati per manipolare i dati.</span><span class="sxs-lookup"><span data-stu-id="c80fa-165">Create getter and setter methods for these data fields to manipulate the data.</span></span>

### <a name="step-2-retrieve-data-from-the-database"></a><span data-ttu-id="c80fa-166">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="c80fa-166">Step 2.</span></span> <span data-ttu-id="c80fa-167">Recuperare i dati dal database</span><span class="sxs-lookup"><span data-stu-id="c80fa-167">Retrieve data from the database</span></span>

<span data-ttu-id="c80fa-168">Specifica la transazione ed estendi le classi dell'adattatore appropriate per recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="c80fa-168">Specify the transaction, and extend the appropriate adapter classes to retrieve the data.</span></span> <span data-ttu-id="c80fa-169">Ad esempio, se utilizzi una transazione **Ordine fornitore**, è necessario estendere `TaxIntegrationPurchTableDataRetrieval` e `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-169">For example, if you use a **Purchase order** transaction, you must extend `TaxIntegrationPurchTableDataRetrieval` and `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span></span> 

> [!NOTE]
> <span data-ttu-id="c80fa-170">`TaxIntegrationPurchParmTableDataRetrieval` è ereditato da `TaxIntegrationPurchTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-170">`TaxIntegrationPurchParmTableDataRetrieval` is inherited from `TaxIntegrationPurchTableDataRetrieval`.</span></span> <span data-ttu-id="c80fa-171">Non deve essere modificato a meno che la logica delle tabelle `purchTable` e `purchParmTable` è diversa.</span><span class="sxs-lookup"><span data-stu-id="c80fa-171">It should not be changed unless the logic of the `purchTable` and `purchParmTable` tables differs.</span></span>

<span data-ttu-id="c80fa-172">Se il campo dati deve essere aggiunto per tutte le transazioni, estendi tutte le classi `DataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-172">If the data field should be added for all transactions, extend all `DataRetrieval` classes.</span></span>

<span data-ttu-id="c80fa-173">Perché tutte le attività **Recupero dati** estendono la stessa classe modello, le strutture della classe, le variabili e i metodi sono simili.</span><span class="sxs-lookup"><span data-stu-id="c80fa-173">Because all **Data Retrieval** activities extend the same template class, the class structures, variables, and methods are similar.</span></span>

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

<span data-ttu-id="c80fa-174">L'esempio seguente mostra la struttura di base quando la tabella `PurchTable` viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="c80fa-174">The following example shows the basic structure when the `PurchTable` table is used.</span></span>

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

<span data-ttu-id="c80fa-175">Quando il metodo `CopyToDocument` viene chiamato, il buffer `this.purchTable` è già esistente.</span><span class="sxs-lookup"><span data-stu-id="c80fa-175">When the `CopyToDocument` method is called, the `this.purchTable` buffer already exists.</span></span> <span data-ttu-id="c80fa-176">Lo scopo di questo metodo è copiare tutti i dati richiesti da `this.purchTable` nell'oggetto `document` utilizzando il metodo setter creato nella classe `DocumentObject`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-176">The purpose of this method is to copy all the required data from `this.purchTable` to the `document` object by using the setter method that was created in the `DocumentObject` class.</span></span>

<span data-ttu-id="c80fa-177">Allo stesso modo, un buffer `this.purchLine` esiste già nel metodo `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-177">Likewise, a `this.purchLine` buffer already exists in the `CopyToLine` method.</span></span> <span data-ttu-id="c80fa-178">Lo scopo di questo metodo è copiare tutti i dati richiesti da `this.purchLine` nell'oggetto `_line` utilizzando il metodo setter creato nella classe `LineObject`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-178">The purpose of this method is to copy all the required data from `this.purchLine` to the `_line` object by using the setter method that was created in the `LineObject` class.</span></span>

<span data-ttu-id="c80fa-179">L'approccio più semplice è estendere i metodi `CopyToDocument` e `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-179">The most straightforward approach is to extend the `CopyToDocument` and `CopyToLine` methods.</span></span> <span data-ttu-id="c80fa-180">Tuttavia, ti consigliamo di provare prima i metodi `copyToDocumentFromHeaderTable` e `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-180">However, we recommend that you try the `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable` methods first.</span></span> <span data-ttu-id="c80fa-181">Se non funzionano come richiesto, implementa il tuo metodo e chiamalo in `CopyToDocument` e `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-181">If they don't work as you require, implement your own method, and call it in `CopyToDocument` and `CopyToLine`.</span></span> <span data-ttu-id="c80fa-182">Esistono tre situazioni comuni in cui potresti utilizzare questo approccio:</span><span class="sxs-lookup"><span data-stu-id="c80fa-182">There are three common situations where you might use this approach:</span></span>

- <span data-ttu-id="c80fa-183">Il campo obbligatorio è in `PurchTable` o `PurchLine`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-183">The required field is in `PurchTable` or `PurchLine`.</span></span> <span data-ttu-id="c80fa-184">In questa situazione, puoi estendere `copyToDocumentFromHeaderTable` e `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-184">In this situation, you can extend `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable`.</span></span> <span data-ttu-id="c80fa-185">Ecco il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="c80fa-185">Here is the sample code.</span></span>

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

- <span data-ttu-id="c80fa-186">I dati richiesti non sono nella tabella predefinita della transazione.</span><span class="sxs-lookup"><span data-stu-id="c80fa-186">The required data isn't in the default table of the transaction.</span></span> <span data-ttu-id="c80fa-187">Tuttavia, esistono alcune relazioni di join con la tabella predefinita e il campo è obbligatorio nella maggior parte delle righe.</span><span class="sxs-lookup"><span data-stu-id="c80fa-187">However, there are some join relationships with the default table, and the field is required on most lines.</span></span> <span data-ttu-id="c80fa-188">In questa situazione, sostituisci `getDocumentQueryObject` o `getLineObject` per eseguire query sulla tabella in base alla relazione di join.</span><span class="sxs-lookup"><span data-stu-id="c80fa-188">In this situation, replace `getDocumentQueryObject` or `getLineObject` to query the table by join relationship.</span></span> <span data-ttu-id="c80fa-189">Nell'esempio seguente, il campo **Consegna ora** è integrato con l'ordine cliente a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="c80fa-189">In the following example, the **Deliver Now** field is integrated with the sales order at the line level.</span></span>

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

    <span data-ttu-id="c80fa-190">In questo esempio, un buffer `mcrSalesLineDropShipment` viene dichiarato e la query viene definita in `getLineQueryObject`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-190">In this example, a `mcrSalesLineDropShipment` buffer is declared, and the query is defined in `getLineQueryObject`.</span></span> <span data-ttu-id="c80fa-191">La query utilizza la relazione `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-191">The query uses the relationship `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span></span> <span data-ttu-id="c80fa-192">In questa situazione, puoi sostituire `getLineQueryObject` con il tuo oggetto query costruito.</span><span class="sxs-lookup"><span data-stu-id="c80fa-192">While you're extending in this situation, you can replace `getLineQueryObject` with your own constructed query object.</span></span> <span data-ttu-id="c80fa-193">Considera però i seguenti punti:</span><span class="sxs-lookup"><span data-stu-id="c80fa-193">However, note the following points:</span></span>

    * <span data-ttu-id="c80fa-194">Perché il valore restituito del metodo `getLineQueryObject` è `SysDaQueryObject`, è necessario costruire questo oggetto utilizzando l'approccio SysDa.</span><span class="sxs-lookup"><span data-stu-id="c80fa-194">Because the return value of the `getLineQueryObject` method is `SysDaQueryObject`, you must construct this object by using the SysDa approach.</span></span>
    * <span data-ttu-id="c80fa-195">Non è possibile rimuovere la tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="c80fa-195">Can't remove existed table.</span></span>

- <span data-ttu-id="c80fa-196">I dati richiesti sono correlati alla tabella delle transazioni da una complicata relazione di join, oppure la relazione non è uno a uno (1:1) ma uno a molti (1:N).</span><span class="sxs-lookup"><span data-stu-id="c80fa-196">The required data is related to the transaction table by a complicated join relationship, or the relation isn't one to one (1:1) but one to many (1:N).</span></span> <span data-ttu-id="c80fa-197">In questa situazione, le cose diventano un po' più complicate.</span><span class="sxs-lookup"><span data-stu-id="c80fa-197">In this situation, things become a little complicated.</span></span> <span data-ttu-id="c80fa-198">Questa situazione si applica all'esempio delle dimensioni finanziarie.</span><span class="sxs-lookup"><span data-stu-id="c80fa-198">This situation applies to the example of financial dimensions.</span></span> 

    <span data-ttu-id="c80fa-199">In questa situazione, puoi implementare il tuo metodo per recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="c80fa-199">In this situation, you can implement your own method to retrieve the data.</span></span> <span data-ttu-id="c80fa-200">Ecco il codice di esempio nel file `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-200">Here is the sample code in the `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` file.</span></span>

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

### <a name="step-3-add-data-to-the-request"></a><span data-ttu-id="c80fa-201">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="c80fa-201">Step 3.</span></span> <span data-ttu-id="c80fa-202">Aggiungere dati alla richiesta</span><span class="sxs-lookup"><span data-stu-id="c80fa-202">Add data to the request</span></span>

<span data-ttu-id="c80fa-203">Estendi il metodo `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` o `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` per aggiungere dati alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="c80fa-203">Extend the `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` or `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method to add data to the request.</span></span> <span data-ttu-id="c80fa-204">Ecco il codice di esempio nel file `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-204">Here is the sample code in the `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` file.</span></span>

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

<span data-ttu-id="c80fa-205">In questo codice, `_destination` è l'oggetto wrapper utilizzato per generare la richiesta di registrazione e `_source` è l'oggetto `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-205">In this code, `_destination` is the wrapper object that is used to generate the post request, and `_source` is the `TaxIntegrationLineObject` object.</span></span> 

> [!NOTE]
> * <span data-ttu-id="c80fa-206">Definisci la chiave utilizzata nel modulo di richiesta come `private const str`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-206">Define the key that is used in the request form as `private const str`.</span></span>
> * <span data-ttu-id="c80fa-207">Imposta il campo nel metodo `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` utilizzando il metodo `SetField`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-207">Set the field in the `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method by using the `SetField` method.</span></span> <span data-ttu-id="c80fa-208">Il tipo di dati del secondo parametro deve essere `string`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-208">The data type of the second parameter should be `string`.</span></span> <span data-ttu-id="c80fa-209">Se il tipo di dati non è `string`, convertilo in `string`.</span><span class="sxs-lookup"><span data-stu-id="c80fa-209">If the data type isn't `string`, convert it to `string`.</span></span>

## <a name="appendix"></a><span data-ttu-id="c80fa-210">Appendice</span><span class="sxs-lookup"><span data-stu-id="c80fa-210">Appendix</span></span>

<span data-ttu-id="c80fa-211">Questa appendice mostra il codice di esempio completo per l'integrazione delle dimensioni finanziarie (**Centro di costo** e **Progetto**) a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="c80fa-211">This appendix shows the complete sample code for the integration of financial dimensions (**Cost center** and **Project**) at the line level.</span></span>

### <a name="taxintegrationlineobject_extensionxpp"></a><span data-ttu-id="c80fa-212">TaxIntegrationLineObject_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="c80fa-212">TaxIntegrationLineObject_Extension.xpp</span></span>

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

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a><span data-ttu-id="c80fa-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="c80fa-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span></span>

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

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a><span data-ttu-id="c80fa-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="c80fa-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span></span>

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
