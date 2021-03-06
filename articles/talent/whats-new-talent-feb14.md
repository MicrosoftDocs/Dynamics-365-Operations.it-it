---
title: Novità o modifiche in Dynamics 365 Talent (14 febbraio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 32f3bab38233833498ed566fa1558a023b3bc0dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461648"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-14-2019"></a>Novità o modifiche in Dynamics 365 Talent (14 febbraio 2019)

Questo argomento descrive le funzionalità nuove o modificate di Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract
Questa versione include correzioni di bug minori.

## <a name="changes-in-onboarding"></a>Modifiche in Onboard
Questa versione include correzioni di bug minori.
 
## <a name="changes-in-core-hr"></a>Modifiche di Core HR 
**Build 8.1.2146**

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a>L'entità Retribuzione fissa dipendente non esporta tutti i record
Con questa modifica, l'entità **Retribuzione fissa dipendente** ora esporterà tutti i record. L'entità può essere utilizzata per creare e aggiornare record di retribuzione fissa esistenti per i dipendenti. 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a>La data di fine impiego non è conforme alle impostazioni di fuso orario preferite del dipendente
Le date di fine impiego ora sono conformi al fuso orario preferito dell'utente quando si crea o si termina un impiego con una società.
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a>Indirizzi del Regno Unito visualizzati in Analisi come indirizzi della Svizzera orientale
In questa versione, è stata apportata una modifica per correggere l'errato allineamento degli indirizzi in **Gestione personale** nel report "Numero dipendenti per ubicazione".
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a>Il codice di fine rapporto non viene popolato nel record dell'assegnazione posizione lavoratore quando si termina la posizione
È stata effettuata una modifica al codice "Motivo fine rapporto" predefinito quando si termina l'assegnazione della posizione dei dipendenti.

### <a name="new-entity-created-for-job-compensation-levels"></a>Nuova entità creata per i livelli di retribuzione delle mansioni
È stata creata una nuova entità DMF (Data Management Framework). Questa entità consente la creazione e l'aggiornamento di livelli retributivi, valori di mercato e informazioni per ogni mansione definita nel sistema.


[!INCLUDE[footer-include](../includes/footer-banner.md)]