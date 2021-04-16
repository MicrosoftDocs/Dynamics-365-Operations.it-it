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
# <a name="nf-e-custom-certificate-validation"></a><span data-ttu-id="4df8c-103">Convalida del certificato personalizzato NF-e</span><span class="sxs-lookup"><span data-stu-id="4df8c-103">NF-e custom certificate validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4df8c-104">Quando si attiva la funzionalità di verifica del certificato personalizzato NF-e, la convalida personalizzata consente una connessione con i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="4df8c-104">When you turn the NF-e custom certificate verification feature, custom validation allows a connection with the web services.</span></span> <span data-ttu-id="4df8c-105">Questa connessione è necessaria per trasmettere NF-e e ricevere l'autorizzazione da SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="4df8c-105">This connection is required to transmit NF-e and receive authorization from SEFAZ.</span></span>

<span data-ttu-id="4df8c-106">La proprietà **Scopo autenticazione server** del certificato V5 viene emessa dall'autorità di certificazione radice brasiliana.</span><span class="sxs-lookup"><span data-stu-id="4df8c-106">The **Server authentication purpose** property from the certificate V5 is issued by the Brazilian Root Certificate Authority.</span></span> <span data-ttu-id="4df8c-107">Questa proprietà è disattivata per impostazione predefinita e deve essere abilitata manualmente.</span><span class="sxs-lookup"><span data-stu-id="4df8c-107">This property is turned off by default and must be manually enabled.</span></span> <span data-ttu-id="4df8c-108">In alcune circostanze, l'aggiornamento automatico del certificato può disabilitare questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="4df8c-108">In some circumstances, the automatic certificate update can switch this property to no longer be enabled.</span></span> <span data-ttu-id="4df8c-109">Se ciò accade, la connessione TLS viene modificata e non è più considerata attendibile.</span><span class="sxs-lookup"><span data-stu-id="4df8c-109">If this happens, the TLS connection is affected and is no longer trusted.</span></span> <span data-ttu-id="4df8c-110">Anche la possibilità di emettere NF-e in ambienti di produzione per gli stati di Minas Gerais (MG) e Paraná (PR) viene modificata.</span><span class="sxs-lookup"><span data-stu-id="4df8c-110">The ability to issue NF-e on production environments for states of Minas Gerais (MG) and Paraná (PR) states is also impacted.</span></span>

<span data-ttu-id="4df8c-111">Questo aggiornamento consente una soluzione alternativa per la convalida del certificato, il che significa che è possibile stabilire una comunicazione sicura.</span><span class="sxs-lookup"><span data-stu-id="4df8c-111">This update allows for an alternative solution for certificate validation, which means that it’s possible to establish a secure communication.</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]