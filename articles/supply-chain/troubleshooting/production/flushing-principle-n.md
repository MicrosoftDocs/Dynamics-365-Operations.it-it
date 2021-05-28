---
title: Le impostazioni del principio di registrazione del consumo di materiali nelle righe DBA non vengono rispettate
description: Le impostazioni del principio di registrazione del consumo di materiali nelle righe della distinta base non vengono rispettate.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026645"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a><span data-ttu-id="509ec-103">Le impostazioni del principio di registrazione del consumo di materiali nelle righe DBA non vengono rispettate</span><span class="sxs-lookup"><span data-stu-id="509ec-103">Flushing principle settings on BOM lines aren't respected</span></span>

<span data-ttu-id="509ec-104">Numero KB: 4612725</span><span class="sxs-lookup"><span data-stu-id="509ec-104">KB number: 4612725</span></span>

## <a name="symptoms"></a><span data-ttu-id="509ec-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="509ec-105">Symptoms</span></span>

<span data-ttu-id="509ec-106">Questo problema si verifica quando il campo **Consumo DBA automatico** nella scheda **Aggiornamento automatico** della pagina **Parametri di controllo produzione** è impostato su *Principio di registrazione del consumo di materiali*.</span><span class="sxs-lookup"><span data-stu-id="509ec-106">This issue occurs when the **Automatic BOM consumption** field on the **Automatic update** tab of the **Production control parameters** page is set to *Flushing principle*.</span></span> <span data-ttu-id="509ec-107">Questa impostazione indica che tutte le righe della distinta base (DBA) devono essere utilizzate automaticamente quando viene ricevuto un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="509ec-107">This setting indicates that all bill of materials (BOM) lines should automatically be consumed when a purchase order is received.</span></span> <span data-ttu-id="509ec-108">Se il campo **Principio di registrazione del consumo di materiali** nelle righe DBA è impostato esplicitamente su *Manuale*, potresti aspettarti che le righe DBA non vengano consumate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="509ec-108">If the **Flushing principle** field on BOM lines is explicitly set to *Manual*, you might expect that the BOM lines won't automatically be consumed.</span></span> <span data-ttu-id="509ec-109">Tuttavia, quando si verifica questo problema, le righe DBA dove il campo **Principio di registrazione del consumo di materiali** è impostato su *Manuale* vengono comunque consumate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="509ec-109">However, when this issue occurs, BOM lines where the **Flushing principle** field is set to *Manual* are automatically consumed anyway.</span></span>

## <a name="resolution"></a><span data-ttu-id="509ec-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="509ec-110">Resolution</span></span>

<span data-ttu-id="509ec-111">Se si verifica questo problema, i parametri di controllo della produzione potrebbero essere impostati per ignorare l'impostazione **Principio di registrazione del consumo di materiali** delle righe DBA.</span><span class="sxs-lookup"><span data-stu-id="509ec-111">If you're experiencing this issue, your production control parameters might be set up to override the **Flushing principle** setting on BOM lines.</span></span> <span data-ttu-id="509ec-112">Nella pagina **Parametri di controllo produzione**, nella scheda **Aggiornamento automatico**, controlla il valore del campo **Consumo DBA automatico**.</span><span class="sxs-lookup"><span data-stu-id="509ec-112">On the **Production control parameters** page, on the **Automatic update** tab, check the value of the **Automatic BOM consumption** field.</span></span> <span data-ttu-id="509ec-113">Se è impostato su *Sempre*, il sistema ignorerà l'impostazione **Principio di registrazione del consumo di materiali** di tutte le righe DBA e registrerà sempre il consumo di materiali delle righe.</span><span class="sxs-lookup"><span data-stu-id="509ec-113">If it's set to *Always*, the system will disregard the **Flushing principle** setting on all BOM lines and will always flush the lines.</span></span> <span data-ttu-id="509ec-114">Affinché il sistema prenda in considerazione l'impostazione **Principio di registrazione del consumo di materiali** per le righe DBA, imposta il valore del campo **Consumo BOM automatico** su *Principio di registrazione del consumo di materiali*.</span><span class="sxs-lookup"><span data-stu-id="509ec-114">To make the system respect the **Flushing principle** setting on BOM lines, change the value of the **Automatic BOM consumption** field to *Flushing principle*.</span></span>
