---
title: Ottimizzare le query di tabelle virtuali di Dataverse
description: Ottimizzare e risolvere i problemi relativi alle prestazioni delle query di tabelle virtuali di Dataverse
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66fb9f2b50079b5eb4eb16da17b8a473d687d354
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054910"
---
# <a name="optimize-dataverse-virtual-table-queries"></a><span data-ttu-id="8a57b-103">Ottimizzare le query di tabelle virtuali di Dataverse</span><span class="sxs-lookup"><span data-stu-id="8a57b-103">Optimize Dataverse virtual table queries</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="8a57b-104">Uscita</span><span class="sxs-lookup"><span data-stu-id="8a57b-104">Issue</span></span>

### <a name="overview"></a><span data-ttu-id="8a57b-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="8a57b-105">Overview</span></span>

<span data-ttu-id="8a57b-106">Quando si usano le tabelle virtuali di Dataverse per sviluppare integrazioni e altre connessioni dati con Dynamics 365 Human Resources, è possibile riscontrare problemi di prestazioni con le query sulle tabelle virtuali.</span><span class="sxs-lookup"><span data-stu-id="8a57b-106">When using Dataverse virtual tables to develop integrations and other data connections with Dynamics 365 Human Resources, you can experience performance issues with queries against the virtual tables.</span></span> <span data-ttu-id="8a57b-107">Una lenta esecuzione delle query può verificarsi su vari client o interfacce.</span><span class="sxs-lookup"><span data-stu-id="8a57b-107">The slow query execution can occur across various clients or interfaces.</span></span> <span data-ttu-id="8a57b-108">Ad esempio, si potrebbe riscontrare il problema nelle seguenti circostanze:</span><span class="sxs-lookup"><span data-stu-id="8a57b-108">For example, you may experience the issue in the following circumstances:</span></span>

- <span data-ttu-id="8a57b-109">Quando si esegue una query su una tabella virtuale tramite l'API Web Dataverse</span><span class="sxs-lookup"><span data-stu-id="8a57b-109">When querying a virtual table through the Dataverse Web API</span></span>
- <span data-ttu-id="8a57b-110">Quando si crea una Power App in una tabella virtuale</span><span class="sxs-lookup"><span data-stu-id="8a57b-110">When creating a Power App against a virtual table</span></span>
- <span data-ttu-id="8a57b-111">Quando si crea un report Power BI in una tabella virtuale</span><span class="sxs-lookup"><span data-stu-id="8a57b-111">When building a Power BI report on a virtual table</span></span>

<span data-ttu-id="8a57b-112">Tutte queste interfacce hanno il potenziale per far emergere il problema di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8a57b-112">All these interfaces have the potential to surface the performance issue.</span></span>

<span data-ttu-id="8a57b-113">Una delle cause del rallentamento delle prestazioni con le tabelle virtuali di Dataverse per Human Resources è rappresentata dalle le colonne di chiave esterna della tabella virtuale correlata alle [proprietà di navigazione](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties) della tabella.</span><span class="sxs-lookup"><span data-stu-id="8a57b-113">One cause of slow performance with Dataverse virtual tables for Human Resources is the foreign key columns of the virtual table related to the table's [navigation properties](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span></span> <span data-ttu-id="8a57b-114">Quando le proprietà di navigazione vengono create per una tabella virtuale, una colonna di chiave esterna viene automaticamente aggiunta alla tabella per rappresentare il valore della chiave per la colonna chiave della tabella virtuale correlata.</span><span class="sxs-lookup"><span data-stu-id="8a57b-114">When navigation properties are created for a virtual table, a foreign key column is automatically added to the table to represent the value of the key for the related virtual table's key column.</span></span> <span data-ttu-id="8a57b-115">Ad esempio, la colonna **_mshr_fk_person_id_value** viene aggiunta alla entità **mshr_hcmworkerbaseentity** con la proprietà di chiave esterna dall'entità **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-115">For example, the **_mshr_fk_person_id_value** column is added to the **mshr_hcmworkerbaseentity** entity with the foreign key property from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="8a57b-116">A causa del modo in cui i valori di queste colonne di chiave esterna vengono mantenuti in una tabella, il recupero dei valori può avere un impatto negativo sulle prestazioni di una query sulla tabella virtuale.</span><span class="sxs-lookup"><span data-stu-id="8a57b-116">Because of how the values for these foreign key columns are maintained in a table, fetching the values can have a negative impact on the performance of a query against the virtual table.</span></span>

### <a name="potential-symptoms"></a><span data-ttu-id="8a57b-117">Potenziali sintomi</span><span class="sxs-lookup"><span data-stu-id="8a57b-117">Potential symptoms</span></span>

<span data-ttu-id="8a57b-118">Un esempio in cui è possibile vedere questo impatto è rappresentato dalle query sull'entità Lavoratore (**mshr_hcmworkerentity**) o Lavoratore base (**mshr_hcmworkerbaseentity**).</span><span class="sxs-lookup"><span data-stu-id="8a57b-118">An example where you may see this impact is in queries against the Worker (**mshr_hcmworkerentity**) or Base worker (**mshr_hcmworkerbaseentity**) entity.</span></span> <span data-ttu-id="8a57b-119">È possibile che il problema relativo alle prestazioni si manifesti in vari modi:</span><span class="sxs-lookup"><span data-stu-id="8a57b-119">You may see the performance issue manifest itself in a few different ways:</span></span>

- <span data-ttu-id="8a57b-120">**Lenta esecuzione delle query**: la query sulla tabella virtuale può restituire i risultati previsti, ma la sua esecuzione può richiedere più tempo del previsto.</span><span class="sxs-lookup"><span data-stu-id="8a57b-120">**Slow query execution**: The query against the virtual table may return the expected results, but take longer than expected to complete execution of the query.</span></span>
- <span data-ttu-id="8a57b-121">**Timeout della query**: è possibile che si verifichi il timeout della query e che venga restituito il seguente errore: "È stato ottenuto un token per chiamare Finance and Operations, ma Finance and Operations ha restituito un errore di tipo InternalServerError."</span><span class="sxs-lookup"><span data-stu-id="8a57b-121">**Query timeout**: The query may time out and return the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type InternalServerError."</span></span>
- <span data-ttu-id="8a57b-122">**Errore imprevisto**: la query potrebbe restituire un errore 400 con il seguente messaggio: "Si è verificato un errore imprevisto."</span><span class="sxs-lookup"><span data-stu-id="8a57b-122">**Unexpected error**: The query may return an error type 400 with the following message: "An unexpected error occurred."</span></span>

  ![Errore 400 su HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType400.png)

- <span data-ttu-id="8a57b-124">**Limitazione**: la query potrebbe utilizzare in modo eccessivo le risorse del server e diventare soggetta a limitazione.</span><span class="sxs-lookup"><span data-stu-id="8a57b-124">**Throttling**: The query may overuse server resources, and become subject to throttling.</span></span> <span data-ttu-id="8a57b-125">In tal caso, la query restituisce il seguente errore: "È stato ottenuto un token per chiamare Finance and Operations, ma Finance and Operations ha restituito un errore 429."</span><span class="sxs-lookup"><span data-stu-id="8a57b-125">In this case, the query returns the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type 429."</span></span> <span data-ttu-id="8a57b-126">Per ulteriori informazioni sulla limitazione in Human Resources, vedere [Domande frequenti sulla limitazione](./hr-admin-integration-throttling-faq.md).</span><span class="sxs-lookup"><span data-stu-id="8a57b-126">For more information in throttling in Human Resources, see [Throttling FAQ](./hr-admin-integration-throttling-faq.md).</span></span>

  ![Errore 429 su HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a><span data-ttu-id="8a57b-128">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="8a57b-128">Resolution</span></span>

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a><span data-ttu-id="8a57b-129">Limitare il numero di colonne incluse nella query di dati</span><span class="sxs-lookup"><span data-stu-id="8a57b-129">Limit the number of columns included in your data query</span></span>

<span data-ttu-id="8a57b-130">Con le tabelle virtuali, uno dei metodi più appropriati di migliorare le prestazioni delle query è limitare il numero di colonne selezionate nella query.</span><span class="sxs-lookup"><span data-stu-id="8a57b-130">With virtual tables, one of the methods with the greatest potential to improve query performance is to limit the number of columns selected in the query.</span></span> <span data-ttu-id="8a57b-131">In generale per ottimizzare le prestazioni delle query è necessario limitare le colonne restituite nella query solo alle proprietà necessarie.</span><span class="sxs-lookup"><span data-stu-id="8a57b-131">The general guidance for optimizing query performance is to limit the columns returned in your query to only those properties that you need.</span></span> <span data-ttu-id="8a57b-132">Ciò è particolarmente vero con le colonne di chiave esterna nelle tabelle virtuali.</span><span class="sxs-lookup"><span data-stu-id="8a57b-132">This is particularly true with the foreign key columns on virtual tables.</span></span> <span data-ttu-id="8a57b-133">Se non sono necessari i valori nelle colonne di chiave esterna per l'integrazione o il report, strutturare la query per selezionare solo le colonne necessarie, escluse le colonne di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="8a57b-133">If you don't need the values in the foreign key columns for your integration or report, then structure the query to select only the columns you need, excluding the foreign key columns.</span></span>

#### <a name="selecting-columns-in-an-odata-query"></a><span data-ttu-id="8a57b-134">Selezione di colonne in una query OData</span><span class="sxs-lookup"><span data-stu-id="8a57b-134">Selecting columns in an OData query</span></span>

<span data-ttu-id="8a57b-135">Quando si esegue una query su una tabella virtuale tramite l'API Web Dataverse, è possibile limitare il numero di colonne incluse nella query utilizzando l'opzione di query di sistema **$select** e definire le colonne per le quali è necessario restituire i risultati.</span><span class="sxs-lookup"><span data-stu-id="8a57b-135">When querying a virtual table through the Dataverse Web API, you can limit the number of columns included in the query by using the **$select** system query option, and define the columns for which you need results returned.</span></span> <span data-ttu-id="8a57b-136">Per massimizzare le prestazioni, escludere le colonne di chiave esterna (quelle con il prefisso **_mshr_FK_**) dalla query.</span><span class="sxs-lookup"><span data-stu-id="8a57b-136">To maximize performance, exclude foreign key columns (those with the **_mshr_FK_** prefix) from the query.</span></span>

<span data-ttu-id="8a57b-137">Ad esempio, la seguente query sull'entità **mshr_hcmworkerbaseentity** includerà solo le colonne incluse nella clausola dell'opzione di query **$select**, esclusi i valori di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="8a57b-137">For example, the following query against the **mshr_hcmworkerbaseentity** entity will include only the columns included in the **$select** query option clause, excluding foreign key values.</span></span> <span data-ttu-id="8a57b-138">Ciò fornisce miglioramenti significativi nelle prestazioni rispetto a una query che include tutte le colonne di tabella.</span><span class="sxs-lookup"><span data-stu-id="8a57b-138">This provides significant improvements in performance over a query that includes all table columns.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="8a57b-139">La raccomandazione di limitare il numero di colonne selezionate si applica anche quando si utilizza l'opzione di query **$expand** per espandere la query alle tabelle virtuali correlate tramite le proprietà di navigazione.</span><span class="sxs-lookup"><span data-stu-id="8a57b-139">The recommendation to limit the number of columns selected also applies when using the **$expand** query option to expand the query to related virtual tables through navigation properties.</span></span> <span data-ttu-id="8a57b-140">Ad esempio, la query seguente include colonne dell'entità **mshr_hcmworkerbaseentity** con colonne espanse dell'entità **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-140">For example, the following query includes columns from the **mshr_hcmworkerbaseentity** entity with expanded columns from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="8a57b-141">Da notare che l'opzione di query **$select** è inclusa anche nella clausola dell'opzione di query **$expand**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-141">Note that the **$select** query option is also included in the **$expand** query option clause.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="8a57b-142">Quando si utilizza questo metodo di recupero dei dati con l'opzione di query **$select** nella clausola di opzione di query **$expand**, in genere si noteranno maggiori miglioramenti delle prestazioni quando la proprietà di navigazione tra le entità è una relazione molti-a-uno.</span><span class="sxs-lookup"><span data-stu-id="8a57b-142">When using this method of retrieving data with the **$select** query option in the **$expand** query option clause, you will typically see greater performance improvements when the navigation property between the entities is a many-to-one relationship.</span></span> <span data-ttu-id="8a57b-143">È possibile non osservare la stessa diminuzione nel tempo di esecuzione delle query quando si espande una relazione uno-a-molti.</span><span class="sxs-lookup"><span data-stu-id="8a57b-143">You may not see the same decrease in query execution time when expanding a one-to-many relationship.</span></span> <span data-ttu-id="8a57b-144">Per ulteriori informazioni sulla definizione della relazione per le tabelle virtuali di Dataverse, vedere [Relazioni tra tabelle](/powerapps/maker/data-platform/create-edit-entity-relationships).</span><span class="sxs-lookup"><span data-stu-id="8a57b-144">For more information on relationship definition for Dataverse virtual tables, see [Table relationships](/powerapps/maker/data-platform/create-edit-entity-relationships).</span></span>

<span data-ttu-id="8a57b-145">Per ulteriori informazioni sull'utilizzo delle opzioni di query di sistema **$select** e **$expand** nell'API Web Dataverse, vedi [Recupera record di entità correlate con una query](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span><span class="sxs-lookup"><span data-stu-id="8a57b-145">For more information on using the **$select** and **$expand** system query options in the Dataverse Web API, see [Retrieve related entity records with a query](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span></span>

#### <a name="selecting-columns-in-power-bi"></a><span data-ttu-id="8a57b-146">Selezione di colonne in Power BI</span><span class="sxs-lookup"><span data-stu-id="8a57b-146">Selecting columns in Power BI</span></span>

<span data-ttu-id="8a57b-147">Se si verifica uno dei suddetti segnali di peggioramento delle prestazioni durante la creazione di un report Power BI su una tabella virtuale Dataverse, è possibile migliorare le prestazioni escludendo le colonne di chiave esterna dalle colonne selezionate nella tabella per il report.</span><span class="sxs-lookup"><span data-stu-id="8a57b-147">If you experience any of the aforementioned indications of slow performance when building a Power BI report against a Dataverse virtual table, you can improve the performance by excluding foreign key columns from the columns selected from the table for the report.</span></span> <span data-ttu-id="8a57b-148">Ad esempio, se si utilizza Power BI Desktop per creare un report sull'entità **mshr_hcmworkerbaseentity**, è possibile utilizzare i seguenti passaggi per selezionare le colonne che si desidera includere nella query del report.</span><span class="sxs-lookup"><span data-stu-id="8a57b-148">For example, if you are using Power BI Desktop to create a report against the **mshr_hcmworkerbaseentity** entity, you can use the following steps to select the columns you want included in the report query.</span></span>

1. <span data-ttu-id="8a57b-149">In Power BI Desktop, selezionare **Altro** nell'elenco a discesa **Ottieni dati** nella barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="8a57b-149">In Power BI Desktop, select **More...** from the **Get data** drop-down list on the action ribbon.</span></span>
2. <span data-ttu-id="8a57b-150">Nella finestra **Ottieni dati**, immettere **Common Data Service** nella casella di ricerca, selezionare il connettore **Common Data Service** e selezionare **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-150">In the **Get Data** window, enter **Common Data Service** in the search box, select the **Common Data Service** connector, and select **Connect**.</span></span>
3. <span data-ttu-id="8a57b-151">Nel campo **URL server** della finestra Common Data Service, immettere l'URI dell'organizzazione per l'ambiente Dataverse in uso e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-151">In the **Server Url** field of the Common Data Service window, enter the organization URI for your Dataverse environment, and select **OK**.</span></span>
  
   ![Immettere l'URI per l'ambiente Dataverse](./media/PowerBIDataverseURLSetup.png)
  
4. <span data-ttu-id="8a57b-153">Nella finestra del navigatore, espandere il nodo **Entità**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-153">In the Navigator window, expand the **Entities** node.</span></span>
5. <span data-ttu-id="8a57b-154">Nella casella di ricerca, immettere **mshr_hcmworkerbaseentity** e selezionare l'entità.</span><span class="sxs-lookup"><span data-stu-id="8a57b-154">In the search box, enter **mshr_hcmworkerbaseentity**, and select the entity.</span></span>
6. <span data-ttu-id="8a57b-155">Selezionare **Trasforma dati**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-155">Select **Transform Data**.</span></span>
7. <span data-ttu-id="8a57b-156">Nella finestra dell'editor di Power Query selezionare **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-156">In the Power Query Editor window, select **Advanced Editor**.</span></span>
8. <span data-ttu-id="8a57b-157">Nella finestra **Editor avanzato**, aggiornare la query in modo che assomigli alla seguente, aggiungendo o rimuovendo eventuali colonne dall'array come necessario.</span><span class="sxs-lookup"><span data-stu-id="8a57b-157">In the **Advanced Editor** window, update the query to look like the below, adding or removing any columns to the array as needed.</span></span>

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Aggiornare la query nell'editor avanzato per l'editor di Power Query](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. <span data-ttu-id="8a57b-159">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-159">Select **Done**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8a57b-160">Se in precedenza è stato visualizzato un errore 429 dalla query prima dell'aggiornamento, potrebbe essere necessario attendere il periodo di nuovo tentativo prima di aggiornare la query affinché venga completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8a57b-160">If you previously received an error of type 429 from the query prior to updating, you may need to wait for the retry period prior to refreshing the query for it to complete successully.</span></span>

10. <span data-ttu-id="8a57b-161">Fare clic su **Chiudi e applica** nella barra multifunzione dell'editor di Power Query.</span><span class="sxs-lookup"><span data-stu-id="8a57b-161">Click **Close & Apply** on the Power Query Editor action ribbon.</span></span>

<span data-ttu-id="8a57b-162">È quindi possibile iniziare a creare il report di Power BI sulle colonne selezionate della tabella virtuale.</span><span class="sxs-lookup"><span data-stu-id="8a57b-162">You're then able to begin building your Power BI report against the columns selected from the virtual table.</span></span>

#### <a name="selecting-columns-in-power-apps"></a><span data-ttu-id="8a57b-163">Selezionare colonne in Power Apps</span><span class="sxs-lookup"><span data-stu-id="8a57b-163">Selecting columns in Power Apps</span></span>

<span data-ttu-id="8a57b-164">Analogamente alle query dell'API Web Dataverse e a Power BI, è possibile migliorare le prestazioni delle query per Power Apps basate sulle tabelle virtuali di Dataverse escludendo colonne di tabelle correlate dall'app.</span><span class="sxs-lookup"><span data-stu-id="8a57b-164">Similar to Dataverse Web API queries and Power BI, you can improve query performance for Power Apps based on Dataverse virtual tables by excluding columns of related tables from your app.</span></span> <span data-ttu-id="8a57b-165">Se in una pagina sono state incluse colonne di una tabella correlata, l'URL della richiesta creato per recuperare i dati includerà le proprietà della chiave esterna della tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="8a57b-165">If any columns from a related table have been included on a page, then the request URL constructed to fetch the data will include foreign key properties of the related table.</span></span> <span data-ttu-id="8a57b-166">Come negli esempi della sezione [Selezione di colonne in una query OData](#selecting-columns-in-power-apps) sopra, ciò riduce le prestazioni provocando ulteriori ricerche di dati.</span><span class="sxs-lookup"><span data-stu-id="8a57b-166">This, as in the examples of [Selecting columns in an OData Query](#selecting-columns-in-power-apps) above, reduces performance by causing additional data lookups.</span></span>

<span data-ttu-id="8a57b-167">Per ovviare a questo problema, è possibile verificare che nessun campo dati delle tabelle correlate sia stato incluso in alcun modulo dati della Power App.</span><span class="sxs-lookup"><span data-stu-id="8a57b-167">To work around this, you can validate that no data fields from related tables have been included on any data form of your Power App.</span></span>

1. <span data-ttu-id="8a57b-168">Nel riquadro della visualizzazione struttura ad albero, selezionare il modulo dati per lo schermo.</span><span class="sxs-lookup"><span data-stu-id="8a57b-168">In the Tree view pane, select the data form for the screen.</span></span>
2. <span data-ttu-id="8a57b-169">Nel riquadro **Proprietà**, selezionare **Modifica** nella proprietà **Campi**.</span><span class="sxs-lookup"><span data-stu-id="8a57b-169">In the **Properties** pane, select **Edit** on the **Fields** property.</span></span>
3. <span data-ttu-id="8a57b-170">Nel riquadro **Dati**, verificare che nessuno dei campi selezionati sia un campo della tabella virtuale dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8a57b-170">In the **Data** pane, verify that none of the selected fields are fields of the virtual table of the data source.</span></span>

<span data-ttu-id="8a57b-171">Ad esempio, se uno dei campi dati inclusi in una pagina nell'app fa riferimento a un'altra tabella, come **ThisItem.Worker.Name**, dove **Worker** è la tabella correlata, un peggioramento delle prestazioni nel recupero dei dati è possibile.</span><span class="sxs-lookup"><span data-stu-id="8a57b-171">For example, if one of the data fields included on a page in the app references another table, such as **ThisItem.Worker.Name**, where **Worker** is the related table, there is a potential for reduced performance in fetching the data.</span></span>

<span data-ttu-id="8a57b-172">È possibile usare [Power Apps Monitor](/powerapps/maker/monitor-overview) per garantire che solo le colonne necessarie siano incluse nella query per ottenere i dati per la Power App.</span><span class="sxs-lookup"><span data-stu-id="8a57b-172">You can use the [Power Apps Monitor](/powerapps/maker/monitor-overview) to ensure that only the columns you need are being included in the query to get the data for the Power App.</span></span> <span data-ttu-id="8a57b-173">È possibile visualizzare l'URL creato per l'operazione getRows per assicurarsi che le colonne selezionate per l'app siano ottimali per il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="8a57b-173">You can view the URL constructed for the getRows operation to ensure the columns you have selected for your app will be optimal for retrieving the data.</span></span>

![Utilizzare di Power Apps Monitor per analizzare l'operazione getData](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a><span data-ttu-id="8a57b-175">Filtro della query di dati</span><span class="sxs-lookup"><span data-stu-id="8a57b-175">Filtering the data query</span></span>

<span data-ttu-id="8a57b-176">Un altro metodo per migliorare le prestazioni di esecuzione delle query consiste nel limitare il numero di record restituiti nei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="8a57b-176">Another method for improving query execution performance is to limit the number of records returned in the query results.</span></span> <span data-ttu-id="8a57b-177">Ciò è possibile filtrando i risultati per assicurarsi di ricevere solo i record necessari.</span><span class="sxs-lookup"><span data-stu-id="8a57b-177">You can do this by filtering the results to ensure that you are only receiving the records you need.</span></span>

<span data-ttu-id="8a57b-178">Vedere [Filtrare i risultati](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) per ulteriori informazioni sul filtro dei dati delle query.</span><span class="sxs-lookup"><span data-stu-id="8a57b-178">See [Filter results](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) for more information on filtering query data.</span></span>

### <a name="limiting-the-page-size-of-the-query"></a><span data-ttu-id="8a57b-179">Limitazione delle dimensioni della pagina della query</span><span class="sxs-lookup"><span data-stu-id="8a57b-179">Limiting the page size of the query</span></span>

<span data-ttu-id="8a57b-180">Se si utilizzano set di dati di grandi dimensioni, è possibile dividere i risultati della query in più pagine aggiungendo l'intestazione della preferenza `odata.maxpagesize` alle query di dati.</span><span class="sxs-lookup"><span data-stu-id="8a57b-180">If you're working with large data sets, you can divide query results into multiple pages by adding the `odata.maxpagesize` preference header to data queries.</span></span>

<span data-ttu-id="8a57b-181">Per ulteriori informazioni sulla paginazione, vedere [Specificare il numero di entità da restituire in una pagina](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span><span class="sxs-lookup"><span data-stu-id="8a57b-181">For more information on paging, see [Specify the number of entities to return in a page](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a57b-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a57b-182">See also</span></span>

- [<span data-ttu-id="8a57b-183">Configurare tabelle virtuali in Dataverse</span><span class="sxs-lookup"><span data-stu-id="8a57b-183">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)
- [<span data-ttu-id="8a57b-184">Domande frequenti sulle tabelle virtuali di Human Resources</span><span class="sxs-lookup"><span data-stu-id="8a57b-184">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)
- [<span data-ttu-id="8a57b-185">Domande frequenti sulla limitazione</span><span class="sxs-lookup"><span data-stu-id="8a57b-185">Throttling FAQ</span></span>](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]