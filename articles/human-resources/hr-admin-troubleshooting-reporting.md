---
title: Opzioni di creazione report
description: In questo articolo viene descritto come risolvere il problema in cui un cliente intende personalizzare i report di Microsoft Dynamics 365 Human Resources o creare nuovi report.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9ee6dba5e37877f1c0b3b9df8306b3194ea2f3e4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009615"
---
# <a name="reporting-options"></a><span data-ttu-id="31a60-103">Opzioni di creazione report</span><span class="sxs-lookup"><span data-stu-id="31a60-103">Reporting options</span></span>

<span data-ttu-id="31a60-104">**Dettagli ambiente**</span><span class="sxs-lookup"><span data-stu-id="31a60-104">**Environment details**</span></span>

<span data-ttu-id="31a60-105">Questo problema è presente in tutti gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="31a60-105">This issue applies to all environments.</span></span>

<span data-ttu-id="31a60-106">**Sintomo**</span><span class="sxs-lookup"><span data-stu-id="31a60-106">**Symptom**</span></span>

<span data-ttu-id="31a60-107">Il cliente desidera personalizzare i report di Microsoft Dynamics 365 Human Resources o creare nuovi report.</span><span class="sxs-lookup"><span data-stu-id="31a60-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="31a60-108">**Uscita**</span><span class="sxs-lookup"><span data-stu-id="31a60-108">**Issue**</span></span>

<span data-ttu-id="31a60-109">L'utente non può personalizzare i report di Microsoft Power BI integrati.</span><span class="sxs-lookup"><span data-stu-id="31a60-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="31a60-110">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="31a60-110">**Solution**</span></span>

- <span data-ttu-id="31a60-111">I dati di Human Resources trasmessi a Common Data Service possono essere dichiarati tramite il connettore Power Apps Common Data Service in Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="31a60-111">The Human Resources data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="31a60-112">Si noti che Common Data Service contiene un sottoinsieme dei dati di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="31a60-112">Note that Common Data Service contains a subset of Human Resources data.</span></span> <span data-ttu-id="31a60-113">Per ulteriori informazioni su Power BI e i dashboard, vedere [Creare report e dashboard Power BI con Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="31a60-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="31a60-114">La creazione di report elettronici (ER) è disponibile per alcuni report in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="31a60-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="31a60-115">Le personalizzazioni eseguite dai clienti possono essere eseguite tramite le opzioni della configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="31a60-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="31a60-116">I dati possono essere esportati in Microsoft Excel o Microsoft Word utilizzando varie entità di dati che Human Resources fornisce mediante l'integrazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="31a60-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="31a60-117">**Soluzione a lungo termine**</span><span class="sxs-lookup"><span data-stu-id="31a60-117">**Long-term solution**</span></span>

<span data-ttu-id="31a60-118">Ulteriori opzioni di Power BI saranno disponibili e ulteriori dati ed entità saranno integrate in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="31a60-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
