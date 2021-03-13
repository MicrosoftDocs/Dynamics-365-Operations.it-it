---
title: Opzioni di creazione report
description: In questo articolo viene descritto come risolvere il problema in cui un cliente intende personalizzare i report di Microsoft Dynamics 365 Human Resources o creare nuovi report.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 830c8c32128a8dfc1b009557afb272e48ae3a1ff
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113084"
---
# <a name="reporting-options"></a>Opzioni di creazione report

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**Dettagli ambiente**

Questo problema è presente in tutti gli ambienti.

**Sintomo**

Il cliente desidera personalizzare i report di Microsoft Dynamics 365 Human Resources o creare nuovi report.

**Uscita**

L'utente non può personalizzare i report di Microsoft Power BI integrati.

**Soluzione**

- I dati di Human Resources trasmessi a Dataverse possono essere dichiarati tramite il connettore Power Apps Dataverse in Power BI Desktop. Si noti che Dataverse contiene un sottoinsieme dei dati di Human Resources. Per ulteriori informazioni su Power BI e i dashboard, vedere [Creare report e dashboard Power BI con Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- La creazione di report elettronici (ER) è disponibile per alcuni report in Human Resources. Le personalizzazioni eseguite dai clienti possono essere eseguite tramite le opzioni della configurazione ER.
- I dati possono essere esportati in Microsoft Excel o Microsoft Word utilizzando varie entità di dati che Human Resources fornisce mediante l'integrazione di Microsoft Office.

**Soluzione a lungo termine**

Ulteriori opzioni di Power BI saranno disponibili e ulteriori dati ed entità saranno integrate in Dataverse.
