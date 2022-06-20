---
title: Teams e Skype interoperabilidade
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Saiba mais sobre os recursos de interoperabilidade entre Teams usuários em sua organização e Skype (Consumidor).
ms.localizationpriority: medium
ms.openlocfilehash: dd5bb05f1206baf94f2651899d0c49edbf6fe902
ms.sourcegitcommit: 5bb00d639828c744951a39705fefe81ed6698efe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2022
ms.locfileid: "66167265"
---
# <a name="teams-and-skype-interoperability"></a>Teams e Skype interoperabilidade

Este artigo fornece uma visão geral dos recursos de interoperabilidade entre Microsoft Teams e Skype (Consumidor). Saiba como Teams usuários e Skype podem se comunicar por meio de chats e chamadas e os controles de administrador que se aplicam.

Teams usuários em sua organização podem conversar e chamar Skype usuários usando seu endereço de email e vice-versa.

- Teams usuários podem pesquisar e iniciar uma conversa somente texto um-para-um ou uma chamada de áudio/vídeo com um Skype usuário.
- Skype usuários podem pesquisar e iniciar uma conversa somente texto um-para-um ou uma chamada de áudio/vídeo com um Teams usuário.

Esses recursos estão disponíveis na área de trabalho, web e clientes móveis (Android e iOS) para clientes Teams e Skype. Para obter uma experiência ideal, recomendamos Skype versão 8.58 e posterior.

> [!NOTE]
> Os recursos de interoperabilidade do Teams e do Skype discutidos neste artigo não estão disponíveis em implantações do GCC, do GCC High ou do DOD ou em ambientes de nuvem privada.

## <a name="chat-and-calling-experience"></a>Experiência de chat e chamada

Aqui está uma visão geral da experiência de chat e chamada.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams usuário inicia um chat ou chamada com um Skype usuário

Teams usuários podem pesquisar um usuário Skype digitando seu endereço de email em um novo chat ou na barra de pesquisa.  O Teams usuário pode selecionar o Skype nos resultados da pesquisa para iniciar um chat ou uma chamada com ele.

Um Skype usuário pode optar por não aparecer nos resultados da pesquisa. Nesse caso, eles não aparecerão nos resultados da pesquisa Teams e Teams os usuários não poderão encontrá-los.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype usuário inicia um chat ou chamada com um Teams usuário

Skype usuários podem pesquisar e iniciar um chat com um Teams usando seu endereço de email. O Teams usuário é notificado de que tem uma nova mensagem de um Skype usuário e precisa primeiro aceitar a mensagem antes de poder responder a ela.

- Se o Teams o usuário selecionar **Aceitar, a** conversa será aceita e ambos os usuários poderão conversar e ligar um para o outro.
- Se o Teams selecionar **Bloquear, a** conversa será bloqueada e as mensagens e chamadas subsequentes desse Skype usuário serão bloqueadas.
- Se o Teams selecionar Exibir **mensagens, a** mensagem será exibida no Teams, o que ajuda o usuário a decidir se deseja aceitar ou bloquear a conversa.

> [!NOTE]
> Se você atualizou do Skype for Business para o Teams e seus usuários estão no modo Somente Teams, chats e chamadas de usuários do Skype para usuários Teams são entregues Teams. Se os usuários estão no modo Ilhas, chats e chamadas de Skype usuários para Teams usuários são entregues Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams usuário bloqueia ou desbloqueia um Skype usuário

Depois que Teams usuário aceita ou bloqueia a solicitação de conversa inicial de um Skype usuário, ele pode optar por bloquear ou desbloquear essa pessoa a qualquer momento. Eles podem fazer isso na conversa ou em suas configurações de privacidade Teams. Skype os usuários não saberão que foram bloqueados.

Usuários Skype bloqueados, juntamente com outras pessoas e números de telefone PSTN (rede telefônica pública comuada) bloqueados por um usuário do Teams, são listados na lista de contatos bloqueados do usuário no Teams.

## <a name="limitations"></a>Limitações

- As conversas são somente texto. Isso significa que não há formatação avançada, @mentions, emojis ou outros recursos de chat disponíveis em uma experiência de [chat Teams nativa](native-chat-for-external-users.md).
- As conversas são somente um para um. Não há suporte para chats em grupo.
- Teams usuários e Skype usuários não podem ver a presença uns dos outros.
- A pesquisa Skype usuários usando sua ID Skype ou número de telefone não é compatível.
- Skype usuários não podem chamar Teams usuários que configuraram o encaminhamento de chamadas para o número de outro usuário, o número de um representante ou um número PSTN (Rede Telefônica Pública Comugada).  Há suporte apenas para a caixa postal.
- Não há suporte para escalonamento de interoperabilidade, chamadas de grupo e reuniões.
- Não há suporte para a capacidade de um representante chamar um Skype em nome de um Teams usuário.
- Não há suporte para o compartilhamento de tela com o chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Definir se Teams usuários podem se comunicar com Skype usuários

Como administrador, você usa o centro de administração do Microsoft Teams ou o PowerShell para definir configurações de acesso externo para controlar se Teams usuários em sua organização podem se comunicar com Skype usuários. Por padrão, essa funcionalidade é ativada para novos locatários. No entanto, há um pré-requisito de que o seguinte registro SRV DNS precise ser configurado pelo Administração de TI, se ainda não estiver disponível para seu domínio, por exemplo, _sipfederationtls._tcp.contoso.com.  

**Serviço**: sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridade**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destino**: sipfed.online.lync.com

Se você tiver atualizado do Skype for Business para o Teams, as configurações de comunicações externas que você definiu no centro de administração do Skype for Business serão migradas para Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>No Centro de administração do Microsoft Teams

No centro Microsoft Teams administradores,  >  acesse Acesso externo aos usuários **e, em** seguida, ative os usuários que podem se **comunicar com Skype usuários**. Para obter diretrizes passo a passo sobre como definir essa e outras configurações de acesso externo, consulte Gerenciar o acesso externo [no Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Siga este procedimento: 
1. Use o cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) ```EnablePublicCloudAccess``` junto com o parâmetro para controlar se Teams usuários podem se comunicar com Skype usuários. Definir o parâmetro para permitir ```true``` que Teams usuários se comuniquem com Skype usuários. Você pode usar o parâmetro ```EnablePublicCloudAudioVideoAccess``` para habilitar/desabilitar chamadas de áudio/vídeo.

2. Use o cmdlet ```Provider``` ```"WindowsLive"``` [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) junto com o parâmetro definido para que Teams usuários possam se comunicar com Skype usuários.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o acesso externo no Teams](manage-external-access.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
