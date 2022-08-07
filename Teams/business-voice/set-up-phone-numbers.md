---
title: Configurar um sistema Telefonia do Microsoft Teams com números de telefone do Plano de Chamadas
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como configurar o sistema Telefonia do Microsoft Teams com números de telefone do Plano de Chamadas para usuários e serviços em sua organização.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
- M365initiative-voice
ms.openlocfilehash: fe94987e4abf8c98c32428f608a19db46aacd4c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268006"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>Etapa 2: Configurar números de telefone do Sistema de Telefonia do Teams

Antes de configurar usuários ou atendedores automáticos em sua organização, você precisa obter números de telefone para eles. Há vários tipos diferentes de números de telefone, no entanto, os seguintes são os dois tipos de números que você precisa adicionar nesta etapa:

- **Números de serviço** Esses números são usados para atendedores automáticos, audioconferência e filas de chamadas. Eles podem ser números de chamada tarifada ou gratuita e podem lidar com grandes quantidades de chamadas ao mesmo tempo. O número de telefone da sua empresa precisa ser um número de serviço, pois ele será atribuído a um atendedor automático em uma etapa posterior.
- **Números de assinante** Esses números são usados para usuários regulares para que possam fazer e receber chamadas telefônicas.

> [!IMPORTANT]
> Mesmo que você queira usar seus números de telefone existentes, será necessário criar e atribuir números de telefone temporários à linha telefônica principal da sua empresa e aos usuários. Você poderá substituir esses números temporários por seus números de telefone existentes em uma etapa posterior.

> [!NOTE]
> Pode levar várias horas para que seus novos números de telefone se tornem disponíveis no Teams.

## <a name="set-up-a-service-number"></a>Configurar um número de serviço

O número de serviço que você configurou agora será usado em uma etapa posterior para o número de telefone principal da sua empresa.

1. Abra o centro de administração do Microsoft Teams e faça logon com um usuário que seja um administrador global (geralmente, essa é a conta que você usou para se inscrever no Microsoft 365).
2. No painel de navegação esquerdo, vá para <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**números de Telefone** > **de**</a> Voz e clique em **Adicionar**.
3. Insira um nome para o pedido e adicione uma descrição.
4. Na página Localização e quantidade, faça o seguinte:
    1. Em **País ou região**, selecione um país ou região.
    2. Em **Tipo de número**, selecione uma das seguintes opções:

        - **Atendedor automático (pedágio)** Número de telefone normal, não gratuito. Taxas de longa distância são cobradas para o chamador.
        - **Atendedor automático (ligação gratuita)** Número de telefone gratuito (EUA e Canadá) ou gratuito (Reino Unido). Taxas de distâncias longas são cobradas para sua empresa. Antes de selecionar essa opção, você precisa comprar Créditos de Comunicação. Para obter mais informações, consulte [O que preciso comprar para obter recursos de voz para minha pequena ou média empresa?](whats-business-voice.md).

    3. Em **Quantidade**, selecione **1**.
        > [!NOTE]
        > Se você receber a mensagem Você não tem **licenças** suficientes para solicitar mais números desse tipo, verifique se você comprou o Telefone do Teams com licenças de pacote do Plano de Chamadas. Para obter mais informações, consulte [O que preciso comprar para obter recursos de voz para minha pequena ou média empresa?](whats-business-voice.md).
    4. Escolha o **código** **de** localização ou área, dependendo se você deseja pesquisar números de telefone usando a cidade de um local ou se deseja pesquisar números em um código de área específico.
    5. Se você selecionar **Local**:

        1. Digite a cidade na qual seu endereço de emergência está localizado na [](set-up-emergency-locations.md) etapa Configurar locais de emergência ou, se precisar criar um novo local para outro escritório ou escritório doméstico, clique em Adicionar um **local**.
        2. Em **Código de área**, selecione um código de área e, em seguida, **selecione Avançar** para reservar seu número.

    6. Se você selecionar **Código de área**, digite o código de área que deseja pesquisar e selecione **Avançar** para reservar seu número.

5. Selecione o número desejado. Você tem 10 minutos para selecionar seu número de telefone e fazer seu pedido. Se você levar mais de 10 minutos, o número de telefone será retornado para o pool de números.
6. Quando estiver pronto para fazer seu pedido, clique em Fazer **pedido** e, em seguida, **Concluir**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurar números de telefone para seus usuários

1. Abra o centro de administração do Microsoft Teams e faça logon com um usuário que seja um administrador global. Geralmente, essa é a conta que você usou para se inscrever no Microsoft 365.
2. No painel de navegação esquerdo, vá para <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**números de Telefone** > **de**</a> Voz e clique em **Adicionar**.
3. Insira um nome para o pedido e adicione uma descrição.
4. Na página Localização e quantidade, faça o seguinte:

    1. Em **País ou região**, selecione um país ou região.
    2. Em **Tipo de número**, selecione **Usuário (assinante)**.
    3. Em **Quantidade**, insira o número de números desejados para sua organização.
    4. Escolha o **código** **de** localização ou área, dependendo se você deseja pesquisar números de telefone usando a cidade de um local ou se deseja pesquisar números em um código de área específico.
    5. Se você selecionar **Local**:

        1. Digite a cidade na qual seu endereço de emergência está localizado na [](set-up-emergency-locations.md) etapa Configurar locais de emergência ou, se precisar criar um novo local para outro escritório ou escritório doméstico, clique em Adicionar um **local**.
        2. Em **Código de área**, selecione um código de área e, em seguida, **selecione Avançar** para reservar seu número.

    6. Se você selecionar **Código de área**, digite o código de área que deseja pesquisar e selecione **Avançar** para reservar seu número.
5. Selecione os números desejados. Você tem 10 minutos para selecionar seus números de telefone e fazer seu pedido. Se você levar mais de 10 minutos, os números de telefone serão retornados para o pool de números.
6. Quando estiver pronto para fazer seu pedido, clique em Fazer **pedido** e, em seguida, **Em Concluir**.

> [!div class="nextstepaction"]
> [Próxima etapa: Atribuir licenças a usuários do Teams](set-up-licenses.md)
