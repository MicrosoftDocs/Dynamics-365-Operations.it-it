---
title: Convalida del certificato personalizzato NF-e
description: Questo argomento fornisce informazioni sull'abilitazione e l'utilizzo del certificato personalizzato NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8144e16b127bdbe954ef44f52c5ac71689a2036e6085e9a4ccc8bb17f91ae9b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755593"
---
# <a name="nf-e-custom-certificate-validation"></a>Convalida del certificato personalizzato NF-e

[!include [banner](../includes/banner.md)]

La proprietà **Scopo autenticazione server** dei certificati emessi dall'autorità di certificazione radice brasiliana è disattivata per impostazione predefinita e deve essere abilitata manualmente. In alcune circostanze, l'aggiornamento automatico del certificato può disabilitare questa proprietà. Se ciò accade, la connessione TLS viene modificata e non può essere considerata attendibile. Anche la possibilità di emettere modelli di documento fiscale elettronico 55 (NF-e) in ambienti di produzione per gli stati di Minas Gerais (MG) e Paraná (PR) viene modificata.

Per abilitare la correzione per **Convalida del certificato personalizzato NF-e**, vai a **Gestione funzionalità**. Questa funzionalità consente una soluzione alternativa per le convalide dei certificati V5 e V10 e consente una connessione affidabile con i servizi Web, necessaria per la trasmissione sicura dell'NF-e e la ricezione dell'autorizzazione da SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
