---
title: Risolvere i problemi di lavoro di magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza il lavoro di magazzino in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 08cc074fe851b952ebfc942ae3d1cb05240d3b91
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837443"
---
# <a name="troubleshoot-warehouse-work"></a>Risolvere i problemi di lavoro di magazzino

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza il lavoro di magazzino in Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a>Impossibile spostare le targhe con articoli con numero di serie quando nel gruppo di dimensioni di tracciabilità sono consentite uscite vuote e ricevute vuote.

### <a name="issue-description"></a>Descrizione del problema

Non è possibile spostare una targa utilizzando la voce di menu **Spostamento** se il numero di serie ha le impostazioni *Uscita non specificata consentita* e *Entrata non specificata consentita* nel gruppo di dimensioni di tracciabilità e se sono presenti più targhe nella stessa ubicazione, alcune delle quali hanno numeri di serie e altre no.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Questo problema verrà risolto dalle modifiche distribuite in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Queste modifiche renderanno il campo **Numero di serie** facoltativo quando sono consentiti entrate o uscite non specificate.

## <a name="i-receive-the-following-error-message-in-the-warehouse-management-mobile-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a>Quando elaboro i movimenti viene visualizzato il seguente messaggio di errore nell'app per dispositivi mobili Gestione magazzino: "Il proprietario dell'inventario %1 non è autorizzato in questo processo."

### <a name="issue-description"></a>Descrizione del problema

La dimensione di tracciabilità **Proprietario** non è presente quando l'app per dispositivi mobili Gestione magazzino viene utilizzata per effettuare gli spostamenti. Un regolare giornale di registrazione trasferimento magazzino dal client Supply Chain Management sembra funzionare come previsto e può essere registrato solo se la dimensione **Proprietario** è compilata.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità. Attualmente, i processi di gestione del magazzino supportano solo l'inventario di proprietà della persona giuridica.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]