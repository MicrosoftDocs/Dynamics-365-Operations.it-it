---
title: Registrare numeri di certificati recuperabili TDS
description: In questo argomento viene illustrato come utilizzare la pagina Certificati recuperabili per registrare i numeri e le date dei certificati dell'imposta dedotta all'origine (TDS) ricevuti per uno specifico conto fornitore, cliente e CoGe.
author: kailiang
mms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b501c331cccc6d030f36d0a13ba0a6a13c08c733
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023344"
---
# <a name="record-tds-recoverable-certificate-numbers"></a><span data-ttu-id="50aa1-103">Registrare numeri di certificati recuperabili TDS</span><span class="sxs-lookup"><span data-stu-id="50aa1-103">Record TDS recoverable certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50aa1-104">In questo argomento viene illustrato come utilizzare la pagina **Certificati recuperabili** per registrare i numeri e le date dei certificati dell'imposta dedotta all'origine (TDS) ricevuti per uno specifico conto fornitore, cliente e CoGe.</span><span class="sxs-lookup"><span data-stu-id="50aa1-104">This topic explains how to use the **Recoverable certificates** page to record the certificate numbers and dates for Tax Deducted at Source (TDS) certificates that are received for a specific vendor, customer, or ledger.</span></span> <span data-ttu-id="50aa1-105">Per aggiornare i numeri e le date dei certificati TDS registrati per le transazioni TDS in questa pagina, utilizza la pagina **Aggiorna certificato** (**Contabilità generale \> Periodico \> Ritenuta d'acconto \> Aggiorna certificato**).</span><span class="sxs-lookup"><span data-stu-id="50aa1-105">To update the TDS certificate numbers and dates that are recorded for TDS transactions on this page, use the **Update certificate** page (**General ledger \> Periodic \> Withholding tax \> Update certificate**).</span></span> <span data-ttu-id="50aa1-106">Dopo aver terminato l'aggiornamento dei numeri di certificato TDS, chiudili.</span><span class="sxs-lookup"><span data-stu-id="50aa1-106">After you've finished updating TDS certificate numbers, close them.</span></span>

<span data-ttu-id="50aa1-107">Segui questi passaggi per registrare i numeri e le date dei certificati TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-107">Follow these steps to record the TDS certificate numbers and dates.</span></span>

1. <span data-ttu-id="50aa1-108">Vai a **Imposta \> Imposte indirette \> Ritenuta d'acconto \> Certificati recuperabili**.</span><span class="sxs-lookup"><span data-stu-id="50aa1-108">Go to **Tax \> Indirect tax \> Withholding tax \> Recoverable certificates**.</span></span>

    <span data-ttu-id="50aa1-109">[![Pagina Certificati recuperabili](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span><span class="sxs-lookup"><span data-stu-id="50aa1-109">[![Recoverable certificates page](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span></span> 

2. <span data-ttu-id="50aa1-110">Nella pagina **Certificati recuperabili**, nel campo **Tipo di imposta**, seleziona **TDS**.</span><span class="sxs-lookup"><span data-stu-id="50aa1-110">On the **Recoverable certificates** page, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="50aa1-111">Selezionare **Nuovo** per creare un record.</span><span class="sxs-lookup"><span data-stu-id="50aa1-111">Select **New** to create a record.</span></span>
4. <span data-ttu-id="50aa1-112">Nel campo **Numero certificato**, immetti il numero di certificato TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-112">In the **Certificate number** field, enter the TDS certificate number.</span></span>
5. <span data-ttu-id="50aa1-113">Nel campo **Tipo di account** seleziona il tipo di conto per il quale viene ricevuto il certificato TDS: **Fornitore**, **Cliente** o **CoGe**.</span><span class="sxs-lookup"><span data-stu-id="50aa1-113">In the **Account type** field, select the type of account that the TDS certificate is received for: **Vendor**, **Customer**, or **Ledger**.</span></span>
6. <span data-ttu-id="50aa1-114">Nel campo **Conto**, seleziona il numero di conto fornitore, cliente o CoGe, a seconda del tipo di conto selezionato.</span><span class="sxs-lookup"><span data-stu-id="50aa1-114">In the **Account** field, select the vendor, customer, or ledger account number, depending on the account type that you selected.</span></span> <span data-ttu-id="50aa1-115">Il campo **Nome** mostra il nome del conto fornitore, cliente o CoGe.</span><span class="sxs-lookup"><span data-stu-id="50aa1-115">The **Name** field shows the name of the vendor, customer, or ledger account.</span></span>
7. <span data-ttu-id="50aa1-116">Nel campo **Importo certificato** immetti l'importo del certificato TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-116">In the **Certificate amount** field, enter the amount of the TDS certificate.</span></span>
8. <span data-ttu-id="50aa1-117">Nel campo **Data**, immetti la data del certificato per il numero del certificato.</span><span class="sxs-lookup"><span data-stu-id="50aa1-117">In the **Date** field, enter the certificate date for the certificate number.</span></span>
9. <span data-ttu-id="50aa1-118">Seleziona **Richieste di informazioni** per aprire la pagina **Transazioni certificati**, in cui puoi visualizzare le transazioni TDS per le quali vengono aggiornati il numero e la data del certificato TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-118">Select **Inquiries** to open the **Certificate transactions** page, where you can view the TDS transactions that the TDS certificate number and date are updated for.</span></span> <span data-ttu-id="50aa1-119">Queste informazioni possono essere aggiornate nella pagina **Aggiorna certificato** (**Imposta \> Dichiarazioni \> Ritenuta d'acconto \> Aggiorna certificato**).</span><span class="sxs-lookup"><span data-stu-id="50aa1-119">This information can be updated on the **Update certificate** page (**Tax \> Declarations \> Withholding tax \> Update certificate**).</span></span>

    <span data-ttu-id="50aa1-120">La pagina **Aggiorna certificato** mostra le seguenti informazioni per ciascuna transazione TDS:</span><span class="sxs-lookup"><span data-stu-id="50aa1-120">The **Update certificate** page shows the following information for each TDS transaction:</span></span>

    - <span data-ttu-id="50aa1-121">**Data** - La data di registrazione della transazione TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-121">**Date** – The posting date of the TDS transaction.</span></span>
    - <span data-ttu-id="50aa1-122">**Giustificativo** - Il numero di giustificativo della transazione TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-122">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="50aa1-123">**Origine** - Il modulo in cui la transazione TDS è stata creata.</span><span class="sxs-lookup"><span data-stu-id="50aa1-123">**Source** – The module that the TDS transaction was created in.</span></span>
    - <span data-ttu-id="50aa1-124">**Conto** - Il numero di conto fornitore, cliente o CoGe per cui è stata creata la transazione TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-124">**Account** – The vendor, customer, or ledger account number that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="50aa1-125">**Nome** - Il numero di conto fornitore, cliente o CoGe per cui la transazione TDS è stata creata.</span><span class="sxs-lookup"><span data-stu-id="50aa1-125">**Name** – The name of the vendor, customer, or ledger account that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="50aa1-126">**Importo** - L'importo della fattura su cui è stata calcolata la TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-126">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="50aa1-127">**Importo imposta** - L'importo della TDS calcolato per la transazione.</span><span class="sxs-lookup"><span data-stu-id="50aa1-127">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>
    - <span data-ttu-id="50aa1-128">**Data certificato** - La data del certificato TDS che è stata aggiornata per la transazione TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-128">**Certificate date** – The TDS certificate date that was updated for the TDS transaction.</span></span>
    - <span data-ttu-id="50aa1-129">**Numero certificato** - Il numero del certificato TDS che è stato aggiornato per la transazione TDS.</span><span class="sxs-lookup"><span data-stu-id="50aa1-129">**Certificate number** – TDS certificate number that was updated for the TDS transaction.</span></span>

10. <span data-ttu-id="50aa1-130">Nella pagina **Certificati recuperabili**, seleziona la casella di controllo **Chiuso** per chiudere il numero del certificato TDS dopo averlo aggiornato per le transazioni TDS nella pagina **Aggiorna certificato**.</span><span class="sxs-lookup"><span data-stu-id="50aa1-130">On the **Recoverable certificates** page, select the **Closed** check box to close the TDS certificate number after you've finished updating it for TDS transactions on the **Update certificate** page.</span></span>

    <span data-ttu-id="50aa1-131">Per selezionare la casella di controllo **Chiuso** per tutti i record nella pagina, seleziona **Contrassegna tutto**.</span><span class="sxs-lookup"><span data-stu-id="50aa1-131">To select the **Closed** check box for all records on the page, select **Mark all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50aa1-132">I numeri di certificato TDS per i quali la casella di controllo **Chiuso** è selezionata non sono disponibili nella pagina **Aggiorna certificato**.</span><span class="sxs-lookup"><span data-stu-id="50aa1-132">TDS certificate numbers that the **Closed** check box is selected for aren't available on the **Update certificate** page.</span></span>
