---
title: Esempio di elaborazione di lettere di sollecito
description: Questo articolo illustra un esempio che mostra il processo di creazione, stampa e registrazione di lettere di sollecito.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 502a026f2070e92a017733ce2c37bf357eaa10ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908156"
---
# <a name="process-collection-letters-example"></a>Esempio di elaborazione di lettere di sollecito

[!include [banner](../../includes/banner.md)]

Questo articolo illustra un esempio che mostra il processo di creazione, stampa e registrazione di lettere di sollecito. L'esempio è basato sull'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** in Credito e riscossioni. Utilizza i dati della società dimostrativa USMF e di un nuovo cliente, US-045.

Per iniziare, selezionare **Contabilità clienti \> Clienti \> Tutti i clienti**, selezionare **Nuovo** e quindi immettere le informazioni necessarie per creare il cliente US-045.

Al termine, procedere come segue.

1. Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Imposta la sequenza lettere di sollecito** e impostare la sequenza delle lettere di sollecito come mostrato nella seguente tabella assegnata al profilo di registrazione cliente.

|     Codice lettera di sollecito      |     Descrizione                           |     Valuta      |     Conto   principale        |     Addebito   in valuta     |     Minimo   oltre        |     Blocco   giorni      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     Lettera di   sollecito 1         |     Seconda   notifica a pagamento        |     USD           |                           |     0,00                  |     0,00                  |     2                 |
|     Lettera di   sollecito 2         |     Seconda   notifica a pagamento        |     USC           |     403150                |     20.00                 |     10.00                 |     3                 |
|     Incasso                    |     Notifica   finale a pagamento         |     USD           |     403150                |     50.00                 |     100.00                |     15                |

La figura seguente mostra come le informazioni presenti nella tabella apparirebbero nella pagina **Lettere di sollecito**. 

[![Impostare una sequenza di lettere di sollecito.](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)

 È ora necessario impostare i due parametri richiesti per questo esempio.

2. Selezionare **Crediti e riscossioni \> Impostazioni \> Parametri contabilità clienti** e procedere come segue:

    1. Nella scheda **Riscossioni**, impostare l'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** su **Sì**.
    2. Assicurarsi che il campo **Crea lettera di sollecito per** sia impostato su **Cliente**.

    [![Impostare parametri di contabilità clienti per crediti e riscossioni.](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)

3. Selezionare **Contabilità clienti \> Fatture \> Tutte le fatture a testo libero**, selezionare **Nuovo** e quindi procedere come segue:

    1. Nel campo **Conto cliente** selezionare **US-045**.
    2. Nel campo **Data fattura** immettere **15/1/2021**.
    3. Nel campo **Data di scadenza** immettere **16/1/2021**.
    4. Nella Scheda dettaglio **Righe fattura** nel campo **Account principale**, immettere **401100**.
    5. Nel campo **Prezzo unitario** immettere **500.00**.
    6. Selezionare **Registra**.

    È ora necessario immettere due note di credito per il cliente.

4. Selezionare **Nuovo** e procedere come segue:

    1. Nel campo **Conto cliente** selezionare **US-045**.
    2. Nel campo **Data fattura** immettere **15/1/2021**.
    3. Nel campo **Data di scadenza** immettere **16/1/2021**.
    4. Nella Scheda dettaglio **Righe fattura** nel campo **Account principale**, immettere **401100**.
    5. Nel campo **Prezzo unitario** immettere **-100,00**.
    6. Selezionare **Registra**.

5. Ripetere il passaggio 4, ma immettere **-200,00** nel campo **Prezzo unitario**.
6. Selezionare **Contabilità clienti \> Clienti \> Tutti i clienti** e selezionare il cliente **US-045**. Quindi, nel riquadro Azioni, selezionare **Transazioni \> Transazioni** per esaminare le transazioni dei clienti registrate in precedenza.

    [![Revisione delle transazioni cliente registrate.](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)

    È ora necessario creare lettere di sollecito per il cliente US-045.

7. Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Crea lettere di sollecito** e procedere come segue.

    1. Impostare le opzioni **Fattura** e **Nota di credito** su **Sì**.

        Per impostazione predefinita, il campo **Lettera di sollecito** deve essere impostato su **Sollecito per cliente**.

    2. Nel campo **Data della lettera di sollecito** immettere **19/1/2021**.
    3. Nella Scheda dettaglio **Record da includere**, selezionare **Filtro** e nel campo **Account cliente** aggiungere il cliente **US-045**.
    4. Selezionare **OK**.
    5. Selezionare **OK** per creare lettere di sollecito.

8. Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Esamina ed elabora lettere di sollecito** e procedere come segue.

    1. Da notare che il codice di lettera di sollecito nell'intestazione e nelle righe della transazione è **Lettera di sollecito 1**, poiché questa lettera di sollecito è la prima lettera di sollecito nella sequenza (per visualizzare le righe della transazione, potrebbe essere necessario selezionare la Scheda dettaglio **Transazioni**).

   [![Verificare che lo stesso codice di lettera di sollecito sia visualizzato nell'intestazione e nelle righe.](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)

    2. Nel riquadro Azioni selezionare **Registra**.
    3. Nel campo **Data di registrazione** immettere **19/1/2021**.

    È ora necessario creare di nuovo lettere di sollecito per il cliente US-045.

9. Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Crea lettere di sollecito** e procedere come segue.

    1. Impostare le opzioni **Fattura** e **Nota di credito** su **Sì**.

        Per impostazione predefinita, il campo **Lettera di sollecito** deve essere impostato su **Sollecito per cliente**.

    2. Nel campo **Data della lettera di sollecito** immettere **23/1/2021**.
    3. Nella Scheda dettaglio **Record da includere**, selezionare **Filtro** e nel campo **Account cliente** aggiungere il cliente **US-045**.
    4. Selezionare **OK**.
    5. Selezionare **OK** per creare lettere di sollecito.

10. Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Esamina ed elabora lettere di sollecito** e procedere come segue.

    1. Da notare che il codice di lettera di sollecito nell'intestazione è **Lettera di sollecito 1**. Tuttavia, il codice nelle righe della transazione è **Lettera di sollecito 2**.

   [![Verificare che codici di lettera di sollecito differenti siano visualizzati nell'intestazione e nelle righe.](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)

  I codici differiscono poiché l'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** è impostata su **Sì**.

  2. Non registrare questa lettera di sollecito.

11. Selezionare **Crediti e le riscossioni \> Impostazioni \> Parametri contabilità clienti** e nella scheda **Solleciti**, impostare l'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** su **No**.

    [![Impostare l'opzione Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito su No.](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)

    È ora necessario creare di nuovo lettere di sollecito per il cliente US-045.

12. Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Crea lettere di sollecito** e procedere come segue.

    1. Impostare le opzioni **Fattura** e **Nota di credito** su **Sì**.

        Per impostazione predefinita, il campo **Lettera di sollecito** deve essere impostato su **Sollecito per cliente**.

    2. Nel campo **Data della lettera di sollecito** immettere **23/1/2021**.
    3. Nella Scheda dettaglio **Record da includere**, selezionare **Filtro** e nel campo **Account cliente** aggiungere il cliente **US-045**.
    4. Selezionare **OK**.
    5. Selezionare **OK** per creare lettere di sollecito.

13. Selezionare **Crediti e riscossioni \> Lettera di sollecito \> Esamina ed elabora lettere di sollecito**. Da notare che il codice di lettera di sollecito nell'intestazione e nelle righe della transazione è **Lettera di sollecito 2**.

    [![Visualizzare di nuovo lo stesso codice di lettera di sollecito nell'intestazione e nelle righe.](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)

    Lo stesso codice appare in entrambe le posizioni poiché l'opzione **Ignora pagamenti e note di credito durante il calcolo del codice di lettera di sollecito** è ora impostata su **No**.
