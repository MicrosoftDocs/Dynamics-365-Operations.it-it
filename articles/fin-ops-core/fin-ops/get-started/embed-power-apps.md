---
title: Incorporare Power Apps
description: In questo argomento viene descritto come incorporare Power Apps nel client per aumentare la funzionalità del prodotto.
author: jasongre
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 755a30f89725ca0a7e1c14252984c617d6ba280e
ms.sourcegitcommit: 4162d9ef4239c9d4e5297b8aaa903dd54f9cafc3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "2824495"
---
# <a name="embed-microsoft-power-apps"></a>Incorporare Microsoft Power Apps

[!include [banner](../includes/banner.md)]

L'aggiornamento 14 della piattaforma supporta l'integrazione con Microsoft Power Apps, un servizio rivolto a utenti non tecnici e sviluppatori che consente di creare app aziendali per dispositivi mobili, tablet e Web senza scrivere codice. Power Apps sviluppate dall'utente, l'organizzazione o l'ecosistema più ampio potranno quindi essere inclusi nelle app Finance and Operations per aumentare la funzionalità del prodotto. Ad esempio, è possibile creare una Power App per completare le app Finance and Operations con informazioni recuperate da un altro sistema.

Per ulteriori informazioni sull'integrazione di Power Apps, guardare il breve video [Come integrare Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-power-app-to-a-page"></a>Aggiunta di una Power App incorporata in una pagina

### <a name="overview"></a>Panoramica

Prima di incorporare una Power App nel client, è necessario trovare o creare una Power App con gli oggetti visivi e/o le funzionalità desiderati. Il processo dettagliato per la creazione di una Power App non viene descritto in questo argomento. L'argomento che [introduce le Power Apps](https://docs.microsoft.com/powerapps/getting-started) è un'ottima risorsa per acquisire familiarità con le Power Apps.

Quando si è pronti a incorporare una specifica Power App, è possibile scegliere tra uno dei due modi di accesso alla Power App in una pagina, a seconda di quale è più appropriato per lo scenario corrente. Il primo modo è tramite il pulsante Power Apps aggiunto al riquadro azioni standard. Le Power Apps aggiunte tramite questo meccanismo saranno visualizzate come voci di menu nel pulsante di menu Power Apps. Se una di queste voci di menu viene selezionata, aprirà un riquadro laterale contenente la Power App incorporata. In alternativa, è possibile scegliere di visualizzare una Power App direttamente in una pagina come nuova scheda, Scheda dettaglio o sezione in un'area di lavoro.

Durante la configurazione della Power App incorporata, è possibile selezionare un singolo campo che si desidera inviare come input alla Power App. Ciò consente alla Power App di essere reattiva in base ai dati correntemente visualizzati.

### <a name="details"></a>Dettagli

Le istruzioni seguenti mostrano come incorporare una Power App Web nel client Web.

1. Passare alla pagina in cui si desidera incorporare la Power App. Sarà la stessa pagina contenente tutti i dati che devono essere passati alla Power App come input.
2. Aprire il riquadro **Inserisci una Power App**:

    - Fare clic su **Opzioni**, quindi selezionare **Personalizza modulo**. Sotto il menu **Inserisci**, scegliere **Power App**. Infine, selezionare la regione in cui si desidera aggiungere la Power App. Se si desidera incorporare la Power App sotto il pulsante di menu Power Apps, scegliere il riquadro azioni. Se si desidera incorporare la Power App direttamente nella pagina, scegliere la scheda, la Scheda dettaglio, il pannello o la sezione (se in un'area di lavoro) appropriata.
    - Se si accederà alla Power App utilizzando il pulsante di menu Power Apps, si può scegliere di fare clic sul pulsante di menu **Power Apps** nel riquadro delle azioni standard e quindi selezionare **Inserisci una Power App**.

3. Configurare la Power App incorporata:

    - Il campo **Nome** indica il testo visualizzato per il pulsante o la scheda che conterrà la Power App incorporata. È spesso possibile che si intenda ripetere il nome della Power App in questo campo.
    - **ID app** è il GUID per la Power App che si desidera incorporare. Per ripristinare questo valore, trovare la Power App in [web.Power Apps.com](https://web.powerapps.com) e quindi individuare il campo **ID app** sotto **Dettagli**.
    - Per **Dati di input per la Power App**, si può scegliere di selezionare il campo che contiene i dati da passare alla Power App come input. Vedere la sezione [Creazione di una Power App che sfrutta i dati inviati dalle app Finance and Operations](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations-apps) più avanti in questo argomento per dettagli su come la Power App può accedere ai dati inviati dalle app Finance and Operations.
    - Scegliere la **Dimensione dell'applicazione** che corrisponde al tipo di Power App che si intende incorporare. Selezionare **Ridotte** per le Power Apps create per dispositivi mobili e **Ampie** per le Power Apps create per tablet. Ciò garantisce l'assegnazione di una quantità di spazio sufficiente per la Power App incorporata.
    - La Scheda dettaglio **Persone giuridiche** consente di scegliere le persone giuridiche per le quali la Power App è disponibile. Il valore predefinito comporta la visualizzazione della Power App in tutte le persone giuridiche.

4. Dopo avere confermato la correttezza della configurazione, fare clic su **Inserisci** per incorporare la Power App nella pagina. Verrà richiesto di aggiornare il browser per visualizzare la Power App incorporata.

## <a name="sharing-an-embedded-power-app"></a>Condivisione di una Power App incorporata

Dopo avere incorporato una Power App in un pagina e averne verificato il corretto funzionamento con il contesto di dati, è possibile che si desideri condividere la Power App incorporata con altri utenti del sistema. Questo può essere realizzato in due modi diversi utilizzando le capacità di personalizzazione del prodotto:

- Lo scenario consigliato è attraverso l'amministratore di sistema, che può inviare una personalizzazione a tutti gli utenti o a un sottoinsieme di utenti.
- In alternativa, è possibile esportare le personalizzazioni della pagina, inviarle a uno o più utenti e chiedere a ciascuno di questi utenti di importarle. L' opzione Gestisci sulla barra degli strumenti di personalizzazione consente di esportare e importare le personalizzazioni.

Per ulteriori informazioni sulle funzionalità di personalizzazione nel prodotto e su come utilizzarle, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

## <a name="building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Creazione di una Power App che sfrutta i dati inviati dalle app Finance and Operations

Una parte importante della creazione di una Power App che verrà incorporata nella app Finance and Operations sta utilizzando i dati di input delle app Finance and Operations. Nella Power App, è possibile accedere a tali dati di input utilizzando la variabile Param("EntityId").

Ad esempio, nella funzione OnStart della Power App, è possibile impostare i dati di input dalle app Finance and Operations su una variabile come la seguente:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-power-app"></a>Visualizzazione di una Power App incorporata

Per visualizzare una Power App incorporata in una pagina della app Finance and Operations, accedere a una pagina con una Power App incorporata. Da notare che alle Power Apps è possibile accedere tramite il pulsante Power Apps nel riquadro azioni standard, oppure che possono essere visualizzate direttamente nella pagina come nuova scheda, Scheda dettaglio, pannello o come nuova sezione in un'area di lavoro. Quando un utente tenta per la prima volta di caricare una Power App in una pagina, gli viene richiesto di accedere alle Power Apps per assicurarsi di disporre delle autorizzazioni necessarie per utilizzare la Power App.

## <a name="editing-an-embedded-power-app"></a>Modifica di una Power App incorporata

Dopo che una Power App è stata incorporata in una pagina, potrebbe essere necessario apportare alcune modifiche alla configurazione della Power App. Ad esempio, si desidera modificare l'etichetta associata alla Power App incorporata oppure è stata creata una nuova versione di una Power App ed è necessario aggiornare l'ID App per puntare alla Power App più recente.

Per modificare la configurazione di una Power App incorporata, seguire questi passaggi:

1. Passare al riquadro **Modifica Power App**.

    - Se si accede alla Power App incorporata tramite il pulsante di menu Power Apps, fare clic con il pulsante destro del mouse sul pulsante di menu Power Apps e selezionare **Personalizza**. Selezionare la Power App che si desidera configurare dal menu a discesa **Seleziona Power App**.
    - Se la Power App incorporata viene visualizzata direttamente nella pagina, selezionare **Opzioni**, quindi selezionare **Personalizza modulo**. Mediante lo strumento **Seleziona**, fare clic sulla Power App incorporata.

2. Apportare le modifiche necessarie alla configurazione delle Power Apps, quindi fare clic su **Salva**.

## <a name="removing-an-embedded-power-app"></a>Rimozione di una Power App incorporata

Dopo che una Power App è stata incorporata in una pagina, esistono due modi per rimuoverla se necessario:

- Passare al riquadro **Modifica Power App** attenendosi alle istruzioni indicate nella precedente sezione [Modifica di una Power App incorporata](#editing-an-embedded-powerapp) in questo argomento. Verificare che il riquadro visualizzi le informazioni per la Power App incorporata che si desidera rimuovere, quindi fare clic sul pulsante **Elimina**.
- Poiché una Power App incorporata viene salvata come dati di personalizzazione, la cancellazione della personalizzazione della pagina determinerà anche la rimozione di tutte le Power Apps incorporate nella pagina. Tenere presente che la cancellazione della personalizzazione della pagina è permanente e non può essere annullata. Per rimuovere le personalizzazioni in una pagina, selezionare **Opzioni** e fare clic su **Personalizza modulo**. Sotto il menu **Gestisci**, selezionare il pulsante **Cancella**. Dopo avere aggiornato la pagina del browser, tutte le precedenti personalizzazioni della pagina saranno rimosse. Per ulteriori informazioni su come ottimizzare le pagine utilizzando la personalizzazione, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

## <a name="appendix"></a>Appendice

### <a name="developer-control-over-where-a-power-app-can-be-embedded"></a>Controllo dello sviluppatore sulla posizione in cui può essere incorporata una Power App

Per impostazione predefinita, gli utenti possono incorporare Power Apps in qualsiasi pagina, sotto il pulsante di menu Power Apps o direttamente come scheda, Scheda dettaglio, pannello o come nuova sezione in un'area di lavoro. Tuttavia, se necessario, gli sviluppatori possono anche configurare questa funzionalità per consentire solo l'incorporamento delle Power Apps in determinate pagine tramite l'implementazione dei seguenti metodi:

- **isPowerAppPersonalizationEnabled** – Se questo metodo restituisce false per una pagina specifica, il pulsante del menu Power Apps non viene visualizzato e gli utenti non possono incorporare Power Apps nella pagina, neppure come scheda.
- **isPowerAppTabPersonalizationEnabled** – Se questo metodo restituisce false per una pagina specifica, gli utenti non possono incorporare Power Apps direttamente nella pagina come scheda, Scheda dettaglio o sezione panoramica. Gli utenti saranno ancora in grado di incorporare Power Apps tramite il pulsante di menu Power Apps se l'incorporazione è consentita nella pagina.

Nel seguente esempio viene illustrata una nuova classe con i due metodi necessari per configurare l'area in cui è possibile incorporare Power Apps.

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```
