---
title: Risolvere i problemi di configurazione e installazione di Store Commerce
description: Questo articolo spiega come risolvere i problemi di installazione e installazione nell'app Microsoft Dynamics 365 Commerce Store Commerce.
author: mugunthanm
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 8af2c476ced05fc159a53131f8b51ad914a6c7c3
ms.sourcegitcommit: c271b2edc4bf777f7194b09139ccbd174a359c75
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2022
ms.locfileid: "9168949"
---
# <a name="troubleshoot-store-commerce-setup-and-installation-issues"></a>Risolvere i problemi di configurazione e installazione di Store Commerce

[!include [banner](../includes/banner.md)]

Questo articolo spiega come risolvere i problemi di installazione e installazione nell'app Microsoft Dynamics 365 Commerce Store Commerce.

## <a name="i-cant-activate-the-app-and-i-receive-a-connectivity-error-message"></a>Non riesco ad attivare l'app e ricevo un messaggio di errore di connettività

Dopo aver immesso l'URL del POS Cloud valido, potresti ricevere un messaggio di errore di connettività simile al seguente:

> Si è verificato un errore di connettività e il tuo dispositivo non può connettersi al POS Cloud. L'URL del POS Cloud digitato potrebbe presentare alcuni problemi.

In questo caso, controlla l'URL per errori tipografici o determina se non è possibile raggiungere il POS Cloud perché è offline.

Verifica inoltre che la versione Cloud Scale Unit (CSU) sia 10.0.25 (9.35.\*.\*) o successiva. Per utilizzare l'app Store Commerce è necessaria la versione POS Cloud 10.0.25 o successiva.

## <a name="i-cant-install-the-app-because-modern-pos-is-already-installed"></a>Non riesco a installare l'app perché Modern POS è già installato

Durante l'installazione, potresti ricevere un messaggio di errore come il seguente esempio:

> Una versione (9.\*.\*.\*) di questo prodotto (Modern POS) è stata precedentemente installata tramite il programma di installazione legacy.

Per correggere l'errore, è necessario disinstallare l'app Modern Point of Sale (MPOS) per tutti gli utenti sul computer e riprovare. Puoi confermare se MPOS è stato rimosso per tutti gli utenti eseguendo il comando PowerShell seguente.

```PowerShell
Get-AppxPackage | Where-Object {$_.PackageFullName -like "Microsoft.Dynamics.*.Pos"} | Remove-AppxPackage -Allusers
```

## <a name="i-cant-activate-the-app-because-of-an-invalid-url-or-an-error-state"></a>Non riesco ad attivare l'app a causa di un URL non valido o di uno stato di errore

Se l'URL del POS Cloud che hai inserito non è valido e desideri modificarlo, o se l'app Store Commerce è in uno stato di errore durante l'attivazione, puoi riavviare il processo reimpostando l'app. L'app Store Commerce salverà solo un URL del POS Cloud valido.

Per ripristinare l'app Store Commerce, segui questi passaggi.

1. Nel menu **Start** di Windows seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) sull'app, quindi seleziona **Altro \> Impostazioni app**.
2. Scorri verso il basso la pagina delle impostazioni dell'app fino a trovare il pulsante **Reimposta**.
3. Selezionare **Reimposta**. Quindi, quando richiesto, conferma di voler ripristinare l'app.
