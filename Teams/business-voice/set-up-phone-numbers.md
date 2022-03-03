---
title: Configurar o Microsoft Teams Sistema de Telefonia com números de telefone do Plano de Chamadas
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Saiba como configurar o Microsoft Teams Sistema de Telefonia com números de telefone do Plano de Chamadas para usuários e serviços em sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d2b165e85620b0fb9e9e8242adacc4c07f2c53
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053250"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>Etapa 2: Configurar Teams Sistema de Telefonia números de telefone

Antes de configurar usuários ou atendentes automáticos em sua organização, você precisa obter números de telefone para eles. Há vários tipos diferentes de números de telefone, no entanto, estes são os dois tipos de números que você precisa adicionar nesta etapa:

- **Números de serviço** Esses números são usados para atendimento automático, audioconferência e filas de chamada. Eles podem ser números de chamada gratuita ou gratuita e podem lidar com grandes quantidades de chamadas ao mesmo tempo. O número de telefone da sua empresa precisa ser um número de serviço porque ele será atribuído a um atendimento automático em uma etapa posterior.
- **Números de assinante** Esses números são usados para usuários regulares para que possam fazer e receber chamadas telefônicas.

> [!IMPORTANT]
> Mesmo que você queira usar seus números de telefone existentes, você precisa criar e atribuir números de telefone temporários à linha telefônica principal da sua empresa e aos seus usuários. Você poderá substituir esses números temporários por seus números de telefone existentes em uma etapa posterior.

> [!NOTE]
> Pode levar várias horas para que seus novos números de telefone se tornem disponíveis Teams.

## <a name="set-up-a-service-number"></a>Configurar um número de serviço

O número de serviço que você configurar agora será usado em uma etapa posterior para o número de telefone principal da sua empresa.

1. Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever no Microsoft 365).
2. Na navegação à esquerda, vá para <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Números Telefone** >  **Voz**</a> e clique em **Adicionar**.
3. Insira um nome para a ordem e adicione uma descrição.
4. Na página Local e quantidade, faça o seguinte:
    1. Em **País ou região**, selecione um país ou região.
    2. Em **Tipo de número**, selecione uma das seguintes opções:

        - **Atendimento automático (Toll)** Número de telefone regular, não gratuito. As taxas de longa distância são cobradas ao chamador.
        - **Atendimento automático (Gratuito)** Número de telefone gratuito (EUA e Canadá) ou telefone gratuito (Reino Unido). As taxas de longa distância são cobradas para sua empresa. Antes de selecionar essa opção, você precisa comprar Créditos de Comunicação. Para obter mais informações, consulte [O que preciso comprar para obter recursos de voz para minha pequena ou média empresa?](whats-business-voice.md).

    3. Em **Quantidade**, selecione **1**.
        > [!NOTE]
        > Se você receber a mensagem **Você não tem licenças** suficientes para solicitar mais números desse tipo, certifique-se de ter comprado Teams Telefone com licenças de pacote do Plano de Chamada. Para obter mais informações, consulte [O que preciso comprar para obter recursos de voz para minha pequena ou média empresa?](whats-business-voice.md).
    4. Escolha o **código Local** ou **Área,** dependendo se você deseja pesquisar números de telefone usando a cidade de um local ou se deseja pesquisar números em um código de área específico.
    5. Se você selecionar **Local**:

        1. Digite a cidade na qual seu endereço de emergência está localizado na [](set-up-emergency-locations.md) etapa Configurar locais de emergência ou, se precisar criar um novo local para outro escritório ou um home office, clique em Adicionar **um local**.
        2. Em **Código de área**, selecione um código de área e selecione **Próximo** para reservar seu número.

    6. Se você selecionar **Código de área**, digite o código de área que deseja pesquisar e selecione **Próximo** para reservar seu número.

5. Selecione o número que deseja. Você tem 10 minutos para selecionar seu número de telefone e fazer seu pedido. Se você demorar mais de 10 minutos, o número de telefone será retornado para o pool de números.
6. Quando você estiver pronto para fazer seu pedido, clique em **Colocar ordem** e, em seguida, **Concluir**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurar números de telefone para seus usuários

1. Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global. Geralmente, essa é a conta que você usou para se inscrever no Microsoft 365.
2. Na navegação à esquerda, vá para <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Números Telefone** >  **Voz**</a> e clique em **Adicionar**.
3. Insira um nome para a ordem e adicione uma descrição.
4. Na página Local e quantidade, faça o seguinte:

    1. Em **País ou região**, selecione um país ou região.
    2. Em **Tipo de número**, selecione **Usuário (assinante)**.
    3. Em **Quantidade**, insira o número de números que você deseja para sua organização.
    4. Escolha o **código Local** ou **Área,** dependendo se você deseja pesquisar números de telefone usando a cidade de um local ou se deseja pesquisar números em um código de área específico.
    5. Se você selecionar **Local**:

        1. Digite a cidade na qual seu endereço de emergência está localizado na [](set-up-emergency-locations.md) etapa Configurar locais de emergência ou, se precisar criar um novo local para outro escritório ou um home office, clique em Adicionar **um local**.
        2. Em **Código de área**, selecione um código de área e selecione **Próximo** para reservar seu número.

    6. Se você selecionar **Código de área**, digite o código de área que deseja pesquisar e selecione **Próximo** para reservar seu número.
5. Selecione os números que você deseja. Você tem 10 minutos para selecionar seus números de telefone e fazer o pedido. Se você demorar mais de 10 minutos, os números de telefone serão retornados para o pool de números.
6. Quando estiver pronto para fazer o pedido, clique em **Colocar ordem** e, em seguida, **Concluir**.

> [!div class="nextstepaction"]
> [Próxima etapa: atribuir licenças a Teams usuários](set-up-licenses.md)
