---
title: Monitorare e gestire l'Intelligence IoT
description: Questo argomento spiega come monitorare e gestire l'Intelligence IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 05aee9865dc90c97e026d5c05fa2032fc0625f7a
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597410"
---
# <a name="monitor-and-manage-iot-intelligence"></a><span data-ttu-id="51b4b-103">Monitorare e gestire l'Intelligence IoT</span><span class="sxs-lookup"><span data-stu-id="51b4b-103">Monitor and manage IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51b4b-104">Questo argomento spiega come monitorare e gestire l'Intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="51b4b-104">This topic explains how to monitor and manage IoT Intelligence.</span></span>

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a><span data-ttu-id="51b4b-105">Monitorare gli scenari in Microsoft Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="51b4b-105">Monitor scenarios in Microsoft Dynamics 365 Supply Chain Management</span></span>

<span data-ttu-id="51b4b-106">Puoi monitorare l'elaborazione Intelligence IoT da diverse posizioni:</span><span class="sxs-lookup"><span data-stu-id="51b4b-106">You can monitor IoT Intelligence processing from several places:</span></span>

+ <span data-ttu-id="51b4b-107">**Moduli \> Controllo produzione \> Richieste di informazioni e report \> Intelligence IoT \> Notifiche**: visualizza l'elenco di notifiche non risolte.</span><span class="sxs-lookup"><span data-stu-id="51b4b-107">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Notifications** – View the list of unresolved notifications.</span></span>
+ <span data-ttu-id="51b4b-108">**Moduli \> Controllo produzione \> Richieste di informazioni e report \> Intelligence IoT \> Notifiche chiuse**: visualizza l'elenco di notifiche risolte o ignorate.</span><span class="sxs-lookup"><span data-stu-id="51b4b-108">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Closed notifications** – View the list of notifications that have been resolved or dismissed.</span></span>
+ <span data-ttu-id="51b4b-109">**Moduli \> Controllo produzione \> Richieste di informazioni e report \> Intelligence IoT \> Metrica chiave**: visualizza la metrica chiave per i grafici delle serie temporali **Stato risorsa**.</span><span class="sxs-lookup"><span data-stu-id="51b4b-109">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Metric keys** – View the metric keys for the **Resource Status** times series charts.</span></span>
+ <span data-ttu-id="51b4b-110">**Moduli \> Controllo produzione \> Esecuzione produzione \> Stato risorsa**: traccia le metriche specifiche utilizzando la finestra di dialogo **Configura**.</span><span class="sxs-lookup"><span data-stu-id="51b4b-110">**Modules \> Production control \> Manufacturing execution \> Resource status** – Track specific metrics by using the **Configure** dialog box.</span></span> <span data-ttu-id="51b4b-111">Se uno scenario rileva un'eccezione, una notifica mostra i dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="51b4b-111">If a scenario detects an exception, a notification shows the details of the exception.</span></span>
+ <span data-ttu-id="51b4b-112">**Aree di lavoro \> Gestione area di produzione \> Notifiche**: visualizza l'elenco delle notifiche non risolte.</span><span class="sxs-lookup"><span data-stu-id="51b4b-112">**Workspaces \> Production floor management \> Notifications** – View the list of unresolved notifications.</span></span>

## <a name="modify-a-running-iot-intelligence-scenario"></a><span data-ttu-id="51b4b-113">Modifica uno scenario Intelligence IoT in esecuzione</span><span class="sxs-lookup"><span data-stu-id="51b4b-113">Modify a running IoT Intelligence scenario</span></span>

<span data-ttu-id="51b4b-114">Quando uno scenario è in esecuzione, puoi apportare queste modifiche:</span><span class="sxs-lookup"><span data-stu-id="51b4b-114">When a scenario is running, you can make these changes:</span></span>

+ <span data-ttu-id="51b4b-115">Aggiungi nuove definizioni dello schema del sensore.</span><span class="sxs-lookup"><span data-stu-id="51b4b-115">Add new sensor schema definitions.</span></span>
+ <span data-ttu-id="51b4b-116">Seleziona nuovi valori dei dati del segnale.</span><span class="sxs-lookup"><span data-stu-id="51b4b-116">Select new signal data values.</span></span>
+ <span data-ttu-id="51b4b-117">Annulla la selezione dei valori dei dati del segnale esistenti.</span><span class="sxs-lookup"><span data-stu-id="51b4b-117">Cancel the selection of existing signal data values.</span></span>
+ <span data-ttu-id="51b4b-118">Aggiungi e mappa nuovi valori dei dati del segnale.</span><span class="sxs-lookup"><span data-stu-id="51b4b-118">Add and map new signal data values.</span></span>
+ <span data-ttu-id="51b4b-119">Aggiorna valori soglia.</span><span class="sxs-lookup"><span data-stu-id="51b4b-119">Update threshold values.</span></span>

<span data-ttu-id="51b4b-120">Quando uno scenario è in esecuzione, queste modifiche sono proibite:</span><span class="sxs-lookup"><span data-stu-id="51b4b-120">When a scenario is running, these changes are prohibited:</span></span>

+ <span data-ttu-id="51b4b-121">Elimina o modifica le definizioni dello schema attualmente utilizzate da uno scenario abilitato.</span><span class="sxs-lookup"><span data-stu-id="51b4b-121">Delete or modify any schema definitions that are currently consumed by an enabled scenario.</span></span>
+ <span data-ttu-id="51b4b-122">Modifica i percorsi dello schema selezionati dello scenario abilitato.</span><span class="sxs-lookup"><span data-stu-id="51b4b-122">Change the enabled scenario's selected schema paths.</span></span>

## <a name="simulation-options"></a><span data-ttu-id="51b4b-123">Opzioni di simulazione</span><span class="sxs-lookup"><span data-stu-id="51b4b-123">Simulation options</span></span>

<span data-ttu-id="51b4b-124">Puoi simulare i segnali di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="51b4b-124">You can simulate factory machine signals.</span></span> <span data-ttu-id="51b4b-125">Per ulteriori informazioni, vedi questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="51b4b-125">For more information, see these topics:</span></span>

+ [<span data-ttu-id="51b4b-126">Connettere IoT DevKit AZ3166 all'hub IoT di Azure</span><span class="sxs-lookup"><span data-stu-id="51b4b-126">Connect IoT DevKit AZ3166 to Azure IoT Hub</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [<span data-ttu-id="51b4b-127">Connettere il simulatore online di Raspberry Pi all'hub IoT di Azure (Node.js)</span><span class="sxs-lookup"><span data-stu-id="51b4b-127">Connect Raspberry Pi online simulator to Azure IoT Hub (Node.js)</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [<span data-ttu-id="51b4b-128">Panoramica dell'acceleratore di soluzione Simulazione dispositivi</span><span class="sxs-lookup"><span data-stu-id="51b4b-128">Device Simulation solution accelerator overview</span></span>](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)
