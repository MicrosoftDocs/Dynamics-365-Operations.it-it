---
title: Accesso a indirizzi privati per ruolo di sicurezza
description: In questo argomento viene descritto come risolvere il problema in cui un cliente non può accedere a indirizzi privati.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 58f3322ad64f7de07e17d193ff665bd6536a4070
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897099"
---
# <a name="access-to-private-addresses-by-security-role"></a>Accesso a indirizzi privati per ruolo di sicurezza

**Uscita**

Dopo che un cliente duplica un ruolo di sicurezza e accede con quel nuovo ruolo, il cliente non può visualizzare indirizzi contrassegnati come privati.

**Risoluzione**

Per risolvere il problema, il cliente deve completare i passaggi seguenti per il ruolo di sicurezza duplicato.

1. Accedere a **Amministrazione organizzazione \> Rubrica globale \> Parametri Rubrica globale**.
2. Nella scheda **Sicurezza ubicazione privata**, spostare il nuovo ruolo di sicurezza dall'elenco **Ruoli disponibili** all'elenco **Ruoli selezionati**.
3. Selezionare **Salva**.

![Pagina dei parametri della rubrica globale](media/GAD-parameters.png)
