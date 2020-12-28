---
title: Data di competenza per le transazioni e il report giornale di registrazione fiscale
description: In questo argomento vengono fornite informazioni sulla data di competenza e illustra come attivare la funzionalità per le transazioni in Italia
author: anasyash
manager: tfehr
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: ''
ms.custom: ''
ms.search.region: Italy
ms.author: anasyash
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 54582e6ca79eff02a056cb2c16baceecb626e9b9
ms.sourcegitcommit: 3d16522c00ba2d30aa43befbf1b7b3eaad377325
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "4592474"
---
# <a name="competence-date-for-transactions-and-the-fiscal-journal-report"></a><span data-ttu-id="f4b73-103">Data di competenza per le transazioni e il report giornale di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4b73-103">Competence date for transactions and the Fiscal journal report</span></span>

<span data-ttu-id="f4b73-104">In questo argomento vengono fornite informazioni sulla data di competenza e illustra come attivare la funzionalità per le transazioni in Italia.</span><span class="sxs-lookup"><span data-stu-id="f4b73-104">This topic provides information about the competence date and explains how to turn on the functionality for transactions in Italy.</span></span>

<span data-ttu-id="f4b73-105">In Italia, le società devono utilizzare una data di registrazione per registrare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="f4b73-105">In Italy, companies must use a posting date when they post transactions.</span></span> <span data-ttu-id="f4b73-106">La data di registrazione nel giornale di registrazione fiscale corrisponde alla data in cui la società conferma la transazione.</span><span class="sxs-lookup"><span data-stu-id="f4b73-106">The posting date in the fiscal journal is the date when the company acknowledges the transaction.</span></span>

<span data-ttu-id="f4b73-107">Le transazioni di chiusura e correzione avvengono in genere alla data in cui lo stato patrimoniale viene approvato dal consiglio di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f4b73-107">Usually, adjustment and closing transactions occur on the date when the balance sheet is approved by the Board of Directors.</span></span> <span data-ttu-id="f4b73-108">Possono tuttavia essere anche completate diversi mesi dopo l'ultimo giorno dell'anno fiscale.</span><span class="sxs-lookup"><span data-stu-id="f4b73-108">However, they can also be completed several months after the last day of the fiscal year.</span></span> <span data-ttu-id="f4b73-109">Tali transazioni devono essere dichiarate nel giornale di registrazione fiscale italiano alla data di registrazione, che deve coincidere con la data di conferma.</span><span class="sxs-lookup"><span data-stu-id="f4b73-109">These transactions must be reported in the Italian fiscal journal on the posting date, which must be the same as the acknowledgment date.</span></span> <span data-ttu-id="f4b73-110">Le transazioni devono tuttavia avere un riferimento alla relativa data di competenza, che rappresenta la data in cui la transazione influisce sull'importo del saldo.</span><span class="sxs-lookup"><span data-stu-id="f4b73-110">However, the transactions must have a reference to their competence date, which represents the date when the transaction affects the balance amount.</span></span>

## <a name="turn-on-the-competence-date-functionality"></a><span data-ttu-id="f4b73-111">Attiva la funzionalità della data di competenza</span><span class="sxs-lookup"><span data-stu-id="f4b73-111">Turn on the competence date functionality</span></span>

1.  <span data-ttu-id="f4b73-112">Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="f4b73-112">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>

2.  <span data-ttu-id="f4b73-113">Nella pagina **Parametri di contabilità generale**, nella scheda **Contabilità generale** impostare l'opzione **Riferimento alla data competenza nella data della transazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f4b73-113">On the **General ledger parameters** page, on the **Ledger** tab, set the **Transaction date reference to competence date** option to **Yes**.</span></span>

    <span data-ttu-id="f4b73-114">Dopo aver attivato la funzionalità della data di competenza, è possibile specificare **Data transazione** come data di conferma per ogni giornale di registrazione utilizzabile per registrare le transazioni di correzione e di chiusura per l'anno fiscale:</span><span class="sxs-lookup"><span data-stu-id="f4b73-114">After the competence date functionality is turned on, you can specify **Transaction date** as an acknowledgment date for each journal that can be used to post the adjustment and closing transactions for the fiscal year:</span></span>

    -   <span data-ttu-id="f4b73-115">Giornale di registrazione generale (**Contabilità generale** \> **Inserimenti nel giornale di registrazione** \> **Giornali di registrazione generale**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-115">General journal (**General ledger** \> **Journal entries** \> **General journals**)</span></span>
    -   <span data-ttu-id="f4b73-116">Giornale di registrazione cespiti (**Cespiti** \> **Scritture contabili** \> **Giornale di registrazione cespiti**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-116">Fixed assets journal (**Fixed assets** \> **Journal entries** \> **Fixed assets journal**)</span></span>
    -   <span data-ttu-id="f4b73-117">Riconciliazione estratti conto bancario (**Gestione cassa e banche** \> **Conti bancari** \> **Conti bancari** \> **Riconcilia** \> **Riconciliazione estratti conto**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-117">Bank account reconciliation (**Cash and bank management** \> **Bank accounts** \> **Bank accounts** \> **Reconcile** \> **Account reconciliation**)</span></span>
    -   <span data-ttu-id="f4b73-118">Rettifiche periodo di chiusura (**Contabilità generale** \> **Periodo chiuso** \> **Rettifiche periodo di chiusura**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-118">Closing period adjustments (**General ledger** \> **Period close** \> **Closing period adjustments**)</span></span>
    -   <span data-ttu-id="f4b73-119">Chiusura di fine anno (**Contabilità generale** \> **Periodo chiuso** \> **Chiusura di fine anno** \> **Esegui chiusura fiscale**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-119">Year-end close (**General ledger** \> **Period close** \> **Year end close** \> **Run fiscal close**)</span></span>
    -   <span data-ttu-id="f4b73-120">Progetto - Registra costi (**Gestione progetti e contabilità** \> **Periodico** \> **Tempistica e materiali** \> **Registra costi** \> **Registra**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-120">Project – Post costs (**Project management and accounting** \> **Periodic** \> **Time and Material** \> **Post Costs** \> **Post**)</span></span>
    -   <span data-ttu-id="f4b73-121">Progetto - Accumula ricavi (**Gestione progetti e contabilità** \> **Periodico** \> **Tempistica e materiali** \> **Accumula ricavi**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-121">Project – Accrue revenue (**Project management and accounting** \> **Periodic** \> **Time and material** \> **Accrue revenue**)</span></span>
    -   <span data-ttu-id="f4b73-122">Progetto - Stima registrata (**Gestione progetti e contabilità** \> **Periodico** \> **Stime** \> **Registra stime**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-122">Project – Estimate post (**Project management and accounting** \> **Periodic** \> \*\*Estimates \> **Post estimates**)</span></span>
    -   <span data-ttu-id="f4b73-123">Progetto - Storna stima (**Gestione progetti e contabilità** \> **Periodico** \> **Stime** \> **Storna stime**)</span><span class="sxs-lookup"><span data-stu-id="f4b73-123">Project – Estimate reverse (**Project management and accounting** \> **Periodic** \> **Estimates** \> **Reverse estimates**)</span></span>

## <a name="fiscal-journal-report"></a><span data-ttu-id="f4b73-124">Report Giornale di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4b73-124">Fiscal journal report</span></span>

<span data-ttu-id="f4b73-125">Il report **Giornale di registrazione fiscale** italiano (**Contabilità generale \> Richieste e report \> Giornale di registrazione fiscale**) è un report mensile che elenca tutti i giustificativi e gli inserimenti nel giornale di registrazione nell'ordine, in base alla data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="f4b73-125">The Italian **Fiscal journal** report (**General ledger \> Inquiries and reports \> Fiscal journal**) is a monthly report that lists all the vouchers and journal entries in the order, by posting date.</span></span>

<span data-ttu-id="f4b73-126">In questo report sono inclusi i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="f4b73-126">This report includes the following fields:</span></span>

-   <span data-ttu-id="f4b73-127">Numero riga</span><span class="sxs-lookup"><span data-stu-id="f4b73-127">Line number</span></span>
-   <span data-ttu-id="f4b73-128">Data di registrazione</span><span class="sxs-lookup"><span data-stu-id="f4b73-128">Posting date</span></span>
-   <span data-ttu-id="f4b73-129">Data competenza</span><span class="sxs-lookup"><span data-stu-id="f4b73-129">Competence date</span></span>
-   <span data-ttu-id="f4b73-130">Numero documento (numero giustificativo)</span><span class="sxs-lookup"><span data-stu-id="f4b73-130">Document number (voucher number)</span></span>
-   <span data-ttu-id="f4b73-131">Data del documento</span><span class="sxs-lookup"><span data-stu-id="f4b73-131">Date for document</span></span>
-   <span data-ttu-id="f4b73-132">Nome e numero del conto CoGe</span><span class="sxs-lookup"><span data-stu-id="f4b73-132">Ledger account number and name</span></span>
-   <span data-ttu-id="f4b73-133">Nome e numero del conto cliente o fornitore</span><span class="sxs-lookup"><span data-stu-id="f4b73-133">Customer/Vendor account number and name</span></span>
-   <span data-ttu-id="f4b73-134">descrizione</span><span class="sxs-lookup"><span data-stu-id="f4b73-134">Description</span></span>
-   <span data-ttu-id="f4b73-135">Valuta</span><span class="sxs-lookup"><span data-stu-id="f4b73-135">Currency</span></span>
-   <span data-ttu-id="f4b73-136">Importo in Dare o in Avere del documento</span><span class="sxs-lookup"><span data-stu-id="f4b73-136">Debit or credit amount of the document</span></span>

![Transazioni del report Giornale di registrazione fiscale](media/ITA-Competence-date-for-transactions-1-fiscal-journal.png)

## <a name="example"></a><span data-ttu-id="f4b73-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4b73-138">Example</span></span>

<span data-ttu-id="f4b73-139">L'anno fiscale della società inizia l'1 gennaio e termina il 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="f4b73-139">The company's fiscal year is from January 1 through December 31.</span></span> <span data-ttu-id="f4b73-140">Lo stato patrimoniale viene approvato il 15 aprile.</span><span class="sxs-lookup"><span data-stu-id="f4b73-140">The balance sheet is approved on April 15.</span></span> <span data-ttu-id="f4b73-141">Di conseguenza, le transazioni di chiusura e correzione vengono dichiarate nel giornale di registrazione fiscale italiano ad aprile, ma influiscono sul saldo al 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="f4b73-141">Therefore, adjustment and closing transactions are reported in the Italian fiscal journal in April, but they affect the balance on December 31.</span></span>

1. <span data-ttu-id="f4b73-142">Andare a **Contabilità generale** \> **Inserimenti nel giornale di registrazione** \> **Giornali di registrazione generali**.</span><span class="sxs-lookup"><span data-stu-id="f4b73-142">Go to **General ledger** \> **Journal entries** \> **General journals**.</span></span>
2. <span data-ttu-id="f4b73-143">Nella pagina **Giornale di registrazione generale** specificare 31 dicembre nel campo **Data**.</span><span class="sxs-lookup"><span data-stu-id="f4b73-143">On the **General journal** page, in the **Date** field, specify December 31.</span></span>
3. <span data-ttu-id="f4b73-144">Nel campo **Data transazione** specificare il 15 aprile.</span><span class="sxs-lookup"><span data-stu-id="f4b73-144">In the **Transaction date** field, specify April 15.</span></span>
4. <span data-ttu-id="f4b73-145">Registrare la transazione.</span><span class="sxs-lookup"><span data-stu-id="f4b73-145">Post the transaction.</span></span>

    ![Pagina del giustificativo giornale di registrazione](media/ITA-Competence-date-for-transactions-2-general-journal.png)

5. <span data-ttu-id="f4b73-147">Andare a **Contabilità generale** \> **Richieste di informazioni e report** \> **Giornale di registrazione fiscale** ed eseguire il report.</span><span class="sxs-lookup"><span data-stu-id="f4b73-147">Go to **General ledger** \> **Inquiries and reports** \> **Fiscal journal**, and run the report.</span></span> <span data-ttu-id="f4b73-148">La transazione viene riportata nella riga del giornale di registrazione fiscale.</span><span class="sxs-lookup"><span data-stu-id="f4b73-148">The transaction is reported on the fiscal journal line.</span></span> <span data-ttu-id="f4b73-149">Il campo **Data di registrazione** è impostato sul 15 aprile e il campo **Data competenza** è impostato sul 31 dicembre.</span><span class="sxs-lookup"><span data-stu-id="f4b73-149">The **Posting date** field is set to April15, and the **Competence date** field is set to December 31.</span></span>

    ![Pagina Giornale di registrazione fiscale](media/ITA-Competence-date-for-transactions-3-fiscal-journal.png)

6. <span data-ttu-id="f4b73-151">Andare a **Contabilità generale \> Richieste di informazioni e report \> Bilancio di verifica** ed esegui il report.</span><span class="sxs-lookup"><span data-stu-id="f4b73-151">Go to **General ledger \> Inquiries and reports \> Trial balance**, and run the report.</span></span>

    ![Descrizione interfaccia utente grafica e descrizione generata automaticamente](media/ITA-Competence-date-for-transactions-4-trial-balance.png)

7. <span data-ttu-id="f4b73-153">Andare a **Contabilità generale** \> **Richieste di informazioni e report** \> **Transazioni giustificativo**.</span><span class="sxs-lookup"><span data-stu-id="f4b73-153">Go to **General ledger** \> **Inquiries and reports** \> **Voucher transactions**.</span></span>
8. <span data-ttu-id="f4b73-154">Nella pagina **Transazioni giustificativo** aggiungere la colonna **Data transazione**.</span><span class="sxs-lookup"><span data-stu-id="f4b73-154">On the **Voucher transactions** page, add the **Transaction date** column.</span></span>
9. <span data-ttu-id="f4b73-155">Verificare il campo **Data** sia impostato sul 31 dicembre e il campo **Data transazione** sia impostato sul 15 aprile.</span><span class="sxs-lookup"><span data-stu-id="f4b73-155">Verify that the **Date** field is set to December 31, and the **Transaction date** field is set to April 15.</span></span>
