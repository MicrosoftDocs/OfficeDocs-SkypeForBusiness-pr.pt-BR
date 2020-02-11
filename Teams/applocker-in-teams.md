---
title: Políticas de controle de aplicativo do AppLocker no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como habilitar o aplicativo cliente da equipe de trabalho com políticas de controle de aplicativo do AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 13a1afd4ad4089db3c6b0c1223bf06831d9be667
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888550"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Políticas de controle de aplicativo do AppLocker no Microsoft Teams

Este artigo explica como habilitar o aplicativo cliente da área de trabalho do teams com as políticas de controle de aplicativo do AppLocker. O uso do AppLocker foi projetado para restringir a execução do programa e do script por usuários não administrativos. Para obter mais informações e diretrizes sobre o AppLocker, consulte [o que é o AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

O processo para habilitar o Teams com AppLocker requer a criação de políticas de lista branca baseadas em AppLocker. As políticas são criadas com o software de gerenciamento de política de grupo e/ou o uso de cmdlets do Windows PowerShell para AppLocker (consulte a [referência técnica do AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obter mais informações). A política AppLocker é salva no formato XML e pode ser editada com qualquer editor de texto ou XML.

## <a name="teams-whitelisting-with-applocker"></a>Lista negra do teams com AppLocker

As regras do AppLocker são organizadas em conjuntos de regras. As regras do AppLocker se aplicam ao aplicativo de destino e são os componentes que compõem a política do AppLocker.  

Para as equipes da lista branca, recomendamos que você use as [regras de condição do fornecedor](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , pois todos os arquivos de aplicativo do teams são assinados digitalmente.
  
Não recomendamos o uso de regras de caminho porque o diretório de instalação do teams é gravável pelo usuário. Também não recomendamos o uso de regras de hash porque as regras precisariam ser atualizadas toda vez que o aplicativo cliente do teams for atualizado.

Como os arquivos executáveis da área de trabalho do teams são assinados digitalmente, a condição de fornecedor identifica um arquivo de aplicativo com base em seus atributos de assinatura digital e versão inserida. A assinatura digital contém informações sobre a empresa que criou o arquivo de aplicativo (o editor). As informações de versão, que são obtidas do recurso binário, incluem o nome do produto do qual o arquivo é parte e o número da versão do arquivo do aplicativo.

### <a name="example-of-publisher-condition-rules"></a>Exemplo de regras de condição do Publisher

Para o aplicativo cliente do Teams (todos os arquivos, todas as versões) adicione o seguinte às regras executáveis & regras de DLL:

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Tópicos relacionados
[O que é o AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Referência técnica do AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
