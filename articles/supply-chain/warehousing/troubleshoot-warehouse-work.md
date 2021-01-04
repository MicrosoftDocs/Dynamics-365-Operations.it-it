---
title: Risolvere i problemi di lavoro di magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza il lavoro di magazzino in Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: a00ae517ff583e4231099d8e9f5d5b5a696cf7f7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645795"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="6013b-103">Risolvere i problemi di lavoro di magazzino</span><span class="sxs-lookup"><span data-stu-id="6013b-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6013b-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza il lavoro di magazzino in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6013b-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="6013b-105">Impossibile spostare le targhe con articoli con numero di serie quando nel gruppo di dimensioni di tracciabilità sono consentite uscite vuote e ricevute vuote.</span><span class="sxs-lookup"><span data-stu-id="6013b-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="6013b-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="6013b-106">Issue description</span></span>

<span data-ttu-id="6013b-107">Non è possibile spostare una targa utilizzando la voce di menu **Spostamento** se il numero di serie ha le impostazioni *Uscita non specificata consentita* e *Entrata non specificata consentita* nel gruppo di dimensioni di tracciabilità e se sono presenti più targhe nella stessa ubicazione, alcune delle quali hanno numeri di serie e altre no.</span><span class="sxs-lookup"><span data-stu-id="6013b-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="6013b-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="6013b-108">Issue resolution</span></span>

<span data-ttu-id="6013b-109">Questo problema verrà risolto dalle modifiche distribuite in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span><span class="sxs-lookup"><span data-stu-id="6013b-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="6013b-110">Queste modifiche renderanno il campo **Numero di serie** facoltativo quando sono consentiti entrate o uscite non specificate.</span><span class="sxs-lookup"><span data-stu-id="6013b-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="6013b-111">Quando elaboro i movimenti viene visualizzato il seguente messaggio di errore nell'app di magazzino: "Il proprietario dell'inventario %1 non è autorizzato in questo processo."</span><span class="sxs-lookup"><span data-stu-id="6013b-111">I receive the following error message in the warehouse app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="6013b-112">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="6013b-112">Issue description</span></span>

<span data-ttu-id="6013b-113">La dimensione di tracciabilità **Proprietario** non è presente quando l'app del magazzino viene utilizzata per effettuare gli spostamenti.</span><span class="sxs-lookup"><span data-stu-id="6013b-113">The **Owner** tracking dimension is missing when the warehouse app is used to make movements.</span></span> <span data-ttu-id="6013b-114">Un regolare giornale di registrazione trasferimento magazzino dal client Supply Chain Management sembra funzionare come previsto e può essere registrato solo se la dimensione **Proprietario** è compilata.</span><span class="sxs-lookup"><span data-stu-id="6013b-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="6013b-115">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="6013b-115">Issue resolution</span></span>

<span data-ttu-id="6013b-116">Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6013b-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="6013b-117">Attualmente, i processi di gestione del magazzino supportano solo l'inventario di proprietà della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6013b-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>
