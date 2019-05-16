---
title: AppLocker diretivas de controle de aplicativo no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Aprenda a habilitar o aplicativo do cliente de desktop equipes com políticas de controle do aplicativo de AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063202"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>AppLocker diretivas de controle de aplicativo no Microsoft Teams

Este artigo explica como habilitar o aplicativo do cliente de desktop equipes com políticas de controle do aplicativo de AppLocker. Uso do AppLocker foi projetado para restringir a execução do programa e script por usuários não administrativos. Para obter mais informações e orientações sobre AppLocker, consulte [Novidades AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

O processo para habilitar as equipes com AppLocker exige a criação de políticas de lista de exceções baseado em AppLocker. As diretivas são criadas com o software de gerenciamento de diretiva de grupo e/ou o uso dos cmdlets do Windows PowerShell para AppLocker (consulte a [referência técnica do AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) para obter mais informações). A política de AppLocker é salvo em formato XML e pode ser editada com qualquer editor de texto ou XML.

## <a name="teams-whitelisting-with-applocker"></a>Lista de exceções de equipes com AppLocker

Regras do AppLocker são organizadas em conjuntos de regras. Regras de AppLocker aplicam-se para o aplicativo de destino, e são os componentes que compõem a política de AppLocker.  

A lista branca equipes, recomendamos que você use as [regras de condição do publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , desde que todos os arquivos de aplicativo de equipes são assinados digitalmente.
  
Não recomendamos o uso de regras de caminho como o diretório de instalação de equipes é gravável de usuário. Também não recomendamos o uso de regras de hash porque as regras teria que ser atualizadas toda vez que o aplicativo cliente de equipes é atualizado.

Desde que arquivos executáveis da área de trabalho de equipes são assinados digitalmente, a condição de editor identifica um arquivo de aplicativo com base em sua assinatura digital e os atributos de versão incorporada. A assinatura digital contém informações sobre a empresa que criou o arquivo de aplicativo (o Editor). As informações de versão, que são obtidas binário de recurso, incluem o nome do produto que o arquivo faz parte do e o número da versão do arquivo do aplicativo.

### <a name="example-of-publisher-condition-rules"></a>Exemplo de regras de condição do publisher

Para o aplicativo de cliente de equipes (todos os arquivos, todas as versões):

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>Tópicos relacionados
[O que é AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker de referência técnica](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)