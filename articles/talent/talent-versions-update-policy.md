---
title: Requisiti di sistema e criteri di aggiornamento di Talent
description: In questo argomento vengono illustrati i requisiti per Dynamics 365 for Talent. nonché i relativi criteri di aggiornamento.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
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
ms.openlocfilehash: ea8b7485b142245a359648a2a85d2a3e2a6d6629
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518379"
---
# <a name="talent-system-requirements-and-update-policy"></a>Requisiti di sistema e criteri di aggiornamento di Talent

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i requisiti di Microsoft Dynamics 365 for Talent, inclusi quelli per Attract, Onboard e Core HR. Vengono descritti inoltre i paesi e le regioni in cui Talent è disponibile, oltre a informazioni su lingue e localizzazione per i dati di Talent. Inoltre, questo argomento descrive i criteri di aggiornamento per Talent.

## <a name="supported-web-browsers"></a>Web browser supportati

L'applicazione Web Microsoft Dynamics 365 for Talent può essere eseguita in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati: 

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
> * Dynamics 365 for Talent è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore. Questa è la latenza da un client browser al data center Microsoft Azure che ospita Dynamics 365 for Talent. Si consiglia di verificare la latenza di rete all'indirizzo [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").
> * I requisiti di larghezza di banda per Dynamics 365 for Talent dipendono dallo scenario in uso. La maggior parte degli scenari tipici richiede una larghezza di banda superiore a 50 kilobyte al secondo (Kbps).
> 
> [!WARNING]
> Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare. Per i clienti con problemi relativi ai requisiti di larghezza di banda, utilizzare una versione di prova di Dynamics 365 for Talent.

## <a name="supported-microsoft-office-applications"></a>Applicazioni Microsoft Office supportate

* Per eseguire i componenti aggiuntivi di Microsoft Excel e Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac. Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Risoluzione dei problemi di integrazione di Office").
* Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versione successiva.

## <a name="regional-availability-languages-and-localization"></a>Disponibilità, lingue e localizzazione regionali

È possibile scaricare un file PDF di paesi, regioni e lingue supportati da Talent tramite la guida [International availability di Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> L'interfaccia utente è localizzata in altre lingue, tuttavia tutti i dati dell'utente sono memorizzati nella lingua in cui sono stati inseriti. È possibile creare e-mail e modelli in altre lingue, ma i dati come le informazioni sulla pianificazione sono disponibili solo in inglese al momento.

Gli sviluppatori interessati a creare personalizzazioni specifiche per paese o regione o per creare una soluzione per un paese o una regione non attualmente supportato da Microsoft possono consultare la pagina [Globalizzazione](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

## <a name="update-policy"></a>Criteri di aggiornamento

Microsoft Dynamics 365 for Talent è un'offerta cloud. Gli aggiornamenti di Dynamics 365 for Talent vengono forniti in modo continuo e applicati automaticamente da Microsoft.

Gli aggiornamenti vengono rilasciati a cadenza regolare e per tutti gli ambienti. Dynamics 365 for Talent è supportato secondo i [criteri relativi al ciclo di vita del supporto di Microsoft](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), che offrono linee guida coerenti e prevedibili in merito alla disponibilità del supporto per il prodotto.
