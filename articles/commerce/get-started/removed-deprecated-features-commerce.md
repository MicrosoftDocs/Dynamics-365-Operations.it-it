---
title: Funzionalità rimosse o deprecate in Dynamics 365 Commerce
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Commerce.
author: josaw
ms.date: 08/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 3ac08a409284681ba9bcc4825b936c0330d14e04
ms.sourcegitcommit: 822aea26c5da259efe11ff3b3dc4cf1598425689
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386743"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Funzionalità rimosse o deprecate in Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Commerce.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione. 

> [!NOTE]
> Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](/dynamics/s-e/). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-commerce-10021-release"></a>Funzionalità rimosse o deprecate nella versione Commerce 10.0.21

[!include [banner](../includes/preview-banner.md)]

### <a name="retail-sdk-distributed-by-using-lifecycle-services"></a>Retail SDK distribuito utilizzando Lifecycle Services

Il Retail SDK viene spedito in Lifecycle Services (LCS). Questo modo di distribuzione è deprecato nella versione 10.0.21. In futuro, i pacchetti di riferimento del Retail SDK, le librerie e gli esempi saranno pubblicati in repository pubblici su GitHub.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Il Retail SDK viene spedito in LCS. Il processo LCS richiede alcune ore per finire, e il processo deve essere ripetuto per ogni aggiornamento. In futuro, i pacchetti di riferimento del Retail SDK, le librerie e gli esempi saranno pubblicati in repository pubblici su GitHub. I campioni di estensione e i pacchetti di riferimento possono essere consumati facilmente, e gli aggiornamenti finiscono in pochi minuti. |
| **Sostituita da un'altra funzionalità?**   |  [Scaricate i campioni del Retail SDK e i pacchetti di riferimento da GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md) |
| **Aree del prodotto interessate**         | Retail SDK |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: A partire dalla release 10.0.21, l'SDK fornito tramite le VM LCS sarà rimosso nell'ottobre 2022. |

### <a name="retail-deployable-package-and-combined-pos-hardware-station-and-cloud-scale-unit-installers"></a>Pacchetto distribuibile al dettaglio e installatori combinati di POS, stazione hardware e unità Cloud Scale

I pacchetti distribuibili al dettaglio generati usando il Retail SDK MSBuild è deprecato nella 10.0.21. In futuro, usa il pacchetto Cloud Scale Unit (CSU) per le estensioni dell'unità Cloud Scale (Commerce Runtime, database di canali, API commerciali senza testa, pagamenti e Cloud Point of Sale (POS)). Utilizza gli installatori di sola estensione per il POS, la stazione hardware e l'unità di scala Cloud autogestita.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Un pacchetto distribuibile al dettaglio è un pacchetto combinato che contiene un insieme completo di pacchetti di estensione e installatori. Questo pacchetto combinato rende complessa la distribuzione, poiché le estensioni CSU vanno all'unità di scala Cloud e gli installatori sono distribuiti nei negozi. Gli installatori includono l'estensione e il prodotto base, il che rende difficili gli aggiornamenti. Con ogni aggiornamento, è necessaria una fusione del codice e la generazione di pacchetti. Per semplificare questo processo, i pacchetti di estensione sono ora separati in componenti per una facile distribuzione e gestione. Con il nuovo approccio, le estensioni e gli installatori del prodotto di base sono separati e possono essere assistiti e aggiornati in modo indipendente senza una fusione del codice o un repackaging.|
| **Sostituita da un'altra funzionalità?**   | Estensioni CSU, installatori di estensioni POS, installatori di estensioni di stazioni hardware |
| **Aree del prodotto interessate**         | Dynamics 365 Commerce estensione e distribuzione |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: A partire dalla release 10.0.21, il supporto per la distribuzione di RetailDeployablePackage in LCS sarà rimosso nell'ottobre 2022. |

Per ulteriori informazioni, vedere:

+ [Generare un pacchetto separato per Commerce Cloud Scale Unit (CSU)](../dev-itpro/retail-sdk/retail-sdk-packaging.md#generate-a-separate-package-for-commerce-cloud-scale-unit-csu)
+ [Creare un pacchetto di estensione Modern POS](../dev-itpro/pos-extension/mpos-extension-packaging.md)
+ [Integrare il POS con un nuovo dispositivo hardware](../dev-itpro/hardware-device-extension.md)
+ Esempi di codice
    + [Unità di scala cloud](https://github.com/microsoft/Dynamics365Commerce.ScaleUnit)
    + [POS, CSU e stazione hardware](https://github.com/microsoft/Dynamics365Commerce.InStore)

### <a name="modernpossln-and-cloudpossln-in-the-retail-sdk"></a>ModernPos.Sln e CloudPOs.sln nell'SDK Retail

Lo sviluppo di estensioni POS utilizzando ModernPos.sln, CloudPOs.sln, POS.Extension.csproj e la cartella POS è deprecato nella versione 10.0.21. D'ora in poi, usa l'SDK di packaging indipendente dal POS per le estensioni POS.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Nelle versioni precedenti del Retail SDK, se ci sono estensioni POS, è necessaria una fusione del codice e un repackaging per aggiornare all'ultima versione del POS. La fusione del codice era un processo di aggiornamento che richiedeva molto tempo e si doveva mantenere l'intero SDK Retail nel repository. Dovevate anche compilare il progetto POS.App di base. Usando il modello di imballaggio indipendente, dovete mantenere solo la vostra estensione. Il processo di aggiornamento all'ultima versione delle estensioni POS è facile come aggiornare la versione del pacchetto NuGet che il vostro progetto consuma. Le estensioni possono essere distribuite indipendentemente, e i servizi usano gli installatori di estensioni. Il POS di base può essere distribuito e mantenuto separatamente, e non è richiesta alcuna fusione o riconfezionamento del codice con l'installatore o il codice di base. |
| **Sostituita da un'altra funzionalità?**   | [SDK di imballaggio indipendente dal POS](../dev-itpro/pos-extension/pos-extension-getting-started.md) |
| **Aree del prodotto interessate**         | Dynamics 365 Commerce Estensione e implementazione del POS |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: A partire dalla release 10.0.21, il supporto per i pacchetti POS combinati e il modello di estensione che utilizzano ModernPos.Sln, CloudPOs.sln e POS.Extensons.csproj in Retail SDK sarà rimosso nell'ottobre 2022. |

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Funzionalità rimosse o deprecate nella versione Commerce 10.0.17

### <a name="full-dataset-generation-interval-is-deprecated"></a>L'intervallo di generazione completo del set di dati è deprecato

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | A partire da questa versione, nel modulo **Parametri dell'utilità di pianificazione di commercio** modulo in Dynamics 365 headquarters, il campo **Intervallo di generazione completo del set di dati in giorni** sarà deprecato. Anche a partire da questa versione, il campo verrà rimosso visivamente in modo che il valore non possa essere modificato. Rimarrà come valore **0**. |
| **Sostituita da un'altra funzionalità?**   | Nessuno |
| **Aree del prodotto interessate**         | Dynamics 365 Commerce |
| **Opzione di distribuzione**              | Tutti|
| **Stato**                         | Deprecato. Non utilizzare questo campo né modificarne il valore.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Funzionalità rimosse o deprecate nella versione Commerce 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Il supporto di Internet Explorer 11 per Dynamics 365 è deprecato

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | A partire da dicembre 2020, il supporto di Microsoft Internet Explorer 11 per tutti i prodotti Dynamics 365 è deprecato e Internet Explorer 11 non sarà supportato dopo agosto 2021.<br><br>Ciò avrà un impatto sui clienti che utilizzano prodotti Dynamics 365 progettati per essere utilizzati tramite un'interfaccia Internet Explorer 11. Dopo agosto 2021, Internet Explorer 11 non sarà supportato per questi prodotti Dynamics 365. |
| **Sostituita da un'altra funzionalità?**   | Consigliamo ai clienti di passare a Microsoft Edge.|
| **Aree del prodotto interessate**         | Tutti i prodotti Dynamics 365 |
| **Opzione di distribuzione**              | Tutti|
| **Stato**                         | Deprecato. Internet Explorer 11 non sarà supportato dopo agosto 2021.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Funzionalità rimosse o deprecate nella versione Commerce 10.0.11
### <a name="data-action-hooks"></a>Hook azioni sui dai
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | La funzione hook di azione dati è stata deprecata a causa di problemi di prestazioni. |
| **Sostituita da un'altra funzionalità?**   | È consigliabile utilizzare [sostituzioni di azioni sui dai](../e-commerce-extensibility/data-action-overrides.md) per modificare la logica aziendale nel livello di azione dati.|
| **Aree del prodotto interessate**         | Azioni dati per l'estendibilità dell'e-commerce |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: dalla versione 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Supporto Retail SDK per Visual Studio 2015, msbuild 14.0 e Retail SDK\Librerie e strumenti di riferimento
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Il supporto di Retail SDK per Visual Studio 2015 è stato deprecato e aggiornato per supportare VS 2017, msbuild 15.0 e tutte le librerie di riferimento e gli strumenti del generatore di proxy commerciali nella cartella RetailSDK\References spostati in pacchetti NuGet per semplificare il modello di estensione e il processo di aggiornamento SDK.|
| **Sostituita da un'altra funzionalità?**   | È consigliabile seguire le informazioni in [Migrare Retail SDK da Visual Studio 2015 a Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) per aggiornare il sistema. |
| **Aree del prodotto interessate**         | Estensioni di Retail SDK |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: dalla versione 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Estensione di Retail Server mediante IEdmModelExtender e CommerceController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | L'estensione di Retail server mediante IEdmModelExtender e CommerceController è stata deprecata per fornire un modello di estensione semplificato. La nuova implementazione avrà solo la classe controller senza alcuna implementazione aggiuntiva della classe IEdmModelExtender. Ciò evita anche la dipendenza con una particolare versione di OData (se la versione di OData viene aggiornata potrebbe rompere le estensioni). |
| **Sostituita da un'altra funzionalità?**   |  Si consiglia di utilizzare il modello di estensione della classe IController importando il pacchetto NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Aree del prodotto interessate**         | Estensioni di Retail Server |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: dalla versione 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Estensione della stazione hardware mediante IHardwareStationController
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | L'estensione della stazione hardware mediante IHardwareStationController è stata deprecata per fornire un modello di estensione semplificato. La nuova implementazione avrà solo la classe IController senza alcuna implementazione di classe aggiuntiva e per evitare la dipendenza con le librerie delle stazioni hardware core, in precedenza l'estensione deve fare riferimento a più librerie. |
| **Sostituita da un'altra funzionalità?**   | Si consiglia di utilizzare il modello di estensione della classe IController importando il pacchetto NuGet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Aree del prodotto interessate**         | Estensioni della stazione hardware |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecato: dalla versione 10.0.11 |

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Funzionalità rimosse o deprecate nella versione Commerce 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Operazione POS 803 - Fare clic su Prelievo e ricevimento
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Le operazioni di prelievo e ricevimento sono deprecate a causa della ridefinizione di nuove operazioni. |
| **Sostituita da un'altra funzionalità?**   | Sì. È sostituita da due nuove operazioni POS: operazione in entrata (804) e operazione in uscita (805).|
| **Aree del prodotto interessate**         | Applicazione POS (Point of sale) |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecata: dalla versione 10.0.10 l'operazione di prelievo e ricevimento non riceverà più alcun nuovo aggiornamento delle funzionalità. Solo le correzioni di bug critici verranno eseguite per questa operazione nelle versioni future. Tutti i clienti sono incoraggiati a passare alle nuove [operazioni in entrata](../pos-inbound-inventory-operation.md) e [operazioni in uscita](../pos-outbound-inventory-operation.md), che continueranno a far parte della nostra roadmap di prodotti a lungo termine. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Funzionalità rimosse o deprecate nella versione Commerce 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API Commerce GetProductAvailabilities e GetAvailableInventoryNearby
| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Nuove API ottimizzate sono state create per sostituire le API GetProductAvailabilities e GetAvailableInventoryNearby. |
| **Sostituita da un'altra funzionalità?**   | Sì: sostituzione tramite le API GetEstimatedAvailabilty e GetEstimatedProductWarehouseAvailability. |
| **Aree del prodotto interessate**         | SDK dell'applicazione e-Commerce |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Obsoleta: dalla versione 10.0.7 non verranno più eseguiti gli investimenti tecnici messi in atto per GetProductAvailabilities e GetAvailableInventoryNearby. Le organizzazioni che utilizzano queste API nelle loro distribuzioni e-Commerce devono passare alle nuove API GetEstimatedAvailability e GetEstimatedProductWarehouseAvailability e abilitare la [funzionalità di calcolo della disponibilità del prodotto ottimizzata](../calculated-inventory-retail-channels.md).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annunci precedenti sulle funzionalità rimosse o deprecate
Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
