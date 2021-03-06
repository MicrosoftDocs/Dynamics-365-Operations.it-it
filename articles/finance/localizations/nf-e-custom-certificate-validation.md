---
title: Convalida del certificato personalizzato NF-e
description: Questo argomento fornisce informazioni sull'abilitazione e l'utilizzo del certificato personalizzato NF-e.
author: gionoder
ms.date: 10/06/2020
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
ms.openlocfilehash: 895513f51798a797ebf59f8a5be4f5cde006726d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813970"
---
# <a name="nf-e-custom-certificate-validation"></a>Convalida del certificato personalizzato NF-e

[!include [banner](../includes/banner.md)]

Quando si attiva la funzionalità di verifica del certificato personalizzato NF-e, la convalida personalizzata consente una connessione con i servizi Web. Questa connessione è necessaria per trasmettere NF-e e ricevere l'autorizzazione da SEFAZ.

La proprietà **Scopo autenticazione server** del certificato V5 viene emessa dall'autorità di certificazione radice brasiliana. Questa proprietà è disattivata per impostazione predefinita e deve essere abilitata manualmente. In alcune circostanze, l'aggiornamento automatico del certificato può disabilitare questa proprietà. Se ciò accade, la connessione TLS viene modificata e non è più considerata attendibile. Anche la possibilità di emettere NF-e in ambienti di produzione per gli stati di Minas Gerais (MG) e Paraná (PR) viene modificata.

Questo aggiornamento consente una soluzione alternativa per la convalida del certificato, il che significa che è possibile stabilire una comunicazione sicura.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]