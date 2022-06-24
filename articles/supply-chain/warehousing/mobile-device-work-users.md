---
title: Account utente dispositivo mobile
description: Questo articolo descrive come configurare e gestire gli account utente che consentono ai lavoratori di accedere e utilizzare l'app di magazzino.
author: Mirzaab
ms.date: 09/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-09-15
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: ffb4a9842f454094b41a1765d1438f6a40ae610b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851306"
---
# <a name="mobile-device-user-accounts"></a>Account utente dispositivo mobile

[!include [banner](../includes/banner.md)]

Ogni volta che un lavoratore inizia a utilizzare l'app di magazzino, deve accedere utilizzando un nome utente e una password. È possibile associare un numero qualsiasi di utenti dell'app di magazzino a ciascun lavoratore nel sistema e i magazzini sono in genere associati a ciascuno di questi utenti dell'app di magazzino. Sono inoltre configurate varie opzioni per ciascun lavoratore, per stabilire le impostazioni predefinite e altre impostazioni rilevanti per l'utilizzo dell'app di magazzino.

## <a name="set-up-the-required-worker-and-employee-records"></a>Imposta i record del lavoratore e dei dipendenti richiesti

Prima di poter configurare gli utenti dell'app di magazzino, ogni lavoratore deve già esistere come dipendente o lavoratore di Supply Chain Management nel modulo **Risorse umane**.

## <a name="set-up-mobile-device-user-accounts"></a><a name="set-wma-users"></a>Configurare gli account utente per i dispositivi mobili

Dopo aver configurato i lavoratori e i dipendenti richiesti in Risorse umane, puoi assegnare gli utenti dell'app di magazzino a ciascuno di essi e impostare altre opzioni che influiscono sul modo in cui possono utilizzare l'app.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoratore**.
1. Per modificare un lavoratore esistente, selezionala nel riquadro elenco. Per aggiungere un nuovo record, seleziona **Nuovo** nel riquadro Azioni.
1. Se stai configurando un nuovo lavoratore, segui questi passaggi:

    1. Nel campo **Lavoratore**, selezionare l'utente di destinazione nell'elenco di dipendenti.
    1. Selezionare **Select**.
    1. Nel riquadro azioni selezionare **Salva**.

1. È possibile utilizzare un profilo predefinito per guidare l'addetto al magazzino presso la stazione di imballaggio attraverso il processo che è richiesto. In alternativa, è possibile utilizzare il profilo predefinito per salvare le impostazioni del profilo preferito per il lavoratore. Nella scheda dettaglio **Profilo**, imposta i seguenti campi:

    - **Criteri imballaggio contenitore**: seleziona criteri di imballaggio dei container che definiscano come devono essere elaborati i container presso la stazione di imballaggio. I criteri di imballaggio del container selezionati qui saranno preselezionati per il lavoratore quando aprirà la stazione di imballaggio. Per ulteriori informazioni, vedi il seguente post del blog: [Funzionalità di imballaggio migliorate](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611),
    - **ID profilo di imballaggio**: seleziona un ID profilo di imballaggio che definisce i criteri di imballaggio e le impostazioni del contenitore utilizzate. Se l'ID del profilo di imballaggio selezionato è associato a criteri di imballaggio del container, non potrai modificare l'impostazione **Criteri di imballaggio del contenitore** in questa pagina.

1. Nella Scheda dettaglio **Stazione di imballaggio predefinita**, impostare i seguenti campi per definire la stazione di confezionamento predefinita che si applica quando l'operatore effettua l'accesso. Il lavoratore può ancora selezionare un'altra stazione di imballaggio in base alle esigenze.

    - **Sito**: seleziona il sito in cui si trova la stazione di imballaggio predefinita.
    - **Magazzino**: seleziona il magazzino in cui si trova la stazione di imballaggio predefinita.
    - **Posizione**: seleziona la posizione della stazione di imballaggio predefinita.

1. La Scheda dettaglio **Utenti** consente di creare un numero qualsiasi di account utente dell'app di magazzino per il lavoratore selezionato. Ciascun conto è associato a uno o più magazzini specifici. Utilizza la barra degli strumenti per aggiungere o rimuovere account utente, reimpostare la password per un account selezionato o assegnare magazzini a un account selezionato. Per ogni account utente, è possibile impostare i seguenti campi:

    - **ID utente**: immetti un ID univoco.
    - **Nome utente**: immetti un nome per l'ID.
    - **Magazzino predefinito**: impostare il magazzino predefinito in cui lavora solitamente il lavoratore. Puoi utilizzare la barra degli strumenti per assegnare magazzini aggiuntivi e l'operatore può passare da un magazzino all'altro utilizzando l'attività indiretta **Modifica magazzino** della voce di menu del dispositivo mobile.
    - **Nome del menu**: seleziona il menu principale che sarà la pagina iniziale per il lavoratore. La possibilità di impostare un menu principale per ogni lavoratore è utile perché ti consente di controllare la struttura del menu che ogni lavoratore può utilizzare. Ad esempio, il menu per i lavoratori attivi solo nell'area in uscita può essere personalizzato per le attività correlate alle operazioni in uscita per quell'area.
    - **Inattivo**: una casella di controllo selezionata indica che l'account utente è inattivo. L'account utente viene disattivato automaticamente se un lavoratore inserisce la password errata per cinque volte di seguito nell'app del magazzino. Tuttavia, puoi inoltre selezionare manualmente questa casella di controllo. Deseleziona la casella di controllo per rendere nuovamente attivo l'utente.

1. Nella Scheda dettaglio **Lvoro**, impostare i seguenti campi:

    - **Consenti override ubicazione prelievo**: imposta questa opzione su *Sì* per consentire al lavoratore di ignorare la posizione per le fasi di prelievo. Questa funzionalità può essere utile se l'inventario fisico non corrisponde alla posizione suggerita dal sistema.
    - **Consenti override ubicazione di stoccaggio**: imposta questa opzione su *Sì* per consentire al lavoratore di ignorare la posizione per le fasi di stoccaggio. Questa funzionalità può essere utile se la posizione di stoccaggio suggerita è attualmente piena o non disponibile o se le posizioni di staging sono cambiate.
    - **Consenti prelievo in eccesso per ordini cliente**: imposta questa opzione su *Sì* per consentire al lavoratore di effettuare un prelievo eccessivo quando vengono prelevati gli ordini fornitore. Per ulteriori informazioni, vedi [Prelievo in eccesso per ordini cliente e di trasferimento](over-picking-for-sales-and-transfer-orders.md).
    - **Consenti prelievo in eccesso per ordini di trasferimento**: imposta questa opzione su *Sì* per consentire al lavoratore di effettuare un prelievo eccessivo quando vengono prelevati gli ordini di trasferimento. Per ulteriori informazioni, vedi [Prelievo in eccesso per ordini cliente e di trasferimento](over-picking-for-sales-and-transfer-orders.md).
    - **Consenti movimento di magazzino e lavoro associato**: imposta questa opzione su *Sì* per consentire al lavoratore di spostare il magazzino già prenotato o già associato con altro lavoro. Per ulteriori informazioni, vedi [Movimento di magazzino con lavoro associato in Warehouse Management](move-inventory-associated-work.md).
    - **Consenti riallocazione manuale articolo**: imposta questa opzione su *Sì* per abilitare la riallocazione manuale del lavoratore durante la riallocazione articolo. La riallocazione degli articoli guida i lavoratori a prelevare le scorte da un'altra posizione. Sebbene la riallocazione automatica sia disponibile per tutti i lavoratori, la riallocazione manuale richiede un'impostazione esplicita per un lavoratore. La possibilità di controllare la riallocazione manuale per ogni lavoratore può essere utile perché consente di controllare la visibilità di ogni lavoratore quando, ad esempio, il prelievo di articoli dall'area di quarantena o di massa è limitato ai lavoratori fidati. Per ulteriori informazioni, vedi il seguente post del blog: [Riallocazione automatica e manuale degli articoli durante la riallocazione dell'articolo](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/11/07/automatic-and-manual-item-reallocation-during-the-short-picking-dynamics-365-for-operations-1611/).
    - **Supervisore conteggio ciclo**: imposta questa opzione su *Sì* per rendere il lavoratore un supervisore del conteggio del ciclo. In questo caso, tutti i conteggi dei cicli eseguiti dal lavoratore sull'app di magazzino verranno immediatamente approvati. I campi **Limite percentuale massima**, **Limite quantità massima** e **Limite valore massimo** non vengono considerati per i lavoratori per cui questa opzione è impostata *Sì*.
    - **Limite percentuale massima**: immettere la percentuale limita più alta che un conteggio di ciclo può variare dal conteggio previsto senza richiedere l'approvazione da un supervisore di conteggio di ciclo di lavorazione.
    - **Limite quantità massima**: immettere la quantità totale che una quantità immessa può differire dalla quantità prevista (in unità) senza richiedere l'approvazione da un supervisore di conteggio di ciclo di lavorazione.
    - **Limite valore massimo**: immettere l'importo massimo di cui il costo dell'inventario può differire dal costo previsto senza richiedere l'approvazione da un supervisore di conteggio di ciclo di lavorazione.

1. Nel riquadro azioni selezionare **Salva**.
1. Se hai aggiunto un nuovo account utente, viene visualizzata la finestra di dialogo **Imposta password** dove è possibile creare una semplice password che l'utente può utilizzare per accedere all'app per dispositivi mobili. Immettere la password semplice due volte, quindi selezionare **Salva password** per continuare.

## <a name="set-the-language-number-formats-and-time-zone-for-each-warehouse-app-user"></a>Imposta la lingua, i formati dei numeri e il fuso orario per ogni utente dell'app di magazzino

Quando un lavoratore accede all'app mobile Warehouse Management, la lingua, i formati dei numeri e il fuso orario cambiano in base alle preferenze di quel lavoratore. Le impostazioni dell'account per il lavoratore selezionato nel passaggio 3 nella sezione [Configurare account utente per dispositivi mobili](#set-wma-users) determina le impostazioni utilizzate. Se hai bisogno di impostazioni separate per ogni utente, usa account lavoratore diversi. La procedura seguente mostra come modificare la lingua, i formati numerici e il fuso orario per ogni utente dell'app Warehouse.

1. Andare a **Gestione magazzino \> Impostazioni \> Lavoratore**.
1. Trova il nome del lavoratore per cui definire la configurazione. Assicurati che il lavoratore disponga di tutti gli account utente dell'app di magazzino richiesti elencati nella Scheda dettaglio **Utenti**. Crea un nuovo lavoratore e/o aggiungi account utente dell'app di magazzino come richiesto, seguendo i passaggi nella sezione [Configurare account utente per dispositivi mobili](#set-wma-users).
1. Selezionare **Amministrazione sistema \> Utenti \> Utenti**.
1. Seleziona l'account utente in cui la colonna **Persona** mostra il nome del lavoratore che hai trovato nel passaggio 2.

    > [!IMPORTANT]
    > I valori **ID utente** che sono elencati nella pagina **Utenti** *non* sono relativi al valore indicato nella Scheda dettaglio **Utenti** della pagina **Lavoratore** che hai aperto nel passaggio 1.

1. Nel riquadro azioni selezionare **Opzioni utente**.
1. Nella scheda **Preferenze**, impostare i seguenti campi:

    - **Lingua**: seleziona la lingua preferita dal lavoratore. Questo campo controlla anche il formato del numero mostrato nell'app del magazzino.
    - **Formato di data, ora e numero** – Seleziona il formato di data e ora preferito dal lavoratore. L'app magazzino utilizza il formato di numero associato alla lingua scelta per il campo **Lingua** invece di questa impostazione.
    - **Fuso orario**: seleziona il fuso orario in cui lavora il lavoratore. Questo campo influisce sul timestamp per tutte le registrazioni effettuate dal lavoratore utilizzando l'app.

> [!NOTE]
> In alcuni casi, l'app di magazzino non sarà in grado di trovare impostazioni specifiche del lavoratore che stabiliscano la lingua, i formati dei numeri e il fuso orario. Vengono applicate le seguenti regole:
>
> - Se l'app non è connessa a un ambiente Supply Chain Management (ad esempio, la prima volta che l'app viene avviata dopo l'installazione), viene utilizzata la lingua del dispositivo locale. Quando cambia la lingua del dispositivo, cambia anche la lingua dell'app. Per ulteriori informazioni su come configurare la lingua per il dispositivo locale, vedi la documentazione del dispositivo e/o del sistema operativo.
> - Se l'app è connessa a un ambiente Supply Chain Management, ma non sono impostate preferenze per il lavoratore che ha eseguito l'accesso, la lingua, i formati numerici e il fuso orario vengono selezionati in base all'account associato all'ID cliente utilizzato dal dispositivo per connettersi a Supply Chain Management. Per ulteriori informazioni, vedi [Creare e configurare un account utente in Supply Chain Management](install-configure-warehouse-management-app.md#user-azure-ad).

> [!TIP]
> Se noti che vengono visualizzati timestamp errati per le registrazioni effettuate utilizzando l'app di magazzino, potrebbe essere necessario modificare il fuso orario impostato per l'account utente utilizzato dai lavoratori per accedere e/o autenticarsi con Supply Chain Management. Come accennato in precedenza, l'impostazione del fuso orario potrebbe provenire dall'account utente utilizzato per accedere all'app di magazzino, come impostato nella pagina **Lavoratore**. In alternativa, se l'account utente non è impostato nella pagina **Lavoratore**, il fuso orario proviene dall'account utente associato all'ID client utilizzato per l'autenticazione, come impostato nella pagina **[Applicazioni Azure Active Directory](install-configure-warehouse-management-app.md)**.
