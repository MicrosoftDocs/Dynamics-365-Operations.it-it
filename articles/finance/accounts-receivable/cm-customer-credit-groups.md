---
title: Gruppi di crediti cliente
description: In questo argomento vengono fornite informazioni su gruppi di crediti cliente.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: f7121b78f3318bae9f82b2f0f951bc7bfe6c4358
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015281"
---
# <a name="customer-credit-groups"></a><span data-ttu-id="7bb05-103">Gruppi di crediti cliente</span><span class="sxs-lookup"><span data-stu-id="7bb05-103">Customer credit groups</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="7bb05-104">È possibile definire gruppi di clienti che hanno lo stesso limite di credito.</span><span class="sxs-lookup"><span data-stu-id="7bb05-104">You can define groups of customers who have the same credit limit.</span></span> <span data-ttu-id="7bb05-105">Viene inoltre considerato il limite di credito individuale definito nel conto delle fatture cliente.</span><span class="sxs-lookup"><span data-stu-id="7bb05-105">The individual credit limit that is defined on the customer invoice account is also considered.</span></span>

<span data-ttu-id="7bb05-106">I membri di un gruppo di crediti cliente possono essere selezionati tra diverse persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="7bb05-106">Members of a customer credit group can be selected from different legal entities.</span></span> <span data-ttu-id="7bb05-107">Quando si aggiunge un cliente all'elenco di clienti nel gruppo di crediti cliente, la data di scadenza del limite di credito per ciascun cliente viene modificata nella data di scadenza assegnata al gruppo.</span><span class="sxs-lookup"><span data-stu-id="7bb05-107">When you add a customer to the list of customers in the customer credit group, the expiration date of the credit limit for each customer is changed to the expiration date that is assigned to the group.</span></span>

<span data-ttu-id="7bb05-108">È possibile impostare gruppi di crediti cliente nella pagina **Gruppi di crediti cliente** (**Gestione crediti \> Gruppi di crediti cliente \> Gruppi di crediti cliente**).</span><span class="sxs-lookup"><span data-stu-id="7bb05-108">You can set up customer credit groups on the **Customer credit groups** page (**Credit management \> Customer credit groups \> Customer credit groups**).</span></span>

1. <span data-ttu-id="7bb05-109">Nei campi **Numero gruppo** e **Descrizione**, immettere un identificatore e una descrizione per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="7bb05-109">In the **Group number** and **Description** fields, enter an identifier and description for the group.</span></span>
2. <span data-ttu-id="7bb05-110">Nei campi **Limite di credito** e **Valuta**, immettere il limite di credito e la valuta da utilizzare quando il sistema controlla il limite di credito per qualsiasi membro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="7bb05-110">In the **Credit limit** and **Currency** fields, enter the credit limit and currency that should be used when the system checks the credit limit for any member of the group.</span></span>
3. <span data-ttu-id="7bb05-111">Nel campo **Scadenza limite di credito**, inserire la data di scadenza del limite di credito.</span><span class="sxs-lookup"><span data-stu-id="7bb05-111">In the **Credit limit to date** field, enter the date when the credit limit expires.</span></span> <span data-ttu-id="7bb05-112">I gruppi di crediti cliente devono avere una data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="7bb05-112">Customer credit groups must have an expiration date.</span></span>

<span data-ttu-id="7bb05-113">Dopo aver completato l'impostazione di un gruppo di crediti cliente, è possibile aggiungervi clienti specificando la relativa persona giuridica e l'ID conto cliente.</span><span class="sxs-lookup"><span data-stu-id="7bb05-113">After you've finished setting up a customer credit group, you can add customers to it by specifying their legal entity and customer account ID.</span></span> <span data-ttu-id="7bb05-114">Quando si aggiunge un nuovo cliente a un gruppo di crediti cliente, il sistema cerca lo stesso conto cliente in tutte le persone giuridiche e richiede di aggiungerlo al gruppo di crediti cliente.</span><span class="sxs-lookup"><span data-stu-id="7bb05-114">When you add a new customer to a customer credit group, the system searches for the same customer account across all legal entities and prompts you to add it to the customer credit group.</span></span>

<span data-ttu-id="7bb05-115">Utilizzare il menu **Saldi con aging** per visualizzare i dettagli del saldo con aging per tutti i clienti di fatturazione in un gruppo di crediti cliente.</span><span class="sxs-lookup"><span data-stu-id="7bb05-115">Use the **Aged balances** menu to view the details of the aging balance for all invoice customers in a customer credit group.</span></span> <span data-ttu-id="7bb05-116">La pagina **Saldo di aging** mostra un riepilogo dei saldi con aging per i conti cliente fattura.</span><span class="sxs-lookup"><span data-stu-id="7bb05-116">The **Aging balance** page shows a summary of the aged balances for the invoice customer accounts.</span></span>