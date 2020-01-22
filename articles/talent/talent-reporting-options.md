---
title: Opzioni per report in Talent
description: In questo argomento viene descritto come risolvere il problema in cui un cliente intende personalizzare i report di Microsoft Dynamics 365 Talent o creare nuovi report.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 05d4a2c4314b40042ae45b4f653554bad09be4fa
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897950"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="02a47-103">Opzioni di creazione dei report in Talent</span><span class="sxs-lookup"><span data-stu-id="02a47-103">Reporting options in Talent</span></span>

<span data-ttu-id="02a47-104">**Dettagli ambiente**</span><span class="sxs-lookup"><span data-stu-id="02a47-104">**Environment details**</span></span>

<span data-ttu-id="02a47-105">Questo problema è presente in tutti gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="02a47-105">This issue applies to all environments.</span></span>

<span data-ttu-id="02a47-106">**Sintomo**</span><span class="sxs-lookup"><span data-stu-id="02a47-106">**Symptom**</span></span>

<span data-ttu-id="02a47-107">Il cliente desidera personalizzare i report di Microsoft Dynamics 365 Talent o creare nuovi report.</span><span class="sxs-lookup"><span data-stu-id="02a47-107">The customer wants to customize Microsoft Dynamics 365 Talent reports or create new reports.</span></span>

<span data-ttu-id="02a47-108">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="02a47-108">**Issue**</span></span>

<span data-ttu-id="02a47-109">L'utente non può personalizzare i report di Microsoft Power BI integrati.</span><span class="sxs-lookup"><span data-stu-id="02a47-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="02a47-110">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="02a47-110">**Solution**</span></span>

- <span data-ttu-id="02a47-111">I dati di Core HR trasmessi a Common Data Service possono essere dichiarati tramite il connettore Power Apps Common Data Service in Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="02a47-111">The Core HR data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="02a47-112">Si noti che Common Data Service contiene un sottoinsieme dei dati di Core HR.</span><span class="sxs-lookup"><span data-stu-id="02a47-112">Note that Common Data Service contains a subset of Core HR data.</span></span> <span data-ttu-id="02a47-113">Per ulteriori informazioni su Power BI e i dashboard, vedere [Creare report e dashboard Power BI con Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="02a47-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="02a47-114">La creazione di report elettronici (ER) è disponibile per alcuni report in Talent.</span><span class="sxs-lookup"><span data-stu-id="02a47-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="02a47-115">Le personalizzazioni eseguite dai clienti possono essere eseguite tramite le opzioni della configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="02a47-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="02a47-116">I dati possono essere esportati in Microsoft Excel o Microsoft Word utilizzando varie entità di dati che Talent fornisce mediante l'integrazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="02a47-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="02a47-117">**Soluzione a lungo termine**</span><span class="sxs-lookup"><span data-stu-id="02a47-117">**Long-term solution**</span></span>

<span data-ttu-id="02a47-118">Ulteriori opzioni di Power BI saranno disponibili e ulteriori dati ed entità saranno integrate in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="02a47-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
