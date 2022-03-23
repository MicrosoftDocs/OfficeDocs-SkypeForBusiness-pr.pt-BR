---
title: Teams de aplicativos com base em tipos de usuários
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como os aplicativos Microsoft Teams se comportam para diferentes tipos de usuários.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 765c0b97d5e277bd086ac4b25ee11ac80cb6fc11
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711475"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>Microsoft Teams comportamento de aplicativos com base em tipos de usuários

Teams os aplicativos se comportam quando convidados, externos (federados) e usuários anônimos estão presentes em um Teams contexto.

- Um **usuário convidado** é alguém que não é um funcionário, aluno ou membro da sua organização. Eles não têm uma conta escolar nem de trabalho com a sua organização.

- Um **usuário externo (federado)** pertence a outro domínio e não tem acesso às equipes ou recursos de equipe da sua organização.

  > [!Note]
  > Para obter uma comparação mais detalhada de convidados versus usuários externos, [consulte se comunicar com usuários de outras organizações](./communicate-with-users-from-other-organizations.md).

- Um **usuário anônimo** é um conceito Teams reuniões em que o usuário ingressou na reunião por meio de um link. O usuário não fez logont com a conta da Microsoft ou da organização.

## <a name="guest-users"></a>Usuários convidados

### <a name="install-update-and-delete-for-guest-users"></a>Instalar, atualizar e excluir usuários convidados

Os convidados não podem instalar, atualizar ou excluir aplicativos em um contexto compartilhado, como chat, canal ou reunião, mas podem usar extensões de mensagens e links diretos. Os convidados não têm acesso ao Teams de aplicativos do Teams da área de trabalho, mas podem acessá-lo com um link direto.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamento e política de uso para usuários convidados

Os convidados podem usar um aplicativo se o aplicativo foi instalado por um usuário nativo.

#### <a name="bots-installed-to-a-channel"></a>Bots instalados em um canal

Os bots podem enviar mensagens proativas aos usuários convidados, mas os convidados não podem interagir com o bot. Os convidados não podem enviar mensagens ao bot um para um, mencionar o bot ou interagir com cartões adaptáveis que se comunicam com o bot.

#### <a name="personal-bots-installed-with-policies"></a>Bots pessoais instalados com políticas

- Os convidados aderirão às políticas de permissão globais e em toda a organização definidas para o locatário do host para qualquer aplicativo. Se um aplicativo for bloqueado para toda a organização host, os convidados também não poderão usar o aplicativo.
- Qualquer bot incluído na política de configuração de aplicativo padrão global também será instalado para convidados.
- Depois que um bot é instalado, os bots podem se comunicar proativamente com convidados e os convidados podem se comunicar novamente com bots.
- Não é possível remover um convidado da política de configuração de aplicativo padrão global.
- Para evitar que os convidados acessem bots, você pode criar mais políticas de configuração de aplicativos, atribuí-las a usuários internos e instalar bots com as políticas personalizadas.

## <a name="external-federated-users"></a>Usuários externos (federados)

### <a name="install-update-and-delete-for-external-users"></a>Instalar, atualizar e excluir usuários externos

Os usuários externos não podem instalar, atualizar ou excluir aplicativos em qualquer contexto, como um pessoal, chat, canal ou reunião. Eles não têm acesso ao Teams de aplicativos da organização de hospedagem.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamento e política de uso para usuários externos

- Pessoas de outras organizações aderem à política global (padrão em toda a organização) da organização de hospedagem
- Os usuários na organização de hospedagem podem adicionar aplicativos em chats de reunião com pessoas de outras organizações. As pessoas de outras organizações não podem adicionar aplicativos em chats de reunião, mas podem interagir com bots, guias e extensões de mensagens depois de adicionadas ao chat.
- Depois que um bot é instalado em um chat de reunião, ele pode se comunicar proativamente com pessoas de outras organizações nesse chat e essas pessoas podem se comunicar com o bot.
- As políticas de dados da organização de hospedagem, bem como as práticas de compartilhamento de dados de quaisquer aplicativos de terceiros compartilhados pela organização desse usuário, são aplicadas.

## <a name="anonymous-users"></a>Usuários anônimos

### <a name="install-update-and-delete-for-anonymous-users"></a>Instalar, atualizar e excluir usuários anônimos

Os usuários anônimos não podem instalar, atualizar ou excluir aplicativos em reuniões.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamento e política de uso para usuários anônimos

Os usuários anônimos não podem usar aplicativos diretamente em reuniões. Os usuários nativos podem continuar a usar aplicativos de reuniões se os usuários anônimos estão presentes. Se um aplicativo enviar um cartão adaptável no chat, os usuários anônimos poderão interagir com o cartão. Para obter mais informações, leia [Permitir que usuários anônimos participem de reuniões](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

Os usuários anônimos herdarão a política de permissão padrão global no nível do usuário. Eles podem interagir com aplicativos Teams reuniões se a política de permissão no nível do usuário habilitar o aplicativo. Os usuários anônimos só podem interagir com aplicativos que já estão disponíveis em uma reunião e não podem adquirir e/ou gerenciar esses aplicativos.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar políticas de configuração de aplicativo no Microsoft Teams](teams-app-setup-policies.md)
