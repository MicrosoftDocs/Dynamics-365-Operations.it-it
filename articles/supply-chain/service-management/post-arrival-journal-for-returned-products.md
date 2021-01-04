---
title: Registrare il giornale di registrazione arrivi per i prodotti resi
description: Registrare il giornale di registrazione arrivi per i prodotti resi.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e07542a369506b810704012bd1b07557b79f50d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431324"
---
# <a name="post-arrival-journal-for-returned-products"></a><span data-ttu-id="887d7-103">Registrare il giornale di registrazione arrivi per i prodotti resi</span><span class="sxs-lookup"><span data-stu-id="887d7-103">Post arrival journal for returned products</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="887d7-104">Per elaborare un reso, è necessario innanzitutto convalidarne la quantità, aggiornare il campo relativo alla quantità nel giornale di registrazione arrivi articoli,</span><span class="sxs-lookup"><span data-stu-id="887d7-104">To process a return, first validate the return quantity, update the quantity field in the item arrival journal.</span></span> <span data-ttu-id="887d7-105">quindi selezionare un codice smaltimento o indicare che il reso deve essere sottoposto a ispezione.</span><span class="sxs-lookup"><span data-stu-id="887d7-105">Then select a disposition code or indicate that the returned items have to be inspected.</span></span> <span data-ttu-id="887d7-106">Dopo avere effettuato queste operazioni, è possibile registrare il giornale arrivi articoli per l'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="887d7-106">After completing these steps, you can post the item arrival journal for the return order.</span></span>

1.  <span data-ttu-id="887d7-107">Fare clic su **Gestione articoli** \> **Periodico** \> **Panoramica arrivi**.</span><span class="sxs-lookup"><span data-stu-id="887d7-107">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="887d7-108">Nel filtro **Nome impostazioni**, selezionare **Ordine di reso**.</span><span class="sxs-lookup"><span data-stu-id="887d7-108">In the **Setup name** filter, select **Return order**.</span></span>

3.  <span data-ttu-id="887d7-109">Se l'elenco dei ricevimenti include molte voci, utilizzare i campi nell'area **Intervallo** per limitare il numero di voci visualizzate.</span><span class="sxs-lookup"><span data-stu-id="887d7-109">If the list of receipts is long, use the fields in the **Range** area to narrow the list.</span></span>

4.  <span data-ttu-id="887d7-110">Individuare la riga dell'ordine di reso da registrare, selezionare la casella **elezionato per arrivo** corrispondente, quindi fare clic su **Inizia arrivo**.</span><span class="sxs-lookup"><span data-stu-id="887d7-110">Locate the line of the return order that you want to post, select its **Select for arrival** box, and then click **Start arrival**.</span></span>

5.  <span data-ttu-id="887d7-111">Fare clic **Giornali di registrazione** \> **Mostra arrivi da ricevimenti** per aprire il modulo **Giornale di registrazione ubicazioni**.</span><span class="sxs-lookup"><span data-stu-id="887d7-111">Click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="887d7-112">Per visualizzare informazioni dettagliate, selezionare un giornale di registrazione, quindi fare clic su <STRONG>Righe</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="887d7-112">To view detailed information, select a journal, and then click <STRONG>Lines</STRONG>.</span></span></P>


6.  <span data-ttu-id="887d7-113">Apportare le modifiche necessarie, quindi fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="887d7-113">Make any necessary updates, and then click **Post**.</span></span>

<span data-ttu-id="887d7-114">Dopo la registrazione del giornale, i resi verranno registrati nelle scorte e nel modulo **Ordini di reso** verrà indicato che gli articoli sono arrivati nel magazzino.</span><span class="sxs-lookup"><span data-stu-id="887d7-114">After the journal is posted, the returned items are registered in inventory, and the **Return orders** form indicates that the items have arrived at the warehouse.</span></span>

## <a name="see-also"></a><span data-ttu-id="887d7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="887d7-115">See also</span></span>

<span data-ttu-id="887d7-116">[Giornale di registrazione ubicazioni (modulo)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="887d7-116">[Location journal (form)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span></span>

  


