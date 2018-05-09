---
title: Modelli record
description: Questo articolo introduce il concetto di modelli di record e illustra come possono essere utilizzati per creare record che condividono le informazioni.
author: pvillads
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2f2c7f302a01593e7327dfe0510fadb3886bddd7
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="record-templates"></a><span data-ttu-id="d7749-103">Modelli record</span><span class="sxs-lookup"><span data-stu-id="d7749-103">Record templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7749-104">Questo articolo introduce il concetto di modelli di record e illustra come possono essere utilizzati per creare record che condividono le informazioni.</span><span class="sxs-lookup"><span data-stu-id="d7749-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="d7749-105">I modelli di record possono aiutare a creare dei record più rapidamente in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d7749-105">Record templates can help you to create records more quickly in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="d7749-106">È possibile creare modelli di record solo per alcuni tipi di record presenti in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d7749-106">You can create record templates for only some of the record types in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="d7749-107">Ad esempio, si supponga di dover inserire le informazioni di noleggio per una società di noleggio auto che ha sede a San Francisco.</span><span class="sxs-lookup"><span data-stu-id="d7749-107">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="d7749-108">Dal momento che è probabile che la maggior parte dei clienti sia dell'area di San Francisco, sarebbe utile poter compilare automaticamente i valori dei campi **Stato**, **Paese** e **Città** del modulo di noleggio.</span><span class="sxs-lookup"><span data-stu-id="d7749-108">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span> 

> [!Note]
> <span data-ttu-id="d7749-109">È possibile applicare i modelli solo alle aree di Finance and Operations per le quali si dispone dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="d7749-109">You can apply templates only for the areas of Finance and Operations that you have access to.</span></span> <span data-ttu-id="d7749-110">Tuttavia, tutti i titoli di modello sono visibili a chi crea un nuovo record e anche agli altri utenti, se si creano modelli che saranno disponibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d7749-110">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="d7749-111">Assicurarsi di considerare questo aspetto quando si denominano i modelli.</span><span class="sxs-lookup"><span data-stu-id="d7749-111">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="d7749-112">Ad esempio, è opportuno evitare di utilizzare nomi che includono parole, ad esempio "provvigione", se è confidenziale che alcuni dipendenti della società abbiano retribuzioni base alle provvigioni.</span><span class="sxs-lookup"><span data-stu-id="d7749-112">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span> 

<span data-ttu-id="d7749-113">Quando sono presenti uno o più modelli a cui si ha accesso per un modulo specifico e si tenta di creare un nuovo record nel modulo, viene visualizzata la pagina **Selezionare un modello per**.</span><span class="sxs-lookup"><span data-stu-id="d7749-113">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="d7749-114">Se si seleziona un modello nell'elenco, il nuovo record viene creato e conterrà informazioni predefinite basate sul modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="d7749-114">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="d7749-115">Se non si desidera utilizzare i modelli quando si creano nuovi record, selezionare la casella di controllo **Non ripetere più la domanda** nella pagina **Selezionare un modello per**.</span><span class="sxs-lookup"><span data-stu-id="d7749-115">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="d7749-116">Per visualizzare di nuovo la finestra di dialogo per la selezione del modello, fare clic con il pulsante destro del mouse su un record qualsiasi, scegliere **Informazioni sui record**, quindi **Mostra selezione modello**.</span><span class="sxs-lookup"><span data-stu-id="d7749-116">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>




