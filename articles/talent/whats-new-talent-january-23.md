---
title: Novità o modifiche in Dynamics 365 Talent - Core HR (23 gennaio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
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
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f97462f088fc1a3cb94f2a34204fc09f1cd66fb0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899130"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-23-2019"></a>Novità o modifiche in Dynamics 365 Talent - Core HR (23 gennaio 2019)

**Build 8.1.2121**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.

## <a name="changes"></a>Modifiche

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a>L'importazione della retribuzione fissa del dipendente non funziona durante la creazione di nuovi record di retribuzione fissa
È stata apportata una modifica all'entità di retribuzione fissa del dipendente per recuperare il livello retributivo all'importazione. Nelle versioni precedenti, viene visualizzato un messaggio indicante che il livello è necessario.

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a>Rimozione del campo Saldo minimo dalla finestra di dialogo Richiesta permessi
Il campo **Saldo minimo** è stato rimosso dalla finestra di dialogo **Richiesta permessi**. Questa modifica influisce su tutte le aree in cui è possibile richiedere dei permessi.

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a>L'aggiornamento dei dati per i livelli retributivi non viene eseguito in tutti gli scenari
È stata effettuata una modifica per aggiornare il livello retributivo nei piani di retribuzione fissa. Questa modifica popolerà il livello retributivo nei piani fissi per la mansione assegnata al dipendente.

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a>Le informazioni sulle retribuzioni nella pagina di gestione delle modifiche sono disponibili solo dopo l'accesso come amministratore di sistema
Questa modifica consente ai dipendenti con ruolo Amministratore retribuzioni di accedere alle informazioni sulle retribuzioni nella pagina **Sequenza temporale modifiche > Gestione modifiche** per la posizione.

### <a name="job-fields-default-to-positions"></a>Per impostazione predefinita i campi della mansione sono impostati sulle posizioni
Quando si modifica la mansione in una posizione, per impostazione predefinita i campi della mansione sono impostati sulla posizione. Verrà visualizzato un messaggio di avviso con un'opzione per accettare i valori predefiniti o mantenere i valori esistenti per tali campi.

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a>Il periodo di prova e il calendario non sono visualizzati per i dipendenti assunti in futuro
Con questa modifica, i campi **Periodo di prova** e **Calendario** sono stati aggiunti alla pagina **Gestione modifiche** per consentire l'immissione di dati per dipendenti futuri e passati.

### <a name="platform-update-23-for-finance-and-operations"></a>Aggiornamento 23 della piattaforma per Finance and Operations
Correzioni di bug secondarie sono state incluse nell'aggiornamento 23 della piattaforma per Finance and Operations. Per ulteriori informazioni, vedere [Novità o modifiche nell'aggiornamento 23 della piattaforma Dynamics 365 Finance and Operations (gennaio 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23). 
