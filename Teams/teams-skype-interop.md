---
title: Interoperabilidade do Teams e do Skype
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Saiba mais sobre os recursos de interoperabilidade entre usuários do Teams em sua organização e usuários do Skype (consumidor).
localization_priority: Normal
ms.openlocfilehash: 9063fc0f13bab9d0168296f9e77c5136e760b7a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802351"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilidade do Teams e do Skype

Este artigo fornece uma visão geral dos recursos de interoperabilidade entre o Microsoft Teams e o Skype (Consumidor). Saiba como os usuários do Teams e os usuários do Skype podem se comunicar por meio de chats e chamadas e os controles de administrador que se aplicam.

Os usuários do Teams em sua organização podem conversar e ligar para usuários do Skype usando seu endereço de email e vice-versa.

- Os usuários do Teams podem pesquisar e iniciar uma conversa somente texto ou uma chamada de áudio/vídeo com um usuário do Skype.
- Os usuários do Skype podem pesquisar e iniciar uma conversa somente texto ou uma chamada de áudio/vídeo com um usuário do Teams.

Esses recursos estão disponíveis na área de trabalho, na Web e nos clientes móveis (Android e iOS) para o Teams e o Skype. Para uma experiência ideal, recomendamos o Skype versão 8.58 e posterior.

> [!NOTE]
> Os recursos de interopção do Teams e do Skype discutidos neste artigo não estão disponíveis em implantações GCC, GCC High ou DOD ou em ambientes de nuvem privada.

## <a name="chat-and-calling-experience"></a>Experiência de chat e chamada

Aqui está uma visão geral da experiência de chat e chamada.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>O usuário do Teams inicia um chat ou uma chamada com um usuário do Skype

Os usuários do Teams podem pesquisar um usuário do Skype digitando seu endereço de email em um novo chat ou na barra de pesquisa.  O usuário do Teams pode selecionar o usuário do Skype nos resultados da pesquisa para iniciar um chat ou uma chamada com ele.

Um usuário do Skype pode optar por não aparecer nos resultados da pesquisa. Nesse caso, eles não aparecerão nos resultados da pesquisa no Teams e os usuários do Teams não poderão encontrá-los.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>O usuário do Skype inicia um chat ou chamada com um usuário do Teams

Os usuários do Skype podem pesquisar e iniciar um chat com um usuário do Teams usando seu endereço de email. O usuário do Teams é notificado de que tem uma nova mensagem de um usuário do Skype e precisa primeiro aceitar a mensagem antes de poder responder a ela.

- Se o usuário do Teams selecionar **Aceitar**, a conversa será aceita, e ambos os usuários poderão conversar e ligar uns para os outros.
- Se o usuário do Teams selecionar **Bloquear**, a conversa será bloqueada e as mensagens e chamadas subsequentes desse usuário do Skype serão bloqueadas.
- Se o usuário do Teams selecionar **Exibir** mensagens, a mensagem será exibida no Teams, o que ajuda o usuário a decidir se aceita ou bloqueia a conversa.

> [!NOTE]
> Se você atualizou do Skype for Business para o Teams e seus usuários estão no modo Somente Teams, chats e chamadas de usuários do Skype para usuários do Teams são entregues ao Teams. Se os usuários estão no modo Ilhas, chats e chamadas de usuários do Skype para usuários do Teams são entregues ao Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>O usuário do Teams bloqueia ou desbloqueia um usuário do Skype

Depois que um usuário do Teams aceita ou bloqueia a solicitação de conversa inicial de um usuário do Skype, ele pode optar por bloquear ou desbloquear essa pessoa a qualquer momento. Eles podem fazer isso na conversa ou em suas configurações de privacidade no Teams. Os usuários do Skype não saberão que foram bloqueados.

Os usuários bloqueados do Skype, juntamente com outras pessoas e números de telefone PSTN (Rede Telefônica Pública Comutada) que um usuário do Teams bloqueou, estão listados na lista de contatos bloqueados do usuário no Teams.

## <a name="limitations"></a>Limitações

- As conversas são somente texto. Isso significa que não há formatação, @mentions, emojis ou outros recursos de chat disponíveis em uma experiência de chat nativa do [Teams.](native-chat-for-external-users.md)
- As conversas são somente um para um. Não há suporte para chats em grupo.
- Os usuários do Teams e os usuários do Skype não podem ver a presença uns dos outros.
- Não há suporte para a pesquisa de usuários do Skype usando a ID ou o número de telefone do Skype.
- Os usuários do Skype não podem ligar para usuários do Teams que configuraram o encaminhamento de chamadas para o número de outro usuário, o número de um representante ou um número PSTN (Rede Telefônica Pública Comutado).  Somente a caixa postal é suportada.
- Não há suporte para escalonamento de interopção, chamadas de grupo e reuniões.
- Não há suporte para a capacidade de um representante chamar um usuário do Skype em nome de um usuário do Teams.
- Não há suporte para compartilhamento de tela com chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Definir se os usuários do Teams podem se comunicar com usuários do Skype

Como administrador, você usa o Centro de administração do Microsoft Teams ou o PowerShell para definir configurações de acesso externo para controlar se os usuários do Teams em sua organização podem se comunicar com usuários do Skype. Por padrão, esse recurso está ligado para novos locatários. No entanto, há um pré-requisito de que o seguinte registro SRV dns precise ser configurado pelo Administrador de IT se ainda não estiver disponível para seu domínio, por exemplo, _sipfederationtls.contoso.com.  

**Serviço**: sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridade**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destino**: sipfed.online.lync.com

Se você tiver atualizado do Skype for Business para o Teams, as configurações de comunicações externas que você definiu no Centro de administração do Skype for Business serão migradas para o Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>No Centro de administração do Microsoft Teams

No centro de administração do Microsoft Teams, acesse as configurações de toda a organização Acesso externo e, em seguida, a a opção Usuários podem se  >  comunicar com usuários **do Skype.** Para obter orientações passo a passo sobre como definir essa e outras configurações de acesso externo, consulte [Gerenciar o acesso externo no Teams.](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)

### <a name="using-powershell"></a>Usando o Windows PowerShell

Siga este procedimento: 
1. Use o cmdlet [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) juntamente com o parâmetro para controlar se os usuários do Teams podem se comunicar ```EnablePublicCloudAccess``` com usuários do Skype. Definir o parâmetro para ```true``` permitir que os usuários do Teams se comuniquem com usuários do Skype. Você pode usar o ```EnablePublicCloudAudioVideoAccess``` parâmetro para habilitar/desabilitar chamadas de áudio/vídeo.

2. Use o cmdlet [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) junto com o parâmetro definido para que os usuários do Teams possam se comunicar ```Provider``` com usuários do ```"WindowsLive"``` Skype.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o acesso externo no Teams](manage-external-access.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
