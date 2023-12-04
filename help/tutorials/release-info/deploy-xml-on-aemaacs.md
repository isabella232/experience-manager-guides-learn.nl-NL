---
title: Toevoegen [!DNL AEM Guides] aan uw [!DNL AEM as a Cloud Service] milieu
description: Meer informatie over toevoegen [!DNL AEM Guides] aan uw [!DNL AEM as a Cloud Service] milieu
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---

# [!DNL AEM Guides] as a Cloud Service implementatie

Meer informatie over toevoegen [!DNL Guides] aan uw [!DNL AEM as a Cloud Service] milieu.

## Handmatige implementatie via de vastlegging in Cloud Manager

Als u [!DNL AEM Guides] as a Cloud Service vóór 29 maart 2022, volg deze plaatsingsinstructies:

* Als u vers start, kunt u de code vervangen die automatisch wordt gegenereerd door [!UICONTROL Cloud Manager] met de code uit de onderstaande repo die al een XML-insteekmodule heeft: https://github.com/Adobe-TCS/XML-documentation-for-AEMaaCS

* Als u al aanpassingen hebt ingecheckt in [!UICONTROL Cloud Manager] git repo, raadpleegt u het onderstaande repo voor instructies over het toevoegen van een XML-plug-in in uw bestaande code: https://github.com/Adobe-TCS/DoX-Installer-for-AEMaaCS

## Implementatie via Cloud Manager

Als u een klant bent die [!DNL AEM Guides] as a Cloud Service op of na 29-03-2022 volgt u deze instructies om [!DNL Guides] aan uw [!DNL AEM as a Cloud Service] milieu:

1. Aanmelden bij [!UICONTROL Cloud Manager].

1. Bewerk het programma waarvoor u wilt configureren [!DNL AEM Guides].

1. Overschakelen op **[!UICONTROL Solutions and Add-ons]** tab.

1. In de **[!UICONTROL Solutions and Add-ons]** tabel, klik op **[!UICONTROL Assets]**.

1. Selecteren **[!UICONTROL Guides]** en selecteert u **[!UICONTROL Save]**.

U hebt met succes uw programma voor automatische levering van AEM oplossing van Gidsen gevormd.

![Oplossing voor AEM hulplijnen configureren](assets/addon-configuration.png)

>[!NOTE]
>
>Om te installeren [!DNL AEM Guides] op elk milieu in het kader van het geïntegreerde programma moet u de pijpleiding voor het milieu in werking stellen . Er is geen aanvullende configuratie vereist in uw CM-it-codebase voor installatie [!DNL AEM Guides].
