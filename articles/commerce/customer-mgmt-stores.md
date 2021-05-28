---
title: Gestione dei clienti nei punti vendita
description: In questo argomento viene descritto come i rivenditori possono abilitare le funzionalità di gestione dei clienti presso il POS in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e43f8f5b91f729dc93eccb9e9e4ee21b5a5d1596
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019989"
---
# <a name="customer-management-in-stores"></a>Gestione dei clienti nei punti vendita

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come i rivenditori possono abilitare le funzionalità di gestione dei clienti presso il POS in Microsoft Dynamics 365 Commerce.

È importante che i dipendenti del punto vendita possano creare e modificare i record cliente nel POS. In tal modo, possono acquisire eventuali aggiornamenti delle informazioni sui clienti come indirizzo e-mail, numero di telefono e indirizzo. Queste informazioni sono utili nei sistemi a valle come il marketing, perché l'efficacia di tali sistemi dipende dall'accuratezza dei dati dei loro clienti.

Gli addetti alle vendite possono attivare il flusso di lavoro di creazione di clienti da due punti di ingresso POS. Possono selezionare un pulsante che è mappato all'operazione **Aggiunta cliente**, oppure possono selezionare **Crea cliente** nella barra dell'applicazione nella pagina dei risultati di ricerca. In entrambi i casi, viene visualizzata la finestra di dialogo **Nuovo cliente** in cui gli addetti alle vendite possono inserire i dettagli del cliente richiesti, come il nome, l'indirizzo e-mail, il numero di telefono, l'indirizzo e qualsiasi altra informazione rilevante per l'attività. Tali informazioni aggiuntive possono essere acquisite utilizzando gli attributi associati al cliente. Per ulteriori informazioni sugli attributi del cliente, vedere [Attributi cliente](dev-itpro/customer-attributes.md).

Gli addetti alle vendite possono anche acquisire indirizzi e-mail e numeri di telefono secondari. Inoltre, possono acquisire la preferenza del cliente sulla ricezione di informazioni di marketing tramite uno qualsiasi di questi indirizzi e-mail o numeri di telefono secondari. Per abilitare questa funzionalità, i rivenditori devono attivare la funzionalità **Acquisisci più e-mail e numeri di telefono e acconsenti attività di marketing per questi contatti** nell'area di lavoro **Gestione funzionalità** in Commerce Headquarters (**Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**).

## <a name="default-customer-properties"></a>Proprietà cliente predefinite

I rivenditori possono utilizzare la pagina **Tutti i punti vendita** in Commerce Headquarters (**Retail e Commerce \> Canali \> Punti vendita**) per associare un cliente predefinito a ogni punto vendita. Commerce copia quindi le proprietà definite per il cliente predefinito in tutti i nuovi record cliente creati. Ad esempio, la finestra di dialogo **Crea cliente** mostra le proprietà ereditate dal cliente predefinito associato al punto vendita. Tali proprietà includono il tipo di cliente, il gruppo di clienti, la preferenza di ricevuta, la valuta e la lingua. Anche eventuali affiliazioni (raggruppamenti di clienti) vengono ereditate dal cliente predefinito. Tuttavia, le dimensioni finanziarie vengono ereditate dal gruppo di clienti associato al cliente predefinito, non dal cliente predefinito stesso.

Gli addetti alle vendite possono acquisire più indirizzi per un cliente. Il nome e il numero di telefono del cliente vengono ereditati dalle informazioni di contatto associate a ciascun indirizzo. La Scheda dettaglio **Indirizzi** di un record cliente include un campo **Scopo** che gli addetti alle vendite possono modificare. Se il tipo di cliente è **Persona**, il valore predefinito è **Domicilio**. Se il tipo di cliente è **Organizzazione**, il valore predefinito è **Azienda**. Altri valori supportati da questo campo includono **Domicilio**, **Ufficio** e **Casella postale**. Il valore del campo **Paese** per un indirizzo viene ereditato dall'indirizzo principale specificato nella pagina **Unità operativa** di Commerce headquarters in **Amministrazione organizzazione \> Organizzazioni \> Unità operative**.

## <a name="sync-customers-and-async-customers"></a>Clienti sincroni e clienti asincroni

In Commerce, vi sono due modalità di creazione di clienti: sincrona e asincrona. Per impostazione predefinita, i clienti vengono creati in modalità sincrona. In altre parole, vengono creati in Commerce Headquarters in tempo reale. La creazione di clienti in modalità sincrona è vantaggiosa perché i nuovi clienti sono immediatamente disponibili per la ricerca nei canali. Tuttavia, ha anche uno svantaggio. Poiché genera chiamate [Commerce Data Exchange: Servizio in tempo reale](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) a Commerce Headquarters, le prestazioni possono essere alterate se vengono effettuate molte chiamate simultanee per la creazione di clienti.

Se l'opzione **Crea cliente in modalità asincrona** è impostata su **Sì** nel profilo di funzionalità del punto vendita (**Retail e Commerce \> Impostazione canale \> Impostazione punto vendita online \> Profili funzionalità**), le chiamate di Servizio in tempo reale non vengono utilizzate per creare record cliente nel database del canale. La creazione di clienti in modalità asincrona non influisce sulle prestazioni di Commerce Headquarters. Un identificatore univoco globale (GUID) temporaneo viene assegnato a ogni nuovo record cliente asincrono e utilizzato come ID account cliente. Questo GUID non è visibile agli utenti POS. Quegli utenti vedranno invece **In attesa di sincronizzazione** come ID account cliente. Sebbene questa configurazione forzi la creazione asincrona dei clienti, notare che le modifiche ai record cliente vengono sempre eseguite in modo sincrono.

### <a name="convert-async-customers-to-sync-customers"></a>Convertire i clienti asincroni in clienti sincroni

Per convertire i clienti asincroni in clienti sincroni, è necessario prima eseguire il processo P per inviare i clienti asincroni a Commerce Headquarters. Esegui quindi il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** per creare ID account cliente. Infine, eseguire il processo **1010** per sincronizzare i nuovi ID account cliente con i canali.

### <a name="async-customer-limitations"></a>Limitazioni dei clienti asincroni

La funzionalità dei clienti asincroni attualmente presenta le seguenti limitazioni:

- I record cliente asincroni non possono essere modificati a meno che il cliente non sia stato in Commerce Headquartes e il nuovo ID account cliente non sia stato sincronizzato di nuovo con il canale.
- Le affiliazioni non possono essere associate a clienti asincroni. Pertanto, i nuovi clienti asincroni non ereditano le affiliazioni del cliente predefinito.
- Le carte fedeltà non possono essere emesse ai clienti asincroni a meno che il nuovo ID account cliente non sia stato sincronizzato di nuovo con il canale.
- Non è possibile acquisire indirizzi e-mail e numeri di telefono secondari per i clienti asincroni.

### <a name="customer-creation-in-pos-offline-mode"></a>Creazione di clienti in modalità offline POS

Se il POS è offline quando è abilitata la modalità di creazione di clienti asincrona, i nuovi record cliente vengono creati in modalità asincrona. Se il POS è offline quando la modalità di creazione di clienti asincrona è disabilitata, il sistema passa automaticamente alla modalità di creazione di cliente asincrona. In altre parole, i record cliente potrebbero essere creati in modalità asincrona anche se la modalità di creazione di clienti asincrona è disabilitata. Pertanto, gli amministratori di Commerce Headquarters devono creare e pianificare un processo batch ricorrente per il processo P, il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** e il processo **1010**, di modo che qualsiasi cliente asincrono sia convertito in cliente sincrono in Commerce Headquarters.

> [!NOTE]
> Se l'opzione **Filtra tabelle di dati di clienti condivise** è impostata su **Sì** nella pagina **Schema del canale di commercio** (**Retail e Commerce \> Impostazione sedi centrali \> Utilità di pianificazione di commercio \> Gruppo di database canale**), i record cliente non vengono creati in modalità offline POS. Per ulteriori informazioni, vedere [Esclusione di dati offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Risorse aggiuntive

[Attributi cliente](dev-itpro/customer-attributes.md)

[Esclusione di dati offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
