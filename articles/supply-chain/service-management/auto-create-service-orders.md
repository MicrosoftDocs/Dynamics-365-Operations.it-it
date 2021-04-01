---
title: Creare ordini di assistenza automaticamente
description: È possibile generare ordini di assistenza in base a un contratto di assistenza per il periodo di validità del contratto stesso.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9c1244cedff23df0350598a3cc876d39d4400b8e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232136"
---
# <a name="automatically-create-service-orders"></a><span data-ttu-id="f2079-103">Creare ordini di assistenza automaticamente</span><span class="sxs-lookup"><span data-stu-id="f2079-103">Automatically create service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f2079-104">È possibile generare ordini di assistenza in base a un contratto di assistenza per il periodo di validità del contratto stesso.</span><span class="sxs-lookup"><span data-stu-id="f2079-104">You can generate service orders that are based on a service agreement for the valid period of the service agreement.</span></span>

<span data-ttu-id="f2079-105">Tutti gli ordini di assistenza generati a partire da un contratto di assistenza sono collegati a tale contratto.</span><span class="sxs-lookup"><span data-stu-id="f2079-105">The service orders that you generate from a service agreement are all attached to the service agreement.</span></span>

<span data-ttu-id="f2079-106">Gli ordini di assistenza vengono generati automaticamente in base alle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="f2079-106">Service orders are generated automatically from the following settings:</span></span>

  - <span data-ttu-id="f2079-107">Impostazione dell'intervallo del contratto di assistenza nelle righe del contratto.</span><span class="sxs-lookup"><span data-stu-id="f2079-107">The service agreement interval that is set up in the service agreement lines.</span></span> <span data-ttu-id="f2079-108">L'intervallo del contratto di assistenza indica la frequenza con la quale vengono create le righe dell'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f2079-108">The service agreement interval indicates the frequency that service-order lines are created.</span></span> <span data-ttu-id="f2079-109">Per ulteriori informazioni, consultare [Intervalli assistenza](service-intervals.md).</span><span class="sxs-lookup"><span data-stu-id="f2079-109">For more information, see [Service intervals](service-intervals.md).</span></span>

  - <span data-ttu-id="f2079-110">Il periodo specificato per definire il periodo di assistenza nei campi **Dal** e **Al** del modulo **Crea ordini di assistenza**.</span><span class="sxs-lookup"><span data-stu-id="f2079-110">The period that you specify to define the service period in the **From date** and **To date** fields in the **Create service orders** form.</span></span> <span data-ttu-id="f2079-111">Per ulteriori informazioni, vedere [Creare ordini di assistenza automaticamente](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="f2079-111">For more information, see [Create service orders automatically](create-service-orders-automatically.md).</span></span>

  - <span data-ttu-id="f2079-112">L'opzione **Combina ordini di assistenza** nell'intestazione del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f2079-112">The **Combine service orders** option on the service agreement header.</span></span> <span data-ttu-id="f2079-113">Questa opzione indica se verranno generate righe di ordine di assistenza da un contratto di assistenza e consente di combinare gli ordini di assistenza in base al dipendente, all'attività di assistenza tecnica, all'oggetto assistenza o al contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f2079-113">This option defines whether service order lines generated from a service agreement, combines service orders according to employee, service task, service object, or service agreement.</span></span> <span data-ttu-id="f2079-114">Per ulteriori informazioni, vedere [Combina ordini di assistenza](combine-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="f2079-114">For more information, see [Combine service orders](combine-service-orders.md).</span></span>

  - <span data-ttu-id="f2079-115">L'opzione **Intervallo di tempo** nella riga del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f2079-115">The **Time window** option on the service agreement line.</span></span> <span data-ttu-id="f2079-116">L'intervallo di tempo definisce il periodo entro il quale una riga dell'ordine di assistenza può essere spostata in relazione alla relativa data calcolata.</span><span class="sxs-lookup"><span data-stu-id="f2079-116">The time window defines how far a service order line can move with regard to its calculated date.</span></span> <span data-ttu-id="f2079-117">Per ulteriori informazioni, vedere [Intervalli di tempo](time-windows.md)..</span><span class="sxs-lookup"><span data-stu-id="f2079-117">For more information, see [Time windows](time-windows.md).</span></span>


> [!NOTE]
> <P><span data-ttu-id="f2079-118">Se nel calendario selezionato nel modulo <STRONG>Parametri di gestione assistenza</STRONG> il giorno specificato per un ordine di assistenza non è aperto, verrà visualizzato un messaggio per segnalare che si è verificato un conflitto tra calendari.</span><span class="sxs-lookup"><span data-stu-id="f2079-118">If the day that is specified for a service order is not open in the calendar that you have selected in the <STRONG>Service management parameters</STRONG> form, a message will indicate that there is a calendar conflict.</span></span> <span data-ttu-id="f2079-119">È possibile ignorare il messaggio senza conseguenze. L'ordine di assistenza verrà creato anche se nel calendario il giorno è chiuso.</span><span class="sxs-lookup"><span data-stu-id="f2079-119">You can safely ignore the message; the service order will be created, even though the day is closed on the calendar.</span></span></P>

## <a name="example-1"></a><span data-ttu-id="f2079-120">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="f2079-120">Example 1</span></span>

<span data-ttu-id="f2079-121">La durata del contratto di assistenza è compresa tra il 1 gennaio 2012 e il 31 dicembre 2012.</span><span class="sxs-lookup"><span data-stu-id="f2079-121">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="f2079-122">Se il periodo di assistenza specificato nel modulo **Crea ordini di assistenza** è compreso tra il 1 novembre 2012 e il 1 febbraio 2013, gli ordini di assistenza verranno creati dal 1 novembre 2012 al 31 dicembre 2012.</span><span class="sxs-lookup"><span data-stu-id="f2079-122">If the service period that you specify in the **Create service orders** form is from November 1, 2012 until February 1, 2013, service orders are created from November 1, 2012 until December 31, 2012.</span></span>

## <a name="example-2"></a><span data-ttu-id="f2079-123">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="f2079-123">Example 2</span></span>

<span data-ttu-id="f2079-124">La durata del contratto di assistenza è compresa tra il 1 gennaio 2012 e il 31 dicembre 2012.</span><span class="sxs-lookup"><span data-stu-id="f2079-124">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="f2079-125">Al contratto di assistenza sono collegate due righe.</span><span class="sxs-lookup"><span data-stu-id="f2079-125">Two service agreement lines are attached to the service agreement.</span></span> <span data-ttu-id="f2079-126">Per la prima riga del contratto di assistenza la data di inizio è il 2 gennaio 2010 e la data di fine è il 1 marzo 2012.</span><span class="sxs-lookup"><span data-stu-id="f2079-126">The first service agreement line has a starting date on January 2, 2012 and an ending date on March 1, 2012.</span></span> <span data-ttu-id="f2079-127">Per la seconda riga la data di inizio è il 1 aprile 2012 e la data di fine è il 31 dicembre 2012.</span><span class="sxs-lookup"><span data-stu-id="f2079-127">The second service agreement line has a starting date on April 1, 2012 and an ending date on December 31, 2012.</span></span> <span data-ttu-id="f2079-128">Nel modulo **Crea ordini di assistenza** si specifica un periodo compreso tra il 1 ottobre 2012 e il 31 dicembre 2012.</span><span class="sxs-lookup"><span data-stu-id="f2079-128">You specify a period in the **Create service orders** form that is from October 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="f2079-129">Gli ordini di assistenza vengono pertanto creati solo per la seconda riga del contratto di assistenza, poiché la data di inizio e di fine della prima riga sono anteriori al periodo specificato per l'ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="f2079-129">Therefore, service orders are generated only for the second agreement line, because the starting date and ending date of the first agreement line are before the period that you specified for the service order.</span></span>

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]