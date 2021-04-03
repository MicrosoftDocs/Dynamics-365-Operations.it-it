---
title: Dimensioni finanziarie e conti principali nelle lingue da destra a sinistra
description: In questo argomento vengono descritte le decisioni che è opportuno considerare quando si utilizza una lingua da destra a sinistra ed è necessario impostare le dimensioni finanziarie e i conti principali.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 496869bd3e7a372a5ec791df66fb7a8c43ccad13
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561002"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a><span data-ttu-id="7dea1-103">Dimensioni finanziarie e conti principali in lingue leggibili da destra a sinistra</span><span class="sxs-lookup"><span data-stu-id="7dea1-103">Financial dimensions and main accounts in right-to-left languages</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7dea1-104">In questo argomento vengono descritte alcune decisioni di implementazione che è opportuno considerare quando si utilizza una lingua da destra a sinistra ed è necessario impostare le dimensioni finanziarie e i conti principali.</span><span class="sxs-lookup"><span data-stu-id="7dea1-104">This topic describes some of the implementation decisions that you should consider when you use a right-to-left language, and you must set up financial dimensions and main accounts.</span></span>

<span data-ttu-id="7dea1-105">Le dimensioni finanziarie e i conti principali sono componenti chiave della fase di pianificazione di un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="7dea1-105">Financial dimensions and main accounts are key components of the planning phase for an implementation.</span></span> <span data-ttu-id="7dea1-106">Dopo che le dimensioni finanziarie e i conti principali vengono creati nel sistema, questi vengono usati nelle pagine **Configura strutture dei conti** **Strutture regole avanzate** e **Configurazione dimensione finanziaria per integrazione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="7dea1-106">After financial dimensions and main accounts are created in the system, they are used on the **Configure account structures**, **Advanced rule structures**, and **Financial dimension configuration for integrating applications** pages.</span></span> <span data-ttu-id="7dea1-107">L'ordine definito in queste pagine viene utilizzato nel sistema per l'immissione e l'utilizzo dei dati.</span><span class="sxs-lookup"><span data-stu-id="7dea1-107">The order that is defined on those pages is used in the system for data entry and consumption.</span></span> <span data-ttu-id="7dea1-108">In alcuni aree del sistema, dimensioni finanziarie e i conti principali vengono visualizzati in campi separati.</span><span class="sxs-lookup"><span data-stu-id="7dea1-108">In some places in the system, the financial dimensions and main accounts appear in separate fields.</span></span> <span data-ttu-id="7dea1-109">In altre aree, ad esempio i giornali di registrazione, le dimensioni finanziarie e i conti principali vengono visualizzate come singola stringa.</span><span class="sxs-lookup"><span data-stu-id="7dea1-109">In other places, such as journals, the financial dimensions and main accounts appear as a single string.</span></span>

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a><span data-ttu-id="7dea1-110">Procedure consigliate per impostare le dimensioni finanziarie e i conti principali in un sistema destra-sinistra</span><span class="sxs-lookup"><span data-stu-id="7dea1-110">Best practices for setting up financial dimensions and main accounts in a right-to-left system</span></span>

- <span data-ttu-id="7dea1-111">Quando si seleziona il delimitatore per i piani dei conti, selezionare una delle opzioni di doppio delimitatore: doppio trattino (`--`), doppia barra (`||`) o doppio punto (`..`) o doppio carattere di sottolineatura (`\\`).</span><span class="sxs-lookup"><span data-stu-id="7dea1-111">When you select the delimiter for charts of accounts, select one of the double delimiter options: double hyphen (`--`), double bar (`||`), double period (`..`), or double underscore (`\\`).</span></span>
- <span data-ttu-id="7dea1-112">Quando si creano i valori delle dimensioni finanziarie e dei conti principali, utilizzare solo numeri e caratteri di lingue da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="7dea1-112">When you create financial dimension and main account values, use only numbers and right-to-left language characters.</span></span>
- <span data-ttu-id="7dea1-113">Evitare di utilizzare il delimitatore di piano dei conti selezionato nei valori delle dimensioni finanziarie e dei conti principali.</span><span class="sxs-lookup"><span data-stu-id="7dea1-113">Avoid using the selected chart of accounts delimiter in financial dimension and main account values.</span></span>

<span data-ttu-id="7dea1-114">Seguendo queste procedure consigliate, contribuite a garantire la rappresentazione coerente dell'ordine definito dall'utente in ogni parte del sistema.</span><span class="sxs-lookup"><span data-stu-id="7dea1-114">By following these best practices, you help guarantee consistent representation of the user defined-order throughout the system.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]