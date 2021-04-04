---
title: Attività periodiche di gestione dei crediti
description: In questo argomento vengono descritte le attività periodiche che sono una parte necessaria del processo di gestione dei limiti di credito per i clienti.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a034d563c12c4ba8b99e13b30ea2683555a01276
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254489"
---
# <a name="periodic-credit-management-tasks"></a><span data-ttu-id="3c3f0-103">Attività periodiche di gestione crediti</span><span class="sxs-lookup"><span data-stu-id="3c3f0-103">Periodic credit management tasks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3c3f0-104">In questo argomento vengono descritte le attività periodiche che sono una parte necessaria del processo di gestione dei limiti di credito per i clienti.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-104">This topic describes the periodic tasks that are a necessary part of the process of managing credit limits for customers.</span></span>

## <a name="update-risk-scores"></a><span data-ttu-id="3c3f0-105">Aggiorna punteggi di rischio</span><span class="sxs-lookup"><span data-stu-id="3c3f0-105">Update risk scores</span></span>

<span data-ttu-id="3c3f0-106">Man mano che le aziende evolvono e le circostanze cambiano, anche i rischi di credito per un determinato cliente possono cambiare.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-106">As businesses evolve and circumstances change, the credit risks for a given customer can also change.</span></span> <span data-ttu-id="3c3f0-107">Per aiutare a mantenere i limiti di credito appropriati per i clienti, è necessario rivedere periodicamente i criteri per ogni punteggio di rischio e aggiornare i punteggi per ogni cliente.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-107">To help maintain appropriate credit limits for your customers, you must periodically review the criteria for each risk score and update the scores for each customer.</span></span> <span data-ttu-id="3c3f0-108">È possibile aggiornare i seguenti punteggi utilizzando la pagina **Aggiorna punteggi di rischio** (**Credito e riscossioni \> Attività periodiche \> Gestione crediti \> Aggiorna punteggi di rischio**).</span><span class="sxs-lookup"><span data-stu-id="3c3f0-108">You can update the following scores by using the **Update risk scores** page (**Credit and collections \> Periodic tasks \> Credit management \> Update risk scores**).</span></span> <span data-ttu-id="3c3f0-109">Vengono inoltre elaborati tutti i calcoli definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-109">All user-defined calculations are also processed.</span></span>

- <span data-ttu-id="3c3f0-110">**Numero medio di giorni per pagamento** - Questo punteggio è il numero medio di giorni che un cliente impiega per pagare le fatture.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-110">**Average payment days** – This score is the average number of days that a customer takes to pay invoices.</span></span>
- <span data-ttu-id="3c3f0-111">**Cliente da** - Questo punteggio è il numero di anni in cui un cliente è stato cliente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-111">**Customer since** – This score is the number of years that a customer has been a customer of your organization.</span></span>
- <span data-ttu-id="3c3f0-112">**In attività da** - Questo punteggio indica il numero di anni di attività di un cliente.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-112">**In business since** – This score is the number of years that a customer has been in business.</span></span> <span data-ttu-id="3c3f0-113">Utilizza il valore del campo **Inizio attività** nella pagina **Clienti**.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-113">It uses the value of the **Business start** field on the **Customers** page.</span></span>
- <span data-ttu-id="3c3f0-114">**Tempo medio di incasso** - Questo punteggio si basa sul saldo della contabilità clienti, sui ricavi delle vendite e sul numero di giorni per il precedente periodo di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-114">**Days sales outstanding** – This score is based on the accounts receivable balance, sales revenue, and number of days for the previous 12-month period.</span></span>
- <span data-ttu-id="3c3f0-115">**Saldo medio** - Questo punteggio si basa sul saldo della contabilità clienti per il precedente periodo di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-115">**Average balance** – This score is based on the accounts receivable balance for the previous 12-month period.</span></span>
- <span data-ttu-id="3c3f0-116">**Gruppo di gestione crediti**, **Stato conto** e **Paese** - Questi punteggi utilizzano le informazioni del cliente.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-116">**Credit management group**, **Account status**, and **Country** – These scores use information from the customer.</span></span>

## <a name="update-customer-balance-statistics"></a><span data-ttu-id="3c3f0-117">Aggiornare le statistiche del saldo clienti</span><span class="sxs-lookup"><span data-stu-id="3c3f0-117">Update customer balance statistics</span></span>

<span data-ttu-id="3c3f0-118">È possibile eseguire il processo **Aggiorna statistiche saldo clienti** per aggiornare il calcolo delle statistiche del saldo visualizzato nella pagina **Richiesta informazioni su statistiche del saldo**.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-118">You can run the **Update customer balance statistics** process to update the calculation of balance statistics that is shown on the **Balance statistics inquiry** page.</span></span> <span data-ttu-id="3c3f0-119">Queste informazioni vengono utilizzate per calcolare i punteggi di rischio e i valori visualizzati nei Dettagli informazioni sulle statistiche del credito nella pagina **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-119">This information is used to calculate risk scores and the values that are shown in the credit statistics FactBoxes on the **Customer** page.</span></span>

<span data-ttu-id="3c3f0-120">Quando si esegue il processo, aggiorna le statistiche sul saldo clienti per un singolo cliente.</span><span class="sxs-lookup"><span data-stu-id="3c3f0-120">When you run the process, it updates customer balance statistics for a single customer.</span></span> <span data-ttu-id="3c3f0-121">Per impostare un processo batch allo scopo di eseguire il processo per più clienti, è possibile utilizzare la pagina **Calcola statistiche saldo** (**Gestione crediti \> Attività periodiche \> Calcola statistiche saldo**).</span><span class="sxs-lookup"><span data-stu-id="3c3f0-121">To set up a batch job to run the process for multiple customers, you can use the **Calculate balance statistics** page (**Credit management \> Periodic tasks \> Calculate balance statistics**).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]