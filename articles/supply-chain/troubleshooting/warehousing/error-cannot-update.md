---
title: Errore durante la selezione dell'ubicazione nel corso della registrazione della distinta di prelievo
description: Errore durante la selezione dell'ubicazione nel corso della registrazione della distinta di prelievo.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026627"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a><span data-ttu-id="56aaf-103">Errore durante la selezione dell'ubicazione nel corso della registrazione della distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="56aaf-103">An error occurs when the location is selected during picking list registration</span></span>

<span data-ttu-id="56aaf-104">Numero KB: 4613106</span><span class="sxs-lookup"><span data-stu-id="56aaf-104">KB number: 4613106</span></span>

## <a name="symptoms"></a><span data-ttu-id="56aaf-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="56aaf-105">Symptoms</span></span>

<span data-ttu-id="56aaf-106">Questo problema si verifica quando il sistema è configurato per prenotare automaticamente ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="56aaf-106">This issue occurs when your system is configured to automatically reserve sales orders.</span></span> <span data-ttu-id="56aaf-107">Se tenti di selezionare l'ubicazione per una riga di registrazione della distinta di prelievo, viene visualizzato il seguente messaggio di errore quando utilizzi i processi di prenotazione di Gestione magazzino (WMS):</span><span class="sxs-lookup"><span data-stu-id="56aaf-107">If you try to select the location for a picking list registration line, you receive the following error message when you use warehouse management (WMS) reservation processes:</span></span>

> <span data-ttu-id="56aaf-108">Impossibile aggiornare la quantità con nuove dimensioni</span><span class="sxs-lookup"><span data-stu-id="56aaf-108">Can't update quantity with new dimensions</span></span>

<span data-ttu-id="56aaf-109">Questo problema può verificarsi perché non disponi di scorte disponibili sufficienti in un'ubicazione specificata.</span><span class="sxs-lookup"><span data-stu-id="56aaf-109">This issue can occur because you don't have enough on-hand inventory at a specified location.</span></span>

## <a name="resolution"></a><span data-ttu-id="56aaf-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="56aaf-110">Resolution</span></span>

<span data-ttu-id="56aaf-111">Il sistema si comporta come previsto.</span><span class="sxs-lookup"><span data-stu-id="56aaf-111">The system is behaving as designed.</span></span>

<span data-ttu-id="56aaf-112">Negli scenari in cui utilizzi il processo di prenotazione a livello di magazzino, se le scorte disponibili non sono prenotate a tutti i livelli delle dimensioni inventariali e non disponi di scorte disponibili sufficienti in un'ubicazione specificata, ti consigliamo di utilizzare il processo di prenotazione manuale dalla riga di prelievo.</span><span class="sxs-lookup"><span data-stu-id="56aaf-112">In scenarios where you use the warehouse-level reservation process, if the on-hand inventory won't be reserved on all inventory dimension levels, and you don't have enough on-hand inventory at a specified location, we recommend that you use the manual reservation process from the picking line.</span></span> <span data-ttu-id="56aaf-113">Successivamente, puoi utilizzare la funzione *Prenota lotto* per distribuire le prenotazioni inferiori, come l'ubicazione, per tutte le quantità disponibili.</span><span class="sxs-lookup"><span data-stu-id="56aaf-113">You can then use the *Reserve lot* function to distribute the lower reservations, such as location, for all the available on-hand quantities.</span></span>
