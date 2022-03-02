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
description: Saiba mais sobre os recursos de interoperabilidade entre Teams usuários em sua organização e usuários Skype (Consumidor).
ms.localizationpriority: medium
ms.openlocfilehash: b18933b70708661dbb9f7f3a05aaa65983792c5c
ms.sourcegitcommit: 71edff2670367082312de59c4e21775682871418
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63043329"
---
# <a name="teams-and-skype-interoperability"></a>Teams e Skype interoperabilidade

Este artigo fornece uma visão geral dos recursos de interoperabilidade entre Microsoft Teams e Skype (Consumidor). Saiba como Teams usuários e Skype usuários podem se comunicar por meio de chats e chamadas e os controles de administrador que se aplicam.

Teams usuários em sua organização podem conversar e chamar Skype usuários usando seu endereço de email e vice-versa.

- Teams os usuários podem pesquisar e iniciar uma conversa somente texto ou uma chamada de áudio/vídeo com um Skype usuário.
- Skype usuários podem pesquisar e iniciar uma conversa somente texto ou uma chamada de áudio/vídeo com um Teams usuário.

Esses recursos estão disponíveis nos clientes desktop, web e mobile (Android e iOS) para clientes Teams e Skype. Para uma experiência ideal, recomendamos Skype versão 8.58 e posterior.

> [!NOTE]
> Os recursos de Teams e Skype de interop discutidos neste artigo não estão disponíveis em implantações do GCC, GCC High ou DOD ou em ambientes de nuvem particulares.

## <a name="chat-and-calling-experience"></a>Experiência de chat e chamada

Aqui está uma visão geral da experiência de chat e chamada.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams usuário inicia um chat ou chamada com um Skype usuário

Teams os usuários podem pesquisar um usuário Skype digitando seu endereço de email em um novo chat ou na barra de pesquisa.  O Teams usuário pode selecionar o usuário Skype nos resultados da pesquisa para iniciar um chat ou uma chamada com ele.

Um Skype usuário pode optar por não aparecer nos resultados da pesquisa. Nesse caso, eles não aparecerão nos resultados da pesquisa em Teams e Teams os usuários não poderão encontrá-los.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype usuário inicia um chat ou chamada com um Teams usuário

Skype os usuários podem pesquisar e iniciar um chat com um usuário Teams usando seu endereço de email. O Teams usuário é notificado de que ele tem uma nova mensagem de um usuário Skype e precisa primeiro aceitar a mensagem antes de poder responder a ela.

- Se o Teams o usuário selecionar **Aceitar**, a conversa será aceita e ambos os usuários poderão conversar e chamar uns aos outros.
- Se o Teams o usuário selecionar **Bloquear**, a conversa será bloqueada e as mensagens e chamadas subsequentes desse Skype usuário serão bloqueadas.
- Se o Teams o usuário selecionar Exibir **mensagens, a** mensagem será exibida no Teams, o que ajuda o usuário a decidir se aceita ou bloqueia a conversa.

> [!NOTE]
> Se você atualizou do Skype for Business para o Teams e seus usuários estão no modo Somente Teams, chats e chamadas de usuários do Skype para Teams usuários são entregues Teams. Se os usuários estão no modo Ilhas, chats e chamadas de usuários Skype usuários Teams usuários são entregues Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams ou desbloqueia um usuário Skype usuário

Depois que um Teams aceita ou bloqueia a solicitação de conversa inicial de um usuário Skype, ele pode optar por bloquear ou desbloquear essa pessoa a qualquer momento. Eles podem fazer isso na conversa ou em suas configurações de privacidade Teams. Skype os usuários não saberão que foram bloqueados.

Os usuários Skype bloqueados, juntamente com outras pessoas e números de telefone PSTN (rede telefônica pública comutada) que um usuário Teams bloqueou, estão listados na lista de contatos bloqueados do usuário no Teams.

## <a name="limitations"></a>Limitações

- As conversas são somente texto. Isso significa que não há formatação, @mentions, emojis ou outros recursos de chat que estão disponíveis em uma experiência de chat Teams [nativa](native-chat-for-external-users.md).
- As conversas são somente um para um. Não há suporte para chats em grupo.
- Teams usuários e Skype usuários não podem ver a presença uns dos outros.
- A pesquisa Skype usuários usando sua Skype ID ou número de telefone não é suportado.
- Skype usuários não podem chamar Teams usuários que configurarem o encaminhamento de chamadas para o número de outro usuário, o número de um representante ou um número PSTN (Rede Telefônica Pública Comugada).  Somente a caixa postal é suportada.
- Não há suporte para escalonamento de interop, chamadas de grupo e reuniões.
- A capacidade de um representante chamar um Skype usuário em nome de um usuário Teams não é suportada.
- Não há suporte para compartilhamento de tela com chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Definir se Teams os usuários podem se comunicar com Skype usuários

Como administrador, você usa o centro de administração do Microsoft Teams ou o PowerShell para definir configurações de acesso externo para controlar se Teams usuários em sua organização podem se comunicar com Skype usuários. Por padrão, esse recurso está ligado para novos locatários. No entanto, há um pré-requisito de que o seguinte registro DNS SRV precise ser configurado pelo Administrador de IT se ainda não estiver disponível para seu domínio, por exemplo, _sipfederationtls._tcp.contoso.com.  

**Serviço**: sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridade**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destino**: sipfed.online.lync.com

Se você tiver atualizado de Skype for Business para Teams, as configurações de comunicações externas configuradas no centro de administração do Skype for Business serão migradas para Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>No Centro de administração do Microsoft Teams

No centro Microsoft Teams de administração, acesse **Configurações** >  em toda a organização **Acessoexternal** e, em seguida, ativar Usuários podem se comunicar **com Skype usuários**. Para obter orientações passo a passo sobre como configurar essa e outras configurações de acesso externo, consulte [Gerenciar o acesso externo no Teams](./manage-external-access.md#allow-or-block-domains).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Siga este procedimento: 
1. Use o cmdlet ```EnablePublicCloudAccess``` [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) juntamente com o parâmetro para controlar se Teams usuários podem se comunicar com Skype usuários. Definir o parâmetro para ```true``` permitir que Teams usuários se comuniquem com Skype usuários. Você pode usar o parâmetro ```EnablePublicCloudAudioVideoAccess``` para habilitar/desabilitar chamadas de áudio/vídeo.

2. Use o cmdlet ```Provider``` ```"WindowsLive"``` [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) juntamente com o parâmetro definido como para que Teams usuários possam se comunicar com Skype usuários.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar acesso externo em Teams](manage-external-access.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
