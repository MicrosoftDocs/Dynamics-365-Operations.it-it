---
title: Pianificare la rubrica globale e altre rubriche
description: Questo argomento descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di impostare e configurare la Rubrica globale ed eventuali rubriche aggiuntive.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f0a53e1f9b378759e0c5adbe0612a5fa8cddc82
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796948"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a><span data-ttu-id="ff0e1-103">Piano per la rubrica globale e altre rubriche</span><span class="sxs-lookup"><span data-stu-id="ff0e1-103">Plan for the global address book and other address books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ff0e1-104">Questo argomento descrive le considerazioni e le decisioni che è necessario prendere durante il processo di pianificazione prima di impostare e configurare la Rubrica globale ed eventuali rubriche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-104">This topic describes the considerations and decisions that you must make during the planning process, before you set up and configure the global address book and any additional address books.</span></span> <span data-ttu-id="ff0e1-105">Alcune decisioni richiederanno la conferma delle decisioni che sono state prese per altre aree del prodotto, ad esempio la gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-105">Some of the decisions will require that you confirm the decisions that have been made for other areas of the product, such as the organization hierarchy.</span></span>

## <a name="global-address-book"></a><span data-ttu-id="ff0e1-106">Rubrica globale</span><span class="sxs-lookup"><span data-stu-id="ff0e1-106">Global address book</span></span>

<span data-ttu-id="ff0e1-107">Prima di iniziare a utilizzare la Rubrica globale, è necessario determinarne i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-107">Before you begin to work with the global address book, you must determine the default values for it.</span></span> <span data-ttu-id="ff0e1-108">Questi valori predefiniti vengono utilizzati per tutte le Rubriche aggiuntive create.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-108">These default values are then used for any additional address books that you create.</span></span>

<span data-ttu-id="ff0e1-109">**Decisioni**</span><span class="sxs-lookup"><span data-stu-id="ff0e1-109">**Decisions**</span></span>

- <span data-ttu-id="ff0e1-110">Qual è la sequenza di visualizzazione desiderata per i record di parti di tipo **Persona**?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-110">What sequence should names be displayed in for party records of the **Person** type?</span></span> <span data-ttu-id="ff0e1-111">Ad esempio, una sequenza è nome, secondo nome e cognome.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-111">For example, one sequence is last name, middle name, first name.</span></span>
- <span data-ttu-id="ff0e1-112">I record di parti devono essere eliminati dalla Rubrica quando il record di ruolo viene eliminato?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-112">Should party records be deleted from the address book when the role record is deleted?</span></span> <span data-ttu-id="ff0e1-113">Ad esempio, se un record cliente viene eliminato, anche il record parte deve essere eliminato?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-113">For example, if a customer record is deleted, should the party record also be deleted?</span></span>
- <span data-ttu-id="ff0e1-114">Quando un nuovo record viene creato, gli utenti devono essere notificati se un record duplicato viene trovato nella Rubrica globale?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-114">When a new record is created, should users be notified if a duplicate record is found in the global address book?</span></span>
- <span data-ttu-id="ff0e1-115">Il numero DUNS (Data Universal Numbering System) deve essere incluso nelle informazioni di un record parte?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-115">Should the Data Universal Numbering System (DUNS) number be included in a party record's information?</span></span>
- <span data-ttu-id="ff0e1-116">Se il numero DUNS viene incluso in un record parte, l'univocità del numero essere controllata?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-116">If the DUNS number is included in a party record, should the uniqueness of the number be checked?</span></span>
- <span data-ttu-id="ff0e1-117">Quando un record parte viene creato nella Rubrica globale, si desidera un tipo, una persona o un'organizzazione predefinita della parte?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-117">When a party record is created in the global address book, do you want a default party type, person, or organization?</span></span>
- <span data-ttu-id="ff0e1-118">Quali ruoli utente possono accedere alle informazioni private sull'indirizzo e sul contatto mediante i record di parti?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-118">Which user roles should have access to the private addresses and contact information of party records?</span></span>

## <a name="additional-address-books"></a><span data-ttu-id="ff0e1-119">Rubriche aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ff0e1-119">Additional address books</span></span>

<span data-ttu-id="ff0e1-120">Dopo aver creato la Rubrica globale, è possibile creare Rubriche aggiuntive in base alle esigenze, ad esempio una Rubrica separata per ogni società nell'organizzazione o per ogni linea di business.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-120">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> <span data-ttu-id="ff0e1-121">Ad esempio, Fabrikam è un'organizzazione internazionale con più società e più linee di business.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-121">For example, Fabrikam is an international organization that has multiple companies and multiple lines of business.</span></span> <span data-ttu-id="ff0e1-122">Fabrikam prevede di creare una rubrica per ogni linea di business.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-122">Fabrikam plans to create an address book for each line of business.</span></span> <span data-ttu-id="ff0e1-123">Per le linee di business che si trovano in più sedi, ad esempio la propria società di strumenti pneumatici, Fabrikam pianifica di creare una rubrica per ogni sede.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-123">For lines of business that occur in more than one location, such as the pneumatic tools business, Fabrikam plans to create an address book for each location.</span></span> <span data-ttu-id="ff0e1-124">Chris, il manager IT di Fabrikam, ha creato il seguente elenco di Rubriche necessarie.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-124">Chris, the IT manager at Fabrikam, has created the following list of address books that are required.</span></span> <span data-ttu-id="ff0e1-125">Questo elenco descrive anche i record di parti che ogni Rubrica deve includere.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-125">This list also describes the party records that each address book must include.</span></span>

- <span data-ttu-id="ff0e1-126">**Contratti settore pubblico (PubSC):** record di tutte le parti impegnate con i contratti del settore pubblico gestiti da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-126">**Public Sector Contracts (PubSC)** – Party records for all parties that are involved in the public sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="ff0e1-127">**Contratti settore privato (PriSC):** record di tutte le parti impegnate con i contratti del settore privato gestiti da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-127">**Private Sector Contracts (PriSC)** – Party records for all parties that are involved in the private sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="ff0e1-128">**Strumenti elettronici (ET):** record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti elettronici o che interagiscono con gli strumenti elettronici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-Giappone.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-128">**Electronic Tools (ET)** – Party records for all parties that are involved in the purchase or sale of electronic tools, or that otherwise interact with the electronic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="ff0e1-129">**Strumenti pneumatici (PTJPN)**: record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti pneumatici o che interagiscono con gli strumenti pneumatici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-Giappone.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-129">**Pneumatic Tools (PTJPN)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="ff0e1-130">**Strumenti pneumatici (PTUSA):** record di tutte le parti impegnate nell'acquisto o nella vendita di strumenti pneumatici o che interagiscono con gli strumenti pneumatici forniti da Fabrikam o acquistati per la stessa nella società Fabrikam-USA.</span><span class="sxs-lookup"><span data-stu-id="ff0e1-130">**Pneumatic Tools (PTUSA)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-US company.</span></span>

<span data-ttu-id="ff0e1-131">**Decisione:**</span><span class="sxs-lookup"><span data-stu-id="ff0e1-131">**Decision:**</span></span>

- <span data-ttu-id="ff0e1-132">Quante Rubriche aggiuntive verranno create?</span><span class="sxs-lookup"><span data-stu-id="ff0e1-132">How many additional address books will you create?</span></span>
