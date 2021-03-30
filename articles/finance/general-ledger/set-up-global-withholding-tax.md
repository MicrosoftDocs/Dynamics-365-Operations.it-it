---
title: Impostare la ritenuta d'acconto globale
description: Questo argomento elenca i passaggi per impostare la ritenuta d'acconto globale per vendite e acquisti.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 00c472e90f4926c52ffe9b19661e68cbfa6bd493
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204835"
---
# <a name="set-up-global-withholding-tax"></a>Impostare la ritenuta d'acconto globale

Questo argomento elenca i passaggi per impostare la ritenuta d'acconto globale per vendite e acquisti. 

1. Configurare le autorità di ritenuta d'acconto nella pagina **Autorità ritenuta d'acconto**.

2. Configurare i periodi di liquidazione ritenuta alla fonte nella pagina **Periodi di liquidazione della ritenuta d'acconto**.

3. Configurare il gruppo di registrazione della contabilità generale nella pagina **Ritenuta d'acconto > gruppo registrazione contabile**.

   > [!Note] 
   >
   > Il conto **Ritenuta d'acconto** verrà assegnato a un account principale con il **Tipo di registrazione** della ritenuta d'acconto. Il conto **Offset ritenuta d'acconto** verrà inoltre assegnato a un conto principale con il **Tipo di registrazione** "offset della ritenuta d'acconto". Vai a **Contabilità generale > Piano dei conti> Conti > Conti principali**, configura il **Tipo di registrazione** nel sottomodulo **Convalida della registrazione** per i conti principali.

4. Configurare i codici di ritenuta d'acconto nella pagina **Codici ritenuta d'acconto**.

5. Configurare i gruppi di ritenuta d'acconto nella pagina **Gruppi ritenuta d'acconto**.

6. Configurare i tipi di ricavi con ritenuta d'acconto nella pagina **Ricavi ritenuta d'acconto** **tipi**.

7. Configurare i gruppi di ritenuta d'acconto nella pagina **Gruppi ritenute d'acconto articoli**.

8. Configurare **Importo minimo della fattura** nella pagina **Parametri di contabilità generale > Ritenuta d'acconto**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]