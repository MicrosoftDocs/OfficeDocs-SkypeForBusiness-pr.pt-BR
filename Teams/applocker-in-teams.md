---
title: Políticas de controle AppLocker
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
description: Saiba como habilitar o aplicativo cliente de área de trabalho do Teams com políticas de controle de aplicativo AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526687"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Políticas de controle de aplicativo AppLocker no Microsoft Teams

Este artigo explica como habilitar o aplicativo cliente de área de trabalho do Teams com políticas de controle de aplicativo AppLocker. O uso do AppLocker foi projetado para restringir a execução de programas e scripts por usuários não administrativos. Para obter mais informações e orientações sobre o AppLocker, consulte [O que é AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

O processo para habilitar o Teams com AppLocker requer a criação de políticas de listagem de permitir baseadas em AppLocker. As políticas são criadas com o software de gerenciamento de Política de Grupo e/ou com o uso de cmdlets do Windows PowerShell para AppLocker (consulte a referência técnica [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obter mais informações). A política AppLocker é salva no formato XML e pode ser editada com qualquer editor de texto ou XML.

## <a name="teams-allow-list-with-applocker"></a>Lista de permitir do Teams com o AppLocker

As regras do AppLocker são organizadas em coleções de regras. As regras do AppLocker se aplicam ao aplicativo direcionado e são os componentes que comem a política AppLocker.  

Para permitir o Teams, recomendamos que você use as regras de condição do [editor,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) uma vez que todos os arquivos do aplicativo Teams estão assinados digitalmente.
  
Não recomendamos o uso de regras de caminho porque o diretório de instalação do Teams pode ser escrito pelo usuário. Também não recomendamos o uso de regras de hash porque as regras devem ser atualizadas sempre que o aplicativo cliente do Teams for atualizado.

Como os arquivos executáveis da área de trabalho do Teams são assinados digitalmente, a condição do editor identifica um arquivo de aplicativo com base em sua assinatura digital e atributos de versão inserida. A assinatura digital contém informações sobre a empresa que criou o arquivo de aplicativo (o editor). As informações de versão, obtidas do recurso binário, incluem o nome do produto do qual o arquivo faz parte e o número da versão do arquivo do aplicativo.

### <a name="example-of-publisher-condition-rules"></a>Exemplo de regras de condição do editor

Para o aplicativo cliente teams (todos os arquivos, todas as versões) adicione o seguinte às Regras Executáveis & Regras DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Tópicos relacionados
[O que é AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referência técnica do AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
