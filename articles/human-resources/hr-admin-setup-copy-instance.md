---
title: Copiare un'istanza
description: È possibile utilizzare Microsoft Dynamics Lifecycle Services (LCS) per copiare un database di Microsoft Dynamics 365 Human Resources in un ambiente sandbox.
author: twheeloc
ms.date: 07/22/2020
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
ms.openlocfilehash: 20a2ffb44f9b99800146e3365e6f0d6df8e9a75e
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324262"
---
# <a name="copy-an-instance"></a>Copiare un'istanza

_**Si applica a**: Human Resources nell'infrastruttura autonoma_ 

> [!NOTE]
> A partire da giugno 2022, gli ambienti Human Resources possono essere distribuiti solo nell'infrastruttura delle app per la finanza e le operazioni. Per ulteriori informazioni, vedere [Provisioning di Human Resources nell'infrastruttura di finanza e operazioni](hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> L'infrastruttura di finanza e operazioni non supporta la funzione di copia di un'istanza. È possibile distribuire nuovi ambienti e usare gli spostamenti dei database per creare copie. Per ulteriori informazioni sulle distribuzioni self-service, vedere [Panoramica delle distribuzioni self-service](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md). Per ulteriori informazioni sugli spostamenti dei database nell'infrastruttura di finanza e operazioni, vedere [Home page delle operazioni di spostamento dei database](../fin-ops-core/dev-itpro/database/dbmovement-operations.md).

È possibile utilizzare Microsoft Dynamics Lifecycle Services (LCS) per copiare un database di Microsoft Dynamics 365 Human Resources in un ambiente sandbox. Se è disponibile un altro ambiente sandbox, è anche possibile copiare il database da tale ambiente in un ambiente sandbox di destinazione.

Per copiare un'istanza, tenere presente i seguenti suggerimenti:

- L'istanza di Human Resources che si desidera sovrascrivere deve essere un ambiente sandbox.

- Gli ambienti utilizzati per la copia devono essere nella stessa area. Non è possibile copiare da un'area in un'altra area.

- È necessario essere un amministratore nell'ambiente di destinazione in modo da potervi accedere dopo aver copiato l'istanza.

- Quando si copia il database di Human Resources, non si copiano gli elementi (app o dati) contenuti in un ambiente Microsoft Power Apps. Per informazioni su come copiare elementi in un ambiente Power Apps, vedere [Copiare un ambiente](/power-platform/admin/copy-environment). L'ambiente Power Apps che si desidera sovrascrivere deve essere un ambiente sandbox. È necessario essere un amministratore tenant globale per modificare un ambiente di produzione Power Apps in un ambiente sandbox. Per ulteriori informazioni sulla modifica di un ambiente Power Apps, vedere [Passare a un'altra istanza](/dynamics365/admin/switch-instance).

- Se si copia un'istanza nell'ambiente sandbox e si desidera integrare l'ambiente sandbox con Dataverse, è necessario riapplicare i campi personalizzati alle tabelle Dataverse. Vedere [Applicare campi personalizzati a Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).

## <a name="effects-of-copying-a-human-resources-database"></a>Effetti della copia di un database di Human Resources

> [!Note]
> A partire da agosto 2022, i documenti nell'archiviazione BLOB di Microsoft Azure vengono inclusi quando si copia un ambiente di produzione in un ambiente sandbox. Tutti i documenti e i modelli allegati verranno copiati dall'ambiente di origine all'ambiente di destinazione.

I seguenti eventi si verificano quando si copia un database di Human Resources:

- Il processo di copia cancella il database esistente nell'ambiente di destinazione. Una volta completato il processo di copia, non è possibile ripristinare il database esistente.

- L'ambiente di destinazione non sarà disponibile fino al completamento del processo di copia.

- Tutti gli utenti eccetto quelli con il ruolo di sicurezza "Amministratore sistema" e altri account utente del servizio interno saranno disponibili. L'utente amministratore può eliminare i dati prima di autorizzare altri utenti nel sistema.

- Qualsiasi utente con il ruolo di sicurezza "Amministratore sistema" deve apportare le modifiche necessarie alla configurazione, come la riconnessione di endpoint di integrazione a servizi o URL specifici.

## <a name="copy-the-human-resources-database"></a>Copiare il database di Human Resources

Per completare questa attività, innanzi tutto copiare un'istanza, quindi accedere all'interfaccia di amministrazione di Microsoft Power Platform per copiare il proprio ambiente Power Apps.

> [!WARNING]
> Quando si copia un'istanza, il database viene cancellato nell'istanza di destinazione. L'istanza di destinazione non è disponibile durante questo processo.

1. Accedere a LCS e selezionare il progetto LCS che contiene l'istanza che si desidera copiare.

2. Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**.

3. Selezionare l'istanza da copiare, quindi selezionare **Copia**.

4. Nel riquadro attività **Copia un'istanza**, selezionare l'istanza da sovrascrivere, quindi selezionare **Copia**. Attendere che il campo **Stato copia** venga aggiornato in **Completata**.

   ![[Selezionare l'istanza da sovrascrivere.](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Selezionare **Power Platform** e accedere all'interfaccia di amministrazione di Microsoft Power Platform.

   ![[Selezionare Power Platform.](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Selezionare l'ambiente Power Apps da copiare, quindi selezionare **Copia**.

Per ulteriori informazioni sulla copia degli ambienti Power Apps, vedere [Copia di un ambiente](/power-platform/admin/copy-environment#copy-an-environment-1).

7. Al termine del processo di copia, accedere all'istanza di destinazione e abilitare l'integrazione di Dataverse. Per ulteriori informazioni e istruzioni, vedere [Configurare l'integrazione di Dataverse](./hr-admin-integration-common-data-service.md).

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

Alcuni di questi elementi non vengono copiati perché sono specifici dell'ambiente. Alcuni esempi sono i record **BatchServerConfig** e **SysCorpNetPrinters**. Altri elementi non vengono copiati a causa del volume dei ticket di supporto. Ad esempio:

- È possibile che vengano inviati messaggi di posta elettronica duplicati perché SMTP è ancora abilitato nell'ambiente di test di accettazione dell'utente (sandbox).

- È possibile che vengano inviati messaggi di integrazione non validi perché i processi batch sono ancora abilitati.

- Gli utenti potrebbero essere abilitati prima che gli amministratori possano eseguire azioni di pulizia post-aggiornamento.

Inoltre, i seguenti stati cambiano quando si copia un'istanza:

- Tutti gli utenti tranne quelli con il ruolo di sicurezza "Amministratore sistema" sono impostati su **Disabilitato**.

- Tutti i processi batch, ad eccezione di alcuni processi di sistema, sono impostati su **Trattenuto**.

## <a name="environment-admin"></a>Amministratore di ambiente

Tutti gli utenti nell'ambiente sandbox di destinazione, inclusi gli amministratori, vengono sostituiti dagli utenti dell'ambiente di origine. Prima di copiare un'istanza, assicurarsi di essere un amministratore nell'ambiente di origine. In caso contrario, non è possibile accedere all'ambiente sandbox di destinazione al termine della copia.

Tutti gli utenti non amministratori nell'ambiente sandbox di destinazione sono disabilitati per impedire accessi indesiderati nell'ambiente sandbox. Gli amministratori possono riabilitare gli utenti se necessario.

## <a name="apply-custom-fields-to-dataverse"></a>Applicare campi personalizzati a Dataverse

Se si copia un'istanza nell'ambiente sandbox e si desidera integrare l'ambiente sandbox con Dataverse, è necessario riapplicare i campi personalizzati alle tabelle Dataverse.

Per ogni campo personalizzato esposto nelle tabelle Dataverse, eseguire le seguenti operazioni:

1. Andare al campo personalizzato e selezionare **Modifica**.

2. Deselezionare il campo **Abilitato** per ogni entità cdm_* in cui è abilitato il campo personalizzato.

3. Selezionare **Applica modifiche**.

4. Selezionare **Modifica** nuovamente.

5. Selezionare il campo **Abilitato** per ogni entità cdm_* in cui è abilitato il campo personalizzato.

6. Selezionare di nuovo **Applica modifiche**.

Il processo di deselezione, applicazione delle modifiche, riselezione e riapplicazione delle modifiche richiede l'aggiornamento dello schema in Dataverse per includere i campi personalizzati.

Per ulteriori informazioni sui campi personalizzati, vedere [Creare e utilizzare campi personalizzati](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).

## <a name="see-also"></a>Vedere anche

[Provisioning di Human Resources](hr-admin-setup-provision.md)</br>
[Rimuovere un'istanza](hr-admin-setup-remove-instance.md)</br>
[Aggiornare un processo](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
