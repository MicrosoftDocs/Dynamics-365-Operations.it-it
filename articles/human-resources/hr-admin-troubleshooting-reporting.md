---
title: Opzioni di creazione report
description: In questo articolo viene descritto come risolvere il problema in cui un cliente intende personalizzare i report di Microsoft Dynamics 365 Human Resources o creare nuovi report.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 2d0fc6b2d4af6ad021943717645bfff7a27797a8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803899"
---
# <a name="reporting-options"></a>Opzioni di creazione report

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]