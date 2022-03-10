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
ms.openlocfilehash: 1857d2e35e369bcd0c8f02a059a307f31da8b3b9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067456"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>Ottimizzare le query di tabelle virtuali di Dataverse


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>Uscita

### <a name="overview"></a>Panoramica

Quando si usano le tabelle virtuali di Dataverse per sviluppare integrazioni e altre connessioni dati con Dynamics 365 Human Resources, è possibile riscontrare problemi di prestazioni con le query sulle tabelle virtuali. Una lenta esecuzione delle query può verificarsi su vari client o interfacce. Ad esempio, si potrebbe riscontrare il problema nelle seguenti circostanze:

- Quando si esegue una query su una tabella virtuale tramite l'API Web Dataverse
- Quando si crea una Power App in una tabella virtuale
- Quando si crea un report Power BI in una tabella virtuale

Tutte queste interfacce hanno il potenziale per far emergere il problema di prestazioni.

Una delle cause del rallentamento delle prestazioni con le tabelle virtuali di Dataverse per Human Resources è rappresentata dalle le colonne di chiave esterna della tabella virtuale correlata alle [proprietà di navigazione](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties) della tabella. Quando le proprietà di navigazione vengono create per una tabella virtuale, una colonna di chiave esterna viene automaticamente aggiunta alla tabella per rappresentare il valore della chiave per la colonna chiave della tabella virtuale correlata. Ad esempio, la colonna **_mshr_fk_person_id_value** viene aggiunta alla entità **mshr_hcmworkerbaseentity** con la proprietà di chiave esterna dall'entità **mshr_dirpersonentity**. A causa del modo in cui i valori di queste colonne di chiave esterna vengono mantenuti in una tabella, il recupero dei valori può avere un impatto negativo sulle prestazioni di una query sulla tabella virtuale.

### <a name="potential-symptoms"></a>Potenziali sintomi

Un esempio in cui è possibile vedere questo impatto è rappresentato dalle query sull'entità Lavoratore (**mshr_hcmworkerentity**) o Lavoratore base (**mshr_hcmworkerbaseentity**). È possibile che il problema relativo alle prestazioni si manifesti in vari modi:

- **Lenta esecuzione delle query**: la query sulla tabella virtuale può restituire i risultati previsti, ma la sua esecuzione può richiedere più tempo del previsto.
- **Timeout della query**: è possibile che si verifichi il timeout della query e che venga restituito il seguente errore: "È stato ottenuto un token per chiamare Finanza e operazioni, ma Finanza e operazioni ha restituito un errore di tipo InternalServerError."
- **Errore imprevisto**: la query potrebbe restituire un errore 400 con il seguente messaggio: "Si è verificato un errore imprevisto."

  ![Errore 400 su HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType400.png)

- **Limitazione**: la query potrebbe utilizzare in modo eccessivo le risorse del server e diventare soggetta a limitazione. In tal caso, la query restituisce il seguente errore: "È stato ottenuto un token per chiamare Finanza e operazioni, ma Finanza e operazioni ha restituito un errore 429." Per ulteriori informazioni sulla limitazione in Human Resources, vedere [Domande frequenti sulla limitazione](./hr-admin-integration-throttling-faq.md).

  ![Errore 429 su HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>Risoluzione

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>Limitare il numero di colonne incluse nella query di dati

Con le tabelle virtuali, uno dei metodi più appropriati di migliorare le prestazioni delle query è limitare il numero di colonne selezionate nella query. In generale per ottimizzare le prestazioni delle query è necessario limitare le colonne restituite nella query solo alle proprietà necessarie. Ciò è particolarmente vero con le colonne di chiave esterna nelle tabelle virtuali. Se non sono necessari i valori nelle colonne di chiave esterna per l'integrazione o il report, strutturare la query per selezionare solo le colonne necessarie, escluse le colonne di chiave esterna.

#### <a name="selecting-columns-in-an-odata-query"></a>Selezione di colonne in una query OData

Quando si esegue una query su una tabella virtuale tramite l'API Web Dataverse, è possibile limitare il numero di colonne incluse nella query utilizzando l'opzione di query di sistema **$select** e definire le colonne per le quali è necessario restituire i risultati. Per massimizzare le prestazioni, escludere le colonne di chiave esterna (quelle con il prefisso **_mshr_FK_**) dalla query.

Ad esempio, la seguente query sull'entità **mshr_hcmworkerbaseentity** includerà solo le colonne incluse nella clausola dell'opzione di query **$select**, esclusi i valori di chiave esterna. Ciò fornisce miglioramenti significativi nelle prestazioni rispetto a una query che include tutte le colonne di tabella.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

La raccomandazione di limitare il numero di colonne selezionate si applica anche quando si utilizza l'opzione di query **$expand** per espandere la query alle tabelle virtuali correlate tramite le proprietà di navigazione. Ad esempio, la query seguente include colonne dell'entità **mshr_hcmworkerbaseentity** con colonne espanse dell'entità **mshr_dirpersonentity**. Da notare che l'opzione di query **$select** è inclusa anche nella clausola dell'opzione di query **$expand**.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

Quando si utilizza questo metodo di recupero dei dati con l'opzione di query **$select** nella clausola di opzione di query **$expand**, in genere si noteranno maggiori miglioramenti delle prestazioni quando la proprietà di navigazione tra le entità è una relazione molti-a-uno. È possibile non osservare la stessa diminuzione nel tempo di esecuzione delle query quando si espande una relazione uno-a-molti. Per ulteriori informazioni sulla definizione della relazione per le tabelle virtuali di Dataverse, vedere [Relazioni tra tabelle](/powerapps/maker/data-platform/create-edit-entity-relationships).

Per ulteriori informazioni sull'utilizzo delle opzioni di query di sistema **$select** e **$expand** nell'API Web Dataverse, vedi [Recupera record di entità correlate con una query](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).

#### <a name="selecting-columns-in-power-bi"></a>Selezione di colonne in Power BI

Se si verifica uno dei suddetti segnali di peggioramento delle prestazioni durante la creazione di un report Power BI su una tabella virtuale Dataverse, è possibile migliorare le prestazioni escludendo le colonne di chiave esterna dalle colonne selezionate nella tabella per il report. Ad esempio, se si utilizza Power BI Desktop per creare un report sull'entità **mshr_hcmworkerbaseentity**, è possibile utilizzare i seguenti passaggi per selezionare le colonne che si desidera includere nella query del report.

1. In Power BI Desktop, selezionare **Altro** nell'elenco a discesa **Ottieni dati** nella barra multifunzione.
2. Nella finestra **Ottieni dati**, immettere **Common Data Service** nella casella di ricerca, selezionare il connettore **Common Data Service** e selezionare **Connetti**.
3. Nel campo **URL server** della finestra Common Data Service, immettere l'URI dell'organizzazione per l'ambiente Dataverse in uso e selezionare **OK**.
  
   ![Immettere l'URI per l'ambiente Dataverse.](./media/PowerBIDataverseURLSetup.png)
  
4. Nella finestra del navigatore, espandere il nodo **Entità**.
5. Nella casella di ricerca, immettere **mshr_hcmworkerbaseentity** e selezionare l'entità.
6. Selezionare **Trasforma dati**.
7. Nella finestra dell'editor di Power Query selezionare **Editor avanzato**.
8. Nella finestra **Editor avanzato**, aggiornare la query in modo che assomigli alla seguente, aggiungendo o rimuovendo eventuali colonne dall'array come necessario.

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Aggiornare la query nell'editor avanzato per l'editor di Power Query.](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. Selezionare **Fine**.

   > [!NOTE]
   > Se in precedenza è stato visualizzato un errore 429 dalla query prima dell'aggiornamento, potrebbe essere necessario attendere il periodo di nuovo tentativo prima di aggiornare la query affinché venga completata correttamente.

10. Fare clic su **Chiudi e applica** nella barra multifunzione dell'editor di Power Query.

È quindi possibile iniziare a creare il report di Power BI sulle colonne selezionate della tabella virtuale.

#### <a name="selecting-columns-in-power-apps"></a>Selezionare colonne in Power Apps

Analogamente alle query dell'API Web Dataverse e a Power BI, è possibile migliorare le prestazioni delle query per Power Apps basate sulle tabelle virtuali di Dataverse escludendo colonne di tabelle correlate dall'app. Se in una pagina sono state incluse colonne di una tabella correlata, l'URL della richiesta creato per recuperare i dati includerà le proprietà della chiave esterna della tabella correlata. Come negli esempi della sezione [Selezione di colonne in una query OData](#selecting-columns-in-power-apps) sopra, ciò riduce le prestazioni provocando ulteriori ricerche di dati.

Per ovviare a questo problema, è possibile verificare che nessun campo dati delle tabelle correlate sia stato incluso in alcun modulo dati della Power App.

1. Nel riquadro della visualizzazione struttura ad albero, selezionare il modulo dati per lo schermo.
2. Nel riquadro **Proprietà**, selezionare **Modifica** nella proprietà **Campi**.
3. Nel riquadro **Dati**, verificare che nessuno dei campi selezionati sia un campo della tabella virtuale dell'origine dati.

Ad esempio, se uno dei campi dati inclusi in una pagina nell'app fa riferimento a un'altra tabella, come **ThisItem.Worker.Name**, dove **Worker** è la tabella correlata, un peggioramento delle prestazioni nel recupero dei dati è possibile.

È possibile usare [Power Apps Monitor](/powerapps/maker/monitor-overview) per garantire che solo le colonne necessarie siano incluse nella query per ottenere i dati per la Power App. È possibile visualizzare l'URL creato per l'operazione getRows per assicurarsi che le colonne selezionate per l'app siano ottimali per il recupero dei dati.

![Utilizzare Power Apps Monitor per analizzare l'operazione getData.](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>Filtro della query di dati

Un altro metodo per migliorare le prestazioni di esecuzione delle query consiste nel limitare il numero di record restituiti nei risultati della query. Ciò è possibile filtrando i risultati per assicurarsi di ricevere solo i record necessari.

Vedere [Filtrare i risultati](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) per ulteriori informazioni sul filtro dei dati delle query.

### <a name="limiting-the-page-size-of-the-query"></a>Limitazione delle dimensioni della pagina della query

Se si utilizzano set di dati di grandi dimensioni, è possibile dividere i risultati della query in più pagine aggiungendo l'intestazione della preferenza `odata.maxpagesize` alle query di dati.

Per ulteriori informazioni sulla paginazione, vedere [Specificare il numero di entità da restituire in una pagina](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).

## <a name="see-also"></a>Vedere anche

- [Configurare tabelle virtuali in Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
- [Domande frequenti sulle tabelle virtuali di Human Resources](hr-admin-virtual-entity-faq.md)
- [Domande frequenti sulla limitazione](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
