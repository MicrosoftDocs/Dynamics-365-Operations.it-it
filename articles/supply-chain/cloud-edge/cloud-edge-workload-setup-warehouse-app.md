---
title: Configurare l'app per dispositivi mobili Warehouse Management per le unità di scala nel cloud e nella rete perimetrale
description: Questo articolo spiega come configurare le app per dispositivi mobili Warehouse Management per i magazzini serviti da un'unità di scala cloud o perimetrale.
author: perlynne
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, SysUserManagement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 86edef2dfa6e9c71c04d50f185148be3a622fea1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865240"
---
# <a name="configure-the-warehouse-management-mobile-app-for-cloud-and-edge-scale-units"></a>Configurare l'app per dispositivi mobili Warehouse Management per le unità di scala nel cloud e nella rete perimetrale

[!include [banner](../includes/banner.md)]

Questo articolo spiega come configurare le app per dispositivi mobili Warehouse Management in modo da poter essere utilizzate nei magazzini serviti da un'unità di scala cloud o perimetrale.

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare a configurare i dispositivi mobili per la connessione a un'unità di scala cloud o perimetrale, verifica che possano connettersi all'hub aziendale. Per istruzioni, vedi [Installare e connettere l'app per dispositivi mobili Warehouse Management](../warehousing/install-configure-warehouse-management-app.md).

## <a name="additional-setup-when-you-run-the-warehouse-management-mobile-app-against-a-scale-unit"></a>Configurazione aggiuntiva quando si esegue l'app per dispositivi mobili Warehouse Management su un'unità di scala

Come parte del [processo di distribuzione per carichi di lavoro di unità di scala di magazzino](cloud-edge-landing-page.md#scale-unit-manager-portal), la maggior parte dei dati necessari per connettere i dispositivi dell'app per dispositivi mobili Warehouse Management viene sincronizzata automaticamente dall'hub aziendale all'unità di scala. Tuttavia, devi immettere i dati nella pagina **Applicazioni Azure Active Directory** (**Amministrazione di sistema \> Imposta \> Applicazioni Azure Active Directory**) sulla distribuzione dell'unità di scala. Inoltre, potrebbe essere necessario aggiornare il valore **Società** predefinito per l'ID utente o creare un nuovo utente. Gli utenti associati a un'azienda che non esiste in una distribuzione di unità di scala non potranno accedere quando l'app per dispositivi mobili Warehouse Management è connessa a tale unità di scala.

> [!NOTE]
> Dal momento che i dati nella pagina **Applicazioni Azure Active Directory** non sono sincronizzati, è necessario gestire manualmente questi dati se si desidera spostare i carichi di lavoro del magazzino su un'altra unità di scala.

Ricorda che, come parte della configurazione della connessione di ciascuna app per dispositivi mobili di Warehouse Management, l'URL della risorsa Azure Active Directory deve essere specificato per l'unità di scala anziché per l'hub aziendale.
