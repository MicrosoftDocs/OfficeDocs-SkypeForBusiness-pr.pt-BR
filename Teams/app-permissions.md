---
title: Permissões e considerações dos aplicativos Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: O administrador pode saber quais dados e permissões os aplicativos do Microsoft Teams estão solicitando de sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05be32bff1069d11ea26d28e6eb5377ec04e65e9
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299060"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Permissões e considerações dos aplicativos Microsoft Teams

Os aplicativos do Microsoft Teams são uma maneira de agregar um ou mais recursos em aplicativos que podem ser instalados, atualizados e desinstalados. Os recursos dos aplicativos incluem:

* Bots
* Extensões de mensagens
* Guias
* Conectores

Como administrador, você somente gerencia aplicativos. No entanto, o artigo se concentra em permissões e considerações no nível de funcionalidade, pois as funcionalidades em um aplicativo afetam as permissões necessárias e os perfis de risco do aplicativo. Para uso, os aplicativos são consentidos por usuários e gerenciados por profissionais de TI de uma perspectiva de política.

As permissões listadas abaixo em letras maiúsculas, por exemplo `RECEIVE_MESSAGE` e `REPLYTO_MESSAGE` são apenas para fins de ilustração e explicação. Essas cadeias de caracteres ou permissões não aparecem em nenhum lugar na [documentação do desenvolvedor do Microsoft Teams](/microsoftteams/platform/overview) ou as [permissões do Microsoft Graph](/graph/permissions-reference).

## <a name="global-app-permissions-and-considerations"></a>Permissões e considerações globais do aplicativo

### <a name="required-permissions"></a>Permissões necessárias

Nenhum

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

* Um aplicativo deve divulgar quais dados ele usa e para que dados são usados em seus links de política de privacidade e termos de uso.

* [O consentimento específico do recurso](resource-specific-consent.md) fornece um conjunto de permissões que os aplicativos podem solicitar, que aparecem na tela de instalação do aplicativo. Para saber mais sobre permissões de consentimento específicas do recurso, consulte [Referência de permissões do Graph](/graph/permissions-reference#teams-resource-specific-consent-permissions).

* Os aplicativos também podem precisar de permissões diferentes das permissões de consentimento específicas do recurso. Depois que um aplicativo é instalado, o aplicativo pode solicitar permissões do Graph por meio de uma solicitação de consentimento. Para saber mais, consulte [Noções básicas sobre as experiências de consentimento do aplicativo do Azure AD](/azure/active-directory/develop/application-consent-experience). Você pode configurar permissões de API e consentimento no portal do Azure. Para saber mais, consulte [Estrutura de consentimento do Azure Active Directory](/azure/active-directory/develop/consent-framework).

## <a name="bots-and-messaging-extensions"></a>Bots e extensões de mensagens

### <a name="required-permissions"></a>Permissões necessárias

* RECEIVE_MESSAGE, REPLYTO_MESSAGE: o bot pode receber mensagens dos usuários e responder a eles. <sup>1</sup>

* POST_MESSAGE_USER: depois que um usuário envia uma mensagem para um bot, o bot pode enviar mensagens diretas do usuário (também chamadas de *mensagens proativas* a qualquer momento.

* GET_CHANNEL_LIST: os bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais em uma equipe.

### <a name="optional-permissions"></a>Permissões opcionais

* IDENTIDADE: quando ele é usado em um canal, os bots do aplicativo podem acessar informações básicas de identidade dos membros da equipe (nome, sobrenome, nome UPN, endereço de email). Quando ele é usado em um chat pessoal ou em grupo, o bot pode acessar as mesmas informações para esses usuários.

* POST_MESSAGE_TEAM: permite que os bots de um aplicativo enviem mensagens diretas (proativas) para o membro da equipe a qualquer momento, mesmo que o usuário nunca tenha interagido com o bot.

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

* Os bots somente têm acesso às equipes às quais foram adicionados ou aos usuários que as instalaram.

* Os bots recebem apenas mensagens nas quais são explicitamente mencionados pelos usuários. Esses dados saem da rede corporativa.

* Os bots só podem responder a conversas nas quais são mencionados.

* Quando um usuário conversa com um bot, se o bot armazena a ID do usuário, ele pode enviar mensagens diretas ao usuário a qualquer momento.

* Teoricamente, é possível que as mensagens de bot contenham links para sites de phishing ou malware. No entanto, os bots podem ser bloqueados pelo usuário, pelo administrador do locatário ou globalmente pela Microsoft. [Verificações de validação e verificação do aplicativo](overview-of-app-validation.md) garantem que nenhum aplicativo falso esteja disponível na loja do Teams.

* Um bot pode recuperar (e pode armazenar) informações básicas de identidade para os membros da equipe aos quais o aplicativo foi adicionado ou para usuários individuais em chats pessoais ou em grupo. Para obter mais informações sobre esses usuários, o bot deve exigir que eles se conectem ao Azure Active Directory (Azure AD).

* Os bots podem recuperar (e podem armazenar) a lista de canais em uma equipe; esses dados saem da rede corporativa.

* Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem solicitar que os usuários se conectem; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer coisas adicionais. Exatamente o que essas outras coisas são depende do bot e de onde o usuário entra: um bot é um aplicativo do Azure AD registrado no https://apps.dev.microsoft.com/ e pode ter seu próprio conjunto de permissões.

* Quando um arquivo é enviado para um bot, o arquivo sai da rede corporativa. Enviar e receber arquivos requer aprovação do usuário para cada arquivo.

* Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem solicitar que os usuários se conectem; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer coisas adicionais. Exatamente o que essas coisas adicionais são depende do bot e do local em que o usuário entra: um bot é um aplicativo do Azure AD registrado no [Portal de Registro de Aplicativos](https://apps.dev.microsoft.com/?referrer=https:%2f%2fdocs.microsoft.com%2f#/appList) e pode ter seu próprio conjunto de permissões.

* Os bots são informados sempre que os usuários são adicionados ou excluídos de uma equipe.

* Os bots não veem os endereços IP dos usuários ou outras informações do referenciador. Todas as informações são provenientes da Microsoft. (Há uma exceção: se um bot implementar sua própria experiência de entrada, a interface do usuário de entrada verá os endereços IP dos usuários e as informações do referenciador.)

* As extensões de mensagens, por outro lado, veem os endereços IP dos usuários e as informações do referenciador.

* As diretrizes de aplicativo (e nosso processo de revisão do AppSource) exigem discrição na postagem de mensagens de chat pessoais para os usuários (por meio da POST_MESSAGE_TEAM) para fins válidos. Em caso de abuso, os usuários podem bloquear o bot, os administradores de locatários podem bloquear o aplicativo e a Microsoft pode bloquear os bots centralmente, se necessário.

<sup>1</sup> Alguns bots enviam apenas mensagens (POST_MESSAGE_USER). Eles são chamados de bots "somente notificação", mas o termo não se refere ao que um bot tem permissão ou não de fazer, isso significa que o bot não deseja expor uma experiência de conversa. O Teams usa esse campo para desabilitar a funcionalidade na interface do usuário que normalmente seria habilitada; o bot não está restrito ao que ele tem permissão para fazer em comparação com bots que expõem uma experiência de conversa.

<sup>2</sup> Governada pela propriedade booliana supportsFiles no objeto de bot no arquivo `manifest.json` para o aplicativo.

> [!NOTE]
> Se um bot tiver sua própria entrada, haverá uma segunda experiência de consentimento diferente na primeira vez que o usuário entrar.
>
>Atualmente, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo do Teams (bot, guia, conector ou extensão de mensagens) são completamente separadas das permissões do Teams listadas aqui.

## <a name="tabs"></a>Guias

Uma guia é um site em execução no Teams.

### <a name="required-permissions"></a>Permissões necessárias

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum (atualmente)

### <a name="considerations"></a>Considerações

* O perfil de risco para uma guia é quase idêntico ao mesmo site em execução em uma guia do navegador.

* Uma guia também obtém o contexto no qual está em execução, incluindo o nome de entrada e o UPN do usuário atual, a ID de Objeto do Azure AD para o usuário atual, a ID do Grupo do Microsoft 365 no qual ele reside (se for uma equipe), a ID do locatário e a localidade atual do usuário. No entanto, para mapear essas IDs para as informações de um usuário, a guia teria que fazer com que o usuário entre no Azure AD.

## <a name="connectors"></a>Conectores

Um conector posta mensagens em um canal quando ocorrem eventos em um sistema externo.

### <a name="required-permissions"></a>Permissões necessárias

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permissões opcionais

REPLYTO_CONNECTOR_MESSAGE. Determinados conectores dão suporte a mensagens acionáveis, que permitem que os usuários postem respostas direcionadas à mensagem do conector, por exemplo, adicionando uma resposta a um problema do GitHub ou adicionando uma data a um cartão Trello.

### <a name="considerations"></a>Considerações

* O sistema que posta mensagens do conector não sabe para quem está postando ou para quem recebe as mensagens: nenhuma informação sobre o destinatário é divulgada. (A Microsoft é o destinatário real, não o locatário; A Microsoft faz a postagem real no canal.)

* Nenhum dado sai da rede corporativa quando as mensagens do conector são postadas em um canal.

* Conectores que dão suporte a mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE) também não veem o endereço IP e as informações do referenciador; essas informações são enviadas para a Microsoft e, em seguida, roteados para pontos de extremidade HTTP que foram registrados anteriormente com a Microsoft no portal Conectores.

* Sempre que um conector é configurado para um canal, uma URL exclusiva para essa instância do conector é criada. Se essa instância do conector for excluída, a URL não poderá mais ser usada.

* As mensagens do conector não podem conter anexos de arquivo.

* A URL da instância do conector deve ser tratada como secreta/confidencial: qualquer pessoa que tenha essa URL pode postá-la, como um endereço de email. Portanto, há algum risco de spam ou links para sites de phishing ou malware. Se isso acontecer, os proprietários da equipe poderão excluir a instância do conector.

* Se o serviço que envia mensagens do conector for comprometido e começar a enviar links de spam/phishing/malware, um administrador de locatários poderá impedir que novas instâncias de conector sejam criadas e a Microsoft poderá bloqueá-las centralmente.

> [!NOTE]
> No momento, não é possível saber quais conectores dão suporte a mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE).

## <a name="outgoing-webhooks"></a>Webhooks de saída

_Webhooks de saída_ são criados por proprietários de equipe ou membros da equipe. Eles não são recursos de aplicativos do Teams; essas informações são incluídas para integridade.

### <a name="required-permissions"></a>Permissões necessárias

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Pode receber mensagens de usuários e responder a eles.

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

* Os webhooks de saída são semelhantes aos bots, mas têm menos privilégios. Eles devem ser mencionados explicitamente, assim como os bots.

* Quando um webhook de saída é registrado, um segredo é gerado, o que permite que o webhook de saída verifique se o remetente é o Microsoft Teams em vez de um invasor mal-intencionado. Esse segredo deve permanecer um segredo; qualquer pessoa que tenha acesso a ele pode representar o Microsoft Teams. Se o segredo estiver comprometido, exclua e recrie o webhook de saída para gerar um novo segredo.

* Embora seja possível criar um webhook de saída que não valide o segredo, não recomendamos isso.

* Além de receber e responder a mensagens, os webhooks de saída não podem fazer muito: eles não podem enviar mensagens proativamente, não podem enviar ou receber arquivos, não podem fazer mais nada que os bots possam fazer, exceto receber e responder a mensagens.
