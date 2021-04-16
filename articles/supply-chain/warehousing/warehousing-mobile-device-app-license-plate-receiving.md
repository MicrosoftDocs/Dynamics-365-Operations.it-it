---
title: Ricezione della targa tramite l'app per dispositivi mobili Gestione magazzino
description: Questo argomento spiega come configurare l'app per dispositivi mobili Gestione magazzino per supportare l'utilizzo di un processo di ricezione della targa per ricevere l'inventario fisico.
author: perlynne
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 8c662da296bea7def443cb166bd3f7e501c9abcc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823193"
---
# <a name="license-plate-receiving-via-the-warehouse-management-mobile-app"></a>Ricezione della targa tramite l'app per dispositivi mobili Gestione magazzino

[!include [banner](../includes/banner.md)]

Questo argomento spiega come configurare l'app per dispositivi mobili Gestione magazzino in modo che supporti l'utilizzo di un processo di ricezione della targa per ricevere l'inventario fisico.

È possibile utilizzare questa funzionalità per registrare rapidamente l'entrata di inventario in entrata correlata a un avviso di spedizione anticipata (ASN). Il sistema crea automaticamente un ASN quando i processi di gestione del magazzino vengono utilizzati per spedire un ordine di trasferimento. Per il processo dell'ordine fornitore, un ASN può essere registrato manualmente oppure può essere importato automaticamente utilizzando un processo dell'entità dati ASN in entrata.

I dati ASN sono collegati a carichi e spedizioni tramite le *strutture di imballaggio*, dove i pallet (targhe padre) possono contenere casi (targhe nidificate).

> [!NOTE]
> Per ridurre il numero di transazioni di inventario quando vengono utilizzate strutture di imballaggio con targhe nidificate, il sistema registra l'inventario fisico disponibile sulla targa padre. Per attivare il movimento dell'inventario fisico disponibile dalla targa padre alle targhe nidificate, in base ai dati della struttura dell'imballaggio, il dispositivo mobile deve fornire una voce di menu basata sul processo di creazione del lavoro *Imballa in targhe nidificate*.

## <a name="warehousing-mobile-device-app-processing"></a>Elaborazione dell'app Warehousing per dispositivi mobili

Quando un lavoratore esegue la scansione di un ID targa in entrata, il sistema inizializza un processo di ricevimento di targhe. Sulla base di queste informazioni, il contenuto della targa (dati provenienti dall'ASN) viene fisicamente registrato nell'ubicazione della banchina in entrata. I flussi che seguono dipenderanno dalle esigenze dei processi aziendali.

## <a name="work-policies"></a>Criteri di lavoro

Come (ad esempio) per il processo della voce di menu *Dichiarazione di finito* dei dispositivi mobili, il processo di ricevimento delle targhe supporta diversi flussi di lavoro basati sulla configurazione definita.

### <a name="work-policies-with-work-creation"></a>Criteri di lavoro con creazione di lavoro

Quando si registrano articoli in arrivo utilizzando un criterio di lavoro che crea lavoro, il sistema genera e salva i record di lavoro di stoccaggio per ogni registrazione. Se si utilizza il processo di lavoro *Ricevimento e stoccaggio targa*, la registrazione e lo stoccaggio vengono gestiti come un'unica operazione utilizzando una singola voce di menu dei dispositivi mobili. Se si utilizza il processo *Ricevimento targa*, i processi di ricevimento e stoccaggio vengono gestiti come due diverse operazioni di magazzino, ciascuna con la propria voce di menu dei dispositivi mobili.

### <a name="work-policies-without-work-creation"></a>Criteri di lavoro senza creazione di lavoro

È possibile utilizzare il processo di ricevimento delle targhe senza creare lavoro. Se si definiscono criteri di lavoro il cui tipo di ordine di lavoro è *Entrata ricevimento* e/o *Ordini fornitore* e si utilizza processo per *Ricevimento (e stoccaggio) targa*, i seguenti due processi dell'app Warehousing per dispositivi mobili non creano lavoro. Invece, registreranno semplicemente le scorte fisiche in entrata sulla targa nella banchina di ricevimento in entrata.

- *Ricevimento targa*
- *Ricevimento e stoccaggio targa*

> [!NOTE]
> - È necessario definire almeno un'ubicazione per un criterio di lavoro nella sezione **Ubicazioni di magazzino**. Non è possibile specificare la stessa ubicazione per molteplici criteri di lavoro.
> - L'opzione **Stampa etichetta** per le voci di menu di dispositivi mobili dell'app Warehousing non stampa un'etichetta di targa senza creazione di lavoro.

Per rendere disponibile questa funzionalità nel sistema, attivare *Miglioramenti del ricevimento della targa* in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>Ricevere le scorte in un'ubicazione che non tiene traccia delle targhe

È possibile utilizzare un'ubicazione di magazzino assegnata a un profilo di ubicazione anche quando **Usa rilevamento targa** non è attivata. Pertanto, quando si ricevono le scorte, è possibile registrare direttamente le scorte disponibili in un'ubicazione senza creazione di lavoro.

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>Aggiungere voci di menu di dispositivi mobili per ogni ubicazione di ricevimento in un magazzino

La funzionalità *Miglioramenti del ricevimento della targa* consente il ricevimento in qualsiasi ubicazione di un magazzino aggiungendo voci di menu per ricevimento (e stoccaggio) della targa specifiche dell'ubicazione all'app Warehousing per dispositivi mobili. In precedenza, il sistema supportava il ricevimento solo nell'ubicazione predefinita definita per ciascun magazzino. Tuttavia, se questa funzionalità è attivata, le voci di menu di dispositivi mobili per il ricevimento (e lo stoccaggio) della targa includono ora l'opzione **Utilizza dati predefiniti**, che consente di selezionare un'ubicazione "a" personalizzata per ciascuna voce di menu. Questa opzione era già disponibile per alcuni altri tipi di voci di menu.

Per rendere disponibile questa funzionalità nel sistema, attivare *Miglioramenti del ricevimento della targa* in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="show-or-skip-the-receiving-summary-page"></a>Visualizzare o ignorare la pagina di riepilogo del ricevimento

È possibile utilizzare la funzionalità *Controlla se visualizzare una pagina di riepilogo di ricevimento su dispositivi mobili* per sfruttare un ulteriore flusso dettagliato dell'app per dispositivi mobili Gestione magazzino come parte del processo di ricevimento della targa.

Quando questa funzione è attivata, le voci di menu del dispositivo mobile per il ricevimento della targa o il ricevimento e lo stoccaggio della targa forniranno l'impostazione **Visualizza la pagina di riepilogo di ricevimento**. Questa impostazione ha le seguenti opzioni:

- **Visualizza un riepilogo dettagliato** - Durante il ricevimento della targa, i lavoratori vedranno una pagina aggiuntiva che mostra le informazioni ASN complete.
- **Ignora il riepilogo** - I lavoratori non vedranno le informazioni ASN complete. Inoltre, gli addetti al magazzino non saranno in grado di impostare un codice smaltimento o aggiungere eccezioni durante il processo di ricevimento.

Per rendere disponibile questa funzionalità nel sistema, attivare la funzionalità *Controlla se visualizzare una pagina di riepilogo di ricevimento su dispositivi mobili* in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Impedire che le targhe spedite dall'ordine di trasferimento vengano utilizzate in magazzini diversi dal magazzino di destinazione

Un processo di ricevimento della targa non può essere utilizzato se un ASN contiene un ID targa già esistente e ha dati fisici disponibili in un'ubicazione del magazzino diversa da quella in cui avviene la registrazione della targa.

Per gli scenari di ordine di trasferimento in cui il magazzino di transito non tiene traccia delle targhe (e quindi non tiene traccia dell'inventario fisico disponibile per targa), è possibile utilizzare la funzione *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione* per impedire aggiornamenti fisici disponibili delle targhe in transito.

Per rendere disponibile questa funzionalità nel sistema, attivare *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione* in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Per gestire la funzionalità quando questa funzione è disponibile, attenersi alla seguente procedura.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Generale**, nella scheda dettaglio **Targhe**, impostare il campo **Criteri targa del magazzino in transito** su uno dei seguenti valori:

    - **Consenti il riutilizzo di una targa non tracciata** – Il sistema funziona come quando la funzione *Impedisci che le targhe spedite dall'ordine di trasferimento vengano utilizzate su altri magazzini diversi dal magazzino di destinazione* non è disponibile. Questo valore è l'impostazione predefinita quando si attiva per la prima volta la funzione.
    - **Impedisci il riutilizzo della targa non tracciata** - Solo gli aggiornamenti disponibili relativi a una targa di spedizione spedita saranno consentiti nel magazzino di destinazione fino al ricevimento dell'ordine di trasferimento.

## <a name="more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sulle voci di menu dei dispositivi mobili, vedere [Configurare i dispositivi mobili per il lavoro di magazzino](configure-mobile-devices-warehouse.md).

Per ulteriori informazioni sullo scenario di produzione *Dichiarazione di finito*, vedere [Panoramica dei criteri di lavoro del magazzino](warehouse-work-policies.md).

Per ulteriori informazioni sulla gestione dei carichi in entrata, vedere [Gestione magazzino dei carichi in entrata per gli ordini fornitore](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]