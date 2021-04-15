---
title: Sospendere e riprendere una transazione nel POS
description: In questo argomento viene illustrato come gli utenti possono sospendere le transazioni in corso e quindi riprenderle successivamente o su un registratore di cassa differente utilizzando Dynamics 365 Commerce.
author: jblucher
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fdb693cb3b7520a9850d3e37dd512fc5b2a847f3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798659"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a><span data-ttu-id="fda5c-103">Sospendere e riprendere una transazione nel POS</span><span class="sxs-lookup"><span data-stu-id="fda5c-103">Suspend and resume a transaction in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="fda5c-104">Gli utenti POS possono sospendere le transazioni in corso e quindi riprenderle successivamente o su un registratore di cassa differente.</span><span class="sxs-lookup"><span data-stu-id="fda5c-104">Point of sale (POS) users can suspend in-progress transactions, and then resume them later or on a different register.</span></span> <span data-ttu-id="fda5c-105">Le transazioni vengono spesso sospese per liberare rapidamente un registro di cassa per un'attività differente senza perdita di dati nella transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="fda5c-105">Transactions are often suspended to quickly free up a register for a different task without losing any progress on the current transaction.</span></span> <span data-ttu-id="fda5c-106">Ad esempio, un associato di un punto vendita inizia a elaborare la transazione di un cliente su un dispositivo mobile ma deve completarla su un registratore con un cassetto della cassa.</span><span class="sxs-lookup"><span data-stu-id="fda5c-106">For example, a store associate starts to process a customer's transaction on a mobile device but must complete it on a register that has a cash drawer.</span></span> <span data-ttu-id="fda5c-107">In questo caso, l'associato del punto vendita può sospendere la transazione sul dispositivo mobile e quindi richiamarla e riprenderla su un registratore di cassa.</span><span class="sxs-lookup"><span data-stu-id="fda5c-107">In this case, the store associate can suspend the transaction on the mobile device, and then recall and resume it on a register.</span></span>

## <a name="configure-suspend-and-resume-functionality"></a><span data-ttu-id="fda5c-108">Configurare la funzionalità per sospendere e riprendere una transazione</span><span class="sxs-lookup"><span data-stu-id="fda5c-108">Configure suspend and resume functionality</span></span>

### <a name="pos-operations"></a><span data-ttu-id="fda5c-109">Operazioni POS</span><span class="sxs-lookup"><span data-stu-id="fda5c-109">POS operations</span></span>

<span data-ttu-id="fda5c-110">Due [Operazioni POS](pos-operations.md) consentono al supporto POS di sospendere e riprendere gli scenari.</span><span class="sxs-lookup"><span data-stu-id="fda5c-110">Two [POS operations](pos-operations.md) let the POS support suspend and resume scenarios.</span></span> <span data-ttu-id="fda5c-111">È possibile assegnare queste operazioni a [griglie di pulsanti](pos-screen-layouts.md) nella pagina delle transazioni o nella pagina di benvenuto.</span><span class="sxs-lookup"><span data-stu-id="fda5c-111">You can assign these operations to [button grids](pos-screen-layouts.md) on the transaction page or the welcome page.</span></span>

- <span data-ttu-id="fda5c-112">503: Sospendi transazione</span><span class="sxs-lookup"><span data-stu-id="fda5c-112">503: Suspend transaction</span></span>
- <span data-ttu-id="fda5c-113">504: Richiama transazione</span><span class="sxs-lookup"><span data-stu-id="fda5c-113">504: Recall transaction</span></span>

### <a name="receipt-template"></a><span data-ttu-id="fda5c-114">Modello di ricevuta</span><span class="sxs-lookup"><span data-stu-id="fda5c-114">Receipt template</span></span>

<span data-ttu-id="fda5c-115">Il POS può essere configurato per generare una distinta stampata quando una transazione viene sospesa.</span><span class="sxs-lookup"><span data-stu-id="fda5c-115">The POS can be configured to generate a printed slip when a transaction is suspended.</span></span> <span data-ttu-id="fda5c-116">Tale distinta può quindi essere utilizzata per identificare e richiamare rapidamente la transazione in seguito.</span><span class="sxs-lookup"><span data-stu-id="fda5c-116">That slip can then be used to quickly identify and recall the transaction later.</span></span>

<span data-ttu-id="fda5c-117">Per abilitare il POS per la stampa di una distinta, è necessario aggiungere il formato di ricevuta **Transazione sospesa** al profilo di ricevuta del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fda5c-117">To enable the POS to print a slip, you must add the **Suspended transaction** receipt format to the store's receipt profile.</span></span> <span data-ttu-id="fda5c-118">È possibile progettare il formato di ricevuta di modo che includa o non includa specifici dettagli sulla transazione.</span><span class="sxs-lookup"><span data-stu-id="fda5c-118">You can design the receipt format so that it includes or excludes specific details about the transaction.</span></span> <span data-ttu-id="fda5c-119">Ad esempio, il formato può includere un codice a barre per supportare la scansione.</span><span class="sxs-lookup"><span data-stu-id="fda5c-119">For example, the format can include a barcode to support scanning.</span></span>

### <a name="receipt-numbering"></a><span data-ttu-id="fda5c-120">Numerazione ricevute</span><span class="sxs-lookup"><span data-stu-id="fda5c-120">Receipt numbering</span></span>

<span data-ttu-id="fda5c-121">Per gli altri tipi di transazione POS che generano una ricevuta stampata, è possibile definire una sequenza numerica per le transazioni sospese nella sezione **Numerazione ricevute** del profilo funzionalità del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fda5c-121">As for other POS transaction types that generate a printed receipt, you can define a number sequence for suspended transactions in the **Receipt numbering** section of the store's functionality profile.</span></span>

### <a name="void-when-closing-shift"></a><span data-ttu-id="fda5c-122">Annulla alla chiusura del turno</span><span class="sxs-lookup"><span data-stu-id="fda5c-122">Void when closing shift</span></span>

<span data-ttu-id="fda5c-123">È possibile utilizzare l'opzione **Annulla alla chiusura del turno** per far sì che gli utenti completino o annullino tutte le transazioni sospese prima di chiudere il proprio turno.</span><span class="sxs-lookup"><span data-stu-id="fda5c-123">You can use the **Void when closing shift** option to require that users either complete or void any suspended transactions before they close their shift.</span></span> <span data-ttu-id="fda5c-124">Durante l'operazione **Chiudi turno**, il POS richiederà agli utenti di visualizzare o annullare tutte le transazioni sospese.</span><span class="sxs-lookup"><span data-stu-id="fda5c-124">During the **Close shift** operation, the POS will prompt users to either view or void any outstanding suspended transactions.</span></span>

## <a name="suspend-and-resume-a-transaction"></a><span data-ttu-id="fda5c-125">Sospendere e riprendere una transazione</span><span class="sxs-lookup"><span data-stu-id="fda5c-125">Suspend and resume a transaction</span></span>

### <a name="suspend-a-transaction"></a><span data-ttu-id="fda5c-126">Sospendere una transazione</span><span class="sxs-lookup"><span data-stu-id="fda5c-126">Suspend a transaction</span></span>

<span data-ttu-id="fda5c-127">Gli utenti con privilegi sufficienti e con un layout di schermo che include l'operazione **Sospendi transazione** possono sospendere una transazione e quindi richiamarla successivamente o su un registro di cassa differente.</span><span class="sxs-lookup"><span data-stu-id="fda5c-127">Users who have sufficient privileges, and who have a screen layout that includes the **Suspend transaction** operation, can suspend a transaction so that it can be recalled later or on a different register.</span></span>

<span data-ttu-id="fda5c-128">Le transazioni possono essere sospese solo se **non** contengono i seguenti tipi di righe:</span><span class="sxs-lookup"><span data-stu-id="fda5c-128">Transactions can be suspended only if they do **not** contain the following types of lines:</span></span>

- <span data-ttu-id="fda5c-129">Righe pagamento attive</span><span class="sxs-lookup"><span data-stu-id="fda5c-129">Active payment lines</span></span>
- <span data-ttu-id="fda5c-130">Righe gift card (per emettere una gift card o per un'aggiunta al saldo gift card)</span><span class="sxs-lookup"><span data-stu-id="fda5c-130">Gift card lines (either to issue a gift card or to add to the gift card balance)</span></span>

<span data-ttu-id="fda5c-131">Una transazione sospesa non influisce sulle informazioni relative alle vendite o alla disponibilità delle scorte per il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="fda5c-131">A suspended transaction doesn't affect sales information or inventory availability information for the store.</span></span>

### <a name="resume-a-suspended-transaction"></a><span data-ttu-id="fda5c-132">Riprendere una transazione sospesa</span><span class="sxs-lookup"><span data-stu-id="fda5c-132">Resume a suspended transaction</span></span>

<span data-ttu-id="fda5c-133">Le transazioni sospese possono essere richiamate e riprese nello stesso punto vendita da qualsiasi utente con privilegi sufficienti e che dispone di un layout che include l'operazione **Richiama transazione**.</span><span class="sxs-lookup"><span data-stu-id="fda5c-133">Suspended transactions can be recalled and resumed in the same store by any user who has sufficient privileges, and who also has a layout that includes the **Recall transaction** operation.</span></span>

<span data-ttu-id="fda5c-134">Per richiamare rapidamente e facilmente una transazione sospesa, eseguire la scansione del codice a barre sulla distinta stampata durante la visualizzazione dell'elenco delle transazioni dall'operazione **Richiama transazione**.</span><span class="sxs-lookup"><span data-stu-id="fda5c-134">To quickly and easily recall a suspended transaction, scan the barcode on the printed slip while you're viewing the list of transactions from the **Recall transaction** operation.</span></span>

### <a name="considerations-for-offline-mode"></a><span data-ttu-id="fda5c-135">Considerazioni sulla modalità offline</span><span class="sxs-lookup"><span data-stu-id="fda5c-135">Considerations for offline mode</span></span>

- <span data-ttu-id="fda5c-136">Qualsiasi transazione sospesa quando il POS è in modalità in linea non può essere ripresa in modalità offline, poiché i dati non vengono sincronizzati al database offline.</span><span class="sxs-lookup"><span data-stu-id="fda5c-136">Any transaction that is suspended while the POS is in online mode can't be resumed in offline mode, because the data isn't synced to the offline database.</span></span>
- <span data-ttu-id="fda5c-137">Se si sospende una transazione quando il POS è in modalità offline, è possibile richiamarla in modalità offline purché il POS non sia passato di nuovo alla modalità in linea dopo la sospensione della transazione.</span><span class="sxs-lookup"><span data-stu-id="fda5c-137">If you suspend a transaction while the POS is in offline mode, you can recall it in offline mode, provided that the POS wasn't switched back to online mode at any time since you suspended the transaction.</span></span> <span data-ttu-id="fda5c-138">Quando il POS passa di nuovo alla modalità in linea, i dati relativi alle transazioni sospese vengono spostati nel database in linea e rimossi dal database offline.</span><span class="sxs-lookup"><span data-stu-id="fda5c-138">When the POS is switched back to online mode, data about suspended transactions is moved to the online database and removed from the offline database.</span></span> <span data-ttu-id="fda5c-139">Di conseguenza, le transazioni possono essere riprese solo in modalità in linea.</span><span class="sxs-lookup"><span data-stu-id="fda5c-139">Therefore, the transactions can be resumed only in online mode.</span></span> <span data-ttu-id="fda5c-140">Se il POS passa di nuovo alla modalità offline, non sarà possibile riprendere le transazioni sospese, in quanto sono già state rimosse dal database offline.</span><span class="sxs-lookup"><span data-stu-id="fda5c-140">If you switch the POS back to offline mode, you won't be able to resume those suspended transaction, because they have already been removed from the offline database.</span></span>

### <a name="void-a-suspended-transaction"></a><span data-ttu-id="fda5c-141">Annullare una transazione sospesa</span><span class="sxs-lookup"><span data-stu-id="fda5c-141">Void a suspended transaction</span></span>

<span data-ttu-id="fda5c-142">È possibile annullare le transazioni sospese richiamando la transazione e quindi eseguendo l'operazione **Annulla transazione** oppure selezionando la transazione nell'elenco **Richiama transazione** e quindi **Annulla** sulla barra delle app.</span><span class="sxs-lookup"><span data-stu-id="fda5c-142">You can void suspended transactions either by recalling the transaction and then performing the **Void transaction** operation, or by selecting the transaction in the **Recall transaction** list and selecting **Void** on the app bar.</span></span> <span data-ttu-id="fda5c-143">In alternativa, il punto vendita può essere configurato affinché gli utenti annullino le transazioni sospese quando chiudono il proprio turno.</span><span class="sxs-lookup"><span data-stu-id="fda5c-143">Alternatively, the store can be configured to prompt users to void suspended transactions when they close their shift.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]