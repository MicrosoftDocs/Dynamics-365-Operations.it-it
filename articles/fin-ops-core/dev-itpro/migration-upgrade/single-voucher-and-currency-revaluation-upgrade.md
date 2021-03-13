---
title: Aggiornare rivalutazioni valuta e giornali di registrazione a singolo giustificativo
description: Questo argomento descrive come aggiornare rivalutazioni valuta e giornali di registrazione a singolo giustificativo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3504c01a4ed1571866fd2a0cd83eef86a57d684a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127305"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a><span data-ttu-id="18639-103">Aggiornare rivalutazioni valuta e giornali di registrazione a singolo giustificativo</span><span class="sxs-lookup"><span data-stu-id="18639-103">Upgrade single-voucher journals and currency revaluations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18639-104">Alcune organizzazioni compilano giornali di registrazione che contengono un unico giustificativo che ha più clienti o fornitori ed eseguono anche il processo di rivalutazione valuta estera per la contabilità clienti o la contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="18639-104">Some organizations enter journals that contain a single voucher that has more than one customer or vendor, and they also run the Accounts receivable or Accounts payable foreign currency revaluation process.</span></span> <span data-ttu-id="18639-105">In questo argomento vengono descritti i passaggi che queste organizzazioni devono seguire quando eseguono l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="18639-105">This topic describes the steps that these organizations should follow when they upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

<span data-ttu-id="18639-106">Quando si esegue l'aggiornamento a Microsoft Dynamics 365 for Operations versione 1611, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="18639-106">Follow these steps when you upgrade to Microsoft Dynamics 365 for Operations version 1611.</span></span>

1.  <span data-ttu-id="18639-107">Prima di eseguire l'aggiornamento a Finance and Operations, eseguire i processi di rivalutazione valuta estera per la Contabilità clienti e la Contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="18639-107">Before you upgrade to Finance and Operations, run the foreign currency revaluation processes for Accounts receivable and Accounts payable.</span></span> <span data-ttu-id="18639-108">Impostare il campo **Metodo** su **Data fattura**.</span><span class="sxs-lookup"><span data-stu-id="18639-108">Set the **Method** field to **Invoice date**.</span></span> <span data-ttu-id="18639-109">Viene creata una transazione di rivalutazione che annulla l'ultima rivalutazione valuta estera.</span><span class="sxs-lookup"><span data-stu-id="18639-109">A revaluation transaction is created that reverses the last foreign currency revaluation.</span></span> <span data-ttu-id="18639-110">Di conseguenza, le transazioni aperte vengono valutate alla valuta di contabilizzazione originale.</span><span class="sxs-lookup"><span data-stu-id="18639-110">Therefore, the open transactions are valued at their original accounting currency.</span></span>
2.  <span data-ttu-id="18639-111">Eseguire l'aggiornamento alla versione 1611.</span><span class="sxs-lookup"><span data-stu-id="18639-111">Upgrade to version 1611.</span></span>
3.  <span data-ttu-id="18639-112">Eseguire di nuovo il processo di rivalutazione valuta esterna per la contabilità fornitori e la contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="18639-112">Run the Accounts receivable and Accounts payable foreign currency revaluation processes again.</span></span> <span data-ttu-id="18639-113">Impostare questa volta il campo **Metodo** su **Standard**.</span><span class="sxs-lookup"><span data-stu-id="18639-113">This time, set the **Method** field to **Standard**.</span></span> <span data-ttu-id="18639-114">Viene creata una nuova transazione di rivalutazione basata sui tassi di cambio correnti.</span><span class="sxs-lookup"><span data-stu-id="18639-114">A new revaluation transaction is created that is based on the current exchange rates.</span></span> <span data-ttu-id="18639-115">Questa transazione registra il profitto/la perdita non realizzati e il conto CoGe riepilogativo corretto.</span><span class="sxs-lookup"><span data-stu-id="18639-115">This transaction records the unrealized gain/loss and the correct summary ledger account.</span></span>
