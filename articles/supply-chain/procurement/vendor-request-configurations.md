---
title: Configurazioni richiesta fornitore
description: In questo argomento vengono descritti i campi obbligatori in una richiesta nuovo fornitore.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 98b759e5c5c918f14ca36bec93908d2f5eeb35044de77e3f450d79ead0993c16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725700"
---
# <a name="vendor-request-configurations"></a>Configurazioni richiesta fornitore
[!include [banner](../includes/banner.md)]

Per completare una richiesta fornitore, un contatto del fornitore deve completare la procedura guidata di registrazione del fornitore potenziale.

Nel modulo **Configurazioni richiesta fornitore**, è possibile creare profili che specificano i campi obbligatori e i campi visibili nella procedura guidata di registrazione del fornitore potenziale.

La procedura guidata per la registrazione del fornitore inizierà chiedendo al fornitore potenziale in quale paese opera il fornitore. Queste informazioni consentono di determinare la configurazione applicabile. Se nessuna specifica configurazione è definita per un paese, verrà utilizzata una configurazione predefinita.

### <a name="set-up-a-vendor-request-configuration"></a>Impostare una configurazione delle richieste fornitore

Per impostazione predefinita, è disponibile una configurazione fornitore nel modulo di configurazione delle richieste del fornitore.

Non è possibile selezionare paesi per la configurazione predefinita, quindi la sezione **Paesi** non può essere modificata.

1. Fare clic su **Approvvigionamento** > **Impostazione** > **Fornitori** e **Configurazioni richiesta fornitore**.
2. Fare clic sulla scheda **Campi** per impostare lo stato dei campi elencati.
3. Nascosto (non visibile)
4. Visualizzato (visibile ma non obbligatorio)
5. Obbligatorio (visibile e obbligatorio)
6. Fare clic sulla scheda **Contenuto** per specificare se il testo verrà visualizzato nella procedura guidata e se è necessario confermare che l'utente del fornitore potenziale deve accettarlo prima di continuare al passaggio successivo della procedura guidata. L'accettazione verrà richiesta per tutti i termini e le condizioni che l'utente deve accettare per continuare.

È inoltre possibile immettere un messaggio di conferma che viene visualizzato quando la procedura guidata è finalizzata e aggiungere uno o più questionari.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>Creare una configurazione del fornitore per un paese specifico
1.  Fare clic su **Approvvigionamento** > **Impostazione** > **Fornitori** e **Configurazioni richiesta fornitore**.
2.  Fare clic su **Nuovo** per creare una nuova configurazione e immettere un nome per la configurazione.
3.  Fare clic su **Salva**.
4.  Aprire la scheda **Paesi** per selezionare il paese per cui la configurazione deve essere utilizzata.
5.  Completare la configurazione seguendo le indicazioni per la configurazione predefinita.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]