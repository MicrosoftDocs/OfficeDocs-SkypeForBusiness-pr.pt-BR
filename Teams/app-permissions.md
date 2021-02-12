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
description: O administrador pode saber quais dados e permissões os aplicativos do Microsoft Teams estão solicitando em sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739379"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Permissões e considerações dos aplicativos Microsoft Teams

Os aplicativos Microsoft Teams são uma forma de agregar um ou mais recursos em um _pacote de aplicativo_ que pode ser instalado, atualizado e desinstalado. Os recursos incluem:

- Bots
- Extensões de mensagens
- Guias
- Conectores

Os aplicativos são aceitos pelos usuários e gerenciados pela TI a partir de uma perspectiva política. No entanto, em grande parte, as permissões e o perfil de risco de um aplicativo são definidos pelas permissões e perfis de risco dos recursos que o aplicativo contém. Assim, este artigo foca em permissões e considerações no nível de recurso.

As permissões listadas abaixo em maiúsculas, por exemplo, RECEIVE_MESSAGE e REPLYTO_MESSAGE, não aparece em nenhum lugar da [documentação do desenvolvedor do Microsoft Teams](https://aka.ms/teamsdevdocs) nem no [Gráfico de permissões da Microsoft](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). São somente uma abreviação descritiva para o propósito deste artigo.


| Título   | Descrição    |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Use as tabelas abaixo como um guia para entender quais permissões os aplicativos que você está investigando estão solicitando.</li></ul> |
| ![Um ícone representando o passo seguinte](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Pesquise o próprio aplicativo ou serviço para decidir se deseja permitir o acesso a ele em sua organização. Por exemplo, os bots enviam e recebem mensagens de usuários e, exceto bots personalizados da empresa, estão localizados fora do limite de conformidade. Portanto, qualquer aplicativo que inclua um bot requer essas permissões e tem esse perfil de risco, no mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Considerações e permissões globais do aplicativo

### <a name="required-permissions"></a>Permissões necessárias

Nenhum

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

- Um aplicativo deve divulgar quais dados ele usa e para que os dados são usados em seus termos de uso e links de política de privacidade.

- [O consentimento específico do recurso](resource-specific-consent.md) fornece um conjunto de permissões que os aplicativos podem solicitar, que aparecem na tela de instalação do aplicativo. Para saber mais sobre permissões de consentimento específicas do recurso, consulte [a referência de permissões do Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)

- Os aplicativos também podem precisar de permissões diferentes de permissões de consentimento específicas do recurso. Depois que um aplicativo é instalado, o aplicativo pode solicitar permissões do Graph por meio de um aviso de consentimento. Para saber mais, consulte Noções básicas sobre as experiências de consentimento do aplicativo [Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience) Você pode configurar permissões e consentimento da API no portal do Azure. Para saber mais, confira a estrutura de consentimento do [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>Bots e extensões de mensagens

### <a name="required-permissions"></a>Permissões necessárias

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. O bot pode receber mensagens de usuários e respondá-los. <sup>1</sup>

- POST_MESSAGE_USER. Depois que um usuário envia uma mensagem para um bot, o bot pode enviar mensagens diretas ao usuário (também chamadas de mensagens *proativas* a qualquer momento.

- GET_CHANNEL_LIST. Os bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais em uma equipe.

### <a name="optional-permissions"></a>Permissões opcionais

- Identidade. Quando ele é usado em um canal, os bots do aplicativo podem acessar informações básicas de identidade dos membros da equipe (nome, sobrenome, nome do usuário principal [UPN], endereço de email); quando é usado em um chat pessoal ou em grupo, o bot pode acessar as mesmas informações para esses usuários.

- POST_MESSAGE_TEAM. Permite que os bots de um aplicativo enviem mensagens diretas (proativas) a qualquer membro da equipe a qualquer momento, mesmo que o usuário nunca tenha falado com o bot antes.

- As permissões a seguir não são explícitas, mas estão implícitas por RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots podem ser usados, declarados no manifesto:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controla se um bot pode enviar e receber arquivos no chat pessoal (ainda sem suporte para chats em grupo ou canais).

### <a name="considerations"></a>Considerações

- Os bots só têm acesso às equipes às quais foram adicionados ou aos usuários que as instalaram.

- Os bots só recebem mensagens nas quais são explicitamente mencionados pelos usuários. Esses dados deixam a rede corporativa.

- Os bots só podem responder às conversas nas quais são mencionados.

- Depois que um usuário conversar com um bot, se o bot armazenar a ID desse usuário, ele poderá enviar mensagens diretas a esse usuário a qualquer momento.

- É possível que mensagens de bot contenham links para sites de phishing ou malware, mas os bots podem ser bloqueados pelo usuário, pelo administrador do locatário ou globalmente pela Microsoft.

- Um bot pode recuperar (e pode armazenar) informações de identidade muito básicas para os membros da equipe aos que o aplicativo foi adicionado ou para usuários individuais em chats pessoais ou em grupo. Para obter mais informações sobre esses usuários, o bot deve exigir que eles entre no Azure Active Directory (Azure AD).

- Os bots podem recuperar (e podem armazenar) a lista de canais em uma equipe; esses dados deixam a rede corporativa.

- Quando um arquivo é enviado para um bot, o arquivo deixa a rede corporativa. O envio e o recebimento de arquivos exige aprovação do usuário para cada arquivo. 

- Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem solicitar que os usuários entrem; assim que o usuário entrar, o bot terá um token de acesso com o qual ele pode fazer coisas adicionais. Exatamente o que são esses recursos adicionais depende do bot e de onde o usuário entrar: um bot é um aplicativo do Azure AD registrado e pode ter seu próprio conjunto https://apps.dev.microsoft.com/ de permissões.

- Os bots são informados sempre que os usuários são adicionados ou excluídos de uma equipe.

- Os bots não veem os endereços IP dos usuários ou outras informações de referência. Todas as informações vêm da Microsoft. (Há uma exceção: se um bot implementar sua própria experiência de login, a interface do usuário de login verá os endereços IP dos usuários e informações de referência.)

- As extensões de mensagens, por outro lado, verão os endereços IP dos usuários e as informações de referência.

- As diretrizes de aplicativos (e nosso processo de revisão appSource) exigem critério na postagem de mensagens de chat pessoais aos usuários (por meio da permissão POST_MESSAGE_TEAM de usuário) para fins válidos. Em caso de abuso, os usuários podem bloquear o bot, os administradores de locatários podem bloquear o aplicativo e a Microsoft pode bloquear os bots centralmente, se necessário.

<sup>1</sup> Alguns bots só enviam mensagens (POST_MESSAGE_USER). Eles são chamados de bots "somente notificação", mas o termo não se refere ao que um bot pode ou não fazer, significa que o bot não quer expor uma experiência de conversa. O Teams usa esse campo para desabilitar a funcionalidade na interface do usuário que normalmente seria habilitada; o bot não está restrito no que é permitido fazer em comparação com bots que expõem uma experiência de conversa.

<sup>2</sup> Regido pela propriedade booliana de arquivos compatíveis no objeto de bot no manifest.jsno arquivo do aplicativo.

> [!NOTE]
> Se um bot tiver sua própria assinatura, haverá uma segunda experiência de consentimento ( diferente) da primeira vez que o usuário entrar.
>
>Atualmente, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo do Teams (bot, guia, conector ou extensão de mensagens) são completamente separadas das permissões do Teams listadas aqui.

## <a name="tabs"></a>Guias

Uma guia é um site em execução no Teams.

### <a name="required-permissions"></a>Permissões necessárias

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum (atualmente)

### <a name="considerations"></a>Considerações

- O perfil de risco de uma guia é quase idêntico ao mesmo site em execução em uma guia do navegador. 

- Uma guia também obtém o contexto no qual está sendo executado, incluindo o nome de login e o UPN do usuário atual, a ID de Objeto do Azure AD para o usuário atual, a ID do Grupo do Microsoft 365 no qual ele reside (se for uma equipe), a ID do locatário e a localidade atual do usuário. No entanto, para mapear essas IDs para as informações de um usuário, a guia teria que fazer o usuário entrar no Azure AD.

## <a name="connectors"></a>Conectores

Um conector posta mensagens em um canal quando ocorrem eventos em um sistema externo.

### <a name="required-permissions"></a>Permissões necessárias

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permissões opcionais

REPLYTO_CONNECTOR_MESSAGE. Certos conectores são compatíveis com mensagens ativas, que permitem que os usuários postem respostas direcionadas à mensagem do conector, por exemplo, adicionando uma resposta a um problema do GitHub ou adicionando uma data a um cartão Trello.

### <a name="considerations"></a>Considerações

- O sistema que posta mensagens do conector não sabe para quem ele está postando ou para quem recebe as mensagens: nenhuma informação sobre o destinatário é divulgada. (A Microsoft é o destinatário real, não o locatário; A Microsoft faz a postagem real no canal.)

- Nenhum dado deixa a rede corporativa quando as mensagens do conector são postadas em um canal.

- Conectores compatíveis com mensagens ativas (REPLYTO_CONNECTOR_MESSAGE permissão) também não veem o endereço IP e as informações do remetente; essas informações são enviadas para a Microsoft e roteadas para pontos de extremidade HTTP anteriormente registrados com a Microsoft no portal conectores.

- Sempre que um conector é configurado para um canal, uma URL exclusiva para essa instância do conector é criada. Se essa instância do conector for excluída, a URL não poderá mais ser usada.

- As mensagens do conector não podem conter anexos de arquivo.

- A URL da instância do conector deve ser tratada como secreta/confidencial: qualquer pessoa que tenha essa URL pode postá-la, como um endereço de email. Portanto, há algum risco de spam ou links para sites de phishing ou malware. Se isso acontecer, os proprietários da equipe poderão excluir a instância do conector.

- Se o serviço que envia mensagens de conectores fosse comprometido e começa a enviar links de spam/phishing/malware, um administrador de locatários pode impedir a criação de novas instâncias de conector e a Microsoft pode bloqueá-las centralmente.

> [!NOTE]
> No momento, não é possível saber quais conectores são compatíveis com mensagens ativas (REPLYTO_CONNECTOR_MESSAGE permissão).

## <a name="outgoing-webhooks"></a>Webções de saída

*Webções de saída são criadas* em tempo real por proprietários da equipe ou membros da equipe. Eles não são recursos de aplicativos do Teams; essas informações são incluídas para a conclusão.

### <a name="required-permissions"></a>Permissões necessárias

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Pode receber mensagens de usuários e respondá-las.

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

- Webções de saída são semelhantes aos bots, mas têm menos privilégios. Eles devem ser explicitamente mencionados, assim como os bots.

- Quando um web browser de saída é registrado, um segredo é gerado, o que permite que o remetente verifique se o remetente é o Microsoft Teams em vez de um invasor mal-intencionado. Esse segredo deve permanecer um segredo; qualquer pessoa que tenha acesso a ele pode representar o Microsoft Teams. Se o segredo for comprometido, a web seta de saída poderá ser excluída e re criada, e um novo segredo será gerado.

- Embora seja possível criar uma web seita de saída que não valide o segredo, recomendamos contra ela.

- Além de receber e responder a mensagens, web dinâmicas de saída não podem fazer muito: não podem enviar mensagens proativamente, não podem enviar ou receber arquivos, não podem fazer mais nada que os bots possam fazer, exceto receber e responder mensagens.
