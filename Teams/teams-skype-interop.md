---
title: Teams e interoperabilidade do Skype
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
description: Saiba mais sobre os recursos de interoperabilidade entre usuários do teams na sua organização e usuários do Skype (cliente).
localization_priority: Normal
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055643"
---
# <a name="teams-and-skype-interoperability"></a>Teams e interoperabilidade do Skype

Este artigo oferece uma visão geral dos recursos de interoperabilidade entre o Microsoft Teams e o Skype (consumidor). Saiba como os usuários do Microsoft Teams e usuários do Skype podem se comunicar por meio de chats e chamadas e dos controles de administração que se aplicam.

Os usuários do teams em sua organização podem conversar com usuários do Skype e fazer chamadas para usuários do Skype usando o endereço de e-mail e vice-versa.

- Os usuários do teams podem pesquisar e iniciar uma conversa apenas com texto único ou uma chamada de áudio/vídeo com um usuário do Skype.
- Os usuários do Skype podem pesquisar e iniciar uma conversa apenas com texto único ou uma chamada de áudio/vídeo com um usuário do teams.

Esses recursos estão disponíveis nos clientes da área de trabalho, Web e móvel (Android e iOS) para o Teams e o Skype. Para obter uma experiência ideal, recomendamos o Skype versão 8,58 e posterior.

> [!NOTE]
> As equipes e os recursos do Skype Interop discutidos neste artigo não estão disponíveis em implantações GCC, GCC High ou DOD ou em ambientes de nuvem privada.

## <a name="chat-and-calling-experience"></a>Experiência de chat e chamadas

Aqui está uma visão geral da experiência de chat e chamadas.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>O usuário do teams inicia um chat ou uma chamada com um usuário do Skype

Os usuários do teams podem pesquisar um usuário do Skype, digitando o endereço de e-mail deles em um novo chat ou na barra de pesquisa.  O usuário do teams pode, em seguida, selecionar o usuário do Skype nos resultados da pesquisa para iniciar um chat ou uma chamada.

Um usuário do Skype pode optar por não aparecer nos resultados da pesquisa. Nesse caso, eles não aparecerão nos resultados da pesquisa no Teams e os usuários do Teams não poderão encontrá-los.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>O usuário do Skype inicia um chat ou uma chamada com um usuário do teams

Os usuários do Skype podem pesquisar e iniciar um chat com um usuário do teams usando o endereço de e-mail deles. O usuário do teams é notificado de que ele tem uma nova mensagem de um usuário do Skype e precisa primeiro aceitar a mensagem para poder respondê-la.

- Se o usuário do teams selecionar **aceitar**, a conversa é aceita, e ambos os usuários podem conversar entre si e fazer chamadas.
- Se o usuário do teams selecionar **Bloquear**, a conversa será bloqueada e as chamadas e mensagens subsequentes desse usuário do Skype serão bloqueadas.
- Se o usuário do teams selecionar **Exibir mensagens**, a mensagem será exibida no Microsoft Teams, o que ajuda o usuário a decidir se deseja aceitar ou bloquear a conversa.

> [!NOTE]
> Se você atualizou do Skype for Business para o Teams e seus usuários estão no modo somente equipes, chats e chamadas de usuários do Skype para o Teams usuários são entregues ao Teams. Se os usuários estiverem no modo de ilhas, chats e chamadas de usuários do Skype para os usuários do teams serão entregues ao Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>O usuário do teams bloqueia ou desbloqueia um usuário do Skype

Depois que um usuário do teams aceitar ou bloquear a solicitação de conversa inicial de um usuário do Skype, ele pode optar por bloquear ou desbloquear essa pessoa a qualquer momento. Isso pode ser feito na conversa ou nas configurações de privacidade do Microsoft Teams. Os usuários do Skype não saberão que foram bloqueados.

Os usuários bloqueados do Skype, juntamente com outras pessoas e números de telefone PSTN (rede telefônica pública comutada) que o usuário do teams bloqueou, estão listados na lista de contatos bloqueados do usuário no Microsoft Teams.

## <a name="limitations"></a>Relacionadas

- As conversas são somente texto. Isso significa que não há formatação avançada, @mentions, emojis ou outros outros recursos de chat que estão disponíveis em uma experiência de chat de [equipes nativas](native-chat-for-external-users.md).
- As conversas são apenas uma a uma. Não há suporte para chats em grupo.
- Os usuários do Microsoft Teams e os usuários do Skype não conseguem ver a presença dos outros.
- Não há suporte para a pesquisa de usuários do Skype usando sua ID Skype ou número de telefone.
- Os usuários do Skype não podem chamar usuários de equipes que configuram o encaminhamento de chamadas para o número de outro usuário, o número de um representante ou um número de rede telefônica pública comutada (PSTN).  Só há suporte para correio de voz.
- Não há suporte para escalonamento de interoperabilidade, chamadas de grupo e reuniões.
- A capacidade de um representante fazer chamadas para um usuário do Skype em nome de um usuário do Teams não é compatível.
- Não há suporte para o compartilhamento de tela com o chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Definir se os usuários do teams podem se comunicar com usuários do Skype

Como administrador, você usa o centro de administração do Microsoft Teams ou o PowerShell para definir as configurações de acesso externo para controlar se os usuários de equipes em sua organização podem se comunicar com os usuários do Skype. Por padrão, essa funcionalidade está ativada para novos locatários. No entanto, há um pré-requisito de que o registro SRV DNS a seguir precisa ser configurado pelo administrador de ti se ainda não estiver disponível para seu domínio, por exemplo _sipfederationtls. contoso. com.  

**Serviço**: sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridade**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destino**: sipfed.online.Lync.com

Se você atualizou do Skype for Business para o Teams, as configurações de comunicações externas que você configurou no centro de administração do Skype for Business serão migradas para o Microsoft Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>No Centro de administração do Microsoft Teams

No centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  >  **acesso externo** e ative **os usuários podem se comunicar com usuários do Skype**. Para obter orientação passo a passo sobre como definir essa e outras configurações de acesso externo, consulte [gerenciar o acesso externo no Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Siga este procedimento: 
1. Use o cmdlet [set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) juntos com o ```EnablePublicCloudAccess``` parâmetro para controlar se os usuários do teams podem se comunicar com os usuários do Skype. Definir o parâmetro para ```true``` permitir que os usuários do Team se comuniquem com usuários do Skype. Você pode usar o ```EnablePublicCloudAudioVideoAccess``` parâmetro para habilitar/desabilitar chamadas de áudio/vídeo.

2. Use o cmdlet [set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) juntos com o ```Provider``` parâmetro definido para ```"WindowsLive"``` que os usuários do teams possam se comunicar com usuários do Skype.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o acesso externo no Teams](manage-external-access.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
