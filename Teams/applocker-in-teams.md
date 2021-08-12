---
title: Políticas de controle do AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como habilitar o aplicativo cliente Teams área de trabalho com políticas de controle de aplicativo AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b68d698ffcb703e70e12f3801ff70fb0719bb17cb09e23facf47121529a86b0b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288439"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Políticas de controle do aplicativo AppLocker em Microsoft Teams

Este artigo explica como habilitar o aplicativo cliente Teams área de trabalho com as políticas de controle do aplicativo AppLocker. O uso do AppLocker foi projetado para restringir a execução de programas e scripts por usuários não administrativos. Para obter mais informações e orientações sobre o AppLocker, consulte [O que é AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

O processo para habil Teams com o AppLocker requer a criação de políticas de listagem de permitir baseadas em AppLocker. As políticas são criadas com software de gerenciamento de Política de Grupo e/ou o uso de cmdlets Windows PowerShell para AppLocker (consulte a referência técnica do [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obter mais informações). A política AppLocker é salva no formato XML e pode ser editada com qualquer texto ou editor XML.

## <a name="teams-allow-list-with-applocker"></a>Teams lista de permitir com o AppLocker

As regras do AppLocker são organizadas em coleções de regras. As regras do AppLocker se aplicam ao aplicativo direcionado e são os componentes que comem a política do AppLocker.  

Para permitir Teams, recomendamos que você [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) use as regras de condição do editor, já que todos os Teams de aplicativos são assinados digitalmente.
  
Não recomendamos o uso de regras de caminho porque o diretório Teams de instalação é writable pelo usuário. Também não recomendamos o uso de regras de hash porque as regras teriam que ser atualizadas sempre que o aplicativo cliente Teams é atualizado.

Como Teams arquivos executáveis da área de trabalho são assinados digitalmente, a condição do editor identifica um arquivo de aplicativo com base em sua assinatura digital e atributos de versão incorporada. A assinatura digital contém informações sobre a empresa que criou o arquivo de aplicativo (o editor). As informações de versão, que são obtidas do recurso binário, incluem o nome do produto do qual o arquivo faz parte e o número de versão do arquivo de aplicativo.

### <a name="example-of-publisher-condition-rules"></a>Exemplo de regras de condição do editor

Para o Teams cliente (todos os arquivos, todas as versões) adicione o seguinte às Regras Executáveis & Regras DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Tópicos relacionados
[O que é AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referência técnica do AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)