---
title: Data di competenza per le transazioni
description: "In questo argomento vengono fornite informazioni sulla data di competenza e illustra come attivare la funzionalità per le transazioni in Italia."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264534
ms.search.region: Italy
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e4cf02c5362be209d792ecd0d75321fdf724840e
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="competence-date-for-transactions"></a><span data-ttu-id="db7bb-103">Data di competenza per le transazioni</span><span class="sxs-lookup"><span data-stu-id="db7bb-103">Competence date for transactions</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="db7bb-104">In questo argomento vengono fornite informazioni sulla data di competenza e illustra come attivare la funzionalità per le transazioni in Italia.</span><span class="sxs-lookup"><span data-stu-id="db7bb-104">This topic provides information about the competence date and explains how to enable the functionality for transactions in Italy.</span></span>

<span data-ttu-id="db7bb-105">In Italia, le società devono utilizzare una data di registrazione per registrare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="db7bb-105">In Italy, companies must use a posting date when they post transactions.</span></span> <span data-ttu-id="db7bb-106">La data di registrazione è la data in cui la società conferma la transazione.</span><span class="sxs-lookup"><span data-stu-id="db7bb-106">The posting date is the date when the company acknowledges the transaction.</span></span> <span data-ttu-id="db7bb-107">Le transazioni di chiusura e rettifica possono essere effettuate diversi mesi dopo l'ultimo giorno dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="db7bb-107">Adjustment and closing transactions can be done several months after the last day of the fiscal year.</span></span> <span data-ttu-id="db7bb-108">In genere, queste transazioni vengono effettuate alla data in cui lo stato patrimoniale viene approvato dal Consiglio di Amministrazione. Queste transazioni devono essere dichiarate nel giornale di registrazione fiscale italiano alla data in cui vengono registrate, ma devono disporre di un riferimento alla data di competenza.</span><span class="sxs-lookup"><span data-stu-id="db7bb-108">(Usually, these transactions occur on the date when the balance sheet is approved by the Board of Directors.) These transactions must be reported on the Italian fiscal journal on the date when they are posted, but they must have a reference to their competence date.</span></span> <span data-ttu-id="db7bb-109">Due sono pertanto le date richieste:</span><span class="sxs-lookup"><span data-stu-id="db7bb-109">Therefore, two dates are required:</span></span>

-   <span data-ttu-id="db7bb-110">La data di competenza, che rappresenta la data in cui la transazione influisce sull'importo del saldo</span><span class="sxs-lookup"><span data-stu-id="db7bb-110">The competence date, which represents the date when the transaction affects the balance amount</span></span>
-   <span data-ttu-id="db7bb-111">La data di registrazione, che è la data in cui l'utente registra la transazione</span><span class="sxs-lookup"><span data-stu-id="db7bb-111">The posting date, which is the date when the user posts the transaction</span></span>

<span data-ttu-id="db7bb-112">**Esempio:** l'anno fiscale della società inizia l'1 gennaio e termina il 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="db7bb-112">**Example:** The company's fiscal year is from January 1 through December 31.</span></span> <span data-ttu-id="db7bb-113">Lo stato patrimoniale viene approvato il 15 aprile.</span><span class="sxs-lookup"><span data-stu-id="db7bb-113">The balance sheet is approved on April 15.</span></span> <span data-ttu-id="db7bb-114">Di conseguenza, le transazioni di chiusura e rettifica vengono dichiarate nel giornale di registrazione fiscale italiano ad aprile, ma influiscono sul saldo al 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="db7bb-114">Therefore, adjustment and closing transactions are reported on the Italian fiscal journal in April, but they affect the balance on December 31.</span></span>

## <a name="enable-the-competence-date"></a><span data-ttu-id="db7bb-115">Attivare la data di competenza</span><span class="sxs-lookup"><span data-stu-id="db7bb-115">Enable the competence date</span></span>
<span data-ttu-id="db7bb-116">Per attivare questa funzionalità per le transazioni, nella pagina **Parametri di contabilità generale**, nella scheda **Contabilità generale**, impostare l'opzione **Riferimento alla data competenza nella data della transazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="db7bb-116">To enable this functionality for transactions, on the **General ledger parameters** page, on the **Ledger** tab, set the **Transaction date reference to competence date** option to **Yes**.</span></span> <span data-ttu-id="db7bb-117">Dopo aver attivato la data di competenza, è possibile specificare le date di competenza e delle transazioni per ogni giornale di registrazione utilizzato per registrare le transazioni di rettifica e di chiusura/apertura per l'anno fiscale:</span><span class="sxs-lookup"><span data-stu-id="db7bb-117">After the competence date is enabled, you can specify the competence and transactions dates for each journal that is used to post the adjustment and closing/opening transactions for the fiscal year:</span></span>

-   <span data-ttu-id="db7bb-118">Giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="db7bb-118">General journal</span></span>
-   <span data-ttu-id="db7bb-119">Giornale di registrazione cespiti</span><span class="sxs-lookup"><span data-stu-id="db7bb-119">Fixed assets journal</span></span>
-   <span data-ttu-id="db7bb-120">Riconciliazione estratti conto</span><span class="sxs-lookup"><span data-stu-id="db7bb-120">Bank account reconciliation</span></span>
-   <span data-ttu-id="db7bb-121">Bilancio di chiusura</span><span class="sxs-lookup"><span data-stu-id="db7bb-121">Closing sheet</span></span>
-   <span data-ttu-id="db7bb-122">Transazione di apertura</span><span class="sxs-lookup"><span data-stu-id="db7bb-122">Opening transaction</span></span>
-   <span data-ttu-id="db7bb-123">Progetto - Registra costi</span><span class="sxs-lookup"><span data-stu-id="db7bb-123">Project – Post costs</span></span>
-   <span data-ttu-id="db7bb-124">Progetto - Volume d'affari accumulato</span><span class="sxs-lookup"><span data-stu-id="db7bb-124">Project – Accrue turnover</span></span>
-   <span data-ttu-id="db7bb-125">Progetto - Stima registrata</span><span class="sxs-lookup"><span data-stu-id="db7bb-125">Project – Estimate post</span></span>
-   <span data-ttu-id="db7bb-126">Progetto - Storna stima</span><span class="sxs-lookup"><span data-stu-id="db7bb-126">Project – Estimate reverse</span></span>





