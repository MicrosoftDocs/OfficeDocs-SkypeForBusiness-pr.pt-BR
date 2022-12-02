---
title: Interoperabilidade do Teams e do Skype
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Saiba mais sobre os recursos de interoperabilidade entre usuários do Teams em sua organização e usuários do Skype (Consumidor).
ms.localizationpriority: medium
ms.openlocfilehash: 5cbb4bdf492de67131c75c97685317ef8cae866c
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242315"
---
# <a name="teams-and-skype-interoperability"></a>Interoperabilidade do Teams e do Skype

Este artigo fornece uma visão geral dos recursos de interoperabilidade entre Microsoft Teams e Skype (Consumidor). Saiba como os usuários do Teams e os usuários do Skype podem se comunicar por meio de chats e chamadas e dos controles de administrador que se aplicam.

Os usuários do Teams em sua organização podem conversar e chamar usuários do Skype usando seu endereço de email e vice-versa.

- Os usuários do Teams podem pesquisar e iniciar uma conversa de texto individual ou uma chamada de áudio/vídeo com um usuário do Skype.
- Os usuários do Skype podem pesquisar e iniciar uma conversa de texto individual ou uma chamada de áudio/vídeo com um usuário do Teams.

Esses recursos estão disponíveis na área de trabalho, na Web e nos clientes móveis (Android e iOS) para o Teams e o Skype. Para uma experiência ideal, recomendamos o Skype versão 8.58 e posterior.

> [!NOTE]
> Os recursos de interoperabilidade do Teams e do Skype discutidos neste artigo não estão disponíveis em implantações do GCC, do GCC High ou do DOD ou em ambientes de nuvem privada.

## <a name="chat-and-calling-experience"></a>Experiência de chat e chamada

Aqui está uma visão geral da experiência de chat e chamada.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>O usuário do Teams inicia um chat ou uma chamada com um usuário do Skype

Os usuários do Teams podem procurar um usuário do Skype digitando seu endereço de email em um novo chat ou na barra de pesquisa.  Em seguida, o usuário do Teams pode selecionar o usuário do Skype nos resultados da pesquisa para iniciar um chat ou chamar com eles.

Um usuário do Skype pode optar por não aparecer nos resultados da pesquisa. Nesse caso, eles não aparecerão nos resultados da pesquisa nos usuários do Teams e do Teams não poderão encontrá-los.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>O usuário do Skype inicia um chat ou uma chamada com um usuário do Teams

Os usuários do Skype podem pesquisar e iniciar um chat com um usuário do Teams usando seu endereço de email. O usuário do Teams é notificado de que tem uma nova mensagem de um usuário do Skype e precisa primeiro aceitar a mensagem antes de poder responder a ela.

- Se o usuário do Teams selecionar **Aceitar**, a conversa será aceita e ambos os usuários poderão conversar e chamar uns aos outros.
- Se o usuário do Teams selecionar **Bloquear**, a conversa será bloqueada e as mensagens e chamadas subsequentes desse usuário do Skype serão bloqueadas.
- Se o usuário do Teams selecionar **Exibir mensagens**, a mensagem será exibida no Teams, o que ajudará o usuário a decidir se aceita ou bloqueia a conversa.

> [!NOTE]
> Se você tiver atualizado de Skype for Business para o Teams e seus usuários estiverem no modo Somente Do Teams, chats e chamadas de usuários do Skype para usuários do Teams serão entregues ao Teams. Se os usuários estiverem no modo Ilhas, chats e chamadas de usuários do Skype para usuários do Teams serão entregues para Skype for Business.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>O usuário do Teams bloqueia ou desbloqueia um usuário do Skype

Depois que um usuário do Teams aceitar ou bloquear a solicitação de conversa inicial de um usuário do Skype, ele poderá optar por bloquear ou desbloquear essa pessoa a qualquer momento. Eles podem fazer isso na conversa ou em suas configurações de privacidade no Teams. Os usuários do Skype não saberão que foram bloqueados.

Os usuários bloqueados do Skype, juntamente com outras pessoas e números de telefone PSTN (rede telefônica pública) bloqueados por um usuário do Teams, estão listados na lista de contatos bloqueados do usuário no Teams.

## <a name="limitations"></a>Limitações

- As conversas são somente texto. Isso significa que não há nenhuma formatação avançada, @mentions, emojis ou outros recursos de chat disponíveis em uma [experiência de chat do Teams nativo](native-chat-for-external-users.md).
- As conversas são somente um a um. Não há suporte para chats em grupo.
- Os usuários do Teams e os usuários do Skype não podem ver a presença uns dos outros.
- Não há suporte para procurar usuários do Skype usando a ID do Skype ou o número de telefone.
- Os usuários do Skype não podem chamar usuários do Teams que configuraram o encaminhamento de chamadas para o número de outro usuário, o número de um delegado ou um número PSTN (Rede Telefônica Comutada Pública).  Há suporte apenas para caixa postal.
- Não há suporte para escalonamento de interoperabilidade, chamadas de grupo e reuniões.
- Não há suporte para a capacidade de um delegado chamar um usuário do Skype em nome de um usuário do Teams.
- Não há suporte para o compartilhamento de tela com chat.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Definir se os usuários do Teams podem se comunicar com usuários do Skype

Como administrador, você usa o centro de administração do Microsoft Teams ou o PowerShell para definir configurações de acesso externo para controlar se os usuários do Teams em sua organização podem se comunicar com usuários do Skype. Por padrão, essa funcionalidade é ativada para novos locatários. No entanto, há um pré-requisito para que o seguinte registro DNS SRV precise ser configurado pelo Administração de TI se ainda não estiver disponível para seu domínio, por exemplo, _sipfederationtls._tcp.contoso.com.  

**Serviço**: sipfederationtls<br/>
**Protocolo**: TCP<br/>
**Prioridade**: 100<br/>
**Peso**: 1<br/>
**Porta**: 5061<br/>
**Destino**: sipfed.online.lync.com

Se você tiver atualizado de Skype for Business para o Teams, as configurações de comunicação externa configuradas no centro de administração Skype for Business serão migradas para o Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>No Centro de administração do Microsoft Teams

No centro de administração do Microsoft Teams, acesse **Usuários** > **Acesso externo** e ative **Os usuários podem se comunicar com usuários do Skype**. Para obter diretrizes passo a passo sobre como configurar essa e outras configurações de acesso externo, consulte [Gerenciar acesso externo no Teams](./manage-external-access.md).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Siga este procedimento: 
1. Use o cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) junto com o parâmetro para controlar se os usuários do ```EnablePublicCloudAccess``` Teams podem se comunicar com usuários do Skype. Definir o parâmetro para ```true``` permitir que os usuários do Teams se comuniquem com usuários do Skype. Você pode usar o ```EnablePublicCloudAudioVideoAccess``` parâmetro para habilitar/desabilitar chamadas de áudio/vídeo.

2. Use o cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) junto com o parâmetro definido para ```"WindowsLive"``` que os usuários do ```Provider``` Teams possam se comunicar com usuários do Skype.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o acesso externo no Teams](manage-external-access.md)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
