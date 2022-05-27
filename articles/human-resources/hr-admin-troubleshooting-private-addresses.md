---
title: Accedere a indirizzi privati per ruolo di sicurezza
description: Questo argomento spiega come risolvere quando un cliente non può accedere agli indirizzi privati.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 213aada51a477257df0b079c95e74610854b5a4f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689580"
---
# <a name="access-to-private-addresses-by-security-role"></a>Accedere a indirizzi privati per ruolo di sicurezza


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Uscita**

Dopo che un cliente duplica un ruolo di sicurezza e accede con quel nuovo ruolo, il cliente non può visualizzare indirizzi contrassegnati come privati.

**Risoluzione**

Per risolvere il problema, il cliente deve completare i passaggi seguenti per il ruolo di sicurezza duplicato.

1. Accedere a **Amministrazione organizzazione \> Rubrica globale \> Parametri Rubrica globale**.
2. Nella scheda **Sicurezza ubicazione privata**, spostare il nuovo ruolo di sicurezza dall'elenco **Ruoli disponibili** all'elenco **Ruoli selezionati**.
3. Selezionare **Salva**.

![Pagina dei parametri della rubrica globale.](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
