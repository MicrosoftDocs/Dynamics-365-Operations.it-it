---
title: Domande frequenti sulla creazione di report finanziari
description: In questo argomento vengono riportate le domande relative alla creazione di report finanziari poste da altri utenti.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923027"
---
# <a name="financial-reporting-faq"></a>Domande frequenti sulla creazione di report finanziari 

In questo argomento vengono fornite risposte alle domande frequenti sulla creazione di report finanziari. 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Come si limita l'accesso a un report utilizzando la sicurezza dell'albero?

L'esempio seguente mostra come limitare l'accesso a un report utilizzando la sicurezza dell'albero.

La società dimostrativa USMF dispone di un report stato patrimoniale che non desidera rendere accessibile a tutti gli utenti dei report finanziari. È possibile utilizzare la sicurezza dell'albero per limitare l'accesso a un singolo report in modo che solo determinati utenti possano utilizzarlo. Per limitare l'accesso, seguire questi passaggi: 

1. Accedere a Financial Reporter Report Designer.
2. Creare una nuova definizione di albero. Andare a **File> Nuovo> Definizione di albero**.
3. Fare doppio clic sulla riga **Riepilogo** nella colonna **Sicurezza unità**.
4. Selezionare **Utenti e gruppi**.  
5. Selezionare gli utenti o i gruppi che devono accedere a questo report. 
6. Selezionare **Salva**.
7. Nella definizione di report, aggiungere la nuova definizione di albero.
8. Nella definizione di albero, selezionare **Impostazione**. In **Selezione unità gerarchica** selezionare **Includi tutte le unità**.

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a>Come identificare quali conti non corrispondono ai saldi?

Se si dispone di un report che non corrisponde ai saldi, ecco alcuni passaggi che è possibile eseguire per identificare ognuno dei conti e degli scostamenti. 

**Financial Reporter Report Designer**
1. In Financial Reporter Report Designer creare una nuova definizione di riga. 
2. Selezionare **Modifica > Inserisci righe da dimensioni**.
3. Selezionare **MainAccount**.  
4. Selezionare **OK**.
5. Salvare la definizione di riga.
6. Creare una nuova definizione di colonna
7. Creare una nuova definizione di report.
8. Selezionare **Impostazioni** e deselezionare questa opzione.  
9. Generare il report. 
10. Esportare il report in Microsoft Excel.

**Dynamics 365 Finance** 
1. In Dynamics 365 Finance andare a **Contabilità generale > Richieste di informazioni e report > Bilancio di verifica**.
2. Impostare i parametri riportati di seguito.
   - **Dal** - Immettere l'inizio dell'anno fiscale.
   - **Al** - Immettere la data per la quale si sta generando il report.
   - **Dimensione finanziaria** - Imposta questo campo su **Set di conti principali**.
 3. Selezionare **Calcola**.
 4. Esportare il report in Microsoft Excel.

Ora si possono copiare i dati dal report di Excel dello strumento di creazione report finanziari nel report Bilancio di verifica per confrontare le colonne **Saldo finale**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]