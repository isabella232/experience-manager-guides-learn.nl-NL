---
title: Upgrade uitvoeren AEM hulplijnen
description: Leer hoe u AEM hulplijnen kunt bijwerken
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---


# Upgrade uitvoeren AEM hulplijnen {#id213BD050YPH}

1. Open de Git-opslagplaats van uw Cloud Manager.

1. Werk het bestand dox/dox.installer/pom.xml bij.

1. Werk de waarde van de variabele dox.version bij tot de versiedetails die door Adobe worden verstrekt.

1. Leg de wijzigingen vast en voer de Cloud Manager-pijplijn uit om het bijgewerkte pakket te implementeren.


>[!NOTE]
>
> Voor meer details over het gebruiken van pijpleiding CI/CD, zie [De CI/CD-pijpleiding gebruiken in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Browser-cache wissen

Na het verbeteringsproces, moeten alle gebruikers het browser geheime voorgeheugen ontruimen alvorens de promotieversie van AEMGidsen te gebruiken.

**Bovenliggend onderwerp:**[ Downloaden en installeren](download-install.md)

