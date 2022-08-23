---
title: Convalida del certificato personalizzato NF-e
description: Questo articolo fornisce informazioni sull'abilitazione e l'utilizzo del certificato personalizzato NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: f78fdbd133aecaf9dbf8abe0006abd6deb1b1b15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288546"
---
# <a name="nf-e-custom-certificate-validation"></a>Convalida del certificato personalizzato NF-e

[!include [banner](../includes/banner.md)]

La proprietà **Scopo autenticazione server** dei certificati emessi dall'autorità di certificazione radice brasiliana è disattivata per impostazione predefinita e deve essere abilitata manualmente. In alcune circostanze, l'aggiornamento automatico del certificato può disabilitare questa proprietà. Se ciò accade, la connessione TLS viene modificata e non può essere considerata attendibile. Anche la possibilità di emettere modelli di documento fiscale elettronico 55 (NF-e) in ambienti di produzione per gli stati di Minas Gerais (MG) e Paraná (PR) viene modificata.

Per abilitare la correzione per **Convalida del certificato personalizzato NF-e**, vai a **Gestione funzionalità**. Questa funzionalità consente una soluzione alternativa per le convalide dei certificati V5 e V10 e consente una connessione affidabile con i servizi Web, necessaria per la trasmissione sicura dell'NF-e e la ricezione dell'autorizzazione da SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
