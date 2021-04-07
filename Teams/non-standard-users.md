---
title: Comportamento de aplicativos do Teams para usuários não padrão
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como os aplicativos no Microsoft Teams se comportam para usuários não padrão.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc4f4f53262127355afa573b0fc2abec6b05e64
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607513"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Comportamento de aplicativos do Microsoft Teams para usuários não padrão

Este artigo descreve como os aplicativos no Teams se comportam quando os usuários convidados, externos (federados) e anônimos estão presentes em um contexto do Teams.

- Um **usuário convidado** é alguém que não é um funcionário, aluno ou membro da sua organização. Eles não têm uma conta escolar nem de trabalho com a sua organização.

- Um **usuário externo (federado)** pertence a outro domínio e não tem acesso às equipes ou recursos de equipe da sua organização.

>[!Note]
> Para obter uma comparação mais detalhada de convidados versus usuários externos, [consulte se comunicar com usuários de outras organizações.](./communicate-with-users-from-other-organizations.md)

- Um **usuário anônimo é** um conceito nas reuniões do Teams em que o usuário ingressou na reunião por meio de um link. O usuário não fez logont com a conta da Microsoft ou da organização.

## <a name="guest-user-access"></a>Acesso de usuário convidado

### <a name="install-update-and-delete-for-guest-users"></a>Instalar, atualizar e excluir usuários convidados

Os convidados não podem instalar, atualizar ou excluir aplicativos em um contexto compartilhado, como chat, canal ou reunião. Eles podem instalar, atualizar ou excluir aplicativos em seu escopo pessoal usando extensões de mensagens e links diretos. Os convidados não têm acesso à loja de aplicativos do Teams.

### <a name="usage-behavior-and-policy-for-guest-users"></a>Comportamento e política de uso para usuários convidados

Os convidados podem usar um aplicativo se o aplicativo foi instalado por um usuário nativo.

Os bots podem enviar mensagens proativas aos usuários convidados, mas os convidados não podem interagir com o bot. Os convidados não podem enviar mensagens ao bot 1:1, @ mencionar o bot ou interagir com cartões adaptáveis que se comunicam com o bot.

Os convidados aderirão às políticas de permissão globais e em toda a organização definidas para o locatário do host para qualquer aplicativo. Em outras palavras, se um aplicativo for bloqueado para toda a organização host, os convidados também não poderão usar o aplicativo.

As políticas de instalação não se aplicam aos usuários convidados. Isso significa que o aplicativo fixado pelo administrador da política padrão não afeta os usuários convidados.

## <a name="external-federated-user-access"></a>Acesso de usuário externo (federado)

### <a name="install-update-and-delete-for-external-users"></a>Instalar, atualizar e excluir usuários externos

Os usuários externos não podem instalar, atualizar ou excluir aplicativos em qualquer contexto, como um pessoal, chat, canal ou reunião. Eles não têm acesso à loja de aplicativos do Teams.

### <a name="usage-behavior-and-policy-for-external-users"></a>Comportamento e política de uso para usuários externos

Os usuários externos não podem usar nenhum aplicativo do Teams e, quando um usuário externo é adicionado a um contexto com usuários nativos, todos os usuários – nativos e externos – não podem mais usar aplicativos.

Os usuários externos não são afetados pelas políticas de aplicativo, pois não podem usar aplicativos do Teams.

## <a name="anonymous-user-in-meetings-access"></a>Usuário anônimo no acesso a reuniões

### <a name="install-update-and-delete-for-anonymous-users"></a>Instalar, atualizar e excluir usuários anônimos

Os usuários anônimos não podem instalar, atualizar ou excluir aplicativos em reuniões.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>Comportamento e política de uso para usuários anônimos

Os usuários anônimos não podem usar aplicativos diretamente em reuniões. Os usuários nativos podem continuar a usar aplicativos de reuniões se os usuários anônimos estão presentes. Se um aplicativo enviar um cartão adaptável no chat, os usuários anônimos poderão interagir com o cartão Para obter mais informações, consulte Permitir que usuários anônimos participem [de reuniões.](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)

Os usuários anônimos herdarão a política de permissão padrão global no nível do usuário. Eles podem interagir com aplicativos em reuniões do Teams se a política de permissão no nível do usuário habilitar o aplicativo. Os usuários anônimos só podem interagir com aplicativos que já estão disponíveis em uma reunião e não podem adquirir e/ou gerenciar esses aplicativos.
