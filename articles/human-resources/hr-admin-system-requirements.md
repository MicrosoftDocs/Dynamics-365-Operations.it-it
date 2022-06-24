---
title: Requisiti di sistema
description: Questo articolo elenca i requisiti di sistema per Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b07d14dfe0e6b53c9489c284520a24b97d9887fa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879339"
---
# <a name="system-requirements"></a>Requisiti di sistema

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo elenca i requisiti di sistema per Microsoft Dynamics 365 Human Resources. Vengono descritti inoltre i paesi e le regioni in cui Human Resources è disponibile, oltre a informazioni su lingue e localizzazione per i dati di Human Resources.

## <a name="supported-web-browsers"></a>Web browser supportati

Gli utenti possono accedere a Microsoft Dynamics 365 Human Resources usando uno qualsiasi dei seguenti browser web che girano sui sistemi operativi specificati: 

*   Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10
*   Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7
*   Google Chrome (ultima versione pubblicamente disponibile)
*   Apple Safari (ultima versione pubblicamente disponibile)

Per trovare l'ultima versione rilasciata di ogni Web browser, andare al sito Web del produttore software. 

## <a name="special-considerations"></a>Considerazioni speciali

* Per permettere a Task Recorder di catturare screenshot e includerli nei documenti Microsoft Word che vengono generati, è necessario installare un'estensione pre-release di Chrome
* L'editor flusso di lavoro viene avviato come un'applicazione ClickOnce. In Microsoft Edge e Internet Explorer (su una versione supportata di Microsoft Windows) supportano le applicazioni ClickOnce. L'applicazione ClickOnce dell'editor flusso di lavoro richiede un sistema operativo compatibile a 64 bit.
* Per visualizzare l'anteprima dei file PDF, si consiglia di utilizzare browser moderni come Microsoft Edge (versione pubblica più recente) su Windows 10 o Google Chrome (versione pubblica più recente) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10.

## <a name="network-requirements"></a>Requisiti di rete

* Human Resources è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore. Questa è la latenza da un client browser al data center Microsoft Azure che ospita Human Resources. Si consiglia di verificare la latenza di rete all'indirizzo [www.azurespeed.com](https://www.azurespeed.com "Test di latenza di Azure").
* I requisiti di larghezza di banda per Human Resources dipendono dallo scenario in uso. Gli scenari tipici richiedono una larghezza di banda di più di 50 kilobyte al secondo (KBps).
 
> [!WARNING]
> Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda. L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare. Per i clienti con problemi relativi ai requisiti di larghezza di banda, utilizzare una versione di prova di Human Resources.

## <a name="supported-microsoft-office-applications"></a>Applicazioni Microsoft Office supportate

* Per eseguire i componenti aggiuntivi di Microsoft Excel e Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac. Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Risolvere i problemi relativi all'integrazione di Office").
* Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versione successiva.

## <a name="regional-availability-languages-and-localization"></a>Disponibilità, lingue e localizzazione regionali

È possibile scaricare un file PDF di paesi, regioni e lingue supportati da Human Resources tramite la guida [International availability di Microsoft Dynamics 365](/dynamics365/get-started/availability). 

> [!NOTE]
> L'interfaccia utente è localizzata in altre lingue, tuttavia tutti i dati dell'utente sono memorizzati nella lingua in cui sono stati inseriti. È possibile creare e-mail e modelli in altre lingue, ma i dati come le informazioni sulla pianificazione sono disponibili solo in inglese al momento.

Gli sviluppatori interessati a creare personalizzazioni specifiche per paese o regione o per creare una soluzione per un paese o una regione non attualmente supportato da Microsoft possono consultare la pagina [Globalizzazione](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
