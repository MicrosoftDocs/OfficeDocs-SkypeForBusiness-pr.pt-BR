---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Saiba como usar o estacionamento de chamada e recuperar para colocar uma chamada em espera no Microsoft Teams.
ms.openlocfilehash: 9092e76b9d8db5e29c1dd5881cd6b0f69d70ae4a
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249503"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamento e recuperação de chamadas no Microsoft Teams

Estacionamento de chamada e recuperação é um recurso que permite que um usuário coloque uma chamada em espera. Quando uma chamada é estacionada, o serviço gera um código exclusivo para recuperação de chamada. O usuário que estacionou a chamada ou outra pessoa pode usar esse código com um aplicativo ou dispositivo com suporte para recuperar a chamada. (Consulte [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) para obter detalhes.)

Alguns dos cenários comuns para o uso do estacionamento de chamada são:

- Uma recepcionista estaciona uma chamada para alguém que trabalha em uma fábrica. Em seguida, a recepcionista anuncia a chamada e o número de código no sistema de endereços público. O usuário para quem a chamada é pode, em seguida, escolher um telefone Teams no piso da fábrica e inserir o código para recuperar a chamada.
- Um usuário estaciona uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia. Em seguida, o usuário pode inserir o código para recuperar a chamada de um telefone Teams de mesa.
- Um representante de suporte estaciona uma chamada do cliente e envia um comunicado em um canal Teams para um especialista recuperar a chamada e ajudar o cliente. Um especialista inssi o código em Teams clientes para recuperar a chamada

Para estacionar e recuperar chamadas, um usuário deve ser Enterprise Voice usuário e deve ser incluído em uma política de estacionamento de chamadas.

> [!NOTE]
> O estacionamento de chamada e a recuperação só estão disponíveis [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) modo de implantação somente e não são suportados em telefones IP Skype for Business ip.

## <a name="configure-call-park-and-retrieve"></a>Configurar estacionamento de chamada e recuperar

Você deve ser um administrador Teams para configurar o estacionamento de chamada e recuperar. Ele está desabilitado por padrão. Você pode habilita-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamada. Quando você aplica a mesma política a um conjunto de usuários, eles podem estacionar e recuperar chamadas entre si.

O intervalo de números de retirada de chamada é predefinido de 10 a 99 e não pode ser modificado. A primeira chamada estacionada será renderizada com um código de retirada de 10, a próxima chamada estacionada será renderizada um código de retirada de 11, etc. até que 99 seja renderizado como um código de retirada. Depois disso, os códigos de retirada renderizados começam de 10 novamente.  Se houver mais de 89 chamadas estacionadas ativas, os códigos de retirada renderizados continuarão aumentando além de 99, de forma que a 90ª chamada estacionada ativa seria renderizada 100 para um código de retirada, a chamada estacionada ativa do 91st seria renderizada com um código de retirada de 101.

Para habilitar uma política de estacionamento de chamada

1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Políticas**  >  **de estacionamento de Chamada de Voz**.
2. Na guia **Gerenciar políticas,** clique em **Adicionar**.
3. Dê um nome à política e **alterne Permitir** estacionamento de chamada para **On**. (O intervalo de retirada de chamada e o tempo de saída não podem ser personalizados.)

    ![Captura de tela das configurações de política de estacionamento de chamada.](media/call-park-add-policy.png)

4. Selecione **Salvar**.

Você pode editar a política selecionando-a na lista e clicando em **Editar**.

Para que a política funcione, ela deve ser atribuída aos usuários. Você pode [atribuir a política aos usuários individualmente](assign-policies.md) ou atribuí-la a um grupo.

Para atribuir uma política de estacionamento de chamada a um grupo

1. Na página **Políticas de estacionamento de** chamada, na guia Atribuição de **política** de grupo, clique em **Adicionar grupo**.
2. Pesquise o grupo que você deseja usar e clique em **Adicionar**.
3. Escolha uma classificação em comparação com outras atribuições de grupo.
4. Em **Selecionar uma política,** escolha a política à qual você deseja atribuir esse grupo.

    ![imagem de políticas de estacionamento.](media/call-park-assign-policy-to-group.png)

5. Selecione **Aplicar**.

## <a name="related-topics"></a>Tópicos relacionados

[Estae uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Atribuir políticas aos usuários no Microsoft Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
