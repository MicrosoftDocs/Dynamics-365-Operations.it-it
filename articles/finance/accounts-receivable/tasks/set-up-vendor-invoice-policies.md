---
title: Impostare criteri di fatture fornitore
description: In questo argomento viene spiegato come impostare i criteri di fatture fornitore.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58518f5291b70c63506c20717034daff0268901b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444802"
---
# <a name="set-up-vendor-invoice-policies"></a>Impostare criteri di fatture fornitore

[!include [banner](../../includes/banner.md)]

In questo argomento viene spiegato come impostare i criteri di fatture fornitore. I criteri fattura fornitore vengono eseguiti quando si registra una fattura fornitore tramite la pagina Fattura fornitore e quando si apre la pagina violazioni dei criteri per fatture fornitore. È inoltre possibile configurare il flusso di lavoro delle fatture fornitore affinché i criteri fatture fornitore vengano eseguiti ogni volta che si invia una fattura al flusso di lavoro. 

- I criteri fatture fornitore non sono applicabili alle fatture create nel registro fatture o nel giornale di registrazione fatture.  
- La convalida di abbinamento fatture non utilizza i criteri fatture fornitore, ma viene invece impostata nella pagina Parametri contabilità fornitori.  
- Questa registrazione utilizza la società dimostrativa USMF. Il ruolo di responsabile della contabilità fornitori o del responsabile della contabilità eseguirebbe le operazioni. Prima di iniziare, assicurarsi che sia selezionata la chiave di configurazione Abbinamento fatture.


## <a name="prepare-to-create-vendor-invoice-policies"></a>Eseguire le operazioni preliminari alla creazione dei criteri fatture fornitore
1. Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione > Parametri contabilità fornitori**.
2. Selezionare la scheda **Convalida fattura**.
3. Selezionare o deselezionare la casella di controllo **Aggiorna automaticamente lo stato dell'intestazione fattura**.
4. Selezionare **OK**.
5. Nel campo **Registra fattura con discrepanze**, selezionare un'opzione.
6. Chiudere la pagina.
7. Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione criteri > Criteri fatture fornitore**.
8. Selezionare **Parametri**.
9. Selezionare **Aggiungi**.
10. Chiudere la pagina per tornare alla home page.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>Creare i tipi di regole dei criteri per fatture fornitore
1. Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione criteri > Tipi di regole dei criteri per le fatture fornitore**.
2. Selezionare **Nuovo**.
3. Immettere valori nei campi **Nome regola** e **Descrizione**.
4. Nel campo **Nome query**, selezionare il pulsante a discesa per aprire la ricerca, quindi selezionare il record desiderato.
5. Selezionare **Salva**.
6. Chiudere la pagina per tornare alla home page.

## <a name="define-a-vendor-invoice-policy"></a>Definire una regola dei criteri fattura fornitore
1. Andare a **Pannello di navigazione > Moduli > Contabilità fornitori > Impostazione criteri > Criteri fatture fornitore**.
2. Selezionare **Nuovo**.
3. Immettere valori nei campi **Nome** e **Descrizione**.
4. Espandere o comprimere la sezione **Organizzazioni criteri**.
5. Nella struttura selezionare **Contoso Entertainment Systems USA**.
6. Selezionare **Aggiungi**.
7. Espandere o comprimere la sezione **Regole dei criteri**.
8. Selezionare **Crea regola dei criteri**.
9. Nel campo **Descrizione regola dei criteri**, immettere un valore.
10. Selezionare **Filtro**.
11. Selezionare **Aggiungi**. Selezionare il record desiderato.
12. Nei campi **Tabella**, **Tabella derivata**, **Campo** selezionare o immettere le opzioni dai menu a discesa.
13. Chiudere la pagina.
14. Digitare un valore nel campo **Criteri**.
15. Selezionare **OK**.
16. Selezionare **OK**.
17. Chiudere le pagine per tornare alla home page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]