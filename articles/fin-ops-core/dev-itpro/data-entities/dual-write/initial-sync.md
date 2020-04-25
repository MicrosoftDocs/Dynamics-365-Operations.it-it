---
title: Catena delle dipendenze delle entità (ordine di sincronizzazione)
description: In questo argomento specifica l'ordine di sincronizzazione che è necessario seguire per creare i dati iniziali.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 4adb2c8d57ad8f67346b8d34212b7a4b0bd052ab
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173133"
---
# <a name="entity-dependency-chain-synchronization-order"></a>Catena delle dipendenze delle entità (ordine di sincronizzazione)

[!include [banner](../../includes/banner.md)]



Nelle seguenti tabelle le entità sono elencate nell'ordine in cui è necessario abilitarle. Quando si abilita una mappa per la sincronizzazione iniziale, la doppia scrittura rileva automaticamente altre mappe che devono essere abilitate. Puoi usare la pagina **Doppia scrittura** nelle app Finance and Operations per selezionare o annullare la selezione di entità durante la sincronizzazione iniziale.

Nell'ultima versione della doppia scrittura, è possibile abilitare solo alcune entità e le dipendenze vengono gestite automaticamente.

## <a name="dynamics-365-supply-chain-management-entities"></a>Entità Dynamics 365 Supply Chain Management

Le seguenti entità per Supply Chain Management sono elencate nell'ordine in cui è necessario abilitarle.

| Mappare il nome nella pagina di doppia scrittura | Nome dei metadati dell'entità in Supply Chain Management | Nome dei metadati dell'entità in Common Data Service | Note |
|---|---|---|---|
| Unità ... uoms                                                                      | UnitOfMeasureEntity                                    | uom                                          | |
| Conversioni di unità ... msdyn_unitofmeasureconversions                                 | UnitOfMeasureConversionEntity                          | msdyn_unitofmeasureconversion                | |
| Tutti i prodotti ... msdyn_globalproducts                                               | EcoResEveryProductEntity                               | msdyn_globalproduct                          | |
| Gruppi di dimensioni del prodotto ... msdyn_productdimensiongroups                           | EcoResProductDimensionGroupEntity                      | msdyn_productdimensiongroup                  | |
| Gruppi di dimensioni di immagazzinamento ... msdyn_productstoragedimensiongroups                    | EcoResStorageDimensionGroupEntity                      | msdyn_productstoragedimensiongroup           | |
| Gruppi di dimensioni di tracciabilità ... msdyn_producttrackingdimensiongroups                  | EcoResTrackingDimensionGroupEntity                     | msdyn_producttrackingdimensiongroup          | |
| Colori ... msdyn_productcolors                                                      | EcoResProductColorEntity                               | msdyn_productcolor                           | |
| Dimensioni ... msdyn_productsizes                                                        | EcoResProductSizeEntity                                | msdyn_productsize                            | |
| Stili ... msdyn_productstyles                                                      | EcoResProductSizeEntity                               | msdyn_productstyle                           | |
| Configurazioni ... msdyn_productconfigurations                                      | EcoResProductConfigurationEntity                       | msdyn_productconfiguration                   | |
| Prodotti V2 rilasciati ... msdyn_sharedproductdetails                                 | EcoResReleasedProductV2Entity                          | msdyn_sharedproductdetail                    | |
| Prodotti specifici rilasciati da Common Data Service ... products                         | EcoResReleasedDistinctProductCommon Data ServiceEntity | prodotto                                      | |
| Codice a barre identificativo del numero prodotto ... msdyn_productbarcodes                         | EcoResProductNumberIdentifiedBarcodeEntity             | msdyn_productbarcode                         | |
| Impostazioni ordine predefinite ... msdyn_productdefaultordersettings                        | InventProductDefaultOrderSettingsEntity                | msdyn_productdefaultordersetting             | |
| Impostazioni ordine predefinite del prodotto V2 ... msdyn_productspecificdefaultordersettings     | InventProductSpecificOrderSettingsV2Entity             | msdyn_productspecificdefaultordersetting     | |
| Conversioni di unità specifiche del prodotto ... msdyn_productspecificunitofmeasureconversions | EcoResProductSpecificUnitConversionEntity              | msdyn_productspecificunitofmeasureconversion | |
| Siti ... msdyn_operationalsites                                                    | InventOperationalSiteEntity                            | msdyn_operationalsite                        | |
| Magazzini ... msdyn_warehouses                                                     | InventWarehouseEntity                                  | msdyn_warehouse                              | Vedere la [nota 1](#scm-notes). |
| Colori principali del prodotto ... msdyn_sharedproductcolors                                 | EcoResProductMasterColorEntity                         | msdyn_sharedproductcolor                     | |
| Dimensioni principali del prodotto ... msdyn_sharedproductsizes                                   | EcoResProductMasterSizeEntity                          | msdyn_sharedproductsize                      | |
| Stili principali del prodotto ... msdyn_sharedproductstyles                                 | EcoResProductMasterStyleEntity                         | msdyn_sharedproductstyle                     | |
| Configurazioni principali del prodotto ... msdyn_sharedproductconfigurations                 | EcoResProductMasterConfigurationEntity                 | msdyn_sharedproductconfiguration             | |
| Categorie del prodotto ... msdyn_productcategories                                      | EcoResProductCategoryEntity                            | msdyn_productcategory                        | Vedere la [nota 2](#scm-notes). |
| Assegnazioni di categorie del prodotto ... msdyn_productcategoryassignments                   | EcoResProductCategoryAssignmentEntity                  | msdyn_productcategoryassignment              | |
| Gerarchie di categorie del prodotto ... msdyn_productcategoryhierarchies                   | EcoResProductCategoryHierarchyEntity                   | msdyn_productcategoryhierarchy               | |
| Ruoli della gerarchia di categorie del prodotto ... msdyn_productcategoryhierarchyroles            | EcoResProductCategoryHierarchyRoleEntity               | msdyn_productcategoryhierarchyrole           | |
| Sezione di magazzino ... msdyn_warehouseaisles                                           | WMSWarehouseAisleEntity                                | msdyn_warehouseaisle                         | |
| Zone magazzinaggio ... msdyn_warehouses                                            | WHSWarehouseZoneEntity                                 | msdyn_warehousezone                          | |
| Gruppi di zone magazzinaggio ... msdyn_warehousezonegroups                                 | WHSWarehouseZoneGroupEntity                            | msdyn_warehousezonegroup                     | |
| Ubicazioni di magazzino ... msdyn_inventorylocations                                    | WMSWarehouseLocationEntity                             | msdyn_inventorylocation                      | Vedere la [nota 3](#scm-notes). |
| Intestazioni di lavoro di magazzino ... msdyn_warehouseworkheaders                               | WHSWarehouseWorkHeaderEntity                           | msdyn_warehouseworkheader                    | |
| Righe di lavoro di magazzino ... msdyn_warehouseworklines                                    | WHSWarehouseWorkLineEntity                             | msdyn_warehouseworklines                     | Vedere la [nota 4](#scm-notes). |
| Modalità di consegna ... msdyn_shipvias                                                | DlvDeliveryModeEntity                                  | msdyn_shipvias                               | |
| Termini di consegna ... msdyn_termsofdeliveries                                       | DeliveryTermsEntity                                    | msdyn_termsofdelivery                        | |
| Codici di origine dell'ordine di vendita ... msdyn_salesorderorigins                                | SalesOrderOriginEntity                                 | msdyn_salesorderorigin                       | |
| Intestazioni degli ordini di vendita Common Data Service ... salesorders                             | SalesOrderHeaderCommon Data ServiceEntity              | salesorder                                   | |
| Righe dell'ordine cliente Common Data Service ... salesorderdetails                         | SalesOrderLineCommon Data ServiceEntity                | salesorderdetails                            | |
| Intestazione offerta di vendita Common Data Service ... quotes                               | SalesQuotationHeaderCommon Data ServiceEntity          | offerta                                        | |
| Righe di offerta di vendita Common Data Service ... quotedetails                          | SalesQuotationLineCommon Data ServiceEntity            | QuoteDetails                                 | |
| Intestazioni fattura di vendita V2 ... invoices                                               | SalesInvoiceHeaderV2Entity                             | fattura                                      | |
| Righe fattura di vendita V2 ... invoicedetails                                           | SalesInvoiceLineV2Entity                               | invoicedetail                                | |

### <a name="mapping-specific-notes"></a><a id='scm-notes'></a>Note specifiche per la mappatura

1. A causa dell'autodipendenza, potrebbe essere necessario eseguire la sincronizzazione iniziale due volte.
2. Per impostazione predefinita, la sincronizzazione iniziale è disattivata a causa della relazione padre-figlio (l'ordinamento "intelligente" non è gestito dalla piattaforma). Pertanto, le categorie di prodotti esistenti devono essere sincronizzate manualmente (ad esempio, aggiornando la descrizione della categoria) nell'ordine corretto (prima la categoria principale, quindi i figli e quindi i figli dei figli). Scegliere **Gestione informazioni sul prodotto \> Impostazioni \> Categorie e attributi \> Gerarchie di categorie**. Nella pagina **Gerarchie di categorie**, è possibile selezionare ciascuna gerarchia e vedere le categorie di prodotti in essa contenute.
3. La mappatura dei campi di ricerca **ItemNumberInLocation** vuoti e la prima, la seconda e la terza zona magazzinaggio aggiuntiva causeranno un errore nella sincronizzazione iniziale. Pertanto, queste mappature vengono rimosse per ora.
4. La mappatura del campo **CaptureWeight** vuoto causa l'esito negativo della sincronizzazione iniziale. Pertanto, questa mappatura viene rimossa per ora.

### <a name="setup-related-information"></a>Informazioni relative all'impostazione

+ Quando i record vengono creati per la prima volta nell'entità **Prodotti** nelle app basate su modello in Dynamics 365, hanno uno stato di **Bozza**. Per cambiare lo stato in **Attivo**, vai a **Impostazioni \> Amministrazione \> Impostazioni di sistema \> Vendite** nell'app basata su modello e impostare l'opzione **Crea prodotti in stato attivo** su **Sì**.
+ Se si creano record nell'entità **Prodotti** nelle app basate su modello in Dynamics 365 o in Common Data Service prima di abilitare la doppia scrittura, tali record verranno aggiornati solo se l'intera chiave, inclusa la **società**, corrisponde ai dati nell'app Finance and Operations.
+ La sincronizzazione dell'entità **Prodotti** è unidirezionale, dalle app Finance and Operations a Common Data Service. Se un campo mappato nell'entità **Prodotti** nelle app basate su modello in Dynamics 365 viene aggiornato, l'aggiornamento verrà sovrascritto durante la successiva sincronizzazione dalle app Finance and Operations.

### <a name="known-issues"></a>Problemi noti

- Si verifica un errore quando un'unità viene eliminata in un'app Finance and Operations. Quando le unità di misura sono sincronizzate dalle app Finance and Operations a Common Data Service, la prima unità di una classe specifica verrà creata come unità principale e impedirà l'eliminazione.

    **Mitigazione:** per prima cosa eliminare l'unità in Common Data Service. Può essere eliminata anche nell'app Finance and Operations.

- Si verifica un errore quando viene eliminato un sito operativo in Common Data Service. Il messaggio di errore indica "Infolog: avviso: l'indirizzo primario non può essere eliminato. Avviso: impossibile cancellare il record dell'entità perché la convalida non è riuscita per la seguente origine dati: InventSiteLogisticsLocation (InventSiteLogisticsLocation)". Questo errore è causato da un problema nell'entità dati dell'app Finance and Operations.

    **Mitigazione:** è possibile eliminare il sito nell'app Finance and Operations. Il sito verrà quindi eliminato in Common Data Service se la corrispondente mappa a doppia scrittura è in esecuzione.

## <a name="dynamics-365-finance-entities"></a>Entità Dynamics 365 Finance

Le seguenti entità per Dynamics 365 Finance sono elencate nell'ordine in cui è necessario abilitarle.

| Mappare il nome nella pagina di doppia scrittura | Nome dei metadati dell'entità in Finance | Nome dei metadati dell'entità in Common Data Service | Note |
|---|---|---|---|
| Valute ... transactioncurrencies                                            | CurrencyEntity                              | Valuta                                   | |
| Tipo di tasso di cambio ... msdyn_exchangeratetypes                                  | ExchangeRateTypeEntity                      | msdyn_exchangeratetype                     | |
| Coppia di valute tasso di cambio ... msdyn_currencyexchangeratepairs                 | ExchangeRateCurrencyPairEntity              | msdyn_currencyexchangeratepair             | |
| Tassi di cambio Common Data Service ... msdyn_currencyexchangerates              | ExchangeRateCommon Data ServiceEntity       | msdyn_currencyexchangerate                 | Vedere la [nota 1](#fin-notes). |
| Entità integrazione del calendario fiscale ... msdyn_fiscalcalendars                    | FiscalCalendarEntity                        | msdyn_fiscalcalendar                       | |
| Entità integrazione dell'anno di calendario fiscale ... msdyn_fiscalcalendaryears           | FiscalCalendarYearEntity                    | msdyn_fiscalcalendaryear                   | |
| Periodo di calendario fiscale ... msdyn_fiscalcalendarperiods                          | FiscalPeriodEntity                          | msdyn_fiscalcalendarperiod                 | |
| Tipo di gerarchia organizzativa ... msdyn_internalorganizationhierarchytypes        | OMOrganizationHierarchyTypeEntity           | msdyn_internalorganizationhierarchytype    | Vedere la [nota 1](#fin-notes). |
| Scopi della gerarchia organizzativa ... msdyn_internalorganizationhierarchypurposes | OMOrganizationHierarchyPurposeEntity        | msdyn_internalorganizationhierarchypurpose | Vedere la [nota 1](#fin-notes). |
| Persone giuridiche ... msdyn_internalorganizations                                  | OMLegalEntity                               | msdyn_internalorganization                 | Vedere la [nota 1](#fin-notes). |
| Persone giuridiche ... cdm_companies                                                | OMLegalEntity                               | cdm_company                                | |
| Unità operativa ... msdyn_internalorganizations                                  | OMOperatingUnitEntity                       | msdyn_internalorganization                 | Vedere la [nota 1](#fin-notes). |
| Gerarchia organizzativa pubblicata ... msdyn_internalorganizationhierarchies    | OMOrganizationHierarchyPublishedEntity      | msdyn_internalorganizationhierarchy        | Vedere la [nota 1](#fin-notes). |
| Affissi nome ... msdyn_nameaffixes                                              | DirNameAffixEntity                          | msdyn_nameaffix                            | |
| Giorni di pagamento  Common Data Service ...  msdyn_paymentdays                          | PaymentDayCommon Data ServiceEntity         | msdyn_paymentday                           | |
| Righe giorno di pagamento Common Data Service V2 ... msdyn_paymentdaylines              | PaymentDayLine Common Data ServiceV2Entity   | msdyn_paymentdayline                       | |
| Scadenzario pagamenti ... msdyn_paymentschedules                                     | PaymentScheduleEntity                       | msdyn_paymentschedule                      | |
| Righe scadenzario pagamenti ... msdyn_paymentschedulelines                           | PaymentScheduleLineEntity                   | msdyn_paymentscheduleline                  | |
| Termini di pagamento ... msdyn_paymentterms                                         | PaymentTermEntity                           | msdyn_paymentterm                          | |
| Metodo di pagamento del cliente ... msdyn_customerpaymentmethods                        | CustomerPaymentMethodEntity                 | msdyn_customerpaymentmethod                | |
| Metodo di pagamento del fornitore ... msdyn_vendorpaymentmethods                            | VendorPaymentMethodEntity                   | msdyn_vendorpaymentmethod                  | |
| Gruppi di clienti ... msdyn_customergroups                                        | CustCustomerGroupEntity                     | msdyn_customergroup                        | |
| Gruppi di fornitori ... msdyn_vendorgroups                                            | VendVendorGroupEntity                       | msdyn_vendorgroup                          | |
| Fascia IVA ... msdyn_taxgroups                                            | TaxGroupEntity                              | msdyn_taxgroup                             | |
| Fascia IVA articoli ... msdyn_taxitemgroups                                   | TaxItemGroupEntity                          | msdyn_taxitemgroup                         | |
| Gruppi registrazione contabile IVA V2 ... msdyn_taxpostinggroups                   | TaxPostingGroupEntityV2                     | msdyn_taxpostinggroup                      | |
| Entità del codice esente da imposta sulle vendite in Common Data Service ... msdyn_taxexemptcodes       | TaxExemptCodeCommon Data ServiceEntity      | msdyn_taxexemptcode                        | |
| Uffici IVA ... msdyn_taxauthorities                                  | TaxAuthorityEntity                          | msdyn_taxauthority                         | |
| Codice IVA ... msdyn_taxcodes                                               | TaxCodeEntity                               | msdyn_taxcode                              | Vedere la [nota 1](#fin-notes). |
| Formato della dimensione finanziaria ... msdyn_financialdimensionformats                  | DimensionIntegrationFormatEntity            | msdyn_financialdimensionformat             | |
| Dimensioni finanziarie ... msdyn_dimensionattributes                              | DimensionAttributeEntity                    | msdyn_dimensionattribute                   | |
| Gruppi di ritenute d'acconto ... msdyn_withholdingtaxgroups                           | TaxWithholdingGroupEntity                   | msdyn_withholdingtaxgroup                  | |
| Codici di ritenuta d'acconto ... msdyn_withholdingtaxcodes                             | TaxWithholdingTaxCodes                      | msdyn_withholdingtaxcode                   | |
| Piano dei conti ... msdyn_chartofaccountses                                   | LedgerChartOfAccountsEntity                 | msdyn_chartofaccounts                      | |
| Contabilità generale ... msdyn_ledgers                                                        | LedgerEntity                                | msdyn_ledger                               | Vedere la [nota 1](#fin-notes). |
| Categorie di conti principali ... msdyn_mainaccountcategories                         | MainAccountCategoryEntity                   | msdyn_mainaccountcategory                  | |
| Conto principale ... msdyn_mainaccounts                                             | MainAccountEntity                           | msdyn_mainaccount                          | |
| Clienti V3 ... accounts                                                       | CustCustomerV3Entity                        | conto                                    | Vedere la [nota 2](#fin-notes). |
| Clienti V3 ... contacts                                                       | CustCustomerV3Entity                        | contatto                                    | Vedere la [nota 3](#fin-notes). |
| Fornitori V2 ... msdyn_vendors                                                    | VendVendorV2Entity                          | msdyn_vendor                               | Vedere la [nota 2](#fin-notes). |
| Contatti Common Data Service V2 ... contacts                                    | smmContactPerson Common Data ServiceV2Entity | contatto                                    | Vedere la [nota 4](#fin-notes). |
| Contatti Common Data Service V2 ... contacts                                    | smmContactPerson Common Data ServiceV2Entity | contatto                                    | Vedere la [nota 5](#fin-notes). |

### <a name="mapping-specific-notes"></a><a id='fin-notes'></a>Note specifiche per la mappatura

1. La sincronizzazione unidirezionale si verifica dalle app Finance and Operations a Common Data Service.
2. A causa dell'autodipendenza, potrebbe essere necessario eseguire la sincronizzazione più volte. Assicurarsi di selezionare **Cliente** come tipo di relazione quando si crea un account utilizzando la pagina **Conti** in Common Data Service. In caso di problemi con il campo **Contatto primario** durante la sincronizzazione iniziale, rimuovere quel campo dalla mappatura, quindi eseguire nuovamente la sincronizzazione iniziale. Dopo che la sincronizzazione iniziale è stata completata correttamente, interrompere la mappatura e aggiungere di nuovo il campo **Contatto primario**. Quindi avviare la mappatura ignorando la sincronizzazione iniziale. Il valore del campo **Contatto primario** non verrà incluso nella sincronizzazione iniziale ed è necessario migrare manualmente i valori.
3. Assicurarsi di impostare l'opzione **Vendibile** su **Sì** nella pagina **Contatti** in Common Data Service quando si tenta di creare un cliente di tipo **Persona**.
4. Questa mappatura ha un filtro su entrambi i lati per collegare i contatti dei clienti. Aprire i dettagli della mappatura, selezionare il pulsante di filtro (simbolo dell'imbuto) accanto al nome dell'entità **Sales.Contact** e assicurarsi che i criteri del file contengano **msdyn_contactforvendor eq true and msdyn_sellable eq false**.
5. Questa mappatura ha un filtro su entrambi i lati per collegare i contatti dei fornitori. Aprire i dettagli della mappatura, selezionare il pulsante filtro (simbolo dell'imbuto) accanto al nome dell'entità **Sales.Contact** e assicurarsi che i filtri del file contengano **msdyn_contactforvendor eq true and msdyn_sellable eq false**. 

## <a name="dynamics-365-human-resources-entities"></a>Entità Dynamics 365 Human Resources

Le seguenti entità per Dynamics 365 Human Resources sono elencate nell'ordine in cui è necessario abilitarle.

| Mappare il nome nella pagina di doppia scrittura | Nome dei metadati dell'entità in Human Resources | Nome dei metadati dell'entità in Common Data Service | Note |
|---|---|---|---|
| cdm_jobfunction - Funzione lavorativa                                |                                   | cdm_jobfunction                  | |
| cdm_jobtypes - Tipi di lavoro                                      |                                   | cdm_jobtypes                     | |
| cdm_jobs - Lavori                                               |                                   | cdm_jobs                         | |
| cdm_jobs - Dettagli lavoro                                        |                                   | cdm_jobs                         | |
| cdm_positiontype - PositionType                               | HcmPositionTypeEntity             | cdm_positiontype                 | |
| cdm_jobpositions -  Posizione di base                              | HcmPositionBaseEntity             | cdm_jobposition                  | Vedere la [nota 1](#hr-notes). |
| cdm_jobposition - Dettagli posizione                            | HcmPositionDetailEntity           | cdm_jobposition                  | Vedere la [nota 1](#hr-notes). |
| cdm_jobposition - Durata posizione                           | HcmPositionDurationEntity         | cdm_jobposition                  | Vedere la [nota 1](#hr-notes). |
| cdm_jobposition - Gerarchie posizioni                        | HcmPositionHierarchyEntity        | cdm_jobposition                  | Vedere la [nota 1](#hr-notes). |
| cdm_veteranstatus - Stato veterano                            |                                   | cdm_veteranstatus                | |
| cdm_ethnicorigin - Origine etnica                              |                                   | cdm_ethnicorigin                 | |
| cdm_languagecode - Codice lingua                              |                                   | cdm_languagecode                 | |
| cdm_worker - Lavoratore                                           | HcmWorkerEntity                   | cdm_worker                       | |
| cdm_employments - Impieghi                                 |                                   | cdm_employments                  | |
| cdm_employments - Dettaglio impiego                           |                                   | cdm_employments                  | |
| cdm_positionworkerassignmentmaps - Assegnazione lavoratore posizione | HcmPositionWorkerAssignmentEntity | cdm_positionworkerassignmentmaps | Vedere la [nota 2](#hr-notes).|

### <a name="mapping-specific-notes"></a><a id='hr-notes'></a>Note specifiche per la mappatura

1. Una entità Common Data Service è mappata a più entità di app Finance and Operations.
2. Questa mappatura ha un riferimento automatico.

## <a name="asset-management-entities"></a>Entità di gestione cespiti

Le seguenti entità per Gestione cespiti per Dynamics 365 Supply Chain Management sono elencate nell'ordine in cui è necessario abilitarle.

| Mappare il nome nella pagina di doppia scrittura | Nome dei metadati dell'entità in gestione cespiti | Nome dei metadati dell'entità in Common Data Service | Note |
|---|---|---|---|
| FO.AssetManagementAssetLifecycleStates--Common Data Service.msdyn_assetlifecyclestates                           | Stati del ciclo di vita cespiti nella Gestione cespiti               | msdyn_assetlifecyclestates               | |
| FO.AssetManagementAssetLifecycleModels--Common Data Service.msdyn_assetlifecyclemodels                           | Modelli del ciclo di vita cespiti nella Gestione cespiti               | msdyn_assetlifecyclemodels               | |
| FO.AssetManagementFunctionalLocationLifecycleModels--Common Data Service.msdyn_functionallocationlifecyclemodels | Modelli del ciclo di vita unità funzionali della Gestione cespiti | msdyn_functionallocationlifecyclemodels  | |
| FO.AssetManagementFunctionalLocationLifecycleStates--Common Data Service.msdyn_functionallocationlifecyclestates | Stati del ciclo di vita unità funzionali della Gestione cespiti | msdyn_functionallocationlifecyclestates  | |
| FO.AssetManagementAssetTypes--Common Data Service.msdyn_customerassetcategories                                  | Tipi di cespite della Gestione cespiti                          | msdyn_customerassetcategories            | |
| FO.AssetManagementFunctionalLocationTypes--Common Data Service.msdyn_functionallocationtypes                     | Tipi di unità funzionali della Gestione cespiti            | msdyn_functionallocationtypes            | |
| FO.AssetManagementFunctionalLocations--Common Data Service.msdyn_functionallocations                             | Unità funzionali della Gestione cespiti                 | msdyn_functionallocations                | Vedere [la nota](#am-notes). |
| FO.AssetManagementAssets--Common Data Service.msdyn_customerassets                                               | Cespiti della Gestione cespiti                               | msdyn_customerassets                     | Vedere [la nota](#am-notes). |
| FO.AssetManagementManufacturers--Common Data Service.msdyn_manufacturers                                         | Produttori della Gestione cespiti                        | msdyn_manufacturers                      | |
| FO.AssetManagementModels--Common Data Service.msdyn_models                                                       | Modelli della Gestione cespiti                               | msdyn_models                             | |
| FO.AssetManagementWarranty--Common Data Service.msdyn_warranties                                                 | Garanzia della gestione cespiti                             | msdyn_warranties                         | |

### <a name="mapping-specific-notes"></a><a id='am-notes'></a>Note specifiche per la mappatura

- A causa dell'autodipendenza, potrebbe essere necessario eseguire la sincronizzazione più volte.
