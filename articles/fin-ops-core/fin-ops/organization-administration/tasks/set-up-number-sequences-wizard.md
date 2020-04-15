---
title: Impostazione guidata sequenze numeriche
description: In questo argomento viene illustrato come impostare contemporaneamente tutte le sequenze numeriche richieste utilizzando la procedura guidata.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
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
ms.openlocfilehash: 76dc32f2254ffd2a2e33eef594d6e602092bcb6f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140502"
---
# <a name="set-up-number-sequences-using-a-wizard"></a><span data-ttu-id="fd676-103">Impostazione guidata sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="fd676-103">Set up number sequences using a wizard</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fd676-104">Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono.</span><span class="sxs-lookup"><span data-stu-id="fd676-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="fd676-105">Un record transazioni o dati master che richiede un identificatore viene definito riferimento.</span><span class="sxs-lookup"><span data-stu-id="fd676-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="fd676-106">Prima di poter creare nuovi record per un riferimento, è necessario impostare una sequenza numerica e associarla al riferimento.</span><span class="sxs-lookup"><span data-stu-id="fd676-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="fd676-107">In questo argomento viene illustrato come impostare contemporaneamente tutte le sequenze numeriche richieste utilizzando la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="fd676-107">This topic explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="fd676-108">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="fd676-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="fd676-109">Andare a **Pannello di navigazione > Moduli > Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche**.</span><span class="sxs-lookup"><span data-stu-id="fd676-109">Go to **Navigation > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="fd676-110">Selezionare **Genera**.</span><span class="sxs-lookup"><span data-stu-id="fd676-110">Select **Generate**.</span></span>
3. <span data-ttu-id="fd676-111">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fd676-111">Select **Next**.</span></span>

   - <span data-ttu-id="fd676-112">Da questa pagina è possibile modificare il codice identificativo, il valore minimo e il valore massimo.</span><span class="sxs-lookup"><span data-stu-id="fd676-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="fd676-113">Inoltre, è possibile Indicare se la sequenza numerica deve essere continua.</span><span class="sxs-lookup"><span data-stu-id="fd676-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
   - <span data-ttu-id="fd676-114">Non selezionare l'opzione **Continua** se si devono preallocare numeri per la sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="fd676-114">Do not select the **Continuous** option if you must preallocate numbers for the number sequence.</span></span> <span data-ttu-id="fd676-115">Per aggiungere un segmento ambito al formato di una sequenza numerica, selezionare il formato nell'elenco, quindi selezionare **Includi ambito nel formato**.</span><span class="sxs-lookup"><span data-stu-id="fd676-115">To add a scope segment to the format of a number sequence, select the format in the list, and then select **Include scope in format**.</span></span> <span data-ttu-id="fd676-116">Per eliminare un segmento ambito dal formato di una sequenza numerica, selezionare il formato nell'elenco, quindi selezionare **Rimuovi ambito dal formato**.</span><span class="sxs-lookup"><span data-stu-id="fd676-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then select **Remove scope from format**.</span></span> <span data-ttu-id="fd676-117">Per escludere una sequenza numerica dalla generazione automatica, selezionare la sequenza numerica nell'elenco, quindi selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="fd676-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then select **Delete**.</span></span>  

4. <span data-ttu-id="fd676-118">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fd676-118">Select **Next**.</span></span>
5. <span data-ttu-id="fd676-119">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="fd676-119">Select **Finish**.</span></span>

