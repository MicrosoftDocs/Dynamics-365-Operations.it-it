---
title: Domande frequenti sulla creazione di report finanziari
description: In questo argomento vengono fornite alcune risposte alle domande frequenti sulla creazione di report finanziari.
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
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266635"
---
# <a name="financial-reporting-faq"></a>Domande frequenti sulla creazione di report finanziari

In questo argomento vengono fornite risposte alle domande frequenti sulla creazione di report finanziari.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>Come si limita l'accesso a un report utilizzando la sicurezza dell'albero?

L'esempio seguente mostra come limitare l'accesso a un report utilizzando la sicurezza dell'albero.

La società dimostrativa USMF dispone di un report **stato patrimoniale** che non desidera rendere accessibile a tutti gli utenti dei report finanziari. È possibile utilizzare la sicurezza dell'albero per limitare l'accesso a un singolo report in modo che solo specifici utenti possano accedervi.

1. Accedere a Financial Reporter Report Designer.
2. Selezionare **File \> Nuovo \> Definizione di albero** per creare una nuova definizione di albero.
3. Fare doppio tocco o doppio clic sulla riga **Riepilogo** nella colonna **Sicurezza unità**.
4. Selezionare **Utenti e gruppi**.
5. Selezionare gli utenti o i gruppi che devono accedere al report.
6. Selezionare **Salva**.
7. Nella definizione di report, aggiungere la nuova definizione di albero.
8. Nella definizione di albero, selezionare **Impostazione**. Quindi, in **Selezione unità gerarchica** selezionare **Includi tutte le unità**.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>Come identificare quali conti non corrispondono ai saldi?

Se si dispone di un report che non corrisponde ai saldi, utilizzare le seguenti procedure per identificare ciascun conto e scostamento.

### <a name="in-financial-reporter-report-designer"></a>In Financial Reporter Report Designer

1. Creare una nuova definizione di riga.
2. Selezionare **Modifica \> Inserisci righe da dimensioni**.
3. Selezionare **MainAccount**.
4. Selezionare **OK**.
5. Salvare la definizione di riga.
6. Creare una nuova definizione di colonna.
7. Creare una nuova definizione di report.
8. Selezionare **Impostazioni** e deselezionare questa opzione.
9. Generare il report. 
10. Esportare il report in Microsoft Excel.

### <a name="in-dynamics-365-finance"></a>In Dynamics 365 Finance

1. Andare a **Contabilità generale \> Richieste di informazioni e report \> Bilancio di verifica**.
2. Impostare i seguenti campi:

    - **Dal** - Immettere la data di inizio dell'anno fiscale.
    - **Al** - Immettere la data per la quale si sta generando il report.
    - **Dimensione finanziaria** - Impostare questo campo su **Set di conti principali**.

3. Selezionare **Calcola**.
4. Esportare il report in Excel.

Ora si possono copiare i dati dal report di Excel di Financial Reporter nel report **Bilancio di verifica** per confrontare le colonne **Saldo di chiusura**.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Quando si progetta un report in Report Designer o quando si genera un report finanziario, viene visualizzato il seguente messaggio: "Impossibile completare l'operazione a causa di un problema nel framework del provider di dati". Come si deve rispondere?

Il messaggio indica che si è verificato un problema quando il sistema ha tentato di recuperare i metadati finanziari dal data mart mentre veniva utilizzato il report finanziario. Ci sono due modi per rispondere a questo problema:

- Rivedere lo stato di integrazione dei dati andando su **Strumenti \> Stato di integrazione** in Report Designer. Se l'integrazione è incompleta, attendere che venga completata. Quindi ripetere l'operazione che si stava facendo quando è stato visualizzato il messaggio.
- Contattare l'assistenza per identificare e risolvere il problema. È possibile che siano presenti dati incoerenti nel sistema. I tecnici dell'assistenza possono aiutare a identificare il problema sul server e a trovare i dati specifici che potrebbero richiedere un aggiornamento.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
