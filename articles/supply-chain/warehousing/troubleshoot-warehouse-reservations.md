---
title: Risolvere i problemi delle prenotazioni in Gestione magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le prenotazioni dei magazzini in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828108"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="5e710-103">Risolvere i problemi delle prenotazioni in Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="5e710-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e710-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le prenotazioni dei magazzini in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5e710-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="5e710-105">Per argomenti relativi alle registrazioni di batch e numeri di serie, vedi [Risolvere i problemi relativi a gerarchie di prenotazione batch e numeri di serie di magazzino](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="5e710-105">For topics that are related to batch and serial number registrations, see [Troubleshoot warehouse batch and serial reservation hierarchies](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="5e710-106">Viene visualizzato il seguente messaggio di errore "Impossibile rimuovere le prenotazioni perché è presente lavoro creato che si basa sulle prenotazioni".</span><span class="sxs-lookup"><span data-stu-id="5e710-106">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="5e710-107">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5e710-107">Issue description</span></span>

<span data-ttu-id="5e710-108">Non è possibile annullare la prenotazione dell'inventario su una riga di vendita, perché c'è lavoro aperto per la riga.</span><span class="sxs-lookup"><span data-stu-id="5e710-108">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5e710-109">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5e710-109">Issue resolution</span></span>

<span data-ttu-id="5e710-110">Verificare se esiste un lavoro di gruppo di imballaggio aperto per portare l'articolo da una stazione di imballaggio a un'altra ubicazione (ad esempio *Portellone*).</span><span class="sxs-lookup"><span data-stu-id="5e710-110">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="5e710-111">Rivedere i record delle pagine **Registro della cronologia di creazione del lavoro** e **Dettagli del lavoro** per determinare cosa sta fisicamente prenotando l'inventario, quindi completare o eliminare il lavoro per liberare la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="5e710-111">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="5e710-112">Viene visualizzato il seguente messaggio di errore: "Impossibile aggiornare la quantità inventario -%1 a causa di transazioni di magazzino insufficienti per l'articolo %2."</span><span class="sxs-lookup"><span data-stu-id="5e710-112">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="5e710-113">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5e710-113">Issue description</span></span>

<span data-ttu-id="5e710-114">Questo problema può verificarsi se il sistema non è in grado di aggiornare una quantità di inventario perché non ci sono sufficienti transazioni di inventario con le dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="5e710-114">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="5e710-115">Di seguito è riportato il messaggio di errore completo:</span><span class="sxs-lookup"><span data-stu-id="5e710-115">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="5e710-116">Impossibile aggiornare la quantità di inventario -%1 perché non ci sono sufficienti transazioni di inventario per l'articolo %2 con le dimensioni specificate=%3, Colore=%4, Aggiunte=%5, Sito=%6, Magazzino=%7, Ubicazione=%8, Stato inventario=Disponibile, Targa=%9, Numero batch=%10 per ID riferimento %11 in ID lotto %12.</span><span class="sxs-lookup"><span data-stu-id="5e710-116">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5e710-117">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5e710-117">Issue resolution</span></span>

<span data-ttu-id="5e710-118">Assicurarsi che nessuna transazione di magazzino stia prenotando fisicamente la quantità.</span><span class="sxs-lookup"><span data-stu-id="5e710-118">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="5e710-119">Ad esempio, queste transazioni potrebbero aprire ordini di controllo qualità, record di blocco dell'inventario o ordini di uscita.</span><span class="sxs-lookup"><span data-stu-id="5e710-119">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="5e710-120">Viene visualizzato il seguente messaggio di errore: "Impossibile prenotare le scorte fisiche perché nell'inventario sono disponibili solo 0,00".</span><span class="sxs-lookup"><span data-stu-id="5e710-120">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="5e710-121">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5e710-121">Issue description</span></span>

<span data-ttu-id="5e710-122">Questo problema può verificarsi se il sistema non è in grado di aggiornare una quantità di inventario perché non ci sono sufficienti transazioni di inventario con le dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="5e710-122">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="5e710-123">Di seguito è riportato il messaggio di errore completo:</span><span class="sxs-lookup"><span data-stu-id="5e710-123">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="5e710-124">Sito scorte fisiche=%1, Magazzino=%2, Stato inventario=Disponibile, Numero batch=%3, Proprietario=%4: %5 non può essere prenotato perché solo 0,00 sono disponibili nell'inventario.</span><span class="sxs-lookup"><span data-stu-id="5e710-124">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5e710-125">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5e710-125">Issue resolution</span></span>

<span data-ttu-id="5e710-126">Questo problema è probabilmente causato da un lavoro aperto.</span><span class="sxs-lookup"><span data-stu-id="5e710-126">This issue is probably caused by open work.</span></span> <span data-ttu-id="5e710-127">Completare il lavoro o ricevere senza crearlo.</span><span class="sxs-lookup"><span data-stu-id="5e710-127">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="5e710-128">Assicurarsi che nessuna transazione di magazzino stia prenotando fisicamente la quantità.</span><span class="sxs-lookup"><span data-stu-id="5e710-128">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="5e710-129">Ad esempio, queste transazioni potrebbero essere ordini di controllo qualità aperti, record di blocco dell'inventario o ordini di uscita.</span><span class="sxs-lookup"><span data-stu-id="5e710-129">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
