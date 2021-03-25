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
description: Saiba como habilitar o aplicativo cliente da área de trabalho do Teams com políticas de controle de aplicativos AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120843"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Políticas de controle de aplicativo do AppLocker no Microsoft Teams

Este artigo explica como habilitar o aplicativo cliente da área de trabalho do Teams com políticas de controle de aplicativos AppLocker. O uso do AppLocker foi projetado para restringir a execução de programas e scripts por usuários não administrativos. Para obter mais informações e orientações sobre o AppLocker, consulte [O que é AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

O processo de habilitação do Teams com o AppLocker requer a criação de políticas de listagem de permitir baseadas em AppLocker. As políticas são criadas com software de gerenciamento de Política de Grupo e/ou o uso de cmdlets Windows PowerShell appLocker (consulte a referência técnica [do AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obter mais informações). A política AppLocker é salva no formato XML e pode ser editada com qualquer texto ou editor XML.

## <a name="teams-allow-list-with-applocker"></a>As equipes permitem lista com o AppLocker

As regras do AppLocker são organizadas em coleções de regras. As regras do AppLocker se aplicam ao aplicativo direcionado e são os componentes que comem a política do AppLocker.  

Para permitir o Teams, recomendamos que você use as regras de condição do [editor,](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) já que todos os arquivos de aplicativo do Teams são assinados digitalmente.
  
Não recomendamos o uso de regras de caminho porque o diretório de instalação do Teams pode ser escrito pelo usuário. Também não recomendamos o uso de regras de hash porque as regras teriam que ser atualizadas sempre que o aplicativo cliente do Teams for atualizado.

Como os arquivos executáveis da área de trabalho do Teams são assinados digitalmente, a condição do editor identifica um arquivo de aplicativo com base em sua assinatura digital e atributos de versão incorporada. A assinatura digital contém informações sobre a empresa que criou o arquivo de aplicativo (o editor). As informações de versão, que são obtidas do recurso binário, incluem o nome do produto do qual o arquivo faz parte e o número de versão do arquivo de aplicativo.

### <a name="example-of-publisher-condition-rules"></a>Exemplo de regras de condição do editor

Para o aplicativo cliente do Teams (todos os arquivos, todas as versões) adicione o seguinte às Regras Executáveis & Regras DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Tópicos relacionados
[O que é AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referência técnica do AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)