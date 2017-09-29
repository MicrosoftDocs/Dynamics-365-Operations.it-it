---
title: Ricevimento targa mista
description: "Questo argomento descrive come utilizzare Ricevimento targa mista per registrare e creare lavoro per più articoli con un dispositivo mobile."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0e785d71e7ae3c5f60d36d8b190001b5e356c626
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="mixed-license-plate-receiving"></a><span data-ttu-id="2e762-103">Ricevimento targa mista</span><span class="sxs-lookup"><span data-stu-id="2e762-103">Mixed license plate receiving</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2e762-104">Ricevimento targa mista consente di creare una targa costituita da più articoli prima di registrare e creare lavoro di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="2e762-104">Mixed license plate receiving allows you to build a license plate consisting of multiple items before you register and create put-away work.</span></span> 

<span data-ttu-id="2e762-105">Una targa costituita da più articoli non deve essere suddivisa alla banchina di entrata per registrare ogni articolo.</span><span class="sxs-lookup"><span data-stu-id="2e762-105">A license plate that consists of multiple items does not have to be split at the receiving dock for you to register each item.</span></span> 

<span data-ttu-id="2e762-106">Quando si utilizza un flusso correlato ad articoli per identificare le righe di documenti di origine, è possibile analizzare i codici a barre sul monitoraggio dell'articoloo.</span><span class="sxs-lookup"><span data-stu-id="2e762-106">When using an item-related flow to identify the source document lines, you can scan bar codes on the item control.</span></span> <span data-ttu-id="2e762-107">Se il codice a barre ha una quantità e un'unità di misura (UOM) configurati, l'articolo e la quantità verranno aggiunti automaticamente alla targa mista e si verrà reindirizzati alla schermata per analizzare un altro articolo.</span><span class="sxs-lookup"><span data-stu-id="2e762-107">If the bar code has a quantity and a unit of measure (UOM) configured on it, the item and quantity will automatically be added to the mixed license plate, and you will be returned to the screen to scan another item.</span></span> <span data-ttu-id="2e762-108">Ciò consente di analizzare rapidamente tutti gli articoli senza dover confermare a ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="2e762-108">This allows you to quickly scan all the items without having to make a confirmation at each step.</span></span> 

<span data-ttu-id="2e762-109">Nel flusso per Ricevimento targa mista, è possibile visualizzare l'elenco degli articoli già analizzati sulla targa e da qui modificare o correggere la quantità di un articolo.</span><span class="sxs-lookup"><span data-stu-id="2e762-109">In the flow for mixed license plate receiving, you can display the list of items that are already scanned to the license plate and from here you can modify or correct the quantity of an item.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="2e762-110">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="2e762-110">Where it applies</span></span>

<span data-ttu-id="2e762-111">Ricevimento targa mista è un flusso di ricevimento su dispositivo mobile che consente di registrare e creare lavoro per più righe/articoli contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2e762-111">Mixed license plate receiving is a mobile device receiving flow to register and create work for multiple lines/items at the same time.</span></span> <span data-ttu-id="2e762-112">Questa opzione è utile se si ricevono targhe in entrata con più articoli.</span><span class="sxs-lookup"><span data-stu-id="2e762-112">This is useful if you receive inbound license plates with multiple items.</span></span> 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a><span data-ttu-id="2e762-113">Istruzioni per la configurazione di Ricevimento targa mista</span><span class="sxs-lookup"><span data-stu-id="2e762-113">How to set up mixed license plate receiving</span></span>
<span data-ttu-id="2e762-114">Ricevimento targa mista viene configurato come voce di meno di un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="2e762-114">Mixed license plate receiving is set up as a mobile device menu item.</span></span>

<span data-ttu-id="2e762-115">È necessario creare una nuova voce di menu contenente la modalità di lavoro che non utilizza lavoro esistente e utilizza uno dei seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="2e762-115">You need to create a new menu item with mode work that does not use existing work and use one of the following methods:</span></span>

- <span data-ttu-id="2e762-116">Ricevimento targa mista</span><span class="sxs-lookup"><span data-stu-id="2e762-116">Mixed license plate receiving</span></span>
- <span data-ttu-id="2e762-117">Ricevimento e stoccaggio targa mista</span><span class="sxs-lookup"><span data-stu-id="2e762-117">Mixed license plate receiving and put away</span></span>

<span data-ttu-id="2e762-118">Le opzioni per identificare righe di documenti di origine sono articolo ordine fornitore, riga ordine fornitore, ordine di reso, articolo ordine di trasferimento e riga di ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="2e762-118">The options to identify the source document lines are purchase order item, purchase order line, return order, transfer order item, and transfer order line.</span></span> <span data-ttu-id="2e762-119">Queste opzioni possono modificare l'ordine di ricevimento per una singola targa.</span><span class="sxs-lookup"><span data-stu-id="2e762-119">These options can change the receiving order on a single license plate.</span></span> <span data-ttu-id="2e762-120">L'ultima opzione è per articolo caricato.</span><span class="sxs-lookup"><span data-stu-id="2e762-120">The last option is by load item.</span></span> <span data-ttu-id="2e762-121">È possibile aggiungere più articoli alla targa, ma non è possibile passare tra i diversi carichi.</span><span class="sxs-lookup"><span data-stu-id="2e762-121">You can add multiple items to a license plate, but you cannot switch between multiple loads.</span></span>

