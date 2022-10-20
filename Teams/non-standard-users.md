---
title: Disponibilidade e uso de aplicativos do Teams por diferentes tipos de usuários
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: kojika
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Saiba como os aplicativos no Microsoft Teams funcionam para convidados, usuários federados e usuários anônimos.
ms.localizationpriority: high
ms.date: 09/28/2022
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: 201130f218a2ad482a60a7c746203f93120cc773
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613973"
---
# <a name="use-teams-apps-as-an-external-attendees-or-guest"></a>Usar aplicativos do Teams como participantes externos ou convidados

Os aplicativos do Teams permitem a colaboração com pessoas de fora da sua organização. Como administrador, você controla quem pode acessar chats, reuniões e canais do Teams para colaborar com os usuários da sua organização. Para obter informações detalhadas, [confira como permitir a colaboração com participantes externos e](manage-external-access.md) o que [os convidados podem fazer no Teams](guest-access.md). Este artigo se concentra no uso de aplicativos por pessoas de fora da sua organização.

Os tipos de usuários a seguir podem estar presentes em um chat ou reunião do Teams e, se você permitir, eles podem usar aplicativos no Teams.

* Um **usuário convidado** é alguém que não é um funcionário, aluno ou membro da sua organização. Eles não têm uma conta escolar nem de trabalho com a sua organização.

* Um **usuário externo (federado)** é de outro domínio e não tem acesso aos recursos do Teams da sua organização.

* Um **usuário anônimo** é um usuário que ingressa em uma reunião por meio de um link. O usuário não está conectado com sua conta da Microsoft ou com a conta da organização.

Para obter uma comparação mais detalhada entre usuários convidados e externos, consulte [a comunicação com usuários de outras organizações](communicate-with-users-from-other-organizations.md).

## <a name="guests"></a>Convidados

### <a name="install-update-and-delete-apps-for-guests"></a>Instalar, atualizar e excluir aplicativos para convidados

Os convidados não podem instalar, atualizar ou excluir aplicativos em um contexto compartilhado, como chat, canal ou reunião. Os convidados podem fazer isso em seu escopo pessoal usando extensões de mensagem e links diretos. Os convidados não podem acessar a loja de aplicativos do Teams no aplicativo da área de trabalho do Teams, mas podem acessar a loja com um link direto.

### <a name="usage-behavior-and-policy-for-guests"></a>Comportamento de uso e política para convidados

Os convidados poderão usar um aplicativo se o aplicativo tiver sido instalado pelo usuário de uma organização.

#### <a name="bots-installed-to-a-channel"></a>Bots instalados em um canal

Os convidados podem mencionar o bot e interagir com cartões adaptáveis.

#### <a name="personal-bots-installed-with-policies"></a>Bots pessoais instalados com políticas

* Para qualquer aplicativo, os convidados seguem as políticas de permissão globais e em toda a organização definidas para a organização host. Se um aplicativo estiver bloqueado para toda a organização host, os convidados também não poderão usar o aplicativo.
* Qualquer bot incluído na política de configuração de aplicativo padrão global também será instalado para convidados.
* Depois que um bot é instalado, bots e convidados podem se comunicar proativamente entre si.
* Não é possível remover um convidado da política de configuração de aplicativo padrão global.
* Para evitar que o convidado acesse bots, você pode criar mais políticas de configuração de aplicativo, atribuí-las a usuários internos e instalar bots com as políticas personalizadas.

## <a name="federated-users"></a>Usuários federados

### <a name="install-update-and-delete-apps-for-federated-users"></a>Instalar, atualizar e excluir aplicativos para usuários federados

Os usuários federados não podem instalar, atualizar ou excluir aplicativos em qualquer contexto, como um chat, um canal ou uma reunião pessoal. Eles não têm acesso à loja de aplicativos do Teams da organização de hospedagem.

### <a name="usage-behavior-and-policy-for-federated-users"></a>Comportamento e política de uso para usuários federados

* Pessoas de outras organizações aderem à política global da organização de hospedagem (padrão em toda a organização)
* Os usuários na organização de hospedagem podem adicionar aplicativos em chats de reunião com pessoas de outras organizações. Pessoas de outras organizações não podem adicionar aplicativos em chats de reunião, mas podem interagir com bots, guias e extensões de mensagem depois de adicionados ao chat.
* Depois que um bot é instalado em um chat de reunião, ele pode se comunicar proativamente com pessoas de outras organizações nesse chat, e essas pessoas podem se comunicar com o bot.
* As políticas de dados da organização de hospedagem são aplicadas.
* As práticas de compartilhamento de dados de aplicativos de terceiros compartilhados pela organização desse usuário são aplicadas.

## <a name="anonymous-users"></a>Usuários anônimos

### <a name="install-update-and-delete-apps-for-anonymous-users"></a>Instalar, atualizar e excluir aplicativos para usuários anônimos

Os usuários anônimos não podem instalar, atualizar ou excluir aplicativos em reuniões.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamento e política de uso para usuários anônimos

Usuários anônimos não podem usar aplicativos diretamente em reuniões. Se um aplicativo enviar um cartão adaptável no chat, os usuários anônimos poderão interagir com o cartão. Esses usuários poderão interagir com aplicativos em reuniões do Teams se a política de permissão no nível do usuário habilitar o aplicativo. Os usuários anônimos herdam a política de permissão padrão global no nível do usuário.

Os usuários anônimos só podem interagir com os aplicativos que já estão disponíveis em uma reunião, mas não podem adquirir e gerenciar esses aplicativos. Os usuários nativos podem continuar a usar aplicativos de reuniões mesmo quando os usuários anônimos estão participando de uma reunião.

### <a name="disallow-anonymous-users-to-use-apps-in-meetings"></a>Não permitir que usuários anônimos usem aplicativos em reuniões

Por padrão, os usuários anônimos podem interagir com os aplicativos existentes em uma reunião. Você pode não permitir que usuários anônimos interajam com aplicativos.

1. Entre no centro de administração do Teams e acesse as **configurações de Reunião** > **[de Reuniões](https://admin.teams.microsoft.com/meetings/settings)**.

1. Em **Participantes, altere** a alternância para que os **usuários anônimos possam interagir com aplicativos em reuniões** para **Desativado**.

1. Selecione **Salvar**.

## <a name="related-articles"></a>Artigos relacionados

* [Permitir que usuários anônimos ingressem em reuniões](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Gerenciar políticas de configuração de aplicativo no Microsoft Teams](teams-app-setup-policies.md).
* [Como permitir a colaboração com convidados e participantes externos](manage-external-access.md).
* [O que os convidados podem fazer no Teams](guest-access.md)
