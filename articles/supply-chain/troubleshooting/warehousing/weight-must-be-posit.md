---
title: Il peso deve essere positivo
description: Il peso deve essere positivo
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dcbcde3143cb509b68b277cb7c709263e2659b5b
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924305"
---
# <a name="weight-must-be-positive"></a><span data-ttu-id="51456-103">Il peso deve essere positivo</span><span class="sxs-lookup"><span data-stu-id="51456-103">Weight must be positive</span></span>

<span data-ttu-id="51456-104">Codice di errore: WeightMustBePositive</span><span class="sxs-lookup"><span data-stu-id="51456-104">Error code: WeightMustBePositive</span></span>

## <a name="symptoms"></a><span data-ttu-id="51456-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="51456-105">Symptoms</span></span>

<span data-ttu-id="51456-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="51456-106">The system shows the following error message:</span></span>

> <span data-ttu-id="51456-107">Il peso deve essere positivo</span><span class="sxs-lookup"><span data-stu-id="51456-107">Weight must be positive.</span></span>

## <a name="cause"></a><span data-ttu-id="51456-108">Causa</span><span class="sxs-lookup"><span data-stu-id="51456-108">Cause</span></span>

<span data-ttu-id="51456-109">Il campo **Peso lordo** è impostato su *0* (zero) o un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="51456-109">The **Gross Weight** field is set to *0* (zero) or a negative value.</span></span>

## <a name="resolution"></a><span data-ttu-id="51456-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="51456-110">Resolution</span></span>

<span data-ttu-id="51456-111">Per specificare un peso, effettuare uno dei seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="51456-111">To specify a weight, follow one of these steps.</span></span>

- <span data-ttu-id="51456-112">Nel campo **Peso lordo**, impostare un valore.</span><span class="sxs-lookup"><span data-stu-id="51456-112">In the **Gross weight** field, set a value.</span></span> <span data-ttu-id="51456-113">Quindi selezionare un'unità dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="51456-113">Then select a unit in the drop-down list.</span></span>
- <span data-ttu-id="51456-114">Selezionare **Ottieni peso sistema** per calcolare il valore **Peso lordo**.</span><span class="sxs-lookup"><span data-stu-id="51456-114">Select **Get system weight** to calculate the **Gross weight** value.</span></span>
