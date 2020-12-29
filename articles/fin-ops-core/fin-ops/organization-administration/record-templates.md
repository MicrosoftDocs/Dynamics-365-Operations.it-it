---
title: Panoramica dei modelli di record
description: Questo articolo introduce il concetto di modelli di record e illustra come possono essere utilizzati per creare record che condividono le informazioni.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0b55046e6c523398b4a30e674dc9f77bb6fedf3
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693210"
---
# <a name="record-templates-overview"></a><span data-ttu-id="11976-103">Panoramica dei modelli di record</span><span class="sxs-lookup"><span data-stu-id="11976-103">Record templates overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11976-104">Questo articolo introduce il concetto di modelli di record e illustra come possono essere utilizzati per creare record che condividono le informazioni.</span><span class="sxs-lookup"><span data-stu-id="11976-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="11976-105">I modelli di record consentono di creare più rapidamente i record, ma è possibile creare i modelli di record solo per alcuni tipi di record.</span><span class="sxs-lookup"><span data-stu-id="11976-105">Record templates can help you to create records more quickly, however you can only create record templates for some record types.</span></span>

<span data-ttu-id="11976-106">Ad esempio, si supponga di dover inserire le informazioni di noleggio per una società di noleggio auto che ha sede a San Francisco.</span><span class="sxs-lookup"><span data-stu-id="11976-106">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="11976-107">Dal momento che è probabile che la maggior parte dei clienti sia dell'area di San Francisco, sarebbe utile poter compilare automaticamente i valori dei campi **Stato**, **Paese** e **Città** del modulo di noleggio.</span><span class="sxs-lookup"><span data-stu-id="11976-107">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span>

> [!NOTE]
> <span data-ttu-id="11976-108">È possibile applicare i modelli solo nelle aree a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="11976-108">You can apply templates only in areas that you have access to.</span></span> <span data-ttu-id="11976-109">Tuttavia, tutti i titoli di modello sono visibili a chi crea un nuovo record e anche agli altri utenti, se si creano modelli che saranno disponibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="11976-109">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="11976-110">Assicurarsi di considerare questo aspetto quando si denominano i modelli.</span><span class="sxs-lookup"><span data-stu-id="11976-110">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="11976-111">Ad esempio, è opportuno evitare di utilizzare nomi che includono parole, ad esempio "provvigione", se è confidenziale che alcuni dipendenti della società abbiano retribuzioni base alle provvigioni.</span><span class="sxs-lookup"><span data-stu-id="11976-111">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span>

<span data-ttu-id="11976-112">Quando sono presenti uno o più modelli a cui si ha accesso per un modulo specifico e si tenta di creare un nuovo record nel modulo, viene visualizzata la pagina **Selezionare un modello per**.</span><span class="sxs-lookup"><span data-stu-id="11976-112">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="11976-113">Se si seleziona un modello nell'elenco, il nuovo record viene creato e conterrà informazioni predefinite basate sul modello selezionato.</span><span class="sxs-lookup"><span data-stu-id="11976-113">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="11976-114">Se non si desidera utilizzare i modelli quando si creano nuovi record, selezionare la casella di controllo **Non ripetere più la domanda** nella pagina **Selezionare un modello per**.</span><span class="sxs-lookup"><span data-stu-id="11976-114">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="11976-115">Per visualizzare di nuovo la finestra di dialogo per la selezione del modello, fare clic con il pulsante destro del mouse su un record qualsiasi, scegliere **Informazioni sui record**, quindi **Mostra selezione modello**.</span><span class="sxs-lookup"><span data-stu-id="11976-115">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>
