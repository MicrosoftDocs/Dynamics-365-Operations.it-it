---
title: Ricezione della targa tramite l'app del magazzino
description: Questo argomento spiega come configurare l'app del magazzino per supportare l'utilizzo di un processo di ricezione della targa per ricevere l'inventario fisico.
author: perlynne
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 7d5ac6598ab80ece0164d7c92f5d84e91d21b385
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346378"
---
# <a name="license-plate-receiving-via-the-warehousing-app"></a>Ricezione della targa tramite l'app del magazzino

Questo argomento spiega come configurare l'app del magazzino in modo che supporti l'utilizzo di un processo di ricezione della targa per ricevere l'inventario fisico.

È possibile utilizzare questa funzionalità per registrare rapidamente l'entrata di inventario in entrata correlata a un avviso di spedizione anticipata (ASN). Il sistema crea automaticamente un ASN quando i processi di gestione del magazzino vengono utilizzati per spedire un ordine di trasferimento. Per il processo dell'ordine fornitore, un ASN può essere registrato manualmente oppure può essere importato automaticamente utilizzando un processo dell'entità dati ASN in entrata.

I dati ASN sono collegati a carichi e spedizioni tramite le *strutture di imballaggio*, dove i pallet (targhe padre) possono contenere casi (targhe nidificate).

> [!NOTE]
> Per ridurre il numero di transazioni di inventario quando vengono utilizzate strutture di imballaggio con targhe nidificate, il sistema registra l'inventario fisico disponibile sulla targa padre. Per attivare il movimento dell'inventario fisico disponibile dalla targa padre alle targhe nidificate, in base ai dati della struttura dell'imballaggio, il dispositivo mobile deve fornire una voce di menu basata sul processo di creazione del lavoro *Imballa in targhe nidificate*.

<!-- To be used later (will require further editing):
## Warehousing mobile device app processing

When a worker scans an incoming license plate ID, the system initializes a license plate receiving process. Based on this information, the content of the license plate (data coming from the ASN) gets physically registered at the inbound dock location. The flows that follow will depend your business process needs.

## Work policies

As with (for example) the *Report as finished* mobile device menu item process, the license plate receiving process supports several workflows based on the defined setup.

### Work policies with work creation

Registration of physical on-hand where either the same warehouse worker immediately process a put-away work process following the inbound receiving (License plate receiving and put away) or where the registration and put away process gets handled as two different warehouse operations (License plate receiving) following the processing of the put-away work by using the existing work process via another mobile device menu item.

## Work policies without work creation

You can use the license plate receiving process without creating work by using the *License plate receiving without creating work* feature.

By defining **Work policies** with a **Work order type** of *Transfer receipt* and/or *Purchase orders*, and using the **Process** for **License plate receiving (and put away)**, the two Warehousing app process:

- License plate receiving
- License plate receiving and put away

will not create work, but only register the inbound physical inventory on the license plate at the inbound receiving dock.

For more information about the *Report as finished* production scenario, see the [Warehouse work policies overview](warehouse-work-policies.md).

-->

## <a name="show-or-skip-the-receiving-summary-page"></a>Visualizzare o ignorare la pagina di riepilogo di ricezione

È possibile utilizzare la funzionalità *Controlla se visualizzare una pagina di riepilogo di ricezione su dispositivi mobili* per sfruttare un ulteriore flusso dettagliato dell'app di magazzino come parte del processo di ricezione della targa.

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, questa funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome della funzione:** *Controlla se visualizzare una pagina di riepilogo di ricezione su dispositivi mobili*

Quando questa funzione è attivata, le voci di menu del dispositivo mobile per la ricezione della targa o la ricezione e la memorizzazione della targa forniranno l'impostazione **Visualizza la pagina di riepilogo di ricezione**. Questa impostazione ha le seguenti opzioni:

- **Visualizza un riepilogo dettagliato** - Durante la ricezione della targa, i lavoratori vedranno una pagina aggiuntiva che mostra le informazioni ASN complete.
- **Ignora il riepilogo** - I lavoratori non vedranno le informazioni ASN complete. Inoltre, gli addetti al magazzino non saranno in grado di impostare un codice smaltimento o aggiungere eccezioni durante il processo di ricezione.

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Impedire che le targhe spedite dall'ordine di trasferimento vengano utilizzate in magazzini diversi dal magazzino di destinazione

Un processo di ricezione della targa non può essere utilizzato se un ASN contiene un ID targa già esistente e ha dati fisici disponibili in una posizione del magazzino diversa dalla posizione del magazzino in cui si sta verificando la registrazione della targa.

Per gli scenari di ordine di trasferimento in cui il magazzino di transito non tiene traccia delle targhe (e quindi non tiene traccia dell'inventario fisico disponibile per targa), è possibile utilizzare la funzione *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione* per impedire aggiornamenti fisici disponibili delle targhe in transito.

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, questa funzione è elencata nel modo seguente:

- **Modulo:** *Gestione magazzino*
- **Nome della funzione:** *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione*

Per gestire la funzionalità quando questa funzione è disponibile, attenersi alla seguente procedura.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Generale**, nella scheda dettaglio **Targhe**, impostare il campo **Criteri targa del magazzino in transito** su uno dei seguenti valori:

    - **Consenti il riutilizzo di una targa non tracciata** – Il sistema funziona come quando la funzione *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione* non è disponibile. Questo valore è l'impostazione predefinita quando si attiva per la prima volta la funzione.
    - **Impedisci il riutilizzo della targa non tracciata** - Solo gli aggiornamenti disponibili relativi a una targa di spedizione spedita saranno consentiti nel magazzino di destinazione fino alla ricezione dell'ordine di trasferimento.

## <a name="more-information"></a>Ulteriori informazioni

<!-- To read more about inbound loads, see [Link for Inbound load (Olga's doc.)] -->

Per ulteriori informazioni sulle voci di menu dei dispositivi mobili, vedere [Configurare i dispositivi mobili per il lavoro di magazzino](configure-mobile-devices-warehouse.md).
