---
title: Nascondere le modalità di consegna non vettore dalle opzioni di spedizione nel POS
description: In questo argomento viene descritta un'opzione di configurazione che può impedire la visualizzazione delle modalità di consegna non vettore per la selezione quando gli ordini di spedizione vengono creati nell'applicazione POS.
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 75e7e8f183982f7829db78eb75b8c29c9ab95e89
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023109"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="6bcc9-103">Nascondere le modalità di consegna non vettore dalle opzioni di spedizione nel POS</span><span class="sxs-lookup"><span data-stu-id="6bcc9-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6bcc9-104">In questo argomento viene descritta un'opzione di configurazione disponibile per l'applicazione POS.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="6bcc9-105">Questa opzione di configurazione modifica il comportamento per la selezione di una modalità di consegna quando gli ordini di spedizione vengono creati in POS.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="6bcc9-106">Quando gli utenti creano gli ordini di spedizione per il cliente nel POS, possono selezionare una modalità di consegna per la spedizione.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="6bcc9-107">Questa funzionalità è disponibile indipendentemente dal fatto che si invii l'intero ordine o solo righe selezionate.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="6bcc9-108">Per impostazione predefinita, la finestra di dialogo in cui è selezionata una modalità di consegna mostra tutte le modalità di consegna valide per la combinazione di un canale, un articolo e un indirizzo di consegna.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="6bcc9-109">Queste modalità di consegna sono definite nella pagina **Modi di consegna** in Headquarters (**Vendite e marketing \> Impostazioni \> Distribuzione \> Modi di consegna**).</span><span class="sxs-lookup"><span data-stu-id="6bcc9-109">These modes of delivery are defined on the **Modes of delivery** page in Headquarters (**Sales and marketing \> Setup \> Distribution \> Modes of delivery**).</span></span> <span data-ttu-id="6bcc9-110">I modi di consegna "non vettore", ad esempio **Esegui** o **Ritiro**, potrebbero essere disponibili per la selezione nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup**, might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="6bcc9-111">Tuttavia, è stata aggiunta una funzione che consente di nascondere le modalità di consegna non vettore nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="6bcc9-112">Per attivare questa funzionalità, nella pagina **Parametri di commercio**, nella scheda **Ordini cliente**, impostare l'opzione per **visualizzare solo le opzioni della modalità di consegna vettore per ordini di spedizione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-112">To turn on this feature, on the **Commerce parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes**.</span></span> <span data-ttu-id="6bcc9-113">Dopo aver attivato questa funzionalità ed eseguito i processi di distribuzione appropriati per sincronizzare le informazioni con il database del canale, le modalità di consegna non vettore non verranno visualizzate per la selezione durante il processo di creazione degli ordini di spedizione in POS.</span><span class="sxs-lookup"><span data-stu-id="6bcc9-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>
