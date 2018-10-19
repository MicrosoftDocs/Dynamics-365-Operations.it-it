--- 
title: EUR-00015 Ricerca della parte utilizzando l'ID IVA
description: "In questa procedura verrà descritto come eseguire una ricerca di parti tramite un ID registrazione."
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: ec36ead402882c1022811b7b398a03c6325ef7c0
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="eur-00015-party-search-using-vat-id"></a><span data-ttu-id="5ab50-103">EUR-00015 Ricerca della parte utilizzando l'ID IVA</span><span class="sxs-lookup"><span data-stu-id="5ab50-103">EUR-00015 Party search using VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5ab50-104">In questa procedura verrà descritto come eseguire una ricerca di parti tramite un ID registrazione.</span><span class="sxs-lookup"><span data-stu-id="5ab50-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="5ab50-105">Prima di poter eseguire la procedura, è necessario impostare gli ID IVA e immettere tutti gli ID IVA per i fornitori, clienti, o persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="5ab50-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="5ab50-106">Questa procedura si applica a tutti i paesi europei.</span><span class="sxs-lookup"><span data-stu-id="5ab50-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="5ab50-107">La procedura è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Germania.</span><span class="sxs-lookup"><span data-stu-id="5ab50-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="5ab50-108">Questa procedura è progettata per un responsabile della contabilità fornitori, o un responsabile della contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="5ab50-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="5ab50-109">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="5ab50-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="5ab50-110">Scegliere Amministrazione organizzazione > Rubrica globale > Rubrica globale.</span><span class="sxs-lookup"><span data-stu-id="5ab50-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="5ab50-111">Fare clic su Ricerca ID registrazione.</span><span class="sxs-lookup"><span data-stu-id="5ab50-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="5ab50-112">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5ab50-112">Click Add.</span></span>
4. <span data-ttu-id="5ab50-113">Nel campo Tipo di registrazione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5ab50-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab50-114">Ad esempio, per trovare parti con un ID registrazione di tipo ID IVA, selezionare ID IVA.</span><span class="sxs-lookup"><span data-stu-id="5ab50-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="5ab50-115">Nel campo Paese/regione, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5ab50-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="5ab50-116">Ad esempio, immettere DEU.</span><span class="sxs-lookup"><span data-stu-id="5ab50-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="5ab50-117">Nel campo Numero di registrazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5ab50-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="5ab50-118">Fare clic su Trova.</span><span class="sxs-lookup"><span data-stu-id="5ab50-118">Click Find.</span></span>
    * <span data-ttu-id="5ab50-119">Tutte le parti con tale ID registrazione verranno visualizzate.</span><span class="sxs-lookup"><span data-stu-id="5ab50-119">All parties with that registration ID will be displayed.</span></span>  


