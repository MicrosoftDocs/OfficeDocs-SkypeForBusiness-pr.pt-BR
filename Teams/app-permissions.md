---
title: Permissões e considerações dos aplicativos Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Saiba que aplicativos de dados e permissões estão solicitando da sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d7548d4d162310bc239c752e2bce38e725008f9
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845222"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Permissões e considerações dos aplicativos Microsoft Teams

Os aplicativos Microsoft Teams são uma forma de agregar um ou mais recursos em um _pacote de aplicativo_ que pode ser instalado, atualizado e desinstalado. Os recursos incluem:

- Bots
- Extensões de mensagens
- Guias
- Conectores

Os aplicativos são aceitos pelos usuários e gerenciados pela TI a partir de uma perspectiva política. No entanto, para a maioria das partes, as permissões e o perfil de risco de um aplicativo são definidos pelas permissões e pelos perfis de risco das funcionalidades que o aplicativo contém. Assim, este artigo foca em permissões e considerações no nível de recurso.

As permissões listadas abaixo em maiúsculas, por exemplo, RECEIVE_MESSAGE e REPLYTO_MESSAGE, não aparece em nenhum lugar da [documentação do desenvolvedor do Microsoft Teams](https://aka.ms/teamsdevdocs) nem no [Gráfico de permissões da Microsoft](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). São somente uma abreviação descritiva para o propósito deste artigo.


|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Use as tabelas a seguir como um guia para entender quais permissões os aplicativos que você está investigando estão solicitando.</li></ul> |
| ![Um ícone representando o passo seguinte](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Pesquise o aplicativo ou o próprio serviço para decidir se deseja permitir o acesso a ele dentro da sua organização. Por exemplo, os bots enviam e recebem mensagens de usuários e, exceto para os bots de linha de negócios corporativo, estão localizados fora do limite de conformidade. Portanto, qualquer aplicativo que inclua um bot requer essas permissões e tem esse perfil de risco, no mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Permissões e considerações globais do aplicativo

### <a name="required-permissions"></a>Permissões necessárias

Nenhum

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

Um aplicativo deve divulgar quais dados ele usa e o que os dados são usados nos termos de uso e nos links da política de privacidade.</td>

## <a name="bots-and-messaging-extensions"></a>Bots e extensões de mensagens

### <a name="required-permissions"></a>Permissões necessárias

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. O bot pode receber mensagens de usuários e responder a elas.<sup>1</sup>

- POST_MESSAGE_USER. Depois que um usuário envia uma mensagem para um bot, o bot pode enviar mensagens diretas ao usuário (também chamadas de *mensagens proativas* a qualquer momento.

- GET_CHANNEL_LIST. Os bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais de uma equipe.

### <a name="optional-permissions"></a>Permissões opcionais

- Entidade. Quando ele é usado em um canal, os bots do aplicativo podem acessar informações de identidade básicas dos membros da equipe (nome, sobrenome, nome UPN, endereço de email); Quando ele é usado em um chat pessoal ou em grupo, o bot pode acessar as mesmas informações para esses usuários.

- POST_MESSAGE_TEAM. Permite que os bots de um aplicativo enviem mensagens diretas (pró-ativas) para qualquer membro da equipe a qualquer momento, mesmo que o usuário nunca tenha se falado ao bot antes.

- As seguintes permissões não são explícitas, mas são implícitas por RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots podem ser usados, declarados no manifesto:
 
    - RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM

- SEND_FILES RECEIVE_FILES. <sup>2</sup> controla se um bot pode enviar e receber arquivos em um chat pessoal (ainda não compatível com o chat em grupo ou canais).

### <a name="considerations"></a>Considerações

- Os bots só têm acesso às equipes às quais foram adicionados ou aos usuários que os instalaram.

- Os bots recebem apenas mensagens que são explicitamente mencionadas pelos usuários. Esses dados saem da rede corporativa.

- Os bots só podem responder a conversas nas quais são mencionados.

- Depois que um usuário tiver disparado com um bot, se o bot armazenar a ID do usuário, ele poderá enviar mensagens diretas ao usuário a qualquer momento.

- Teoricamente, é possível que as mensagens de bot contenham links para sites de phishing ou de malware, mas os bots podem ser bloqueados pelo usuário, pelo administrador de locatários ou globalmente pela Microsoft.

- Um bot pode recuperar (e pode armazenar) informações de identidade muito básicas para os membros da equipe para os quais o aplicativo foi adicionado ou para usuários individuais em chats pessoais ou em grupo. Para obter mais informações sobre esses usuários, o bot deve exigir que eles entrem no Azure Active Directory (Azure AD)

- Os bots podem recuperar (e podem armazenar) a lista de canais em uma equipe; esses dados saem da rede corporativa.

- Quando um arquivo é enviado a um bot, o arquivo sai da rede corporativa. O envio e recebimento de arquivos requer a aprovação do usuário para cada arquivo. 

- Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem solicitar que os usuários entrem; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer outras coisas. Exatamente o que essas coisas adicionais dependem do bot e do local em que o usuário entra: um bot é um aplicativo do Azure AD https://apps.dev.microsoft.com/ registrado em e pode ter seu próprio conjunto de permissões.

- Os bots são informados sempre que os usuários são adicionados ou excluídos de uma equipe.

- Os bots não visualizam os endereços IP dos usuários nem outras informações referenciais. Todas as informações vêm da Microsoft. (Há uma exceção: se um bot implementar sua própria experiência de entrada, a interface do usuário de entrada exibirá os endereços IP e as informações de referenciador dos usuários.)

- As extensões de mensagens, por outro lado, podem ver os endereços IP e as informações referenciais dos usuários.

- As diretrizes do aplicativo (e o processo de revisão do AppSource) exigem critério de postagem de mensagens de chat pessoais para usuários (por meio da permissão POST_MESSAGE_TEAM) para fins válidos. Em caso de abuso, os usuários podem bloquear o bot, os administradores de locatários podem bloquear o aplicativo e a Microsoft pode bloquear os bots de forma centralizada, se necessário.

<sup>1</sup> alguns bots apenas enviam mensagens (POST_MESSAGE_USER). Eles são chamados de bots de "somente notificação", mas o termo não se refere ao que um bot é permitido ou não pode fazer, isso significa que o bot não quer expor uma experiência de conversa. O Microsoft Teams usa esse campo para desativar a funcionalidade na interface do usuário que normalmente seria habilitada; o bot não está restrito sobre o que pode ser feito em comparação com os bots que expõem uma experiência de conversa.

<sup>2</sup> governada pela propriedade booleana supportsFiles no objeto bot no arquivo manifest. JSON do aplicativo.

> [!NOTE]
> Se um bot tem sua própria entrada, há um segundo: experiência de consentimento diferente na primeira vez que o usuário entra.
>
>Atualmente, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo do Teams (bot, guia, conector ou extensão de mensagens) são completamente separadas das permissões do teams listadas aqui.

## <a name="tabs"></a>Guias

Uma guia é um site em execução dentro do teams.

### <a name="required-permissions"></a>Permissões necessárias

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum (atualmente)

### <a name="considerations"></a>Considerações

- O perfil de risco para uma guia é quase idêntico ao mesmo site em execução em uma guia do navegador. 

- Uma guia também obtém o contexto no qual ele está em execução, incluindo o nome de entrada e o UPN do usuário atual, a ID de objeto do Azure AD para o usuário atual, a ID do grupo do Office 365 em que ele reside (se for uma equipe), a ID do locatário e a localidade atual do usuário. No entanto, para mapear essas IDs para as informações de um usuário, a guia teria que fazer com que o usuário entre no Azure AD.

## <a name="connectors"></a>Alinha

Um conector publica mensagens em um canal quando ocorrem eventos em um sistema externo.

### <a name="required-permissions"></a>Permissões necessárias

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permissões opcionais

REPLYTO_CONNECTOR_MESSAGE. Certos conectores oferecem suporte a mensagens acionáveis, que permitem que os usuários publiquem respostas direcionadas para a mensagem do conector, por exemplo, adicionando uma resposta a um problema do GitHub ou adicionando uma data a um cartão Trello.

### <a name="considerations"></a>Considerações

- O sistema que lança mensagens do conector não sabe para quem está postando ou quem recebe as mensagens: nenhuma informação sobre o destinatário é divulgada. (A Microsoft é o destinatário real, e não o locatário; A Microsoft faz a postagem real para o canal.)

- Nenhum dado sai da rede corporativa quando as mensagens do conector são postadas em um canal.

- Os conectores que dão suporte a mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE) também não vêem o endereço IP e informações de referenciais; essas informações são enviadas à Microsoft e roteadas para pontos de extremidade HTTP que foram registrados anteriormente na Microsoft no portal de conectores.

- Cada vez que um conector é configurado para um canal, uma URL exclusiva para essa instância do conector é criada. Se essa instância do conector for excluída, a URL não poderá mais ser usada.

- As mensagens de conector não podem conter anexos de arquivo.

- A URL da instância do conector deve ser tratada como segredo/confidencial: qualquer pessoa que tenha essa URL pode postá-la, como um endereço de email. Portanto, há algum risco de spam ou links para sites de phishing ou malware. Se isso fosse acontecer, os proprietários da equipe podem excluir a instância do conector.

- Se o serviço que envia mensagens de conector fosse comprometido e começar a enviar spam/phishing/malware links, um administrador de locatário pode impedir que novas instâncias de conector sejam criadas e a Microsoft possa bloqueá-las de forma centralizada.

> [!NOTE]
> No momento, não é possível saber quais conectores suportam mensagens acionáveis (REPLYTO_CONNECTOR_MESSAGE permissão).

## <a name="outgoing-webhooks"></a>WebHooks de saída

Os *WebHooks de saída* são criados instantaneamente por parte dos proprietários da equipe ou dos membros da equipe. Eles não são recursos de aplicativos Teams; essas informações estão incluídas para fins de integridade.

### <a name="required-permissions"></a>Permissões necessárias

RECEIVE_MESSAGE REPLYTO_MESSAGE. Pode receber mensagens de usuários e respondê-las.

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

- Os WebHooks de saída são semelhantes aos bots, mas têm menos privilégios. Eles devem ser explicitamente mencionados, exatamente como os bots.

- Quando um webhook de saída é registrado, um segredo é gerado, o que permite que o webhook de saída Verifique se o remetente é o Microsoft Teams em oposição a um invasor mal-intencionado. Esse segredo deve permanecer como um segredo; qualquer pessoa que tenha acesso a ela pode representar o Microsoft Teams. Se o segredo estiver comprometido, o webhook de saída pode ser excluído e recriado, e um novo segredo será gerado.

- Embora seja possível criar um webhook de saída que não valide o segredo, recomendamos nele.

- Além de receber e responder a mensagens, os WebHooks de saída não podem fazer muito: eles não podem enviar mensagens de forma proativa, eles não podem enviar ou receber arquivos, eles não podem fazer nada que os bots possam fazer, exceto receber e responder a mensagens.
