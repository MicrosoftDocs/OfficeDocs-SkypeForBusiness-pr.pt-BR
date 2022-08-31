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
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 13b807d98b92deaac54ad8b755295b73e90c6548
ms.sourcegitcommit: b4bc3b4c1d167a075a25180818f61758eb56cd6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2021
ms.locfileid: "61041253"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Visão geral do controle de política do Microsoft Teams

A Microsoft tem o compromisso de fornecer informações e controles necessários para você fazer escolhas sobre como os dados são coletados e usados ao usar o Microsoft Teams, uma parte do Microsoft 365.

Este artigo tem como objetivo fornecer informações sobre os controles de privacidade nas seguintes áreas:

- **Dados de diagnóstico** sobre o Teams e o software do Office sendo usados ​​em computadores que executam o Windows em sua organização são coletados e enviados à Microsoft.
- **Experiências conectadas** que usam funcionalidade baseada em nuvem para fornecer recursos avançados do Teams e do Office para você e seus usuários.

Como parte dessas mudanças, haverá elementos novos e atualizados da interface do usuário (IU) e configurações de política

> [!IMPORTANT]
> Para ler mais, análise [Visão geral dos controles de privacidade para aplicativos do Microsoft 365 Apps para Grandes Empresas](/deployoffice/privacy/overview-privacy-controls).

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

Para ver uma lista de eventos de dados de diagnóstico necessários e suas propriedades, consulte os seguintes artigos:

- [Dados de diagnóstico móvel necessários para o Microsoft Teams](policy-control-diagnostic-data-mobile.md)
- [Dados necessários de diagnóstico da área de trabalho para o Microsoft Teams](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Dados de diagnóstico enviados do aplicativo Teams para a Microsoft

Esses dados de diagnóstico sobre o software do Teams sendo usado ​​em computadores que executam o Windows em sua organização são coletados e enviados à Microsoft.

Há três níveis de dados de diagnóstico para o software do Teams que você pode escolher:

- **Obrigatório** Os dados mínimos necessários para ajudar a manter o Office seguro, atualizado e funcionando conforme o esperado no dispositivo em que está instalado.
- **Opcional** Dados opcionais que nos ajudam a melhorar o produto e fornecem informações aprimoradas para nos ajudar a detectar, diagnosticar e corrigir problemas.
- **Nenhum** Nenhum dado de diagnóstico sobre o software do Teams em execução no dispositivo do usuário é coletado e enviado para nós. Essa opção, no entanto, limita significativamente nossa capacidade de detectar, diagnosticar e corrigir problemas que seus usuários podem encontrar usando o Teams.

Os dados de diagnóstico obrigatórios podem incluir, por exemplo, informações sobre a versão do cliente Teams instalado no dispositivo ou incluir informações que indicam que o aplicativo Teams está falhando ao tentar ingressar em uma reunião. Os dados de diagnóstico opcionais podem incluir informações sobre o tempo que leva para iniciar uma chamada telefônica, o que pode indicar um problema de conectividade ou desempenho da rede.

Se você optar por nos enviar dados de diagnóstico opcionais, os dados de diagnóstico obrigatórios também serão incluídos.

Como administrador da sua organização, você poderá usar uma configuração de política para escolher o nível de dados de diagnóstico que será enviado para nós. Dados diagnósticos opcionais serão enviados à Microsoft, a menos que você altere a configuração. O fornecimento de dados de diagnóstico opcionais permite que a equipe de engenharia do Office na Microsoft detecte, diagnostique e atenue os problemas para reduzir os impactos em sua organização. 

Para escolher que nível de dados de diagnóstico são enviados para nós, use o [serviço de política de nuvem do Office](/deployoffice/overview-office-cloud-policy-service) e defina a configuração da política *Configurar o nível de dados de diagnóstico de software cliente enviados pelo Office para a Microsoft*. Essa é a mesma configuração de política usada para configurar que nível de dados de diagnóstico são enviados por outros aplicativos do Office (como Word, Excel e PowerPoint) que vêm com os Aplicativos do Microsoft 365 para empresas.

Os usuários não poderão alterar o nível de dados de diagnóstico de seus dispositivos se eles estiverem conectados ao Teams com suas credenciais organizacionais, que às vezes são chamadas de conta corporativa ou de estudante.

Esses dados de diagnóstico não incluem nomes de usuários, endereços de email ou outros conteúdos de usuário, como arquivos do Office compartilhados no Teams, uma mensagem de chat enviada no Teams ou o texto de uma postagem publicada em um canal do Teams. Nosso sistema cria uma ID exclusiva que é associada a dados de diagnóstico do usuário. Quando recebemos dados de diagnóstico mostrando que o aplicativo Teams falhou 100 vezes, essa ID exclusiva nos permite determinar se foi um único usuário que teve esse problema 100 vezes ou se foi o aplicativo de 100 usuários que falhou uma vez. Não usamos essa ID exclusiva para identificar um usuário específico.

Para ver quais dados de diagnóstico foram enviados à Microsoft, você poderá usar o Visualizador de Dados de Diagnóstico, que você pode baixar e instalar gratuitamente da Microsoft Store. Para saber mais, consulte [Usando o Visualizador de Dados de Diagnóstico com o Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

## <a name="required-service-data-for-connected-experiences"></a>Dados de serviço obrigatórios para experiências conectadas

Dados de serviço necessários são dados que nos permitem fornecer essas experiências conectadas baseadas em nuvem e que ajudam a tornar essas experiências seguras e a funcionarem conforme o esperado. Você pode optar por não oferecer essa funcionalidade a seus usuários; nesse caso, essas informações não serão fornecidas à Microsoft para oferecer suporte à funcionalidade das experiências conectadas. Você pode saber mais sobre os [dados de serviço obrigatórios](/deployoffice/privacy/required-service-data).

## <a name="essential-services-for-microsoft-teams"></a>Serviços essenciais do Microsoft Teams

Também há um conjunto de serviços que são essenciais para os aplicativos do Microsoft 365 Apps para Grandes Empresas e não podem ser desabilitados. Por exemplo, o serviço de licenciamento que confirma que você está corretamente licenciado para usar o Microsoft 365 Apps para Grandes Empresas. Os dados de serviço necessários sobre esses serviços são coletados e enviados à Microsoft, independentemente de qualquer outra configuração de política.

Para saber mais, confira [Serviços essenciais do Office](/deployoffice/privacy/essential-services).
