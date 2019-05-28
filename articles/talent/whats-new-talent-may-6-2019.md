---
title: Novità o modifiche in Dynamics 365 for Talent (6 maggio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
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
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4830c5d626e5e10972c81c3445eb54e4b6b00e6c
ms.sourcegitcommit: 0400bfd66e98af50e64444a1c102575099a9312f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2019
ms.locfileid: "1539407"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-6-2019"></a>Novità o modifiche in Dynamics 365 for Talent (6 maggio 2019)

[!include [banner](includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Modifiche in Attract

### <a name="select-optional-documents-upon-offer-creation"></a>Selezione di documenti facoltativi durante la creazione di offerta

Quando si seleziona un modello di pacchetto di offerta, Attract ora richiede di selezionare i documenti facoltativi applicabili dal modello di pacchetto. È possibile aggiungere altri documenti come facoltativi mentre si prepara l'offerta.

## <a name="changes-in-onboard"></a>Modifiche in Onboard

Questa versione include correzioni di bug minori per Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifiche di Core HR

Le modifiche descritte in questo sezione sono valide per la build numero 8.1.2282. I numeri tra parentesi in alcune intestazioni si riferiscono ai numeri del supporto in Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-26"></a>Update 26 della piattaforma

Per ulteriori dettagli sull'aggiornamento 26 della piattaforma, vedere [Funzionalità di anteprima nell'aggiornamento 26 della piattaforma Dynamics 365 for Finance and Operations (giugno 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26). 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Support dell'entità Common Data Service per i campi personalizzati

Nella versione di questa settimana, le seguenti entità supportano i campi personalizzati: Frequenza calcolo benefit, Velocità calcolo benefit, Tipo di benefit, Calendario di lavoro, Vacanze del calendario di lavoro, Ciclo retributivo e Tipi di identificazione del lavoratore.

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a>Lasciare l'iscrizione collettiva, cambiando la base di livello in "Data di anzianità" non aggiorna il coefficiente di accumulo iniziale (318526)

Quando si registrano in massa dipendenti e si modifica la base di livello, il coefficiente di accumulo iniziale riflette ora la base di livello selezionata.

### <a name="workflow-showing-duplicate-place-holders-313636"></a>Flusso di lavoro con segnaposti duplicati (313636)

Le modifiche apportate a questa versione eliminano la duplicazione dei segnaposto quando vengono inviate notifiche del flusso di lavoro.

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a>I campi relativi alle dimensioni non vengono aggiornati quando si utilizza "Apri in Excel" (176261)

Con questa versione, è ora possibile aggiornare la dimensione finanziaria utilizzando **Apri in Excel** dalla pagina **Lavoratore**. 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a>L'indirizzo del lavoratore creato in Common Data Service non viene sincronizzato in Talent (317555)

Con questa modifica, gli indirizzi creati Common Data Service vengono aggiornati in Talent Core HR.


## <a name="in-preview"></a>In anteprima

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nuova pagina per convalidare i dati della gerarchia di posizioni

Le risorse umane (HR) e gli amministratori possono ora convalidare la gerarchia manageriale per tutti i riferimenti circolari che potrebbero essere stati inavvertitamente importati. È possibile accedere a questa nuova pagina da **Amministrazione organizzazione > Collegamenti> Posizioni> Convalida gerarchia posizioni**.

### <a name="specify-reason-codes-on-leave-types"></a>Specificare i codici motivo per i tipi di congedo

Le organizzazioni potrebbero richiedere informazioni aggiuntive per le richieste di permesso. Ora è possibile specificare i codici motivo per i tipi di congedo e consentire ai dipendenti di selezionare un codice motivo nelle relative richieste di permesso.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Richiedere codici motivo per tipi di congedo specifici nelle richieste di permesso

Le organizzazioni potrebbero richiedere codici motivo per determinati tipi di congedo quando i dipendenti inviano richieste di permesso. Questo requisito potrebbe esistere a causa di criteri aziendali o requisiti normativi. Ora è possibile specificare quali tipi di congedo richiedono un codice motivo ed è possibile richiedere ai dipendenti di fornire un codice motivo per il tipo di congedo nelle relative richieste di permesso.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornire un elenco di transazioni assenze e congedo per le Risorse umane

La possibilità di tracciare il tempo libero dei dipendenti e analizzare come tale tempo viene calcolato non solo consente alle Risorse umane di rispondere alle domande dei dipendenti, ma anche di garantire premi appropriati per i dipendenti. Ora le Risorse umane hanno una nuova visibilità sulle transazioni (concessioni, accumuli, rettifiche e richieste) in modo da poter determinare i motivi dei saldi.

## <a name="coming-soon"></a>Presto disponibili

### <a name="indicate-instance-type-when-provisioning-talent"></a>Indicare il tipo di istanza durante il provisioning di Talent

Quando si esegue il provisioning di una nuova istanza di Talent, è possibile indicare se il tipo di istanza è **Produzione** o **Sandbox**, consentendo il test iniziale di nuove funzionalità. Tutte le istanze Talent esistenti verranno aggiornate al tipo di istanza di produzione. Se si desidera aggiornare una delle istanze esistenti al tipo di istanza di Sandbox, contattare il supporto tecnico per avviare la richiesta di modifica.
