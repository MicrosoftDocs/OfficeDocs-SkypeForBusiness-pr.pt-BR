---
title: Visão geral do controle de política do Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Uma visão geral dos controles de política do Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3665f386f43d8e9b8c49a024663265c25ae96214
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135977"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Visão geral do controle de política do Microsoft Teams

A Microsoft tem o compromisso de fornecer informações e controles necessários para você fazer escolhas sobre como os dados são coletados e usados ao usar o Microsoft Teams, uma parte do Microsoft 365.

Este artigo tem como objetivo fornecer informações sobre os controles de privacidade nas seguintes áreas:

- **Dados de diagnóstico** sobre o Teams e o software do Office sendo usados ​​em computadores que executam o Windows em sua organização são coletados e enviados à Microsoft.
- **Experiências conectadas** que usam funcionalidade baseada em nuvem para fornecer recursos avançados do Teams e do Office para você e seus usuários.

Como parte dessas mudanças, haverá elementos novos e atualizados da interface do usuário (IU) e configurações de política

> [!IMPORTANT]
> Para obter mais informações, confira o conteúdo da [Visão geral do Controle de Política](https://docs.microsoft.com/deployoffice/privacy/overview-privacy-controls) do M365.

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>Dados de diagnóstico enviados do Microsoft 365 Apps para Grandes Empresas para a Microsoft

Os dados de diagnóstico são usados para:

- Manter o Teams seguro e atualizado.
- Detectar, diagnosticar e corrigir problemas.
- Melhorar o produto.

Um exemplo de alguns dos dados coletados inclui:

- Idioma do aplicativo
- Tipo de usuário
- Versão do build do sistema operacional

## <a name="clients-that-adhere-to-diagnostic-controls"></a>Clientes que aderem aos controles de diagnóstico

Os seguintes clientes aderem aos controles de diagnóstico e enviarão dados:

- iOS
- Android
- Área de trabalho (somente o componente que está usando a API do Win32)

Para obter o diagnóstico de dados móveis obrigatórios, confira [Dados de diagnóstico de controle de política para dispositivos móveis](policy-control-diagnostic-data-mobile.md).

Para obter o diagnóstico de dados da área de trabalho obrigatórios, confira [Dados de diagnóstico de controle de política para área de trabalho](policy-control-diagnostic-data-desktop.md).

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Dados de diagnóstico enviados do aplicativo Teams para a Microsoft

Esses dados de diagnóstico sobre o software do Teams sendo usado ​​em computadores que executam o Windows em sua organização são coletados e enviados à Microsoft.

Há três níveis de dados de diagnóstico para o software do Teams que você pode escolher:

- **Obrigatório** Os dados mínimos necessários para ajudar a manter o Office seguro, atualizado e funcionando conforme o esperado no dispositivo em que está instalado.
- **Opcional** Dados opcionais que nos ajudam a melhorar o produto e fornecem informações aprimoradas para nos ajudar a detectar, diagnosticar e corrigir problemas.
- **Nenhum** Nenhum dado de diagnóstico sobre o software do Teams em execução no dispositivo do usuário é coletado e enviado para nós. Essa opção, no entanto, limita significativamente nossa capacidade de detectar, diagnosticar e corrigir problemas que seus usuários podem encontrar usando o Teams.

Os dados de diagnóstico obrigatórios podem incluir, por exemplo, informações sobre a versão do cliente Teams instalado no dispositivo ou incluir informações que indicam que o aplicativo Teams está falhando ao tentar ingressar em uma reunião. Os dados de diagnóstico opcionais podem incluir informações sobre o tempo que leva para iniciar uma chamada telefônica, o que pode indicar um problema de conectividade ou desempenho da rede.

Se você optar por nos enviar dados de diagnóstico opcionais, os dados de diagnóstico obrigatórios também serão incluídos.

Como administrador da sua organização, você poderá usar uma configuração de política para escolher o nível de dados de diagnóstico que será enviado para nós. Dados diagnósticos opcionais serão enviados à Microsoft, a menos que você altere a configuração. O fornecimento de dados de diagnóstico opcionais permite que a equipe de engenharia do Office na Microsoft detecte, diagnostique e atenue os problemas para reduzir os impactos em sua organização.

Os usuários não poderão alterar o nível de dados de diagnóstico de seus dispositivos se eles estiverem conectados ao Teams com suas credenciais organizacionais, que às vezes são chamadas de conta corporativa ou de estudante.

Esses dados de diagnóstico não incluem nomes de usuários, seus endereços de email ou o conteúdo de seus arquivos do Office. Nosso sistema cria uma ID exclusiva que é associada a dados de diagnóstico do usuário. Quando recebemos dados de diagnóstico mostrando que o aplicativo Teams falhou 100 vezes, essa ID exclusiva nos permite determinar se foi um único usuário que teve esse problema 100 vezes ou se foi o aplicativo de 100 usuários que falhou uma vez. Não usamos essa ID exclusiva para identificar um usuário específico.

## <a name="required-service-data-for-connected-experiences"></a>Dados de serviço obrigatórios para experiências conectadas

Dados de serviço necessários são dados que nos permitem fornecer essas experiências conectadas baseadas em nuvem e que ajudam a tornar essas experiências seguras e a funcionarem conforme o esperado. Três tipos de informações compõem os dados de serviço necessários.

- **Conteúdo de cliente**, que é o conteúdo criado por você usando o Office, como o texto digitado em um documento do Word.
- **Dados funcionais**, que inclui informações necessárias para que uma experiência conectada execute suas tarefas, como as informações de configuração do aplicativo.
- **Dados de diagnóstico de serviço**, que são os dados necessários para manter o serviço seguro, atualizado e com o desempenho esperado. Como esses dados estão estritamente relacionados à experiência conectada, eles são separados dos níveis de dados de diagnóstico obrigatórios ou opcionais.

Você pode optar por não oferecer essa funcionalidade a seus usuários; nesse caso, essas informações não serão fornecidas à Microsoft para oferecer suporte à funcionalidade das experiências conectadas. Você pode saber mais sobre os [dados de serviço obrigatórios](https://docs.microsoft.com/deployoffice/privacy/required-service-data).

## <a name="essential-services-for-microsoft-teams"></a>Serviços essenciais do Microsoft Teams

Há também um conjunto de serviços essenciais para que o Microsoft 365 Apps para Grandes Empresas funcione bem e tais serviços não podem ser desabilitados. Por exemplo, o serviço de licenciamento que confirma que você está corretamente licenciado para usar o Microsoft 365 Apps para Grandes Empresas. Os dados de serviço necessários sobre esses serviços são coletados e enviados à Microsoft, independentemente de qualquer outra configuração de política.

Para saber mais, confira [Serviços essenciais do Office](https://docs.microsoft.com/deployoffice/privacy/essential-services).
