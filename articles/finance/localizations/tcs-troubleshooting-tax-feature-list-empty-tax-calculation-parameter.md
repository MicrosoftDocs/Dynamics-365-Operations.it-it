---
title: Elenco di funzionalità fiscali vuoto nei parametri di calcolo delle imposte
description: Questo articolo spiega come risolvere un problema in cui l'elenco delle funzioni fiscali nella pagina Parametri di calcolo delle imposte è vuoto.
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 0d9286ec313a270da86181ff80ddfd690a757c9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869954"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>Elenco di funzionalità fiscali vuoto nei parametri di calcolo delle imposte

[!include [banner](../includes/banner.md)]


## <a name="symptom"></a>Sintomo

Hai pubblicato una funzionalità in Regulatory Configuration Service (RCS), in modo da poterla utilizzare in Microsoft Dynamics 365 Finance. Tuttavia, quando apri Finance, vai a **Imposta** \> **Configura** \> **Configurazione fiscale** \> **Parametri di calcolo delle tasse** e provi a selezionare un valore nel campo **Nome della configurazione della funzione**, l'elenco dei valori è vuoto.

## <a name="reason"></a>Motivo

Questo problema si verifica in genere perché l'ambiente Finance e l'ambiente RCS non si trovano nello stesso tenant.

### <a name="rcs-tenant"></a>Tenant RCS

Segui questi passaggi per trovare l'ID del tuo tenant RCS.

1. Copia l'URL RCS completo. Ad esempio, l'URL potrebbe essere `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`.
2. Apri una finestra del browser InPrivate, incolla l'URL RCS nella barra degli indirizzi, quindi seleziona **INVIO**. Verrai indirizzato alla pagina di accesso, dove puoi trovare l'ID tenant RCS. Ad esempio, se l'URL della pagina di accesso è `https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`, l'ID tenant è l'informazione che appare dopo `https://login.microsoftonline.com/` o **d335a570-a05b-4bc5-8eb3-c42c65f9560d**.

### <a name="finance-environment-tenant-id"></a>ID tenant dell'ambiente Finance

Per trovare l'ID tenant per il tuo ambiente Finance, segui gli stessi passaggi che hai seguito per trovare il tenant RCS. Tuttavia, copia e incolla l'URL completo del tuo ambiente Finance invece dell'URL RCS completo.

## <a name="resolution"></a>Risoluzione

Se i due ID tenant differiscono, si verifica il problema descritto in questo articolo. Se sono uguali, stai riscontrando un problema non correlato. In questo caso, ti consigliamo di contattare il supporto tecnico Microsoft.

### <a name="solution-1"></a>Soluzione 1

Accedi al tuo ambiente RCS con lo stesso tenant a cui è connesso il tuo ambiente Finance. Quindi crea e pubblica la funzione fiscale.

### <a name="solution-2"></a>Soluzione 2

Condividi la funzione fiscale con il tenant Finance in RCS.

1. In RCS, vai a **Funzionalità di globalizzazione** \> **Calcolo delle tasse**.
2. Seleziona la funzione da condividere, quindi nella scheda **Organizzazioni**, seleziona **Condividi con**.
3. Nel campo **Nome dominio organizzazione** immetti un nome. Ad esempio, immetti **contoso.onmicrosoft.com**.
4. Selezionare **Condividi**.

![Condividi la finestra di dialogo a discesa dell'organizzazione esterna.](media/ShareTaxFeature.png)
