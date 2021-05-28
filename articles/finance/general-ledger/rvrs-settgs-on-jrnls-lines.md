---
title: Impostazioni di storno per giornali di registrazione e righe
description: In questo argomento viene illustrato il motivo per cui un movimento di storno immesso in un giornale di registrazione generale potrebbe non essere incluso nella transazione registrata.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 74020f6fc9b0fa8e05a1e2a09fd13dcd60490dc0
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028570"
---
# <a name="reverse-settings-on-journals-and-lines"></a><span data-ttu-id="a1af7-103">Impostazioni di storno per giornali di registrazione e righe</span><span class="sxs-lookup"><span data-stu-id="a1af7-103">Reverse settings on journals and lines</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1af7-104">In questo argomento viene illustrato il motivo per cui un movimento di storno immesso in un giornale di registrazione generale potrebbe non essere incluso nella transazione registrata.</span><span class="sxs-lookup"><span data-stu-id="a1af7-104">This topic addresses why a reversing entry that was entered on a general journal might not be included on the posted transaction.</span></span>  

## <a name="symptom"></a><span data-ttu-id="a1af7-105">Sintomo</span><span class="sxs-lookup"><span data-stu-id="a1af7-105">Symptom</span></span>

<span data-ttu-id="a1af7-106">Un giornale di registrazione generale include una registrazione di storno e una data di storno.</span><span class="sxs-lookup"><span data-stu-id="a1af7-106">A general journal includes a reversing entry and reversing date on the journal.</span></span> <span data-ttu-id="a1af7-107">Quando il giornale di registrazione viene contabilizzato, i giustificativi non vengono stornati.</span><span class="sxs-lookup"><span data-stu-id="a1af7-107">When you post the journal, none of the vouchers are reversed.</span></span> <span data-ttu-id="a1af7-108">Perché succede questo?</span><span class="sxs-lookup"><span data-stu-id="a1af7-108">Why does this happen?</span></span>

## <a name="resolution"></a><span data-ttu-id="a1af7-109">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="a1af7-109">Resolution</span></span>

<span data-ttu-id="a1af7-110">Quando il giornale di registrazione viene contabilizzato, il processo di storno esamina solo le impostazioni **Inserimento di storno** e **Data storno** nella sezione **Righe** del giustificativo.</span><span class="sxs-lookup"><span data-stu-id="a1af7-110">When the journal is posted, the reversing process looks only at the **Revering entry** and **Reversing date** settings on the **Lines** section of the voucher.</span></span> <span data-ttu-id="a1af7-111">Questo approccio consente a un giornale di includere i giustificativi contrassegnati per lo storno ed escludere gli altri.</span><span class="sxs-lookup"><span data-stu-id="a1af7-111">This approach allows a journal to include some vouchers that are marked for reversing, and others that are not.</span></span>

<span data-ttu-id="a1af7-112">I valori del giornale di registrazione vengono utilizzati solo come valori predefiniti durante l'aggiunta di *nuove* righe.</span><span class="sxs-lookup"><span data-stu-id="a1af7-112">The values from the journal are only used as defaults when adding *new* lines.</span></span> <span data-ttu-id="a1af7-113">La modifica dei valori nel giornale di registrazione non influisce sulle righe esistenti.</span><span class="sxs-lookup"><span data-stu-id="a1af7-113">Changing the values on the journal doesn’t affect existing lines.</span></span> <span data-ttu-id="a1af7-114">In questo esempio, le righe del giustificativo sono state inserite per prime.</span><span class="sxs-lookup"><span data-stu-id="a1af7-114">In this example, the voucher lines were entered first.</span></span> <span data-ttu-id="a1af7-115">Quando si immette il dettaglio della riga prima di designare il giornale di registrazione come storno, la designazione come inserimento di storno e data di storno non viene applicata a nessuna riga esistente.</span><span class="sxs-lookup"><span data-stu-id="a1af7-115">When you enter the line detail before designating the journal as reversing, the designation as a reversing entry and date won't be applied to any existing lines.</span></span>

<span data-ttu-id="a1af7-116">La modifica dell'inserimento di storno o della data di storno su una riga esistente viene propagata ad altre righe nello stesso giustificativo.</span><span class="sxs-lookup"><span data-stu-id="a1af7-116">Changing the reversing entry or reversing date on an existing line propagates that change to other lines in the same voucher.</span></span> <span data-ttu-id="a1af7-117">Per ottimizzare le prestazioni, la griglia non viene aggiornata dopo la propagazione delle modifiche ad altre righe.</span><span class="sxs-lookup"><span data-stu-id="a1af7-117">To optimize performance, the grid is not refreshed after propagating changes to other Lines.</span></span> <span data-ttu-id="a1af7-118">È possibile visualizzare i valori modificati aggiornando la griglia.</span><span class="sxs-lookup"><span data-stu-id="a1af7-118">You can display the updated values by refreshing the grid.</span></span>


