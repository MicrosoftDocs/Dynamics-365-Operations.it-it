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
ms.openlocfilehash: 509827d5736887f56e7754a0760af7dea76277f7
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006057"
---
# <a name="talent-system-requirements"></a>Requisiti di sistema di Talent

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i requisiti di Microsoft Dynamics 365 Talent, inclusi quelli per Attract e Onboard. Vengono descritti inoltre i paesi e le regioni in cui Talent è disponibile, oltre a informazioni su lingue e localizzazione per i dati di Talent. Inoltre, questo argomento descrive i criteri di aggiornamento per Talent.

## <a name="supported-web-browsers"></a>Web browser supportati

Microsoft Dynamics 365 Talent può essere eseguita in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati: 

*   Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
*   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
*   Google Chrome (ultima versione pubblicamente disponibile)
*   Apple Safari (ultima versione pubblicamente disponibile)

Per trovare l'ultima versione rilasciata di ogni Web browser, andare al sito Web del produttore software. 

> [!NOTE]
> * Per acquisire le immagini generate da Registrazione attività e includerle nei documenti di Microsoft Word, è necessario che sia installata un'estensione Chrome. 
> * L'editor flusso di lavoro viene avviato come un'applicazione ClickOnce. In Microsoft Edge e Internet Explorer (su una versione supportata di Microsoft Windows) supportano le applicazioni ClickOnce. L'applicazione ClickOnce dell'editor flusso di lavoro richiede un sistema operativo compatibile a 64 bit.
> * Per visualizzare l'anteprima dei file PDF, si consiglia di utilizzare browser moderni come Microsoft Edge (versione pubblica più recente) su Windows 10 o Google Chrome (versione pubblica più recente) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10.
>   Requisiti di rete
> * Dynamics 365 Talent è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore. Questa è la latenza da un client browser al data center Microsoft Azure che ospita Talent. Si consiglia di verificare la latenza di rete all'indirizzo [www.azurespeed.com](https://www.azurespeed.com "Test di latenza di Azure").
> * I requisiti di larghezza di banda per Talent dipendono dallo scenario in uso. La maggior parte degli scenari tipici richiede una larghezza di banda superiore a 50 kilobyte al secondo (Kbps).
> 
> [!WARNING]
> Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare. Per i clienti con problemi relativi ai requisiti di larghezza di banda, utilizzare una versione di prova di Talent.

## <a name="supported-microsoft-office-applications"></a>Applicazioni Microsoft Office supportate

* Per eseguire i componenti aggiuntivi di Microsoft Excel e Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac. Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Risolvere i problemi relativi all'integrazione di Office").
* Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versione successiva.

## <a name="regional-availability-languages-and-localization"></a>Disponibilità, lingue e localizzazione regionali

È possibile scaricare un file PDF di paesi, regioni e lingue supportati da Talent tramite la guida [International availability di Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> L'interfaccia utente è localizzata in altre lingue, tuttavia tutti i dati dell'utente sono memorizzati nella lingua in cui sono stati inseriti. È possibile creare e-mail e modelli in altre lingue, ma i dati come le informazioni sulla pianificazione sono disponibili solo in inglese al momento.

Gli sviluppatori interessati a creare personalizzazioni specifiche per paese o regione o per creare una soluzione per un paese o una regione non attualmente supportato da Microsoft possono consultare la pagina [Globalizzazione](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

