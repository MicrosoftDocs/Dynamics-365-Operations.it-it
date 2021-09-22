---
title: Messaggistica elettronica
description: In questo argomento vengono fornite informazioni sulla messaggistica elettronica in Microsoft Dynamics 365 Finance.
author: liza-golub
ms.date: 08/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 16b0e0fa74109f1c63ed47606bebe2fefc604fc5
ms.sourcegitcommit: efcb853a68a77037cca23582d9f6f96ea573727a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7478726"
---
# <a name="electronic-messaging"></a>Messaggi elettronici

[!include [banner](../includes/banner.md)]

Questo argomento fornisce una panoramica e le informazioni di configurazione per la funzionalità **Messaggi elettronici** (EM).

Recentemente, governi e autorità legislative di vari paesi hanno implementato requisiti di reporting per le società registrate in tali paesi. Lo scopo dei requisiti è di consentire di ottenere i dati di tali società in formato elettronico, direttamente dai sistemi in cui sono stati valutati, archiviati ed elaborati.

La funzionalità EM in Microsoft Dynamics 365 Finance supporta vari processi per l'interoperazione elettronica tra Finance e i sistemi che governi e autorità legislative forniscono per la creazione di report, la presentazione e la ricezione di informazioni ufficiali.

La funzionalità EM è integrata con il modulo **Creazione di report elettronici** (ER). È possibile configurare formati ER per messaggi elettronici. Per ulteriori informazioni, vedere [Creazione di report elettronici (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

## <a name="basic-concepts-for-em-functionality"></a>Concetti di base per la funzionalità EM

La funzionalità EM si basa sulle seguenti entità:

- **Messaggio elettronico** - Report o dichiarazione che dovrebbe essere riportata o trasmessa internamente, come un report che viene inviato a un ufficio delle imposte.
- **Elementi del messaggio elettronico** - Record da includere nel messaggio incluso nel report.
- **Elaborazione messaggio elettronico** - Catena di azioni che devono essere eseguite per raccogliere i dati richiesti, generare report, archiviare dati nell'archiviazione BLOB di Azure, trasmettere report al di fuori del sistema, ricevere risposte esternamente al sistema e, in base alle informazioni ricevute, aggiornare il database. Le azioni nella catena possono essere associate o meno.

L'illustrazione seguente mostra il flusso dei dati per EM.

![Flusso di dati della messaggistica elettronica.](media/electronic-messaging-data-flow.png)

## <a name="scenarios-supported-by-the-em-functionality"></a>Scenari supportati dalla funzionalità EM

La funzionalità EM supporta i seguenti scenari:

- Creare messaggi e generare report manualmente basati su formati ER di esportazione associati di vari tipi. Questi tipi includono Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, testo e Microsoft Word.
- Creare ed elaborare automaticamente messaggi basati sulle informazioni richieste e ricevute da un'autorità tramite un formato ER di importazione associato.
- Raccogliere ed elaborare informazioni da un'origine dati come elementi del messaggio. L'origine dati è una tabella di Finance.
- Archiviare ulteriori informazioni e valutare diversi valori chiamando classi eseguibili definite in modo specifico in relazione a messaggi o elementi del messaggio.
- Aggregare informazioni raccolte in elementi del messaggio, dividere quelle informazioni per messaggio e generare report in formati ER di esportazione associati.
- Trasmettere i report generati a un servizio Web utilizzando informazioni di protezione che vengono archiviate in Azure Key Vault.
- Ricevere una risposta da un servizio Web, interpretare la risposta e aggiornare dati in Finance come appropriato.
- Archiviare ed esaminare tutti i report generati.
- Archiviare ed esaminare tutte le informazioni di registro correlate ad azioni eseguite per un messaggio o un elemento del messaggio.
- Controllare l'elaborazione mediante vari stati del messaggio e stati di elementi del messaggio.

## <a name="security-privileges"></a>Privilegi di sicurezza

I seguenti privilegi di sicurezza sono disponibili per i messaggi elettronici.

| Privilegio di sicurezza           | Livello di accesso | Associazione |
|------------------------------|--------------|-------------|
| Gestisci messaggi elettronici | Questo privilegio fornisce l'accesso completo alle funzionalità EM. Se si dispone di questo privilegio, è possibile impostare la messaggistica elettronica ed eseguire tutta l'elaborazione. | Questo privilegio è incluso nei diritti di sicurezza **Gestire le transazioni IVA**. Tali diritti sono inclusi nel ruolo di sicurezza **Contabile**. |
| Visualizza messaggi elettronici     | Questo privilegio fornisce l'accesso di sola lettura alle funzionalità EM. Se si dispone di questo privilegio, è possibile visualizzare i messaggi e le impostazioni della messaggistica elettronica. Tuttavia, non è possibile configurare o eseguire alcun elemento. | Questo privilegio è incluso nei diritti di sicurezza **Richiedere informazioni sullo stato delle transazioni IVA**. Tali diritti sono inclusi nei seguenti ruoli di sicurezza:<ul><li>Responsabile riscossioni</li><li>Impiegato contabilità clienti</li><li>Responsabile contabilità clienti</li><li>Fiscalista</li><li>Contabile</li><li>Direttore amministrativo</li><li>Supervisore contabile</li><li>Manager vendite</li><li>Addetto contabilità fornitori</li></ul> |
| Gestisci messaggi elettronici  | Questo privilegio fornisce solo l'accesso alle pagine **Messaggi elettronici** ed **Elementi del messaggio elettronico**. Se si dispone di questo privilegio, è possibile eseguire tutte le operazioni di elaborazione richiamate da quelle pagine. | Questo privilegio è incluso nei diritti di sicurezza **Eseguire operazioni con i messaggi elettronici**. Tali diritti sono inclusi nel ruolo di sicurezza **Operatore messaggi elettronici**. |

## <a name="country-specific-regulatory-features-supported-by-the-em-functionality"></a>Funzionalità normative specifiche del paese supportate dalla funzionalità EM

La tabella seguente fornisce informazioni su alcune funzioni normative specifiche del paese supportate dalla funzionalità EM.

| Paese     | Nome funzionalità | Registrazione demo delle funzionalità |
|-------------|--------------|------------------------|
| Spagna       | [Fornitura immediata di informazioni sull'IVA (Suministro Inmediato de Información del IVA, SII)](../localizations/emea-esp-sii.md) | |
| Ungheria     | [Sistema di fatturazione online](../localizations/emea-hun-online-invoicing.md) | |
| Regno Unito | [Digitalizzare le imposte (MTD) - Modifiche all'invio della dichiarazione IVA](../localizations/emea-gbr-mtd-vat-integration.md) | [Finance and Operations: Ricevuta fiscale digitale nel Regno Unito - Dichiarazione IVA in Dynamics 365](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-uk-digital-tax-vat-declaration-in-dynamics-365) |
| Lituania   | [Report i.SAF](../localizations/emea-ltu-isaf.md) | |
| Polonia      | [Dichiarazione IVA con registri (JPK_V7M, VDEK)](../localizations/emea-pol-vdek.md) | [Dynamics 365 Finance: Registri di verifica IVA SAF/JPK](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-finance-saf-jpk-vat-audit-registers-june-4-2020) |
| Paesi Bassi | [Dichiarazione IVA per i Paesi Bassi](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| Repubblica Ceca | [Dichiarazione IVA](../localizations/emea-cze-vat-declaration-tax-declaration-model.md) | |
| Brasile      | [SPED-Reinf](../localizations/latam-bra-sped-reinf-overview.md) | |
| Russia      | [Dichiarazione IVA](../localizations/rus-vat-declaration.md) | |
| Russia      | [Report di contabilità in formato elettronico](../localizations/rus-accounting-reporting.md) | |
| Russia      | [Dichiarazione IVA profitto](../localizations/rus-profit-tax-declaration.md) | |
| Russia      | [Dichiarazione fiscale accertata](../localizations/rus-assessed-tax-declaration.md) | |
| Russia      | [Dichiarazione fiscale per imposte di trasporto](../localizations/rus-transport-tax-declaration.md) | |
| Russia      | [Dichiarazione fiscale per imposte fondiarie](../localizations/rus-land-tax-declaration.md) | |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

