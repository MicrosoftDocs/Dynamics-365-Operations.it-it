---
title: Requisiti di sistema di Talent
description: In questo argomento vengono illustrati i requisiti per Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 10/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 0bd7d7051dd01834f306e165af55d740192b99e0
ms.sourcegitcommit: caeb24027831efccbc316ff8e7f9e62b42010d65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2019
ms.locfileid: "2818481"
---
# <a name="talent-system-requirements"></a><span data-ttu-id="70a32-103">Requisiti di sistema di Talent</span><span class="sxs-lookup"><span data-stu-id="70a32-103">Talent system requirements</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="70a32-104">In questo argomento vengono descritti i requisiti di Microsoft Dynamics 365 Talent, inclusi quelli per Attract, Onboard e Core HR.</span><span class="sxs-lookup"><span data-stu-id="70a32-104">This topic describes requirements for Microsoft Dynamics 365 Talent, including Attract, Onboard, and Core HR.</span></span> <span data-ttu-id="70a32-105">Vengono descritti inoltre i paesi e le regioni in cui Talent è disponibile, oltre a informazioni su lingue e localizzazione per i dati di Talent.</span><span class="sxs-lookup"><span data-stu-id="70a32-105">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="70a32-106">Inoltre, questo argomento descrive i criteri di aggiornamento per Talent.</span><span class="sxs-lookup"><span data-stu-id="70a32-106">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="70a32-107">Web browser supportati</span><span class="sxs-lookup"><span data-stu-id="70a32-107">Supported web browsers</span></span>

<span data-ttu-id="70a32-108">Microsoft Dynamics 365 Talent può essere eseguita in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:</span><span class="sxs-lookup"><span data-stu-id="70a32-108">Microsoft Dynamics 365 Talent can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="70a32-109">Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10</span><span class="sxs-lookup"><span data-stu-id="70a32-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="70a32-110">Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="70a32-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="70a32-111">Google Chrome (ultima versione pubblicamente disponibile)</span><span class="sxs-lookup"><span data-stu-id="70a32-111">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="70a32-112">Apple Safari (ultima versione pubblicamente disponibile)</span><span class="sxs-lookup"><span data-stu-id="70a32-112">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="70a32-113">Per trovare l'ultima versione rilasciata di ogni Web browser, andare al sito Web del produttore software.</span><span class="sxs-lookup"><span data-stu-id="70a32-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="70a32-114">Per acquisire le immagini generate da Registrazione attività e includerle nei documenti di Microsoft Word, è necessario che sia installata un'estensione Chrome.</span><span class="sxs-lookup"><span data-stu-id="70a32-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="70a32-115">L'editor flusso di lavoro viene avviato come un'applicazione ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="70a32-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="70a32-116">In Microsoft Edge e Internet Explorer (su una versione supportata di Microsoft Windows) supportano le applicazioni ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="70a32-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="70a32-117">L'applicazione ClickOnce dell'editor flusso di lavoro richiede un sistema operativo compatibile a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="70a32-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="70a32-118">Per visualizzare l'anteprima dei file PDF, si consiglia di utilizzare browser moderni come Microsoft Edge (versione pubblica più recente) su Windows 10 o Google Chrome (versione pubblica più recente) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="70a32-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="70a32-119">Requisiti di rete</span><span class="sxs-lookup"><span data-stu-id="70a32-119">Network requirements</span></span>
> * <span data-ttu-id="70a32-120">Dynamics 365 Talent è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore.</span><span class="sxs-lookup"><span data-stu-id="70a32-120">Dynamics 365 Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="70a32-121">Questa è la latenza da un client browser al data center Microsoft Azure che ospita Talent.</span><span class="sxs-lookup"><span data-stu-id="70a32-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Talent.</span></span> <span data-ttu-id="70a32-122">Si consiglia di verificare la latenza di rete all'indirizzo [www.azurespeed.com](https://www.azurespeed.com "Test di latenza di Azure").</span><span class="sxs-lookup"><span data-stu-id="70a32-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="70a32-123">I requisiti di larghezza di banda per Talent dipendono dallo scenario in uso.</span><span class="sxs-lookup"><span data-stu-id="70a32-123">Bandwidth requirements for Talent depend on your scenario.</span></span> <span data-ttu-id="70a32-124">La maggior parte degli scenari tipici richiede una larghezza di banda superiore a 50 kilobyte al secondo (Kbps).</span><span class="sxs-lookup"><span data-stu-id="70a32-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="70a32-125">Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="70a32-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="70a32-126">L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare.</span><span class="sxs-lookup"><span data-stu-id="70a32-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="70a32-127">Per i clienti con problemi relativi ai requisiti di larghezza di banda, utilizzare una versione di prova di Talent.</span><span class="sxs-lookup"><span data-stu-id="70a32-127">For customers who are concerned about bandwidth requirements, use a trial version of Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="70a32-128">Applicazioni Microsoft Office supportate</span><span class="sxs-lookup"><span data-stu-id="70a32-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="70a32-129">Per eseguire i componenti aggiuntivi di Microsoft Excel e Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac.</span><span class="sxs-lookup"><span data-stu-id="70a32-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="70a32-130">Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Risolvere i problemi relativi all'integrazione di Office").</span><span class="sxs-lookup"><span data-stu-id="70a32-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="70a32-131">Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="70a32-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="70a32-132">Disponibilità, lingue e localizzazione regionali</span><span class="sxs-lookup"><span data-stu-id="70a32-132">Regional availability, languages, and localization</span></span>

<span data-ttu-id="70a32-133">È possibile scaricare un file PDF di paesi, regioni e lingue supportati da Talent tramite la guida [International availability di Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span><span class="sxs-lookup"><span data-stu-id="70a32-133">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="70a32-134">L'interfaccia utente è localizzata in altre lingue, tuttavia tutti i dati dell'utente sono memorizzati nella lingua in cui sono stati inseriti.</span><span class="sxs-lookup"><span data-stu-id="70a32-134">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="70a32-135">È possibile creare e-mail e modelli in altre lingue, ma i dati come le informazioni sulla pianificazione sono disponibili solo in inglese al momento.</span><span class="sxs-lookup"><span data-stu-id="70a32-135">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="70a32-136">Gli sviluppatori interessati a creare personalizzazioni specifiche per paese o regione o per creare una soluzione per un paese o una regione non attualmente supportato da Microsoft possono consultare la pagina [Globalizzazione](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="70a32-136">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

