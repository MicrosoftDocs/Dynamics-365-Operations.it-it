---
title: Modalità di creazione clienti asicroni
description: Questo articolo descrive la modalità di creazione dei clienti asincroni in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 4ca63fe06a804035e976a3432454078c1cca0020
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880142"
---
# <a name="asynchronous-customer-creation-mode"></a>Modalità di creazione clienti asicroni

[!include [banner](includes/banner.md)]

Questo articolo descrive la modalità di creazione dei clienti asincroni in Microsoft Dynamics 365 Commerce.

In Commerce, vi sono due modalità di creazione di clienti: sincrona (o sync) e asincrona (o async). Per impostazione predefinita, i clienti vengono creati in modalità sincrona. In altre parole, vengono creati in Commerce Headquarters in tempo reale. La creazione di clienti in modalità sincrona è vantaggiosa perché i nuovi clienti sono immediatamente disponibili per la ricerca nei canali. Tuttavia, ha anche uno svantaggio. Poiché genera chiamate [Commerce Data Exchange: Servizio in tempo reale](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) a Commerce Headquarters, le prestazioni possono essere alterate se vengono effettuate molte chiamate simultanee per la creazione di clienti.

Se l'opzione **Crea cliente in modalità asincrona** è impostata su **Sì** nel profilo di funzionalità del punto vendita (**Retail e Commerce \> Impostazione canale \> Impostazione punto vendita online \> Profili funzionalità**), le chiamate di Servizio in tempo reale non vengono utilizzate per creare record cliente nel database del canale. La creazione di clienti in modalità asincrona non influisce sulle prestazioni di Commerce Headquarters. Un identificatore univoco globale (GUID) temporaneo viene assegnato a ogni nuovo record cliente asincrono e utilizzato come ID account cliente. Questo GUID non è visibile agli utenti POS. Quegli utenti vedranno invece **In attesa di sincronizzazione** come ID account cliente.

> [!IMPORTANT]
> Se il POS è offline, il sistema crea automaticamente i clienti in modo asincrono, anche se la modalità di creazione di clienti asincrona è disabilitata. Pertanto, indipendentemente dalla selezione tra la creazione cliente sincrona o asincrona, gli amministratori di Commerce Headquarters devono creare e pianificare un processo batch ricorrente per il **Processo P**, il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** (in precedenza definito processo **Sincronizza clienti e partner commerciali dalla modalità asincrona**) e il processo **1010**, in modo che tutti i clienti asincroni vengano convertiti in clienti sincroni in Commerce Headquarters.

## <a name="async-customer-limitations"></a>Limitazioni dei clienti asincroni

La funzionalità dei clienti asincroni attualmente presenta le seguenti limitazioni:

- I record cliente asincroni non possono essere modificati a meno che il cliente non sia stato in Commerce Headquartes e il nuovo ID account cliente non sia stato sincronizzato di nuovo con il canale.
- Le carte fedeltà non possono essere emesse ai clienti asincroni a meno che il nuovo ID account cliente non sia stato sincronizzato di nuovo con il canale.

## <a name="async-customer-enhancements"></a>Miglioramenti dei clienti asincroni

A partire dalla versione Commerce 10.0.24, puoi abilitare la funzionalità **Abilita la creazione di clienti asincroni migliorata** nell'area di lavoro **Gestione funzionalità**. Questa funzione colma il divario tra le modalità di creazione clienti asincroni e sincroni in POS ed e-commerce nei seguenti modi:

- Le affiliazioni non possono essere associate a clienti asincroni.
- I titoli possono essere aggiunti ai clienti asincroni.
- Non è possibile acquisire indirizzi e-mail e numeri di telefono secondari per i clienti asincroni.

A partire dalla versione Commerce 10.0.22, puoi abilitare la funzionalità **Abilita la creazione asincrona per gli indirizzi dei clienti** nell'area di lavoro **Gestione funzionalità**. Questa funzione consente di salvare in modo asincrono gli indirizzi dei clienti appena creati sia per i clienti sincroni che per i clienti asincroni.

Dopo aver abilitato le precedenti funzionalità, devi pianificare un processo batch ricorrente per il **processo P**, il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** e il processo **1010**, di modo che qualsiasi cliente asincrono sia convertito in cliente sincrono in Commerce Headquarters.

### <a name="customer-creation-in-pos-offline-mode"></a>Creazione di clienti in modalità offline POS

Come indicato in precedenza, se il POS è offline, il sistema crea automaticamente i clienti in modo asincrono, anche se la modalità di creazione di clienti asincrona è disabilitata. Pertanto, gli amministratori di Commerce Headquarters devono creare e pianificare un processo batch ricorrente per il **processo P**, il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** e il processo **1010**, di modo che qualsiasi cliente asincrono sia convertito in cliente sincrono in Commerce Headquarters.

> [!NOTE]
> Se l'opzione **Filtra tabelle di dati di clienti condivise** è impostata su **Sì** nella pagina **Schema del canale di commercio** (**Retail e Commerce \> Impostazione sedi centrali \> Utilità di pianificazione di commercio \> Gruppo di database canale**), i record cliente non vengono creati in modalità offline POS. Per ulteriori informazioni, vedere [Esclusione di dati offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestione dei clienti nei punti vendita](customer-mgmt-stores.md)

[Convertire i clienti asincroni in clienti sincroni](convert-async-to-sync.md)

[Attributi cliente](dev-itpro/customer-attributes.md)

[Esclusione di dati offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
