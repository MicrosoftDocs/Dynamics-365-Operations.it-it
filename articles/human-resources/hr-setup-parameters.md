---
title: Configurare i parametri di Human Resources
description: In questo argomento viene illustrato come impostare parametri specifici della società in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fd9bb907f95ba4c368871a470ca9b2bc807646ee
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771437"
---
# <a name="configure-human-resources-parameters"></a>Configurare i parametri di Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Le impostazioni di alcuni parametri di Human Resources sono condivise tra società, mentre le impostazioni di altri parametri sono specifiche di una società. In questo argomento viene illustrato come impostare parametri di Human Resources specifici di una società.

Per l'impostazione dei parametri di Human Resources vengono utilizzate due pagine. Per i parametri che vengono condivisi tra le società, si utilizza la pagina **Parametri condivisi Human resources**. Per i parametri che sono specifici della società (vale a dire le impostazioni che si applicano a una singola società), si utilizza la pagina **Parametri Risorse umane**.

![Accedere a Parametri di Human Resources.](./media/hr-employee-self-service-human-resources-parameters.png)

Nella pagina **Parametri Human Resource** le impostazioni sono suddivise in sei schede:

- **Generali**
- **Selezione del personale** (questa scheda non è inclusa in Dynamics 365 Human Resources)
- **Retribuzione**
- **Sequenze numeriche**
- **FMLA**
- **Self-service dipendenti**
- **Responsabile self-service**
- **Gestione benefit**
- **Congedo e assenza**
- **Metodi di pagamento**

Ogni scheda contiene informazioni che si riferiscono a una singola società.

## <a name="general"></a>Generali

Le impostazioni nella scheda **Generale** definiscono l'aspetto delle informazioni sull'assenza, gli infortuni, la malattia e le nuove assunzioni. Le impostazioni di questa scheda definiscono inoltre alcuni valori predefiniti che vengono visualizzati quando si lavora. In particolare, questa scheda consente di:

- Selezionare un colore da applicare alle transazioni assenze aperte.
- Specificare il foglio di stile da utilizzare per i report.
- Abilitare l'integrazione tra i corsi di formazione e la registrazione delle assenze.
- Selezionare il codice assenza utilizzato per controllare questa integrazione.
- Indicare per quanto tempo mantenere i casi su eventi di infortunio e malattia.
- Specificare il numero di identificazione predefinito visualizzato quando viene assunto un nuovo lavoratore.
- Specificare la data utilizzata per calcolare gli anni di servizio. 

![Scheda Generale.](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>Selezione del personale

Le impostazioni nella scheda **Selezione del personale** definiscono i tipi di documento utilizzati per la corrispondenza inviata automaticamente ai candidati. È inoltre possibile indicare il progetto di selezione utilizzato per candidature spontanee.

Il periodo che viene definito per l'**aging del progetto di selezione** determina i progetti di selezione che sono inclusi nel riquadro **Progetti di aging** nell'area di lavoro **Gestione della selezione del personale**. Il periodo che viene definito per l'avviso di scadenza della domanda di lavoro viene utilizzato per visualizzare i progetti di selezione che si avvicinano alla scadenza della domanda nel riquadro **Scadenza domanda di lavoro imminente** nell'area di lavoro **Selezione del personale**.

Per ulteriori informazioni sulla selezione, vedere [Selezione dei candidati](hr-personnel-recruit.md).

## <a name="compensation"></a>Retribuzione

In Dynamics 365 Finance, le impostazioni della scheda **Retribuzione** definiscono se gli utenti devono confermare che desiderano salvare le informazioni relative a un piano di retribuzione fissa o variabile. Se si seleziona **Attivare la convalida del salvataggio**, quando gli utenti chiudono una pagina correlata alla retribuzione, ricevono un messaggio in cui viene chiesto se si desidera salvare il record. Alcune pagine di Gestione retribuzioni non permettono agli utenti di eliminare le informazioni. La richiesta agli utenti di verificare se desiderano salvare le informazioni può limitare la quantità di informazioni che vengono salvate, ma che non possono essere successivamente eliminate. Se si deseleziona **Attivare la convalida del salvataggio**, i record vengono salvati immediatamente, possibilmente prima che l'utente sia pronto. Se si utilizza Gestione delle prestazioni, nella scheda **Retribuzione** è possibile selezionare un modello di valutazione da utilizzare al posto di quello assegnato ai piani di retribuzione durante la valutazione delle prestazioni.

In Human Resources, è possibile utilizzare la scheda **Retribuzione** per scegliere di limitare l'accesso ai piani di retribuzione e per impostare una valuta predefinita.

Per ulteriori informazioni sulla retribuzione, vedere [Panoramica dei piani di retribuzione](hr-compensation-overview.md).

![Scheda Retribuzione.](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>Sequenze numeriche

Le impostazioni nella scheda **Sequenza numerica** determina le sequenze utilizzate per assegnare automaticamente gli ID agli articoli in Human Resources, come ad esempio:

- Candidature
- Registrazioni assenze
- Risultati del processo retributivo
- Numeri di caso
- Corsi
- Agende del corso

Per gestire i codici e i riferimenti delle sequenze numeriche, utilizzare la pagina elenco **Sequenze numeriche** (selezionare **Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche**).

Per ulteriori informazioni, vedere [Panoramica delle sequenze numeriche](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

> [!NOTE]
> Il numero di ore lavorate non può superare le 1.250 ore e la durata dell'impiego non può superare i 12 mesi. Questi valori massimi sono definiti in osservanza delle normative federali negli Stati Uniti.

![Scheda Sequenze numeriche.](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

Nella scheda FMLA, si impostano i requisiti di idoneità FMLA e le ore di entitlement FMLA. Per ulteriori informazioni, vedere [Configurare i parametri di congedo e assenza](hr-leave-and-absence-parameters.md).

![Scheda FMLA.](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>Dipendente self-service

Le impostazioni nella scheda **Dipendente self service** determinano la modalità di visualizzazione di **Dipendente self-service** ai dipendenti. In questa scheda è possibile effettuare le seguenti attività:

- Immettere il nome dell'area di lavoro **Dipendente self-service**
- Selezionare le informazioni che un manager può immettere per i dipendenti
- Aggiungere collegamenti utili per i dipendenti
- Impedire ai dipendenti di aggiungere o modificare i dettagli di contatto aziendali. Per ulteriori informazioni, vedere [Impedire la modifica delle informazioni personali](hr-employee-self-service-restrict-editing.md).

Per ulteriori informazioni sulla configurazione di **Dipendente self-service**, vedere [Panoramica del dipendente e del responsabile self-service](hr-employee-manager-self-service-overview.md).

![Scheda Dipendente self-service.](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>Responsabile self-service

Le impostazioni della scheda **Responsabile self service** determinano ciò che i responsabili vedono in **Responsabile self service**. In questa scheda è possibile configurare le seguenti opzioni:

- L'intervallo per i record in scadenza
- Le informazioni che i responsabili possono visualizzare nei record in scadenza
- Se i manager possono visualizzare le posizioni aperte per subalterni estesi
- Visualizzazioni dei lavoratori prossimi a fine rapporto di impiego
- Collegamenti utili per i responsabili

Per ulteriori informazioni sulla configurazione di **Responsabile self-service**, vedere [Panoramica del dipendente e del responsabile self-service](hr-employee-manager-self-service-overview.md).

![Scheda Responsabile self-service.](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>Gestione benefit

Nella scheda **Gestione benefit**, è possibile configurare le opzioni di posta elettronica per Gestione benefit. Per informazioni sulla configurazione e sull'utilizzo di Gestione benefit, vedere [Panoramica di Gestione benefit](hr-benefits-management-overview.md).

![Scheda Gestione benefit.](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>Congedo e assenza

Per ulteriori informazioni sulla configurazione e sull'utilizzo di Congedo e assenza, vedere [Panoramica di Congedo e assenza](hr-leave-and-absence-overview.md).

## <a name="payment-methods"></a>Metodi di pagamento

Nella scheda **Metodi di pagamento**, è possibile selezionare i metodi di pagamento supportati dall'organizzazione. Per ulteriori informazioni sulla configurazione dei piani di retribuzione, vedere [Panoramica di Piani di retribuzione](hr-compensation-overview.md).

![Scheda Metodi di pagamento.](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
