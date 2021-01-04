---
title: Elaborare sconti per il pagamento
description: Questa procedura mostra come convertire gli sconti del cliente approvati ed elaborati in note di accredito.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 981068d26d232b10efd8d7288daaf7358aee3728
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431273"
---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="c52a8-103">Elaborare sconti per il pagamento</span><span class="sxs-lookup"><span data-stu-id="c52a8-103">Process rebates for payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c52a8-104">Questa procedura mostra come convertire gli sconti del cliente approvati ed elaborati in note di accredito.</span><span class="sxs-lookup"><span data-stu-id="c52a8-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="c52a8-105">È possibile utilizzare questa guida nella società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="c52a8-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="c52a8-106">L'assunto per la guida è di avere uno o più richieste di sconto con stato Contrassegna.</span><span class="sxs-lookup"><span data-stu-id="c52a8-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="c52a8-107">Se si utilizza USMF, è necessario eseguire la guida "Generare ed elaborare gli sconti cliente" prima di iniziare questa guida.</span><span class="sxs-lookup"><span data-stu-id="c52a8-107">If you're using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="c52a8-108">Convertire le richieste di sconto in nota di accredito</span><span class="sxs-lookup"><span data-stu-id="c52a8-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="c52a8-109">Scegliere Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="c52a8-109">Go to All customers.</span></span>
2. <span data-ttu-id="c52a8-110">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c52a8-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c52a8-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c52a8-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c52a8-112">Nel riquadro azioni fare clic su Raccolta.</span><span class="sxs-lookup"><span data-stu-id="c52a8-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="c52a8-113">Fare clic su Liquida transazioni.</span><span class="sxs-lookup"><span data-stu-id="c52a8-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="c52a8-114">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="c52a8-114">Click Functions.</span></span>
7. <span data-ttu-id="c52a8-115">Fare clic su Programma sconti.</span><span class="sxs-lookup"><span data-stu-id="c52a8-115">Click Rebate program.</span></span>
    * <span data-ttu-id="c52a8-116">La pagina degli sconti include le richieste di sconto elaborate nel workbench degli sconti del cliente e che sono con stato Contrassegna.</span><span class="sxs-lookup"><span data-stu-id="c52a8-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="c52a8-117">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c52a8-117">Click Edit.</span></span>
    * <span data-ttu-id="c52a8-118">Impostare i segni di spunta nel campo Contrassegna per le richieste da includere nella nota di accredito.</span><span class="sxs-lookup"><span data-stu-id="c52a8-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="c52a8-119">Fare clic su Funzioni.</span><span class="sxs-lookup"><span data-stu-id="c52a8-119">Click Functions.</span></span>
10. <span data-ttu-id="c52a8-120">Fare clic su Crea nota di accredito.</span><span class="sxs-lookup"><span data-stu-id="c52a8-120">Click Create credit note.</span></span>
    * <span data-ttu-id="c52a8-121">Viene visualizzato un messaggio per informare che è stato registrato un giornale di registrazione (questo è il giornale di registrazione relativo all'utilizzo di Contabilità clienti, come specificato nella pagina dei parametri di Contabilità clienti).</span><span class="sxs-lookup"><span data-stu-id="c52a8-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="c52a8-122">Ciò causa il trasferimento dell'importo effettivo di passività (credito) nel saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="c52a8-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="c52a8-123">Significa che sono stati effettuati un accredito sul conto del cliente e un addebito sul conto ratei sconto.</span><span class="sxs-lookup"><span data-stu-id="c52a8-123">This means that the customer's account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="c52a8-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c52a8-124">Close the page.</span></span>
12. <span data-ttu-id="c52a8-125">Scegliere Annulla.</span><span class="sxs-lookup"><span data-stu-id="c52a8-125">Click Cancel.</span></span>
    * <span data-ttu-id="c52a8-126">In questo modo viene aggiornata la pagina e sono visibili gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="c52a8-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="c52a8-127">Nel riquadro azioni fare clic su Raccolta.</span><span class="sxs-lookup"><span data-stu-id="c52a8-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="c52a8-128">Fare clic su Liquida transazioni.</span><span class="sxs-lookup"><span data-stu-id="c52a8-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="c52a8-129">Si noti che una transazione dall'importo negativo, rappresentante l'importo totale dello sconto, senza riferimento alla fattura è stata aggiunta al saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="c52a8-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="c52a8-130">Scegliere Annulla.</span><span class="sxs-lookup"><span data-stu-id="c52a8-130">Click Cancel.</span></span>

