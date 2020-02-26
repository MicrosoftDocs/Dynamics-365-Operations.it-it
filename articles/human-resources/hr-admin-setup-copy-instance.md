---
title: Copiare un'istanza
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0bbe325edb65cad0c1912e0a6ade559e5675dc58
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009496"
---
# <a name="copy-an-instance"></a>Copiare un'istanza

È possibile utilizzare Microsoft Dynamics Lifecycle Services (LCS) per copiare un database di Microsoft Dynamics 365 Human Resources in un ambiente sandbox. Se è disponibile un altro ambiente sandbox, è anche possibile copiare il database da tale ambiente in un ambiente sandbox di destinazione.

Per copiare un'istanza:

- L'istanza di Human Resources che si desidera sovrascrivere deve essere un ambiente sandbox.

- Gli ambienti utilizzati per la copia devono essere nella stessa area. Non è possibile copiare da un'area in un'altra area.

- È necessario essere un amministratore nell'ambiente di destinazione in modo da potervi accedere dopo aver copiato l'istanza.

- Quando si copia il database di Human Resources, non si copiano gli elementi (app o dati) contenuti in un ambiente Microsoft PowerApps. Per informazioni su come copiare elementi in un ambiente PowerApps, vedere [Copiare un ambiente](https://docs.microsoft.com/power-platform/admin/copy-environment). L'ambiente PowerApps che si desidera sovrascrivere deve essere un ambiente sandbox. È necessario essere un amministratore tenant globale per modificare un ambiente di produzione PowerApps in un ambiente sandbox. Per ulteriori informazioni sulla modifica di un ambiente PowerApps, vedere [Passare a un'altra istanza](https://docs.microsoft.com/dynamics365/admin/switch-instance).

## <a name="effects-of-copying-a-human-resources-database"></a>Effetti della copia di un database di Human Resources

I seguenti eventi si verificano quando si copia un database di Human Resources:

- Il processo di copia cancella il database esistente nell'ambiente di destinazione. Una volta completato il processo di copia, non è possibile ripristinare il database esistente.

- L'ambiente di destinazione non sarà disponibile fino al completamento del processo di copia.

- I documenti nell'archivio Blob di Microsoft Azure non vengono copiati da un ambiente all'altro. Pertanto, tutti i documenti e i modelli allegati non verranno copiati e rimarranno nell'ambiente di origine.

- Tutti gli utenti tranne l'utente amministratore e altri account utente del servizio interno non saranno disponibili. Pertanto, l'utente amministratore può eliminare o offuscare i dati prima di autorizzare altri utenti nel sistema.

- L'utente amministratore deve apportare le modifiche alla configurazione necessarie, come la riconnessione di endpoint di integrazione a servizi o URL specifici.

## <a name="copy-the-human-resources-database"></a>Copiare il database di Human Resources

Per completare questa attività, innanzi tutto copiare un'istanza, quindi accedere all'interfaccia di amministrazione di Microsoft Power Platform per copiare il proprio ambiente PowerApps.

> [!WARNING]
> Quando si copia un'istanza, il database viene cancellato nell'istanza di destinazione. L'istanza di destinazione non è disponibile durante questo processo.

1. Accedere a LCS e selezionare il progetto LCS che contiene l'istanza che si desidera copiare.

2. Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**.

3. Selezionare l'istanza da copiare, quindi selezionare **Copia**.

4. Nel riquadro attività **Copia un'istanza**, selezionare l'istanza da sovrascrivere, quindi selezionare **Copia**. Attendere che il valore di **Stato copia** diventi **Completata**.

   ![[Selezionare l'istanza da sovrascrivere](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Selezionare **Power Platform** e accedere all'interfaccia di amministrazione di Microsoft Power Platform.

   ![[Selezionare Power Platform](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Selezionare l'ambiente PowerApps da copiare, quindi selezionare **Copia**.

7. Al termine del processo di copia, accedere all'istanza di destinazione e abilitare l'integrazione di Common Data Service. Per ulteriori informazioni e istruzioni, vedere [Configurare l'integrazione di Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

## <a name="data-elements-and-statuses"></a>Stati ed elementi di dati

I seguenti elementi di dati non vengono copiati quando si copia un'istanza di Human Resources.

- Indirizzi e-mail nella tabella **LogisticsElectronicAddress**

- Lo storico dei processi batch nelle tabelle **BatchJobHistory**, **BatchHistory** e **BatchConstraintHistory**

- La password SMTP (Simple Mail Transfer Protocol) nella tabella **SysEmailSMTPPassword**

- Il relay server SMTP nella tabella **SysEmailParameters**

- Impostazioni di Gestione stampa nelle tabelle **PrintMgmtSettings** e **PrintMgmtDocInstance**

- Record specifici dell'ambiente nelle tabelle **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** e **BatchServerGroup**

- Allegati a documenti nella tabella DocuValue. Questi allegati includono qualsiasi modello Microsoft Office che è stato sovrascritto nell'ambiente di origine

- La stringa di connessione nella tabella **PersonnelIntegrationConfiguration**

Alcuni di questi elementi non vengono copiati perché sono specifici dell'ambiente. Alcuni esempi sono i record **BatchServerConfig** e **SysCorpNetPrinters**. Altri elementi non vengono copiati a causa del volume dei ticket di supporto. Ad esempio, messaggi e-mail duplicati potrebbero essere inviati in quanto SMTP è ancora abilitato nell'ambiente di test di accettazione utenti (sandbox), messaggi di integrazione non validi potrebbero essere inviati in quanto i processi batch sono ancora abilitati e gli utenti potrebbero essere abilitati prima che gli amministratori possano eseguire azioni di pulizia post aggiornamento.

Inoltre, i seguenti stati cambiano quando si copia un'istanza:

- Tutti gli utenti tranne l'utente amministratore sono impostati su **Disabilitato**.

- Tutti i processi batch, ad eccezione di alcuni processi di sistema, sono impostati su **Trattenuto**.

## <a name="environment-admin"></a>Amministratore di ambiente

Tutti gli utenti nell'ambiente sandbox di destinazione, inclusi gli amministratori, vengono sostituiti dagli utenti dell'ambiente di origine. Prima di copiare un'istanza, assicurarsi di essere un amministratore nell'ambiente di destinazione. In caso contrario, non sarà possibile accedere all'ambiente sandbox di destinazione al termine della copia.

Tutti gli utenti non amministratori nell'ambiente sandbox di destinazione sono disabilitati per impedire accessi indesiderati nell'ambiente sandbox. Gli amministratori possono riabilitare gli utenti se necessario.
