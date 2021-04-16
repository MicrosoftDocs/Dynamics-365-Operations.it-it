---
title: Risolvere i problemi di aggiornamento e migrazione alla gestione avanzata del magazzino
description: Questo argomento descrive come risolvere i problemi comuni che potrebbero verificarsi durante l'aggiornamento e la migrazione alla gestione avanzata del magazzino.
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
ms.openlocfilehash: 953b828667a01157767c3ca79349fe972b0fbe9b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826397"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a>Risolvere i problemi di aggiornamento e migrazione alla gestione avanzata del magazzino

[!include [banner](../includes/banner.md)]

Questo argomento descrive come risolvere i problemi comuni che potrebbero verificarsi durante l'aggiornamento e la migrazione alla gestione avanzata del magazzino.

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a>Viene visualizzto il seguente messaggio di errore: "java.security.cert.certPathValidatorException: l'ancoraggio di trust per il percorso di certificazione non è stato trovato."

### <a name="issue-description"></a>Descrizione del problema

Viene visualizzato questo messaggio di errore nell'app per dispositivi mobili Gestione magazzino, perché i certificati autofirmati non sono attendibili su Android 8+ in ambienti locali.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Utilizzare un'autorità di certificazione (CA) esterna (pubblica). Una correzione per questo problema è disponibile nella versione 1.9.0.0 dell'app del magazzino. Per ulteriori informazioni su questo problema e su come risolverlo, vedere [Risolvere i problemi di connessione dell'app per dispositivi mobili Gestione magazzino](troubleshoot-warehouse-app-connection.md).

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a>Qual è il processo approvato per il passaggio dal magazzino di base a quello avanzato?

### <a name="issue-description"></a>Descrizione del problema

Al momento si gestisce stock/inventario e si usa la funzionalità di base delle scorte e si desidera passare al magazzino avanzato per sfruttare i dispositivi mobili, i cicli e il lavoro. Tuttavia, si stanno riscontrando problemi quando si prova a fare questo passaggio. Ad esempio, non è possibile modificare i prodotti in modo che utilizzino le dimensioni di immagazzinamento (sito, magazzino e ubicazione), poiché i prodotti hanno transazioni attive. Pertante, è necessario apprendere il processo approvato per il passaggio dal magazzino di base a quello avanzato.

### <a name="issue-resolution"></a>Risoluzione dei problemi

Per ulteriori informazioni sul processo per il passaggio dal magazzino di base al magazzino avanzato, vedere i seguenti post di blog e documentazione:

- [Abilitare il processo di gestione magazzino per magazzini e articoli esistenti](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [Migrazione di Microsoft Dynamics AX WMS al nuovo magazzino R3 e funzionalità di trasporto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [Migrazione degli articoli WMSI/WMS2](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [Aggiornare la gestione magazzino da Microsoft Dynamics AX 2012 a Supply Chain Management](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]