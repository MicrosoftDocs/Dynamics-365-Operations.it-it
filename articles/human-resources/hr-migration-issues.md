---
title: Problemi noti dell'unione dell'infrastruttura di Dynamics 365 Human Resources
description: In questo articolo vengono elencati i problemi che possono verificarsi durante l'unione dell'infrastruttura di Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 28c2c10a9293d00e26dfcc80ab08b89a122a6135
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733456"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-known-issues"></a>Problemi noti dell'unione dell'infrastruttura di Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="shared-dataverse-environments"></a>Ambienti Dataverse condivisi

Il framework doppia scrittura non supporta il collegamento di due ambienti di app per la finanza e le operazioni allo stesso ambiente Dataverse. Se hai un ambiente Dataverse condiviso con entrambi gli elementi seguenti, è necessario duplicare l'ambiente Dataverse o suddividerlo:

- Un'app per la finanza e le operazioni
- Un ambiente corrente Human Resources

## <a name="environment-type-requirements"></a>Requisiti del tipo di ambiente

Prima di poter eseguire la migrazione sono necessari i seguenti tipi di ambiente:

- Se non disponi di ambienti autonomi sandbox, devi crearne uno per convalidare la migrazione.
- Se disponi di più ambienti standalone di produzione, è possibile migrarne uno. Contatta il supporto tecnico Microsoft per abilitare gli altri ambienti come sandbox.

## <a name="teams-integration"></a>Integrazione Teams

L'app Human Resources esistente in Teams è attualmente in fase di spostamento in una soluzione Microsoft Power Platform. Per ulteriori informazioni, vedere [App Human Resources in Teams](hr-admin-teams-leave-app.md).

## <a name="licensing"></a>Licenze

Non ci sono modifiche alla licenza per Dynamics 365 Human Resources nelle seguenti aree: 

- **Requisito del numero minimo per l'acquisto della licenza**
- **Licenze per un ambiente di produzione e un ambiente sandbox** – Se disponi di licenze Human Resources autonome esistenti che includono un ambiente di produzione e un ambiente sandbox, lo stesso numero di licenze sarà disponibile sull'infrastruttura per la finanza e le operazioni.
- **Licenze sandbox aggiuntive** – Se hai acquistato licenze sandbox aggiuntive per l'applicazione autonoma Human Resources, lo stesso numero di licenze sarà disponibile per gli ambienti sandbox sull'infrastruttura per la finanza e le operazioni. 
