---
title: Risolvere i problemi relativi alle operazioni di magazzino in uscita
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in uscita in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 56bd91d8a6fe895317021d806e180df3a2db302b
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645454"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a>Risolvere i problemi relativi alle operazioni di magazzino in uscita

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in uscita in Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a>Viene visualizzato il seguente messaggio di errore: "Impossibile rilasciare l'ordine cliente".

### <a name="issue-description"></a>Descrizione del problema

Questo problema può verificarsi per diversi motivi. Ad esempio, l'ordine è in attesa della gestione del credito e non è possibile creare spedizioni finché non viene immesso un indirizzo postale valido per tutte le righe di vendita associate all'ordine cliente. In alternativa, esiste una sospensione dell'ordine che deve essere risolta prima che l'ordine possa essere rilasciato al magazzino. Questa sospensione potrebbe essere specifica dell'ordine o potrebbe essere sull'account del cliente.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Aggiungere o aggiornare l'indirizzo nell'ordine cliente e nelle righe ordine, quindi rilasciare l'ordine al magazzino. Gli ordini possono essere rilasciati al magazzino solo se hanno un indirizzo di consegna valido (in base all'impostazione del formato dell'indirizzo nel modulo **Amministrazione organizzazione**).

Esaminare la sospensione dell'ordine e risolvere i problemi. Quindi rimuovere la sospensione dall'ordine o dal cliente e rilasciare l'ordine al magazzino.

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a>Viene visualizzato il seguente messaggio: "La spedizione per il carico 1% è stata confermata." Tuttavia, non vengono registrate le righe.

### <a name="issue-description"></a>Descrizione del problema

È stata confermata una spedizione di un carico, ma non sono state effettuate ulteriori registrazioni.

### <a name="issue-resolution"></a>Risoluzione dei problemi

La conferma della spedizione non influisce sulla registrazione. Aggiorna solo lo stato della spedizione e del carico. La registrazione deve avvenire in un processo separato.

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a>Viene visualizzato il seguente messaggio di errore: "La consegna diretta non è in grado di elaborare per il magazzino 1% poiché la gestione magazzino è abilitata. Specificare un altro magazzino non abilitato per la gestione del magazzino."

### <a name="issue-description"></a>Descrizione del problema

Un articolo viene aggiunto a una riga di vendita per la consegna diretta da un magazzino abilitato per la gestione del magazzino (WMS). Viene visualizzato questo messaggio di errore quando viene aggiornata la riga di vendita. 

### <a name="issue-resolution"></a>Risoluzione dei problemi

Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. Attualmente, WMS non supporta la consegna diretta. Pertanto, per utilizzare la consegna diretta, è necessario selezionare un articolo e un magazzino non WMS.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]