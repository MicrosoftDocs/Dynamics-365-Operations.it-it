---
title: Impostare l'imballaggio manuale (febbraio 2016 e maggio 2016)
description: Il processo di imballaggio consente di convalidare e imballare i prodotti in contenitori.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67e1e99b479752a027c60a878c57bd35d4219981
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431532"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a>Impostare l'imballaggio manuale (febbraio 2016 e maggio 2016)

[!include [banner](../../includes/banner.md)]

Il processo di imballaggio consente di convalidare e imballare i prodotti in contenitori. In questo processo i magazzinieri prelevano i prodotti dai percorsi di immagazzinamento e li spostano in un centro d'imballaggio in cui le quantità e i tipi di articolo vengono controllati e assegnati ai contenitori appropriati. Quando un contenitore è completamente imballato, è possibile chiuderlo e spostarlo nelle banchine di uscita e i prodotti sono pronti per essere spediti. Questa procedura utilizza la società dimostrativa USMF. Questa procedura si riferisce solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics 365 for Operations.


## <a name="set-up-location-profiles"></a>Imposta profili ubicazione
1. Andare a Gestione magazzino > Impostazioni > Magazzino > Profili ubicazione.
2. Fare clic su Nuovo.
    * Il profilo di ubicazione viene utilizzato per i centri di imballaggio e contiene le informazioni e le regole di un'ubicazione.  
3. Nel campo ID profilo ubicazione digitare un valore.
4. Digitare un valore nel campo Nome.
5. Nel campo Formato ubicazione immettere o selezionare un valore.
6. Nel campo Tipo di ubicazione immettere o selezionare un valore.
7. Selezionare Sì nel campo Consenti articoli combinati.
8. Selezionare Sì nel campo Consenti stati inventario combinati.
9. Selezionare Sì nel campo Ignora regole per giorni di batch.
10. Chiudere la pagina.

## <a name="set-up-warehouse-management-parameters"></a>Impostare i parametri per Gestione magazzino 
1. Andare a Gestione magazzino > Impostazioni > Parametri di gestione magazzino.
2. Fare clic sulla scheda Imballaggio.
3. Nel campo ID profilo per l'ubicazione imballaggio immettere o selezionare un valore.
    * Selezionare il profilo di ubicazione da utilizzare per l'imballaggio.  
4. Chiudere la pagina.

## <a name="set-up-container-types"></a>Impostare i tipi di contenitore
1. Andare a Gestione magazzino > Impostazioni > Contenitori > Tipi di contenitore.
2. Fare clic su Nuovo.
    * È possibile definire i tipi di contenitori da utilizzare. È possibile specificare le dimensioni fisiche del contenitore, inclusi tara, peso massimo, volume massimo, lunghezza, larghezza e peso.  Gli attributi sono campi personalizzati che consentono di aggiungere dimensioni extra sul tipo di contenitore.     
3. Nel campo Codice tipo di contenitore immettere un valore.
4. Nel campo Descrizione digitare un valore.
5. Immettere un numero nel campo Tara.
6. Nel campo Peso massimo immettere un numero.
7. Nel campo Volume immettere un numero.
8. Immettere un numero nel campo Lunghezza.
9. Nel campo Larghezza immettere un numero.
10. Nel campo Altezza immettere un numero.
11. Fare clic su Salva.
12. Chiudere la pagina.

## <a name="set-up-packing-profiles"></a>Impostare i profili imballaggio
1. Andare a Gestione magazzino > Impostazioni > Imballaggio > Profili imballaggio.
2. Fare clic su Nuovo.
3. Nel campo ID profilo imballaggio digitare un valore.
4. Nel campo Descrizione digitare un valore.
5. Nel campo ID profilo chiusura contenitore immettere o selezionare un valore.
    * Un ID profilo di chiusura contenitore è facoltativo ed è il profilo contenitore predefinito di chiusura per questo profilo di imballaggio.  
6. Selezionare un'opzione nel campo Modalità ID contenitore.
    * Questa opzione determina se un ID contenitore verrà generato automaticamente quando verrà creato un contenitore o se un ID contenitore verrà creato manualmente.  
7. Nel campo Tipo di contenitore immettere o selezionare un valore.
    * Il tipo di contenitore verrà utilizzato per impostazione predefinita quando verrà creato un nuovo contenitore.  
8. Selezionare la casella di controllo Crea automaticamente il contenitore alla chiusura.
9. Fare clic su Salva.
10. Chiudere la pagina.

## <a name="set-up-container-closing-profiles"></a>Impostare i profili chiusura contenitore
1. Andare a Gestione magazzino > Impostazioni > Contenitori > Profili chiusura contenitore.
    * I profili di chiusura contenitore definiscono l'azione da eseguire quando viene chiuso un contenitore. È possibile impostare più profili contenitore chiuso.       
2. Fare clic su Nuovo.
3. Nel campo ID profilo chiusura contenitore digitare un valore.
4. Nel campo Descrizione digitare un valore.
5. Selezionare un'opzione nel campo Manifesto alle.
    * Specificare se l'esecuzione del manifesto si verificherà quando si chiudono i contenitori o quando si conferma la spedizione. L'esecuzione del manifesto richiede la gestione del trasporto e dovrà essere implementata nei motori di trasporto per funzionare.  
6. Nel campo Magazzino immettere o selezionare un valore.
7. Nel campo Ubicazione predefinita per spedizione finale immettere o selezionare un valore.
    * Questa sarà l'ubicazione in cui i prodotti verranno spostati dopo la chiusura dei contenitori. Questa ubicazione deve essere un profilo di ubicazione definito nei parametri di magazzino.  
8. Nel campo Unità peso immettere o selezionare un valore.
9. Fare clic su Salva.

