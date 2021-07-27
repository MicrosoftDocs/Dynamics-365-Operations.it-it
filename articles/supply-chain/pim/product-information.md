---
title: Panoramica delle informazioni sul prodotto
description: Vengono fornite le informazioni sulla gestione delle informazioni sul prodotto. Gestione informazioni sul prodotto utilizza definizione di prodotto, categorizzazione e identificatori condivisi per tutte le persone giuridiche e le configurazioni specifiche di un prodotto, per integrarsi nei processi aziendali.
author: t-benebo
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace, EcoResProductVariantPerCompanyImagePart, EcoResProductRelationType,EcoResProductAvailabilityPart,  EcoResProductReleasedSelect, EcoResProductLookup, EcoResProductVariantsPendingReleaseFormPart, EcoResProductSearchLookup, EcoResProductNumberRename, EcoResDimensionBasedConfigWorkspace, EcoResProductVariantImagePart, EcoResProductImagePart, EcoResProductVariantsPerCompanyPart, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleaseSessions, EcoResProductVariantMaintainWorkspaceConfiguration, EcoResProductProcessManufacturingWorkspaceConfiguration, EcoResProductMasterVariantsPart, EcoResProductDiscreteManufacturingWorkspaceConfiguration, EcoResProductVariantAvailabilityPart, EcoResProductInformationFactBox, EcoResProductLookupTest, EcoResProductImageTest, EcoResProductReleasedRecentlyCreatedFormPart, EcoResPhysicalProductDimensions, PdsMRCRegulatedListItem, EcoResProductAvailabilityPart, PdsMRCRestrictionList, InventItemIdLookupAllocationId, EcoResProductAvailability, EcoResProductEntityAttributeTableFieldAssociation, EcoResProductImagePart, EcoResProductRelation, EcoResProductReleaseAddProduct, EcoResProductPerCompanyListPage, EcoResProductParameters, PdsMRCRestrictedItemByCountryState, EngChgCasePreview, InventTablePreview, PdsMRCItemDetails, EngChgCaseAssociate, PdsMRCCustomerHistory, PdsMRCVendorHistory, PdsMRCRestrictedCountryStateByItem, InventItemIdGroupLookup, InventLocationLookup, PdsMRCValidityIntervalbyCountry, PdsMRCValidityIntervalbyCountry, PdsMRCEventTracker, PdsMRCReportingCountry, PdsMRCDocument, PdsMRCReportingList, PdsMRCItemCAS, GraphicsTestForm, EngChgPicklist
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2db979454527447bd9b070e77234bcb9498dd0a5
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "6335501"
---
# <a name="product-information-overview"></a>Panoramica delle informazioni sul prodotto

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Vengono fornite le informazioni sulla gestione delle informazioni sul prodotto. Gestione informazioni sul prodotto utilizza definizione di prodotto, categorizzazione e identificatori condivisi per tutte le persone giuridiche e le configurazioni specifiche di un prodotto, per integrarsi nei processi aziendali. 

Le informazioni sul prodotto rappresentano la struttura di base della supply chain e delle applicazioni di commercio per tutti i settori. Fa riferimento ai processi e alle tecnologie incentrati sulla gestione centralizzata delle informazioni sui prodotti (ad esempio, nelle supply chain). È essenziale che le definizioni dei prodotti, la documentazione, gli attributi e gli identificatori comuni vengano utilizzati. Nei vari moduli di una soluzione aziendali, le informazioni specifiche del prodotto e la configurazione sono necessarie per gestire i processi aziendali correlati a prodotti, famiglie di prodotti o categorie di prodotti specifici.

## <a name="product-definition"></a>Definizione di prodotto

Un prodotto viene principalmente definito da un numero prodotto, un nome e una descrizione. Tuttavia, anche altri dati sono necessari per descrivere un prodotto o servizio:

- Tipo di prodotto: articolo o servizio
- Sottotipo di prodotto: prodotti specifici o rappresentazione generale prodotto
- Definizione del modello di variante prodotto:

     - Dimensioni prodotto e gruppi di dimensioni
     - Nomenclatura di prodotto
     - Modelli di configurazione prodotto

- Associazione del prodotto a una o più categorie
- Definizione degli attributi di categorie e prodotti
- Immagini del prodotto
- Allegati
- Unità di misura e conversioni correlate
- Traduzioni per tutti i nomi e le descrizioni

## <a name="distribution-export-and-import-of-product-data"></a>Distribuzione, esportazione e importazione di dati di prodotto

La definizione del prodotto può essere creata in Supply Chain Management. Può inoltre essere importata dai sistemi PLM (Product Lifecycle Management), PDM (Product Data Management) o PIM (Product Information Management). Quando si utilizzano più istanze di Supply Chain Management, un'istanza viene in genere utilizzata come rappresentazione dei dati di prodotto per tutte le altre istanze. Questo approccio è supportato da un ampio insieme di entità di dati che consentono l'esportazione e l'importazione di dati di definizione di prodotto da un'istanza all'altra.

Per supportare la distribuzione dei dati di prodotto su più istanze, Supply Chain Management consente di utilizzare Microsoft Dataverse. Le definizioni di prodotto possono essere esportate da un'istanza di Supply Chain Management a Microsoft Dataverse. Le definizioni di prodotto possono quindi essere utilizzate per il provisioning di altre applicazioni aziendali, ad esempio Dynamics 365 Sales, con i dati di prodotto.

Tenere presente che, nelle organizzazioni dinamiche e flessibili, i dati delle informazioni di prodotto cambiano ogni giorno. Di conseguenza, la gestione di dati di prodotto reali ed accurati è un processo aziendale critico in sé.

## <a name="product-masters-and-product-variants"></a>Rappresentazioni generali prodotto e varianti prodotto

In una situazione agile, in cui i prodotti devono adattarsi rapidamente ai requisiti del cliente, le definizioni di prodotto specificano un set di prodotti anziché prodotti specifici. In Supply Chain Management, i prodotti generici sono noti come *rappresentazioni generali prodotto*. Le rappresentazioni generali prodotto contengono la definizione e le regole che consentono di specificare la modalità in cui i prodotti specifici sono descritti e si comportano nei processi aziendali. In base a queste definizioni, i prodotti specifici possono essere generati. Questi prodotti specifici sono noti come *varianti prodotto*.

Una rappresentazione generale prodotto è associata a un gruppo di dimensioni prodotto e una tecnologia di configurazione per definire le regole di business. Le dimensioni prodotto (colore, dimensioni, stile e configurazione) sono un set specifico di attributi che possono essere utilizzati nell'applicazione per definire e tenere traccia dei comportamenti specifici dei prodotti correlati. Le dimensioni assistono inoltre gli utenti nella ricerca e nell'identificazione dei prodotti.

## <a name="configuration-technologies"></a>Tecnologie di configurazione

È possibile: scegliere tra tre tecnologie di configurazione:

- Le varianti predefinite vengono definite dalle dimensioni di prodotto predefinite. La definizione delle varianti include la definizione di una specifica combinazione valida di dimensioni, ad esempio colore, stile e dimensioni. Ogni combinazione produce una variante di prodotto specifico.
- La configurazione basata su dimensioni viene in genere utilizzata in scenari di produzione e consente di utilizzare la dimensione di configurazione nella definizione delle distinte base (BOMs). Dopo che una specifica configurazione viene selezionata, il sistema utilizza il sottoinsieme di righe DBA valide per tale configurazione per la pianificazione e la produzione. Questo concetto è anche denominato *DBA generale*, poiché una DBA condivisa viene utilizzata per tutte le configurazioni di un prodotto.
- La configurazione basata su vincoli utilizza un modello di configurazione prodotto per descrivere tutti i possibili attributi e componenti necessari per descrivere tutte le varianti possibili di un prodotto in un singolo modello. I vincoli di combinazioni di attributi possono essere definiti con le espressioni standard o i vincoli basati su tabella. I modelli di configurazione e le configurazioni diventano più importanti nella gestione delle informazioni sul prodotto e vengono utilizzati in tutti i settori.

Quando si pianifica l'implementazione di Supply Chain Management, è particolarmente importante scegliere la tecnologia di configurazione corretta per un processo aziendale. Un prodotto non può essere convertito da un modello in un altro dopo l'implementazione.

## <a name="product-variant-model-definition-workspace"></a>Area di lavoro Definizione modello di variante prodotto

L'area di lavoro **Definizione modello di variante prodotto** fornisce una panoramica delle rappresentazioni generali prodotto. Mostra inoltre lo stato di rilascio delle rappresentazioni generali e relative varianti a persone giuridiche specifiche.

## <a name="released-products"></a>Prodotti rilasciati

I prodotti rilasciati a un persona giuridica specifica sono noti come *prodotti rilasciati*. I prodotti possono essere rilasciati in blocco a una persona giuridica o a più persone giuridiche contemporaneamente. Poiché è probabile che le diverse proprietà e attributi dei prodotti debbano essere aggiunte per persona giuridica, l'area di lavoro **Gestione prodotti rilasciati** consente di controllare e completare i prodotti rilasciati di recente in ogni persona giuridica o nelle organizzazioni secondarie di una persona giuridica.

### <a name="released-product-maintenance-workspace"></a>Area di lavoro Gestione prodotti rilasciati

È possibile configurare l'area di lavoro **Gestione prodotti rilasciati** dalla voce di menu **Configura area di lavoro personale**. Selezionare una gerarchia di categorie e una categoria in base a cui filtrare l'area di lavoro. Per rettificare i dati rilevanti del prodotto nell'area di lavoro, è possibile anche definire, in giorni, gli intervalli temporali per **Prodotti rilasciati di recente** e **Prodotti rilasciati interrotti**.

L'area di lavoro è costituita da un riepilogo di riquadri e due elenchi. L'elenco **Casi aperti** mostra i casi di modifiche di prodotti che includono prodotti nella gerarchia di categorie dei prodotti selezionata che non sono stati completati e chiusi. Nell'elenco **Rilasciati di recente** vengono visualizzati i prodotti che sono stati rilasciati all'interno dell'intervallo di tempo impostato durante la configurazione dell'area di lavoro. Per ciascuna voce nell'elenco, viene eseguita la convalida e viene visualizzato lo stato di convalida. Questo stato può indicare che le configurazioni richieste per la persona giuridica non sono state completate. Dall'elenco è possibile accedere direttamente alle pagine **Dettagli prodotto rilasciato**, **Gestione attributi prodotto**, **Gestione categoria di prodotti**, **Impostazioni ordine predefinite** e **Traduzioni testo** per completare la configurazione richiesta del prodotto.

### <a name="manually-creating-a-new-released-product"></a>Creazione manuale di un nuovo prodotto rilasciato

È possibile creare manualmente un prodotto rilasciato in una singola esecuzione, a seconda dei processi aziendali dell'organizzazione e delle regole relative all'utilizzo di questa funzione. Questa funzione crea un nuovo prodotto e lo rilascia automaticamente alla persona giuridica corrente. Per creare un nuovo prodotto, fare clic su **Prodotti rilasciati** nell'area di lavoro **Gestione prodotti rilasciati** o nella pagina elenco **Prodotto rilasciato**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]