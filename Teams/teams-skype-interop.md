---
title: Interoperabilidade do Teams e Skype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Saiba mais sobre os recursos de interoperabilidade entre os usuários do Teams em sua organização e usuários do Skype (Consumidor).
localization_priority: Normal
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055643"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilidade do Teams e Skype

Este artigo apresenta uma visão geral dos recursos de interoperabilidade entre o Microsoft Teams e o Skype (Consumidor). Saiba como os usuários do Teams e os usuários do Skype podem se comunicar por meio de chats e chamadas e os controles de administração que se aplicam.

Os usuários do Teams em sua organização podem conversar e ligar para usuários do Skype usando o endereço de email e vice-versa.

- Os usuários do Teams podem pesquisar e iniciar uma conversa entre duas pessoas ou uma chamada de áudio/vídeo com um usuário do Skype.
- Os usuários do Skype podem pesquisar e iniciar uma conversa entre duas pessoas ou uma chamada de áudio/vídeo com um usuário do Teams.

Esses recursos estão disponíveis nos clientes da área de trabalho, da Web e do celular (Android e iOS) para o Teams e o Skype. Para obter uma experiência ideal, recomendamos o Skype versão 8.58 e posterior.

> [!NOTE]
> Os recursos de interop do Teams e do Skype discutidos neste artigo não estão disponíveis nas implantações GCC, GCC High ou DOD ou em ambientes de nuvem particulares.

## <a name="chat-and-calling-experience"></a>Experiência de chat e chamada

Aqui está uma visão geral da experiência de chat e chamada.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>O usuário do Teams inicia um chat ou chamada com um usuário do Skype

Os usuários do Teams podem pesquisar um usuário do Skype digitando seu endereço de email em um novo chat ou na barra de pesquisa.  O usuário do Teams pode selecionar o usuário do Skype nos resultados da pesquisa para iniciar um chat ou chamada com ele.

Um usuário do Skype pode optar por não aparecer nos resultados da pesquisa. Nesse caso, eles não aparecerão nos resultados da pesquisa no Teams e os usuários do Teams não poderão encontrá-los.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>O usuário do Skype inicia um chat ou chamada com um usuário do Teams

Os usuários do Skype podem pesquisar e iniciar um chat com um usuário do Teams usando seu endereço de email. O usuário do Teams é notificado de que tem uma nova mensagem de um usuário do Skype e deve primeiro aceitar a mensagem antes de poder respondá-la.

- Se o usuário do Teams selecionar **Aceitar,** a conversa será aceita e os dois usuários poderão conversar e ligar um para o outro.
- Se o usuário do Teams selecionar **Bloquear,** a conversa será bloqueada, e as mensagens e chamadas subsequentes desse usuário do Skype serão bloqueadas.
- Se o usuário do Teams selecionar Exibir **mensagens,** a mensagem será exibida no Teams, o que ajuda o usuário a decidir se quer aceitar ou bloquear a conversa.

> [!NOTE]
> Se você atualizou do Skype for Business para o Teams e seus usuários estão no modo Somente equipes, chats e chamadas de usuários do Skype para usuários do Teams são entregues no Teams. Se os usuários estão no modo Ilhas, chats e chamadas de usuários do Skype para usuários do Teams são entregues no Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>O usuário do Teams bloqueia ou desbloqueia um usuário do Skype

Depois que um usuário do Teams aceitar ou bloquear a solicitação de conversa inicial de um usuário do Skype, ele poderá optar por bloquear ou desbloquear essa pessoa a qualquer momento. Eles podem fazer isso na conversa ou em suas configurações de privacidade no Teams. Os usuários do Skype não saberão que foram bloqueados.

Os usuários bloqueados do Skype, juntamente com outras pessoas e números de telefone PSTN (rede telefônica pública comutada) bloqueados por um usuário do Teams, estão listados na lista de contatos bloqueados do usuário no Teams.

## <a name="limitations"></a>Limitações

- As conversas são somente texto. Isso significa que não há formatação, @mentions, emojis ou outros recursos de chat disponíveis em uma experiência de chat nativa do [Teams.](native-chat-for-external-users.md)
- As conversas são somente entre duas pessoas. Não há suporte para chats em grupo.
- Os usuários do Teams e os usuários do Skype não podem ver a presença uns dos outros.
- Não há suporte para a pesquisa de usuários do Skype usando a ID do Skype ou o número de telefone.
- Os usuários do Skype não podem ligar para os usuários do Teams que configuraram o encaminhamento de chamadas para o número de outro usuário, o número de um representante ou um número PSTN (Rede Telefônica Pública Comutado).  Somente a caixa postal é suportada.
- Não há suporte para escalonamento, chamadas em grupo e reuniões.
- Não há suporte para a capacidade de um representante ligar para um usuário do Skype em nome de um usuário do Teams.
- O compartilhamento de tela com chat não é suportado.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Definir se os usuários do Teams podem se comunicar com usuários do Skype

Como administrador, você usa o Centro de administração do Microsoft Teams ou o PowerShell para definir configurações de acesso externo para controlar se os usuários do Teams em sua organização podem se comunicar com usuários do Skype. Por padrão, esse recurso está ligado para novos locatários. No entanto, há um pré-requisito de que o seguinte registro SRV DNS precise ser configurado pelo administrador de IT se ainda não estiver disponível para o seu domínio, por exemplo, _sipfederationtls.contoso.com.  

**Serviço**: sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridade**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destino**: sipfed.online.lync.com

Se você tiver atualizado do Skype for Business para o Teams, as configurações de comunicações externas configuradas no Centro de administração do Skype for Business serão migradas para o Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>No Centro de administração do Microsoft Teams

No Centro de administração do Microsoft Teams, vá para **as** configurações de toda a organização Acesso externo e a opção Usuários podem se comunicar  >  com usuários **do Skype.** Para obter orientações passo a passo sobre como configurar essa e outras configurações de acesso externo, consulte [Gerenciar o acesso externo no Teams.](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)

### <a name="using-powershell"></a>Usando o Windows PowerShell

Siga este procedimento: 
1. Use o cmdlet [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) juntamente com o parâmetro para controlar se os usuários do Teams podem se comunicar ```EnablePublicCloudAccess``` com usuários do Skype. Definindo o parâmetro para ```true``` permitir que os usuários do Teams se comuniquem com usuários do Skype. Você pode usar o ```EnablePublicCloudAudioVideoAccess``` parâmetro para habilitar/desabilitar chamadas de áudio/vídeo.

2. Use o cmdlet [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) juntamente com o parâmetro definido para que os usuários do Teams possam se comunicar ```Provider``` com usuários do ```"WindowsLive"``` Skype.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o acesso externo no Teams](manage-external-access.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
