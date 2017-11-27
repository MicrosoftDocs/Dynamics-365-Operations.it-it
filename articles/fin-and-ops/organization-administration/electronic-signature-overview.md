---
title: Panoramica delle firme elettroniche
description: Questo articolo fornisce una panoramica delle firme elettroniche e descrive come utilizzarle in Microsoft Dynamics 365 for Finance and Operations.
author: maertenm
manager: AnnBe
ms.date: 08/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 698b938e515ff4755c2f111279cda244577ac9f3
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="electronic-signature-overview"></a>Panoramica delle firme elettroniche

[!include[banner](../includes/banner.md)]


Questo articolo fornisce una panoramica delle firme elettroniche e descrive come utilizzarle in Microsoft Dynamics 365 for Finance and Operations.

<a name="what-is-an-electronic-signature"></a>Firma elettronica
--------------------------------

Una firma elettronica consente di confermare l'identità di una persona che sta per avviare o approvare un processo di elaborazione. In alcuni settori una firma elettronica è considerata legalmente vincolante come una firma manuale. 

Le firme elettroniche rappresentano un requisito di legge per diversi settori regolamentati, tra cui quello farmaceutico, quello alimentare e quello aerospaziale e della difesa. Sono inoltre obbligatorie per la conformità alle normative incluse in 21 CFR Part 11 emanate dalla Food and Drug Administration (FDA) negli Stati Uniti. 

**Nota:** una firma elettronica in sé non equivale a una firma digitale. Una firma elettronica viene utilizzata soltanto in sostituzione di una firma manuale, mentre una firma digitale soddisfa ulteriori requisiti di sicurezza, ad esempio consente di rilevare se i dati sono stati manomessi da un altro utente o processo. Una firma digitale può inoltre essere verificata e tale verifica non può essere rifiutata dal proprietario del certificato utilizzato per la firma dei dati. Come descritto più avanti, nelle firme elettroniche di Microsoft Dynamics 365 for Finance and Operations è incorporata la funzionalità di firma digitale.

## <a name="electronic-signatures-in-dynamics-365-for-finance-and-operations"></a>Firme elettroniche in Dynamics 365 for Finance and Operations
In Finance and Operations è possibile utilizzare le firme elettroniche per i processi aziendali critici. In alcuni processi sono disponibili funzionalità di firma elettronica incorporate. È inoltre possibile creare requisiti di firma personalizzati per qualsiasi tabella o campo di database. 

Nelle firme elettroniche è incorporata la funzionalità di firma digitale. Ogni utente che firma documenti deve ottenere un certificato di crittografia valido. Al momento della firma di un documento, la chiave privata associata al certificato viene convalidata. In Finance and Operations le informazioni relative alle firme elettroniche vengono memorizzate in un registro in modo da costituire un audit trail. Per impostare le firme elettroniche, vedere [Impostare le firme elettroniche (guida attività)](tasks/set-up-electronic-signatures.md).

## <a name="users-who-require-access-to-electronic-signatures"></a>Utenti che richiedono l'accesso alle firme elettroniche
Tre tipi di utenti in genere richiedono l'accesso protetto alle firme elettroniche: amministratori delle firme elettroniche, firmatari e revisori delle firme elettroniche.

### <a name="electronic-signature-administrator"></a>Amministratore delle firme elettroniche

L'amministratore delle firme elettroniche imposta i requisiti di firma, i parametri generali e gli approvatori e riceve gli avvisi quando le firme non possono essere verificate. Per impostazione predefinita, un utente che appartiene al ruolo di sicurezza **Responsabile IT** dispone dell'autorizzazione ad amministrare le firme elettroniche.

### <a name="signer"></a>Firmatario

Un firmatario fornisce le firme elettroniche per i documenti e i processi per i quali sono richieste tali firme. Per impostazione predefinita, un utente che appartiene al ruolo di sicurezza **Utente sistema** dispone dell'autorizzazione a firmare documenti elettronicamente. 

**Nota:** è possibile che il firmatario debba disporre di autorizzazioni aggiuntive per ottenere l'accesso ai dati correlati al documento o al processo da firmare. Un utente che apporta modifiche ai dati e deve quindi firmare per tali modifiche deve disporre dell'autorizzazione per la modifica dei dati. Un utente firmatario per conto di un altro utente potrebbe non richiedere l'accesso ai dati. Un esempio di questo tipo di utente è un supervisore che firma per le modifiche di un dipendente.

### <a name="electronic-signature-auditor"></a>Revisore delle firme elettroniche

Il revisore delle firme elettroniche controlla il registro database e il registro di verifica delle firme disponibile nel registro database. Per impostazione predefinita, un utente che appartiene al ruolo di sicurezza **Responsabile IT** dispone dell'autorizzazione ad amministrare le firme elettroniche. 

Se si utilizza un ruolo diverso da **Responsabile IT**, assicurarsi che al ruolo siano assegnati i privilegi seguenti:

-   Visualizza errori firma elettronica
-   Visualizza registro database

## <a name="signing-documents-electronically"></a>Firma elettronica di documenti
### <a name="get-a-certificate"></a>Ottenere un certificato

Per poter apporre la firma elettronica ai documenti in Finance and Operations, è necessario richiedere un certificato. 

**Nota:** Finance and Operations utilizza le funzionalità di Microsoft SQL Server per creare certificati e abilitare la firma elettronica. Non è richiesto alcun certificato aggiuntivo o infrastruttura a chiave pubblica (PKI). 

Per l'utente che richiede un certificato vengono create una chiave pubblica e una chiave privata nel database di Finance and Operations. La chiave privata viene crittografata mediante una password nota solo all'utente. Al momento della firma elettronica di un documento, l'identità del firmatario viene verificata quando si immette la password. 

Per richiedere un certificato, nella pagina **Opzioni** della scheda **Conti** , fare clic su **Ottieni certificato**. 

Immettere e confermare la password che verrà utilizzata per la firma. La password consente la protezione della chiave privata e autorizza l'utilizzo del certificato. La password non viene archiviata nel database e non è disponibile per altri utenti, nemmeno per l'amministratore di Finance and Operations. 

Se si dimentica la password associata al certificato, quest'ultimo deve essere reimpostato. La reimpostazione del certificato non influisce sui documenti firmati con il certificato precedente. Per reimpostare il certificato, nella pagina **Opzioni** fare clic su **Reimposta certificato**.

### <a name="sign-a-document-electronically"></a>Apporre la firma elettronica a un documento

La pagina **Firma documento** viene visualizzata quando si apporta una modifica per la quale è richiesta una firma elettronica.

1.  Nella pagina **Firma documento** fare clic sulla scheda **Documento** per verificare le modifiche apportate al documento.
2.  Nella scheda **Firma** selezionare un codice motivo.
3.  Immettere un commento, se è richiesto un commento.
4.  Se l'ID dell'utente non viene visualizzato nel campo **Firmatario**, selezionarlo dall'elenco.
5.  Immettere l'ubicazione, se queste informazioni sono necessarie.
6.  Scegliere **OK**.

### <a name="sign-for-another-users-changes"></a>Firma per le modifiche apportate da un altro utente

Talvolta si può decidere che un utente firmi per le modifiche apportate da altri. È ad esempio possibile che un supervisore debba firmare per le modifiche apportate alle distinte base (DBA) da un dipendente. Utilizzare questa procedura per designare un utente di Finance and Operations come firmatario per un altro utente. 

**Nota:** Quando un utente firma per una modifica apportata da un altro, la firma deve essere fornita alla workstation dell'utente autore della modifica. Quest'ultimo sarà in grado di salvare la modifica solo dopo che è stata fornita la firma. 

Per designare gli approvatori, attenersi alla procedura indicata di seguito.

1.  Nella pagina **Opzioni** , nella scheda **Conti** , fare clic su **Approvatore designato**.
2.  Nel campo **ID utente approvatore** selezionare l'ID dell'utente che deve firmare per le modifiche apportate da un altro utente.
3.  Nel campo **ID utente per firma** selezionare l'ID dell'utente che ha apportato le modifiche per le quali è richiesta la firma.





