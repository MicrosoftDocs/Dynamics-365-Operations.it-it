---
title: Accedere a indirizzi privati per ruolo di sicurezza
description: Questo articolo spiega come risolvere quando un cliente non può accedere agli indirizzi privati.
author: twheeloc
ms.date: 09/13/2022
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
ms.openlocfilehash: 7c1db052937b03817f22b37c50b9f1b319579cb2
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702105"
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
