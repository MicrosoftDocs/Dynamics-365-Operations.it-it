---
title: Risolvere i problemi di aggiornamento e migrazione alla gestione avanzata del magazzino
description: Questo argomento descrive come risolvere i problemi comuni che potrebbero verificarsi durante l'aggiornamento e la migrazione alla gestione avanzata del magazzino.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f5bfee31ce27e919086f978fb3ff88ca61a65eba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208089"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a><span data-ttu-id="4b63a-103">Risolvere i problemi di aggiornamento e migrazione alla gestione avanzata del magazzino</span><span class="sxs-lookup"><span data-stu-id="4b63a-103">Troubleshoot upgrade and migration to advanced warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b63a-104">Questo argomento descrive come risolvere i problemi comuni che potrebbero verificarsi durante l'aggiornamento e la migrazione alla gestione avanzata del magazzino.</span><span class="sxs-lookup"><span data-stu-id="4b63a-104">This topic describes how to fix common issues that you might encounter while you upgrade and migrate to advanced warehouse management.</span></span>

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a><span data-ttu-id="4b63a-105">Viene visualizzto il seguente messaggio di errore: "java.security.cert.certPathValidatorException: l'ancoraggio di trust per il percorso di certificazione non è stato trovato."</span><span class="sxs-lookup"><span data-stu-id="4b63a-105">I receive the following error message: "java.security.cert.certPathValidatorException: Trust anchor for certification path is not found."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4b63a-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="4b63a-106">Issue description</span></span>

<span data-ttu-id="4b63a-107">Viene visualizzato questo messaggio di errore nell'app del magazzino, perché i certificati autofirmati non sono attendibili su Android 8+ in ambienti locali.</span><span class="sxs-lookup"><span data-stu-id="4b63a-107">You receive this error message in the warehouse app, because self-signed certificates aren't trusted on Android 8+ in on-premises environments.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4b63a-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4b63a-108">Issue resolution</span></span>

<span data-ttu-id="4b63a-109">Utilizzare un'autorità di certificazione (CA) esterna (pubblica).</span><span class="sxs-lookup"><span data-stu-id="4b63a-109">Use an external (public) certifying authority (CA).</span></span> <span data-ttu-id="4b63a-110">Una correzione per questo problema è disponibile nella versione 1.9.0.0 dell'app del magazzino.</span><span class="sxs-lookup"><span data-stu-id="4b63a-110">A fix for this issue is available in version 1.9.0.0 of the warehouse app.</span></span> <span data-ttu-id="4b63a-111">Per ulteriori informazioni su questo problema e su come risolverlo, vedere [Risolvere i problemi di connessione delle app di magazzino](troubleshoot-warehouse-app-connection.md).</span><span class="sxs-lookup"><span data-stu-id="4b63a-111">For more information about this issue and how to fix it, see [Troubleshoot warehouse app connection issues](troubleshoot-warehouse-app-connection.md).</span></span>

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a><span data-ttu-id="4b63a-112">Qual è il processo approvato per il passaggio dal magazzino di base a quello avanzato?</span><span class="sxs-lookup"><span data-stu-id="4b63a-112">What is the approved process for moving from basic warehousing to advanced warehousing?</span></span>

### <a name="issue-description"></a><span data-ttu-id="4b63a-113">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="4b63a-113">Issue description</span></span>

<span data-ttu-id="4b63a-114">Al momento si gestisce stock/inventario e si usa la funzionalità di base delle scorte e si desidera passare al magazzino avanzato per sfruttare i dispositivi mobili, i cicli e il lavoro.</span><span class="sxs-lookup"><span data-stu-id="4b63a-114">You're currently running under stock/inventory management and using basic stock functionality, and you want to move to advanced warehousing to take advantage of mobile devices, waves, and work.</span></span> <span data-ttu-id="4b63a-115">Tuttavia, si stanno riscontrando problemi quando si prova a fare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4b63a-115">However, you're experiencing issues when you try to make this move.</span></span> <span data-ttu-id="4b63a-116">Ad esempio, non è possibile modificare i prodotti in modo che utilizzino le dimensioni di immagazzinamento (sito, magazzino e ubicazione), poiché i prodotti hanno transazioni attive.</span><span class="sxs-lookup"><span data-stu-id="4b63a-116">For example, you can't change your products so that they use storage dimensions (site, warehouse, and location), because the products have transactions against them.</span></span> <span data-ttu-id="4b63a-117">Pertante, è necessario apprendere il processo approvato per il passaggio dal magazzino di base a quello avanzato.</span><span class="sxs-lookup"><span data-stu-id="4b63a-117">Therefore, you must learn the approved process for moving from basic warehousing to advanced warehousing.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4b63a-118">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4b63a-118">Issue resolution</span></span>

<span data-ttu-id="4b63a-119">Per ulteriori informazioni sul processo per il passaggio dal magazzino di base al magazzino avanzato, vedere i seguenti post di blog e documentazione:</span><span class="sxs-lookup"><span data-stu-id="4b63a-119">For more information about the process for moving from basic warehousing to advanced warehousing, see the following blog posts and documentation:</span></span>

- [<span data-ttu-id="4b63a-120">Abilitare il processo di gestione magazzino per magazzini e articoli esistenti</span><span class="sxs-lookup"><span data-stu-id="4b63a-120">Enable warehouse management process for existing items and warehouses</span></span>](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [<span data-ttu-id="4b63a-121">Migrazione di Microsoft Dynamics AX WMS al nuovo magazzino R3 e funzionalità di trasporto</span><span class="sxs-lookup"><span data-stu-id="4b63a-121">Migration of Microsoft Dynamics AX WMS to new R3 warehouse and transportation functionality</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [<span data-ttu-id="4b63a-122">Migrazione degli articoli WMSI/WMS2</span><span class="sxs-lookup"><span data-stu-id="4b63a-122">WMSI/WMS2 item migration</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [<span data-ttu-id="4b63a-123">Aggiornare la gestione magazzino da Microsoft Dynamics AX 2012 a Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="4b63a-123">Upgrade warehouse management from Microsoft Dynamics AX 2012 to Supply Chain Management</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]