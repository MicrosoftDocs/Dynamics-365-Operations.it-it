---
title: Pacchetto separato di orchestrazione dell'applicazione a doppia scrittura
description: Il pacchetto di orchestrazione dell'applicazione a doppia scrittura non è più un singolo pacchetto ma è stato separato in pacchetti più piccoli. Questo argomento spiega le soluzioni e le mappe contenute in ogni pacchetto e la dipendenza da altri pacchetti.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: f6950ec3e6ded49a71f119c21be67f538c8e1c69
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716554"
---
# <a name="separated-dual-write-application-orchestration-package"></a>Pacchetto separato di orchestrazione dell'applicazione a doppia scrittura

[!include [banner](../../includes/banner.md)]



In precedenza, il pacchetto di orchestrazione dell'applicazione a doppia scrittura era un singolo pacchetto che conteneva le seguenti soluzioni:

- Dynamics 365 Notes
- Ancoraggio comune Dynamics 365 Finance e le operazioni
- Mappe di entità a doppia scrittura di Dynamics 365 Finance e le operazioni
- App Gestione cespiti Dynamics 365
- Gestione cespiti Dynamics 365
- Elementi comuni di HCM
- Dynamics 365 Supply Chain Extended
- Dynamics 365 Finance Extended
- Comune Dynamics 365 Finance e le operazioni
- Dynamics 365 Company
- Tassi di cambio valutario
- Field Service Common

Poiché si trattava di un unico pacchetto, questo pacchetto ha creato una situazione "o tutto o niente" per i clienti. Tuttavia, Microsoft ora lo ha separato in pacchetti più piccoli. Pertanto, i clienti possono selezionare solo i pacchetti per le soluzioni di cui hanno bisogno. Ad esempio, se sei un cliente Microsoft Dynamics 365 Supply Chain Management e non richiedi l'integrazione con Dynamics 365 Human Resources, note e gestione delle risorse, è possibile escludere tali soluzioni dalle soluzioni installate. Poiché i nomi delle soluzioni sottostanti, l'editore e le versioni della mappa rimangono gli stessi, questa modifica è univoca. Aggiorna le installazioni esistenti.

![Pacchetto separato.](media/separated-package-1.png)

Questo argomento spiega le soluzioni e le mappe contenute in ogni pacchetto e la dipendenza da altri pacchetti.

## <a name="dual-write-application-core"></a>Core dell'applicazione a doppia scrittura

Il pacchetto Core dell'applicazione a doppia scrittura consente agli utenti di installare e configurare la doppia scrittura senza alcuna app di coinvolgimento del cliente. Sono incluse le seguenti cinque soluzioni.

| Nome univoco                           | Nome visualizzato                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 Company                       |
| Dynamics365FinanceAndOperationsCommon | Comune Dynamics 365 Finance e le operazioni |
| CurrencyExchangeRates                 | Tassi di cambio valutario                    |
| msdyn_DualWriteAppCoreMaps            | Mappe di entità core dell'applicazione a doppia scrittura   |
| msdyn_DualWriteAppCoreAnchor          | Ancoraggio core dell'applicazione a doppia scrittura        |

In questo pacchetto sono disponibili le seguenti mappe.

| App Finanza e operazioni     | App di interazione con i clienti                    |
|---------------------------------|---------------------------------------------|
| Unità operativa                  | msdyn_internalorganizations                 |
| Gerarchia organizzativa          | msdyn_internalorganizationhierarchies       |
| Persone giuridiche                  | msdyn_internalorganizations                 |
| Persone giuridiche                  | cdm_companies                               |
| Scopi gerarchia organizzativa | msdyn_internalorganizationhierarchypurposes |
| Coppia di valute tasso di cambio     | msdyn_currencyexchangeratepairs             |
| Affissi nome                    | msdyn_nameaffixes                           |
| Tipo di tasso di cambio              | msdyn_exchangeratetypes                     |
| Tassi di cambio CDS              | msdyn_currencyexchangerates                 |
| Tipo di gerarchia organizzativa     | msdyn_internalorganizationhierarchytypes    |
| Valute                      | transactioncurrencies                       |
| Entità delle guide alla realtà mista     | msmrw_guides                                |

**Informazioni sulla dipendenza**

Il pacchetto Core dell'applicazione a doppia scrittura non ha alcuna dipendenza da altri pacchetti.

## <a name="dual-write-human-resources"></a>Human Resources a doppia scrittura

Il pacchetto Human Resources a doppia scrittura contiene le soluzioni e le mappe necessarie per sincronizzare i dati di Human Resources. Sono incluse le seguenti tre soluzioni.

| Nome univoco                | Nome visualizzato                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | Elementi comuni di HCM                               |
| msdyn_Dynamics365HCMMaps   | Mappe di entità Dynamics 365 Human Resources |
| msdyn_Dynamics365HCMAnchor | Ancoraggio Dynamics 365 Human Resources      |

In questo pacchetto sono disponibili le seguenti mappe.

| App Finanza e operazioni | App di interazione con i clienti         |
|-----------------------------|----------------------------------|
| Origini etniche              | cdm_ethnicorigins                |
| Funzione lavorativa retribuzione   | cdm_jobfunctions                 |
| Posizioni V2                | cdm_jobpositions                 |
| Mansioni                        | cdm_jobs                         |
| Tipo di posizione lavorativa retribuzione       | cdm_jobtypes                     |
| Codici lingua              | cdm_languages                    |
| Tipo di posizione               | cdm_positiontypes                |
| Assegnazioni lavoratori posizioni | cdm_positionworkerassignmentmaps |
| Stato veterano              | cdm_veteranstatuses              |
| Lavoro                      | cdm_workers                      |
| Impiego per società      | cdm_employments                  |

**Informazioni sulla dipendenza**

Il pacchetto Human Resources a doppia scrittura dipende dal pacchetto Core dell'applicazione a doppia scrittura. Pertanto, è necessario installare il pacchetto Core dell'applicazione a doppia scrittura prima di installare il pacchetto Human Resources a doppia scrittura.

## <a name="dual-write-supply-chain"></a>Supply chain a doppia scrittura

Il pacchetto Supply Chain a doppia scrittura contiene le soluzioni e le mappe necessarie per sincronizzare i dati di Supply Chain Management. Sono incluse le seguenti tre soluzioni.

| Nome univoco                                | Nome visualizzato                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain Extended                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Mappe di entità Dynamics 365 Supply Chain Management extended |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Ancoraggio Dynamics 365 Supply Chain Management extended      |

In questo pacchetto sono disponibili le seguenti mappe.

| App Finanza e operazioni                 | App di interazione con i clienti                      |
|---------------------------------------------|-----------------------------------------------|
| Unità                                       | uoms                                          |
| Intestazioni ordine cliente CDS                     | salesorders                                   |
| Righe ordine cliente CDS                       | salesorderdetails                             |
| Intestazione offerta di vendita CDS                  | offerte                                        |
| Righe di offerta di vendita CDS                   | quotedetails                                  |
| Prodotti specifici CDS rilasciati              | prodotti                                      |
| Zone magazzinaggio                             | msdyn_warehousezones                          |
| Gruppi di zone magazzinaggio                       | msdyn_warehousezonegroups                     |
| Righe di lavoro magazzino                        | msdyn_warehouseworklines                      |
| Intestazioni di lavoro magazzino                      | msdyn_warehouseworkheaders                    |
| Magazzini                                  | msdyn_warehouses                              |
| Sezione magazzino                             | msdyn_warehouseaisles                         |
| Conversioni unità                            | msdyn_unitofmeasureconversions                |
| Termini di consegna                           | msdyn_termsofdeliveries                       |
| Modalità di consegna                           | msdyn_shipvias                                |
| Stili rappresentazione generale prodotto                       | msdyn_sharedproductstyles                     |
| Righe fattura di vendita V2                      | invoicedetails                                |
| Intestazioni fattura di vendita V2                    | fatture                                      |
| Dimensioni rappresentazione generale prodotto                        | msdyn_sharedproductsizes                      |
| Prodotti rilasciati V2                        | msdyn_sharedproductdetails                    |
| Configurazioni rappresentazione generale prodotto               | msdyn_sharedproductconfigurations             |
| Colori rappresentazione generale prodotto                       | msdyn_sharedproductcolors                     |
| Codici origine ordine cliente                    | msdyn_salesorderorigins                       |
| Intestazione entrata prodotti                      | msdyn_purchaseorderreceipts                   |
| Riga entrata prodotti                        | msdyn_purchaseorderreceiptproducts            |
| Intestazioni ordine fornitore V2                   | msdyn_purchaseorders                          |
| Entità preliminare eliminata della riga ordine fornitore CDS | msdyn_purchaseorderproducts                   |
| Entità riga ordine fornitore CDS              | msdyn_purchaseorderproducts                   |
| Gruppi di dimensioni di tracciabilità                   | msdyn_producttrackingdimensiongroups          |
| Stili                                      | msdyn_productstyles                           |
| Gruppi di dimensioni di immagazzinamento                    | msdyn_productstoragedimensiongroups           |
| Conversioni unità specifiche del prodotto           | msdyn_productspecificunitofmeasureconversions |
| Impostazioni ordine predefinite prodotto V2           | msdyn_productspecificdefaultordersettings     |
| Dimensioni                                       | msdyn_productsizes                            |
| Gruppi di dimensioni prodotto                    | msdyn_productdimensiongroups                  |
| Impostazioni ordine predefinite                      | msdyn_productdefaultordersettings             |
| Configurazioni                              | msdyn_productconfigurations                   |
| Tutti i prodotti                                | msdyn_globalproducts                          |
| Colori                                      | msdyn_productcolors                           |
| Ruoli gerarchia di categorie prodotto            | msdyn_productcategoryhierarchyroles           |
| Gerarchie di categorie prodotto                | msdyn_productcategoryhierarchies              |
| Assegnazioni categoria prodotto                | msdyn_productcategoryassignments              |
| Categorie prodotti                          | msdyn_productcategories                       |
| Ubicazioni magazzino                         | msdyn_inventorylocations                      |
| Inventario CDS in                            | msdyn_inventoryonhandentries                  |
| Categorie prodotti                          | msdyn_productcategories                       |
| Inventario CDS in                            | msdyn_inventoryonhandrequests                 |
| Codice a barre identificato per numero prodotto           | msdyn_productbarcodes                         |
| Carta fedeltà                                | msdyn_loyaltycards                            |
| Punti premio fedeltà                       | msdyn_loyaltyrewardpoints                     |
| Gruppi di clienti per prezzo                       | msdyn_pricecustomergroups                     |
| Siti                                       | msdyn_operationalsites                        |
| Righe di offerta di vendita CDS                   | quotedetails                                  |
| Righe ordine cliente CDS                       | salesorderdetails                             |

**Informazioni sulla dipendenza**

Il pacchetto Supply Chain a doppia scrittura dipende dai tre pacchetti seguenti. Pertanto, è necessario installare questi pacchetti prima di installare il pacchetto Supply Chain a doppia scrittura.

- Pacchetto Core dell'applicazione a doppia scrittura
- Pacchetto Finance a doppia scrittura
- Pacchetto Human Resources a doppia scrittura

## <a name="dual-write-finance"></a>Finance a doppia scrittura

Il pacchetto Finance a doppia scrittura contiene le soluzioni e le mappe necessarie per sincronizzare i dati di Dynamics 365 Finance. Sono incluse le seguenti quattro soluzioni.

| Nome univoco                            | Nome visualizzato                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Mappe di entità estese di Dynamics 365 Finance |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Ancoraggio esteso di Dynamics 365 Finance      |

In questo pacchetto sono disponibili le seguenti mappe.

| App Finanza e operazioni             | App di interazione con i clienti        |
|-----------------------------------------|---------------------------------|
| Gruppi ritenute d'acconto                  | msdyn_withholdingtaxgroups      |
| CDS Contacts V2 (cliente)              | contatti                        |
| CDS Contacts V2 (fornitore)                | contatti                        |
| Clienti V3                            | contatti                        |
| Codici ritenuta d'acconto                   | msdyn_withholdingtaxcodes       |
| Fornitori V2                              | msdyn_vendors                   |
| Metodo di pagamento fornitore                   | msdyn_vendorpaymentmethods      |
| Gruppi di fornitori                           | msdyn_vendorgroups              |
| Piano dei conti                       | msdyn_chartofaccountses         |
| Gruppi registrazione contabile IVA V2      | msdyn_taxpostinggroups          |
| Fascia IVA articoli                    | msdyn_taxitemgroups             |
| Fasce IVA                        | msdyn_taxgroups                 |
| Entità codici esenzione IVA CDS        | msdyn_taxexemptcodes            |
| Gruppi di clienti                         | msdyn_customergroups            |
| Metodo di pagamento clienti                 | msdyn_customerpaymentmethods    |
| Dimensioni finanziarie                    | msdyn_dimensionattributes       |
| Uffici IVA                   | msdyn_taxauthorities            |
| Formato dimensione finanziaria              | msdyn_financialdimensionformats |
| Periodo di calendario fiscale                  | msdyn_fiscalcalendarperiods     |
| Entità integrazione calendario fiscale      | msdyn_fiscalcalendars           |
| Entità integrazione anno calendario fiscale | msdyn_fiscalcalendaryears       |
| Termini di pagamento                        | msdyn_paymentterms              |
| Scadenzario pagamenti                        | msdyn_paymentschedules          |
| Righe scadenzario pagamenti                  | msdyn_paymentschedulelines      |
| Giorni di pagamento - CDS                        | msdyn_paymentdays               |
| Righe giorno di pagamento - CDS V2                | msdyn_paymentdaylines           |
| Conto principale                            | msdyn_mainaccounts              |
| Categorie di conti principali                 | msdyn_mainaccountcategories     |
| Ledger                                  | msdyn_ledgers                   |
| Clienti V3                            | conti                        |

**Informazioni sulla dipendenza**

Il pacchetto Finance a doppia scrittura dipende dal pacchetto Core dell'applicazione a doppia scrittura. Pertanto, è necessario installare il pacchetto Core dell'applicazione a doppia scrittura prima di installare il pacchetto Finance a doppia scrittura.

## <a name="dual-write-notes"></a>Notes a doppia scrittura

Il pacchetto Notes a doppia scrittura contiene le soluzioni e le mappe necessarie per sincronizzare i dati di note o annotazioni. Sono incluse le seguenti quattro soluzioni.

| Nome univoco                  | Nome visualizzato                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Dynamics 365 Notes             |
| Dynamics365NotesExtended     | Dynamics 365 notes extended    |
| msdyn_Dynamics365NotesMaps   | Mappe di entità Dynamics 365 notes |
| msdyn_Dynamics365NotesAnchor | Ancoraggio Dynamics 365 notes      |

In questo pacchetto sono disponibili le seguenti mappe.

| Finanza e operazioni                     | Customer Engagement |
|--------------------------------------------|---------------------|
| Allegati documento intestazione ordine cliente    | annotazioni         |
| Allegati cliente                       | annotazioni         |
| Allegati documento fornitore                | annotazioni         |
| Allegati documento intestazione ordine fornitore | annotazioni         |

**Informazioni sulla dipendenza**

Il pacchetto Notes a doppia scrittura dipende dai due pacchetti seguenti. Pertanto, è necessario installare questi pacchetti prima di installare il pacchetto Notes a doppia scrittura.

- Pacchetto Core dell'applicazione a doppia scrittura
- Pacchetto Finance a doppia scrittura

## <a name="dual-write-asset-management"></a>Gestione cespiti a doppia scrittura

Il pacchetto Gestione cespiti a doppia scrittura contiene le soluzioni e le mappe necessarie per sincronizzare i dati dei cespiti di Supply Chain Management o Dynamics 365 Field Service. Sono incluse le seguenti quattro soluzioni.

| Nome univoco                          | Nome visualizzato                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Gestione cespiti Dynamics 365             |
| Dynamics365AssetManagementApp        | App Gestione cespiti Dynamics 365          |
| msdyn_DualWriteAssetManagementMaps   | Mappe entità di Gestione cespiti Dynamics 365 |
| msdyn_DualWriteAssetManagementAnchor | Ancoraggio Gestione cespiti Dynamics 365      |

In questo pacchetto sono disponibili le seguenti mappe.

| App Finanza e operazioni                           | App di interazione con i clienti                |
|-------------------------------------------------------|-----------------------------------------|
| Garanzia della gestione cespiti                             | msdyn_warranties                        |
| Modelli della Gestione cespiti                               | msdyn_models                            |
| Produttori della Gestione cespiti                        | msdyn_manufacturers                     |
| Tipi di unità funzionali della Gestione cespiti            | msdyn_functionallocationtypes           |
| Unità funzionali della Gestione cespiti                 | msdyn_functionallocations               |
| Stati del ciclo di vita unità funzionali della Gestione cespiti | msdyn_functionallocationlifecyclestates |
| Modelli del ciclo di vita unità funzionali della Gestione cespiti | msdyn_functionallocationlifecyclemodels |
| Cespiti della Gestione cespiti                               | msdyn_customerassets                    |
| Tipi di cespite della Gestione cespiti                          | msdyn_customerassetcategories           |
| Stati del ciclo di vita cespiti nella Gestione cespiti               | msdyn_assetlifecyclestates              |
| Modelli del ciclo di vita cespiti nella Gestione cespiti               | msdyn_assetlifecyclemodels              |

**Informazioni sulla dipendenza**

Il pacchetto Gestione cespiti a doppia scrittura dipende dal pacchetto Core dell'applicazione a doppia scrittura. Pertanto, è necessario installare il pacchetto Core dell'applicazione a doppia scrittura prima di installare il pacchetto Gestione cespiti a doppia scrittura.

## <a name="packages-required-for-project-operations"></a>Pacchetti richiesti per Project Operations
Project Operations dipende dai seguenti pacchetti. Pertanto, è necessario installare questi pacchetti prima di installare Project Operations.

- Pacchetto Core dell'applicazione a doppia scrittura
- Pacchetto Finance a doppia scrittura
- Pacchetto Supply chain a doppia scrittura
- Pacchetto Gestione cespiti a doppia scrittura
- Pacchetto Human Resources a doppia scrittura

## <a name="dual-write-party-and-global-address-book-solutions"></a>Soluzioni di doppia scrittura per parte e rubrica globale

Il pacchetto di soluzioni a doppia scrittura e della rubrica globale contiene le seguenti soluzioni e mappe necessarie per sincronizzare i dati della rubrica e della rubrica globale. 

| Nome univoco                       | Nome visualizzato                            |
|-----------------------------------|-----------------------------------------|
| Parte                             | Parte                                   |
| Dynamics365GABExtended            | Dynamics 365 GAB estesa               |
| Dynamics365GABDualWriteEntityMaps | Mappe di entità a doppia scrittura di Dynamics 365 GAB |
| Dynamics365GABParty_Anchor        | Dynamics 365 GAB e parte              |

In questo pacchetto sono disponibili le seguenti mappe.

| App Finanza e operazioni | App di interazione con i clienti | 
|-----------------------------|--------------------------|
| Parti CDS | msdyn_parties | 
| Ubicazioni dell'indirizzo postale CDS | msdyn_postaladdresscollections | 
| Storico indirizzo postale CDS V2 | msdyn_postaladdresses | 
| Ubicazioni dell'indirizzo postale della parte CDS | msdyn_partypostaladdresses | 
| Contatti parte V3 | msdyn_partyelectronicaddresses | 
| Clienti V3 | conti | 
| Clienti V3 | contatti | 
| Fornitori V2 | msdyn_vendors | 
| Titoli contatti | msdyn_salescontactpersontitles | 
| Formule di chiusura | msdyn_complimentaryclosings | 
| Formule di apertura | msdyn_salutations | 
| Ruoli nel processo decisionale | msdyn_decisionmakingroles | 
| Funzioni lavorative impiego | msdyn_employmentjobfunctions | 
| Livelli fedeltà | msdyn_loyaltylevels | 
| Tipi di carattere personale | msdyn_personalcharactertypes | 
| Contatti V2 | msdyn_contactforparties | 
| Intestazione offerta di vendita CDS | offerte | 
| Intestazioni ordine cliente CDS | salesorders | 
| Intestazioni fattura di vendita V2 | fatture | 
| Ruoli indirizzo CDS | msdyn_addressroles |

**Informazioni sulla dipendenza**

Le soluzioni di doppia scrittura parte e rubrica globale dipendono dai tre pacchetti seguenti. Pertanto, è necessario installare questi pacchetti prima di installare il pacchetto di soluzioni doppia scrittura parte e rubrica globale.

- Pacchetto Core dell'applicazione a doppia scrittura
- Pacchetto Finance a doppia scrittura
- Pacchetto Supply chain a doppia scrittura
