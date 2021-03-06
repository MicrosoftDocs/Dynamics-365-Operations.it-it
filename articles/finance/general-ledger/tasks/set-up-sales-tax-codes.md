---
title: Impostare i codici IVA
description: In questo argomento viene illustrato come impostare i codici IVA in Dynamics 365 Finance.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c7208fa65905fcc902d9c08b5b90178745e76d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815046"
---
# <a name="set-up-sales-tax-codes"></a>Impostare i codici IVA

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come impostare i codici IVA. I codici IVA vengono creati per ogni imposta indiretta che la persona giuridica è obbligata a calcolare, riscuotere e pagare agli uffici IVA.

In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a **Pannello di navigazione > Imposta > Imposte indirette > IVA > Codici IVA**.
2. Selezionare **Nuovo**.
3. Nel campo **Codice IVA** digitare un valore.
4. Digitare un valore nel campo **Nome**.
5. Selezionare un **periodo di liquidazione** aprendo l'elenco a discesa per specificare in che ufficio IVA e in quali intervalli l'IVA deve essere dichiarata e pagata.
6. Selezionare un **gruppo di registrazione contabile** per specificare i conti principali per registrare l'IVA nella contabilità generale.
7. Espandere la Scheda dettaglio **Calcolo**. Sono inclusi più campi che controllano la modalità di calcolo degli importi IVA. Completare questi campi in base alle esigenze.  
8. Nel **Riquadro azioni** nella parte superiore dell'interfaccia, selezionare **Codice IVA**.
9. Selezionare **Valori**.
10. Immettere il valore per questo codice IVA nella colonna **valore**.
    - Nella Scheda dettaglio **Calcolo**, nel campo Origine, se Importo unitario è selezionato, il valore verrà moltiplicato per la quantità della transazione per calcolare l'importo IVA.  Se il codice IVA non è un'imposta basata sull'unità, il valore è una percentuale applicata all'origine per il codice IVA per calcolare l'importo IVA.     
11. Selezionare **Salva**.
12. Chiudere la pagina.
13. Selezionare **Salva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]