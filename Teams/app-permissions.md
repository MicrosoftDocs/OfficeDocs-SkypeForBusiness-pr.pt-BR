---
title: Permissões e considerações dos aplicativos Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Administração saber quais dados e permissões os Microsoft Teams aplicativos estão solicitando de sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 925136660ef6adda6374fab1acccf10a2b9f1722
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190281"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Permissões e considerações dos aplicativos Microsoft Teams

Microsoft Teams aplicativos são uma maneira de agregar um ou mais recursos em aplicativos que podem ser instalados, atualizados e desinstalados. Os recursos dos aplicativos incluem:

* Bots
* Extensões de mensagens
* Guias
* Conectores

Como administrador, você só gerencia aplicativos. No entanto, o artigo se concentra em permissões e considerações no nível de funcionalidade, pois as funcionalidades em um aplicativo afetam as permissões necessárias e os perfis de risco do aplicativo. Para uso, os aplicativos são consentidos por usuários e gerenciados por profissionais de TI de uma perspectiva de política.

As permissões listadas abaixo em letras maiúsculas, por exemplo `RECEIVE_MESSAGE` , são `REPLYTO_MESSAGE` apenas para fins de ilustração e explicação. Essas cadeias de caracteres ou permissões não aparecem em nenhum lugar na documentação [Microsoft Teams desenvolvedor](/microsoftteams/platform/overview) ou as permissões [para o Microsoft Graph](/graph/permissions-reference).

## <a name="global-app-permissions-and-considerations"></a>Considerações e permissões globais do aplicativo

### <a name="required-permissions"></a>Permissões necessárias

Nenhum

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

* Um aplicativo deve divulgar quais dados ele usa e para que dados são usados em seus links de política de privacidade e termos de uso.

* [O consentimento específico do recurso](resource-specific-consent.md) fornece um conjunto de permissões que os aplicativos podem solicitar, que aparecem na tela de instalação do aplicativo. Para saber mais sobre permissões de consentimento específicas do recurso, [consulte Graph de permissões](/graph/permissions-reference#teams-resource-specific-consent-permissions).

* Os aplicativos também podem precisar de permissões diferentes das permissões de consentimento específicas do recurso. Depois que um aplicativo é instalado, o aplicativo pode solicitar Graph permissões por meio de um prompt de consentimento. Para saber mais, confira [Noções básicas Azure AD de consentimento do aplicativo](/azure/active-directory/develop/application-consent-experience). Você pode configurar permissões de API e consentimento no portal do Azure. Para saber mais, confira [Azure Active Directory de consentimento](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bots e extensões de mensagens

### <a name="required-permissions"></a>Permissões necessárias

* RECEIVE_MESSAGE, REPLYTO_MESSAGE: o bot pode receber mensagens dos usuários e responder a eles. <sup>1</sup>

* POST_MESSAGE_USER: depois que um usuário envia uma mensagem para um bot, o bot pode enviar mensagens diretas do usuário (também chamadas de mensagens *proativas* a qualquer momento.

* GET_CHANNEL_LIST: Os bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais em uma equipe.

### <a name="optional-permissions"></a>Permissões opcionais

* IDENTIDADE: Quando ele é usado em um canal, os bots do aplicativo podem acessar informações básicas de identidade dos membros da equipe (nome, sobrenome, nome UPN, endereço de email). Quando ele é usado em um chat pessoal ou em grupo, o bot pode acessar as mesmas informações para esses usuários.

* POST_MESSAGE_TEAM: permite que os bots de um aplicativo enviem mensagens diretas (proativas) para o membro da equipe a qualquer momento, mesmo que o usuário nunca tenha interajado com o bot.

* As permissões a seguir não são explícitas, mas são implícitas por RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots podem ser usados, declarados no manifesto:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* As permissões a seguir não são explícitas, mas são implícitas por RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots podem ser usados, declarados no manifesto:

  * RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
  * RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
  * RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

* SEND_FILES, RECEIVE_FILES:<sup>2</sup> Controla se um bot pode enviar e receber arquivos no chat pessoal (ainda não há suporte para chat em grupo ou canais).

### <a name="considerations"></a>Considerações

* Os bots só têm acesso às equipes às quais foram adicionados ou aos usuários que as instalaram.

* Os bots recebem apenas mensagens nas quais são explicitamente mencionados pelos usuários. Esses dados saem da rede corporativa.

* Os bots só podem responder a conversas nas quais são mencionados.

* Quando um usuário conversa com um bot, se o bot armazena a ID do usuário, ele pode enviar mensagens diretas ao usuário a qualquer momento.

* Teoricamente, é possível que as mensagens de bot contenham links para sites de phishing ou malware. No entanto, os bots podem ser bloqueados pelo usuário, pelo administrador do locatário ou globalmente pela Microsoft. [Verificações de validação e verificação de](overview-of-app-validation.md) aplicativo garantem que todos os aplicativos falsas não estejam disponíveis Teams armazenamento.

* Um bot pode recuperar (e pode armazenar) informações básicas de identidade para os membros da equipe aos quais o aplicativo foi adicionado ou para usuários individuais em chats pessoais ou em grupo. Para obter mais informações sobre esses usuários, o bot deve exigir que eles se conectem Azure Active Directory (Azure AD).

* Os bots podem recuperar (e podem armazenar) a lista de canais em uma equipe; esses dados saem da rede corporativa.

* Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem solicitar que os usuários se conectem; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer coisas adicionais. Exatamente o que essas outras coisas são depende do bot e de onde o usuário entra: um bot https://apps.dev.microsoft.com/ é um aplicativo Azure AD registrado e pode ter seu próprio conjunto de permissões.

* Quando um arquivo é enviado para um bot, o arquivo sai da rede corporativa. Enviar e receber arquivos requer aprovação do usuário para cada arquivo.

* Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem solicitar que os usuários se conectem; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer coisas adicionais. Exatamente o que essas coisas adicionais são depende do bot e do local em que o usuário entra: um bot é um aplicativo Azure AD registrado no [Portal](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList) de Registro de Aplicativos e pode ter seu próprio conjunto de permissões.

* Os bots são informados sempre que os usuários são adicionados ou excluídos de uma equipe.

* Os bots não veem os endereços IP dos usuários ou outras informações de referenciador. Todas as informações são provenientes da Microsoft. (Há uma exceção: se um bot implementar sua própria experiência de entrada, a interface do usuário de entrada verá os endereços IP dos usuários e as informações do referenciador.)

* As extensões de mensagens, por outro lado, veem os endereços IP dos usuários e as informações do referenciador.

* As diretrizes de aplicativo (e nosso processo de revisão do AppSource) exigem discrição na postagem de mensagens de chat pessoais para os usuários (por meio da POST_MESSAGE_TEAM) para fins válidos. Em caso de abuso, os usuários podem bloquear o bot, os administradores de locatários podem bloquear o aplicativo e a Microsoft pode bloquear os bots centralmente, se necessário.

<sup>1</sup> Alguns bots enviam apenas mensagens (POST_MESSAGE_USER). Eles são chamados de bots "somente notificação", mas o termo não se refere ao que um bot tem permissão ou não pode fazer, isso significa que o bot não deseja expor uma experiência de conversa. Teams usa esse campo para desabilitar a funcionalidade na interface do usuário que normalmente seria habilitada; o bot não está restrito no que tem permissão para fazer em comparação com bots que expõem uma experiência de conversa.

<sup>2</sup> Governada pela propriedade booliana supportsFiles no objeto de bot no arquivo `manifest.json` do aplicativo.

> [!NOTE]
> Se um bot tiver sua própria entrada, haverá uma segunda experiência de consentimento diferente na primeira vez que o usuário entrar.
>
>Atualmente, as permissões Azure AD associadas a qualquer um dos recursos dentro de um aplicativo do Teams (bot, guia, conector ou extensão de mensagens) são completamente separadas das permissões Teams listadas aqui.

## <a name="tabs"></a>Guias

Uma guia é um site em execução dentro Teams.

### <a name="required-permissions"></a>Permissões necessárias

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum (atualmente)

### <a name="considerations"></a>Considerações

* O perfil de risco de uma guia é quase idêntico ao mesmo site em execução em uma guia do navegador.

* Uma guia também obtém o contexto no qual está em execução, incluindo o nome de entrada e o UPN do usuário atual, a ID de Objeto do Azure AD para o usuário atual, a ID do grupo Microsoft 365 no qual ele reside (se for uma equipe), a ID do locatário e a localidade atual do usuário. No entanto, para mapear essas IDs para as informações de um usuário, a guia teria que fazer com que o usuário entre Azure AD.

## <a name="connectors"></a>Conectores

Um conector posta mensagens em um canal quando ocorrem eventos em um sistema externo.

### <a name="required-permissions"></a>Permissões necessárias

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permissões opcionais

REPLYTO_CONNECTOR_MESSAGE. Determinados conectores dão suporte a mensagens acionáveis, que permitem que os usuários postem respostas direcionadas à mensagem do conector, por exemplo, adicionando uma resposta a um problema de GitHub ou adicionando uma data a um cartão Trello.

### <a name="considerations"></a>Considerações

* O sistema que posta mensagens do conector não sabe para quem está postando ou para quem recebe as mensagens: nenhuma informação sobre o destinatário é divulgada. (A Microsoft é o destinatário real, não o locatário; A Microsoft faz a postagem real no canal.)

* Nenhum dado sai da rede corporativa quando as mensagens do conector são postadas em um canal.

* Conectores que dão suporte a mensagens acionáveis (REPLYTO_CONNECTOR_MESSAGE permissão) também não veem o endereço IP e as informações do referenciador; essas informações são enviadas para a Microsoft e, em seguida, roteados para pontos de extremidade HTTP que foram registrados anteriormente com a Microsoft no portal conectores.

* Sempre que um conector é configurado para um canal, uma URL exclusiva para essa instância do conector é criada. Se essa instância do conector for excluída, a URL não poderá mais ser usada.

* As mensagens do conector não podem conter anexos de arquivo.

* A URL da instância do conector deve ser tratada como secreta/confidencial: qualquer pessoa que tenha essa URL pode postá-la, como um endereço de email. Portanto, há algum risco de spam ou links para sites de phishing ou malware. Se isso acontecer, os proprietários da equipe poderão excluir a instância do conector.

* Se o serviço que envia mensagens do conector for comprometido e começar a enviar links de spam/phishing/malware, um administrador de locatários poderá impedir que novas instâncias de conector sejam criadas e a Microsoft poderá bloqueiá-las centralmente.

> [!NOTE]
> No momento, não é possível saber quais conectores dão suporte a mensagens acionáveis (REPLYTO_CONNECTOR_MESSAGE permissão).

## <a name="outgoing-webhooks"></a>Webhooks de saída

_Os webhooks de saída_ são criados por proprietários de equipe ou membros da equipe. Eles não são recursos de aplicativos Teams; essas informações são incluídas para integridade.

### <a name="required-permissions"></a>Permissões necessárias

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Pode receber mensagens de usuários e responder a eles.

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

* Os webhooks de saída são semelhantes aos bots, mas têm menos privilégios. Eles devem ser mencionados explicitamente, assim como os bots.

* Quando um webhook de saída é registrado, um segredo é gerado, o que permite que o webhook de saída verifique se o remetente está Microsoft Teams em vez de um invasor mal-intencionado. Esse segredo deve permanecer um segredo; qualquer pessoa que tenha acesso a ela pode representar Microsoft Teams. Se o segredo estiver comprometido, o webhook de saída poderá ser excluído e criado novamente, e um novo segredo será gerado.

* Embora seja possível criar um webhook de saída que não valide o segredo, recomendamos isso.

* Além de receber e responder a mensagens, os webhooks de saída não podem fazer muito: eles não podem enviar mensagens proativamente, não podem enviar ou receber arquivos, não podem fazer mais nada que os bots possam fazer, exceto receber e responder a mensagens.
