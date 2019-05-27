---
title: Impostazione guidata sequenze numeriche
description: Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono.
author: sericks007
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1808ab9240ab291f9d203893a634bd390f16e2e7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560546"
---
# <a name="set-up-number-sequences-by-using-a-wizard"></a><span data-ttu-id="094e9-103">Impostazione guidata sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="094e9-103">Set up number sequences by using a wizard</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="094e9-104">Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono.</span><span class="sxs-lookup"><span data-stu-id="094e9-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="094e9-105">Un record transazioni o dati master che richiede un identificatore viene definito riferimento.</span><span class="sxs-lookup"><span data-stu-id="094e9-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="094e9-106">Prima di poter creare nuovi record per un riferimento, è necessario impostare una sequenza numerica e associarla al riferimento.</span><span class="sxs-lookup"><span data-stu-id="094e9-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="094e9-107">In questa procedura verrà illustrato come impostare contemporaneamente tutte le sequenze numeriche richieste utilizzando la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="094e9-107">This procedure explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="094e9-108">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="094e9-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="094e9-109">Andare a Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="094e9-109">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="094e9-110">Fare clic su Genera.</span><span class="sxs-lookup"><span data-stu-id="094e9-110">Click Generate.</span></span>
3. <span data-ttu-id="094e9-111">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="094e9-111">Click Next.</span></span>
    * <span data-ttu-id="094e9-112">Da questa pagina è possibile modificare il codice identificativo, il valore minimo e il valore massimo.</span><span class="sxs-lookup"><span data-stu-id="094e9-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="094e9-113">Inoltre, è possibile Indicare se la sequenza numerica deve essere continua.</span><span class="sxs-lookup"><span data-stu-id="094e9-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
    * <span data-ttu-id="094e9-114">Non selezionare l'opzione Continua se si devono preallocare numeri per la sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="094e9-114">Do not select the Continuous option if you must preallocate numbers for the number sequence.</span></span>     <span data-ttu-id="094e9-115">Per aggiungere un segmento ambito al formato di una sequenza numerica, selezionare il formato nell'elenco, quindi fare clic su Includi ambito nel formato.</span><span class="sxs-lookup"><span data-stu-id="094e9-115">To add a scope segment to the format of a number sequence, select the format in the list, and then click Include scope in format.</span></span>     <span data-ttu-id="094e9-116">Per eliminare un segmento ambito dal formato di una sequenza numerica, selezionare il formato nell'elenco, quindi fare clic su Rimuovi ambito dal formato.</span><span class="sxs-lookup"><span data-stu-id="094e9-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then click Remove scope from format.</span></span>     <span data-ttu-id="094e9-117">Per escludere una sequenza numerica dalla generazione automatica, selezionare la sequenza numerica nell'elenco, quindi fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="094e9-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then click Delete.</span></span>  
4. <span data-ttu-id="094e9-118">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="094e9-118">Click Next.</span></span>
5. <span data-ttu-id="094e9-119">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="094e9-119">Click Finish.</span></span>

