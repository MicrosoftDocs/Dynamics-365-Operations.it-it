---
title: Personalizzare l'interfaccia di esecuzione dell'area di produzione
description: Questo argomento spiega come estendere i moduli correnti o creare nuovi moduli e pulsanti per l'interfaccia di esecuzione del piano di produzione.
author: johanhoffmann
ms.date: 05/04/2022
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ad5037442f27a5068b38613655591f1298808eac
ms.sourcegitcommit: 28537b32dbcdefb1359a90adc6781b73a2fd195e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712945"
---
# <a name="customize-the-production-floor-execution-interface"></a>Personalizzare l'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]

Gli sviluppatori possono estendere i moduli correnti o creare i loro moduli e pulsanti per l'interfaccia di esecuzione del piano di produzione. Dopo aver aggiunto il codice per questi nuovi elementi, gli amministratori o i responsabili dello shop floor possono aggiungerli facilmente all'interfaccia utilizzando i controlli di configurazione standard.

Ad esempio, ecco alcune delle possibili soluzioni se sono necessarie nuove colonne in un modulo principale:

- Estendi il modulo `JmgProductionFloorExecutionMainGrid` e aggiungi i campi desiderati.
- Crea un nuovo modulo e aggiungilo come nuova visualizzazione principale (scheda).

## <a name="add-a-new-button-action"></a>Aggiungere un nuovo pulsante (azione)

Per aggiungere un nuovo pulsante (azione), segui questi passaggi per creare una classe che implementi la tua azione personalizzata.

1. Crea una nuova classe denominata `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`, dove:

    - `<ExtensionPrefix>` identifica in modo univoco la soluzione, in genere utilizzando il nome della società.
    - `<ActionName>` è un nome univoco per la classe. In genere identifica il tipo di azione.

1. La nuova classe deve estendere la classe `JmgProductionFloorExecutionAction`.
1. Sostituisci tutti i metodi necessari.

Ad esempio, guarda il codice per le seguenti classi:

- `JmgProductionFloorExecutionBreakAction` – Una classe per un'azione semplice che non richiede alcun record.
- `JmgProductionFloorExecutionReportFeedbackAction` – Una classe che fornisce funzionalità più complesse.

Al termine, il nuovo pulsante (azione) verrà automaticamente elencato nella pagina **Progettazione schede** in Microsoft Dynamics 365 Supply Chain Management. Qui, tu (o un amministratore o un responsabile del piano) puoi facilmente aggiungerlo alla barra degli strumenti principale o secondaria, proprio come puoi aggiungere i pulsanti standard. Per istruzioni, vedi [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md).

## <a name="add-a-new-main-view"></a>Aggiungere una nuova visualizzazione principale

1. Crea un nuovo modulo con gli elementi e le funzionalità desiderati. Tieni presente che questo modulo è un nuovo modulo, non un'estensione. Assegna un nome al modulo `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`, dove:

    - `<ExtensionPrefix>` identifica in modo univoco la soluzione, in genere utilizzando il nome della società.
    - `<FormName>` è un nome univoco per il modulo.

1. Crea una voce di menu denominata `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`.
1. Crea un'estensione denominata `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, dove il metodo `getMainMenuItemsList` viene esteso aggiungendo la nuova voce di menu all'elenco. Il seguente codice illustra un esempio.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionMenuItemProvider))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

Al termine, la nuova visualizzazione principale verrà automaticamente elencata nella casella combinata **Visualizzazione principale** della pagina **Schede di progettazione** in Supply Chain Management. Qui, tu (o un amministratore o un responsabile del piano) puoi facilmente aggiungerlo a schede nuove o esistenti proprio come puoi aggiungere le visualizzazioni principali standard. Per istruzioni, vedi [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md).

## <a name="add-a-details-view"></a>Aggiungere una visualizzazione dei dettagli

1. Crea un nuovo modulo con gli elementi e le funzionalità desiderati. Tieni presente che questo modulo è nuovo, non un'estensione. Assegna un nome al modulo `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`, dove: 

    - `<ExtensionPrefix>` identifica in modo univoco la soluzione, in genere utilizzando il nome della società.
    - `<FormName>` è un nome univoco per il modulo.

1. Crea una voce di menu denominata `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`.
1. Crea un'estensione denominata `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, dove il metodo `getDetailsMenuItemList` viene esteso aggiungendo la nuova voce di menu all'elenco.

Al termine, la nuova visualizzazione dettagliata verrà automaticamente elencata nella casella combinata **Visualizzazione dettagli** della pagina **Schede di progettazione** in Supply Chain Management. Qui, tu (o un amministratore o un responsabile del piano) puoi facilmente aggiungerlo a schede nuove o esistenti proprio come puoi aggiungere le visualizzazioni dettagli standard. Per istruzioni, vedi [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md).

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>Aggiungere un tastierino numerico a un modulo o a una finestra di dialogo

L'esempio seguente mostra come aggiungere tastierini numerici a un modulo.

1. Il numero di controller del tastierino numerico che ogni modulo contiene deve essere uguale al numero di tastierini numerici in quel modulo.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. Imposta il comportamento di ciascun controller del tastierino numerico e collega ciascun controller del tastierino numerico a una parte del modulo del tastierino numerico.

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>Utilizza un tastierino numerico come finestra di dialogo popup

L'esempio seguente mostra un modo per impostare un controller del tastierino numerico per una finestra di dialogo popup.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

L'esempio seguente mostra un modo per chiamare la finestra di dialogo popup.

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="add-a-date-and-time-controls-to-a-form-or-dialog"></a>Aggiungere un controllo di data e ora a un modulo o finestra di dialogo

Questa sezione mostra come aggiungere i controlli di data e ora a un modulo o a una finestra di dialogo. I controlli touch-friendly di data e ora consentono ai lavoratori di specificare date e orari. Gli screenshot seguenti mostrano come vengono generalmente visualizzati i controlli sulla pagina. Il controllo orario prevede sia la versione 12 ore che quella 24 ore; la versione mostrata seguirà la preferenza impostata per l'account utente con cui è in esecuzione l'interfaccia.

![Esempio di controllo di data.](media/pfe-customize-date-control.png "Esempio di controllo di data")

![Esempio di controllo di ora con orologio a 12 ore.](media/pfe-customize-time-control-12h.png "Esempio di controllo di ora con orologio a 12 ore")

![Esempio di controllo di ora con orologio a 24 ore.](media/pfe-customize-time-control-24h.png "Esempio di controllo di ora con orologio a 24 ore")

Nella procedura seguente viene illustrato un esempio di come aggiungere i controlli di data e ora a un modulo.

1. Aggiungi un controller al modulo per ogni controllo di data e ora che il modulo deve contenere. (Il numero di controllori deve essere uguale al numero di controlli di data e ora nel modulo.)

    ```xpp
    private JmgProductionFloorExecutionDateTimeController  dateFromController; 
    private JmgProductionFloorExecutionDateTimeController  dateToController; 
    private JmgProductionFloorExecutionDateTimeController  timeFromController; 
    private JmgProductionFloorExecutionDateTimeController  timeToController;
    ```

1. Dichiara le variabili obbligatorie (di tipo `utcdatetime`).

    ```xpp
    private utcdatetime fromDateTime;
    private utcdatetime toDateTime;
    ```

1. Crea metodi in cui il datetime verrà aggiornato dai controller datetime. L'esempio seguente mostra tale metodo.

    ```xpp
    private void setFromDateTime(utcdatetime _value)
        {
            fromDateTime = _value;
        }
    ```

1. Imposta il comportamento di ciascun controller di datetime e collega ciascun controller a una parte del modulo. L'esempio seguente mostra come configurare i dati per i controlli di data e ora da. È possibile aggiungere un codice simile per i controlli di data e ora (non mostrati).

    ```xpp
    /// <summary>
    /// Initializes all date and time controllers, defines their behavior, and connects them with the form parts.
    /// </summary>
    private void initializeDateControlControllers()
    {
        dateFromController = new JmgProductionFloorExecutionDateTimeController();
        dateFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        dateFromController.parmDateTimeValue(fromDateTime);
    
        timeFromController = new JmgProductionFloorExecutionDateTimeController();
        timeFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        timeFromController.parmDateTimeValue(fromDateTime);
        
        DateFromFormPart.getPartFormRun().setDateControlController(dateFromController, timeFromController);
        TimeFromFormPart.getPartFormRun().setTimeControlController(timeFromController, dateFromController);
        
        ...

    }
    ```

    Se tutto ciò di cui hai bisogno è un controllo della data, puoi saltare l'impostazione del controllo dell'ora e invece impostare semplicemente il controllo della data come mostrato nell'esempio seguente:

    ```xpp
    {
        dateFromController = new JmgProductionFloorExecutionDateTimeController();
        dateFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        dateFromController.parmDateTimeValue(fromDateTime);
    
        DateFromFormPart.getPartFormRun().setDateControlController(dateFromController, null);
    }
    ```

## <a name="additional-resources"></a>Risorse aggiuntive

- [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-styles.md)
- [Progettare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-tabs.md)
