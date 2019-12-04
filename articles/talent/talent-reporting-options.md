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
ms.openlocfilehash: ecbeb03b535f19131ddc6649d005702876bab65c
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772967"
---
# <a name="reporting-options-in-talent"></a>Opzioni di creazione dei report in Talent

[!include [banner](includes/banner.md)]

**Dettagli ambiente**

Questo problema è presente in tutti gli ambienti.

**Sintomo**

Il cliente desidera personalizzare i report di Microsoft Dynamics 365 Talent o creare nuovi report.

**Uscita**

L'utente non può personalizzare i report di Microsoft Power BI integrati.

**Soluzione**

- I dati di Core HR trasmessi a Common Data Service possono essere dichiarati tramite il connettore Power Apps Common Data Service in Power BI Desktop. Si noti che Common Data Service contiene un sottoinsieme dei dati di Core HR. Per ulteriori informazioni su Power BI e i dashboard, vedere [Creare report e dashboard Power BI con Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- La creazione di report elettronici (ER) è disponibile per alcuni report in Talent. Le personalizzazioni eseguite dai clienti possono essere eseguite tramite le opzioni della configurazione ER.
- I dati possono essere esportati in Microsoft Excel o Microsoft Word utilizzando varie entità di dati che Talent fornisce mediante l'integrazione di Microsoft Office.

**Soluzione a lungo termine**

Ulteriori opzioni di Power BI saranno disponibili e ulteriori dati ed entità saranno integrate in Common Data Service.
