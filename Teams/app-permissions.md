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
description: O administrador pode saber quais dados e permissões Microsoft Teams aplicativos estão solicitando de sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e2766da88fee53124d43b4e2b66c9c104ea41b8e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610418"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Permissões e considerações dos aplicativos Microsoft Teams

Microsoft Teams aplicativos são uma maneira de agregar  um ou mais recursos em um pacote de aplicativos que podem ser instalados, atualizados e desinstalados. Os recursos incluem:

- Bots
- Extensões de mensagens
- Guias
- Conectores

Os aplicativos são consentidos pelos usuários e gerenciados por IT de uma perspectiva de política. No entanto, na maioria das partes, as permissões e o perfil de risco de um aplicativo são definidos pelas permissões e perfis de risco dos recursos que o aplicativo contém. Portanto, este artigo se concentra em permissões e considerações no nível de funcionalidade.

As permissões listadas abaixo em letras [maiúsculas,](/graph/permissions-reference)por exemplo, RECEIVE_MESSAGE e REPLYTO_MESSAGE, não aparecem em qualquer lugar na documentação do [desenvolvedor Microsoft Teams](/microsoftteams/platform/overview) ou nas permissões do Microsoft Graph . Eles são simplesmente uma taquigrafia descritiva para a finalidade deste artigo.


| Título   | Descrição    |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Use as tabelas abaixo como um guia para entender quais permissões os aplicativos que você está investigando estão solicitando.</li></ul> |
| ![Um ícone representando o passo seguinte](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Pesquise o aplicativo ou o próprio serviço para decidir se você deseja permitir o acesso a ele em sua organização. Por exemplo, os bots enviam e recebem mensagens de usuários e, exceto para bots personalizados da empresa, eles estão localizados fora do limite de conformidade. Portanto, qualquer aplicativo que inclua um bot exige essas permissões e tem esse perfil de risco, no mínimo. </li></ul>|

Consulte também [Solicitar permissões de dispositivo para sua Microsoft Teams guia](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).

## <a name="global-app-permissions-and-considerations"></a>Considerações e permissões globais do aplicativo

### <a name="required-permissions"></a>Permissões necessárias

Nenhum

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

- Um aplicativo deve divulgar quais dados ele usa e para que os dados são usados em seus termos de uso e links de política de privacidade.

- [O consentimento específico do recurso](resource-specific-consent.md) fornece um conjunto de permissões que os aplicativos podem solicitar, que aparece na tela de instalação do aplicativo. Para saber mais sobre permissões de consentimento específicas do recurso, [consulte Graph referência de permissões](/graph/permissions-reference#teams-resource-specific-consent-permissions).

- Os aplicativos também podem precisar de permissões diferentes de permissões de consentimento específicas do recurso. Depois que um aplicativo é instalado, o aplicativo pode solicitar Graph permissões por meio de um prompt de consentimento. Para saber mais, consulte [Understanding Azure AD application consent experiences](/azure/active-directory/develop/application-consent-experience). Você pode configurar permissões de API e consentimento no portal do Azure. Para saber mais, consulte [Azure Active Directory de consentimento.](/azure/active-directory/develop/consent-framework)

## <a name="bots-and-messaging-extensions"></a>Bots e extensões de mensagens

### <a name="required-permissions"></a>Permissões necessárias

- RECEIVE_MESSAGE, REPLYTO_MESSAGE. O bot pode receber mensagens dos usuários e responder a eles. <sup>1</sup>

- POST_MESSAGE_USER. Depois que um usuário envia uma mensagem para um bot, o bot pode enviar mensagens diretas do usuário (também chamadas de mensagens *proativas* a qualquer momento.

- GET_CHANNEL_LIST. Bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais em uma equipe.

### <a name="optional-permissions"></a>Permissões opcionais

- IDENTITY. Quando ele é usado em um canal, os bots do aplicativo podem acessar informações básicas de identidade dos membros da equipe (nome, sobrenome, nome principal do usuário [UPN], endereço de email); quando é usado em um chat pessoal ou em grupo, o bot pode acessar as mesmas informações para esses usuários.

- POST_MESSAGE_TEAM. Permite que os bots de um aplicativo enviem mensagens diretas (proativas) a qualquer membro da equipe a qualquer momento, mesmo que o usuário nunca tenha falado com o bot antes.

- Os seguintes não são permissões explícitas, mas estão implícitos por RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots podem ser usados, declarados no manifesto:
 
    - RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL
    - RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT
    - RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM

- SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controla se um bot pode enviar e receber arquivos no chat pessoal (ainda não há suporte para chat em grupo ou canais).

### <a name="considerations"></a>Considerações

- Os bots têm acesso apenas às equipes às quais foram adicionadas ou aos usuários que as instalaram.

- Os bots só recebem mensagens nas quais são explicitamente mencionados pelos usuários. Esses dados deixam a rede corporativa.

- Os bots só podem responder às conversas nas quais são mencionados.

- Depois que um usuário conversar com um bot, se o bot armazenar a ID desse usuário, ele poderá enviar mensagens diretas desse usuário a qualquer momento.

- Teoricamente, é possível que as mensagens bot contenham links para sites de phishing ou malware, mas os bots podem ser bloqueados pelo usuário, pelo administrador do locatário ou globalmente pela Microsoft.

- Um bot pode recuperar (e pode armazenar) informações de identidade muito básicas para os membros da equipe aos que o aplicativo foi adicionado ou para usuários individuais em chats pessoais ou de grupo. Para obter mais informações sobre esses usuários, o bot deve exigir que eles entre no Azure Active Directory (Azure AD).

- Os bots podem recuperar (e podem armazenar) a lista de canais em uma equipe; esses dados deixam a rede corporativa.

- Quando um arquivo é enviado para um bot, o arquivo deixa a rede corporativa. O envio e recebimento de arquivos requer aprovação do usuário para cada arquivo. 

- Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem pedir aos usuários para entrar; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer coisas adicionais. Exatamente o que essas coisas adicionais são depende do bot e de onde o usuário faz o acesso: um bot é um aplicativo do Azure AD registrado e pode ter seu próprio conjunto https://apps.dev.microsoft.com/ de permissões.

- Os bots são informados sempre que os usuários são adicionados ou excluídos de uma equipe.

- Os bots não veem os endereços IP dos usuários ou outras informações de referência. Todas as informações vêm da Microsoft. (Há uma exceção: se um bot implementar sua própria experiência de login, a interface do usuário de login verá os endereços IP dos usuários e informações de referência.)

- As extensões de mensagens, por outro lado, veem os endereços IP dos usuários e informações de referência.

- As diretrizes do aplicativo (e nosso processo de revisão do AppSource) exigem discrição na postagem de mensagens de chat pessoais aos usuários (por meio da permissão POST_MESSAGE_TEAM) para fins válidos. Em caso de abuso, os usuários podem bloquear o bot, os administradores de locatários podem bloquear o aplicativo e a Microsoft pode bloquear os bots centralmente, se necessário.

<sup>1</sup> Alguns bots só enviam mensagens (POST_MESSAGE_USER). Eles são chamados de bots "somente notificação", mas o termo não se refere ao que um bot é permitido ou não pode fazer, isso significa que o bot não quer expor uma experiência de conversa. Teams usa esse campo para desabilitar a funcionalidade na interface do usuário que normalmente seria habilitada; o bot não é restrito no que é permitido fazer em comparação com bots que expõem uma experiência de conversa.

<sup>2</sup> Governada pela propriedade supportsFiles Boolean no objeto bot no arquivo manifest.json para o aplicativo.

> [!NOTE]
> Se um bot tiver sua própria assinatura, haverá uma segunda experiência de consentimento diferente na primeira vez em que o usuário entrar.
>
>Atualmente, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo Teams (bot, guia, conector ou extensão de mensagens) estão completamente separadas das permissões Teams listadas aqui.

## <a name="tabs"></a>Guias

Uma guia é um site em execução dentro Teams.

### <a name="required-permissions"></a>Permissões necessárias

SEND_AND_RECEIVE_WEB_DATA

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum (no momento)

### <a name="considerations"></a>Considerações

- O perfil de risco de uma guia é quase idêntico ao mesmo site em execução em uma guia do navegador. 

- Uma guia também obtém o contexto em que está sendo executado, incluindo o nome de login e o UPN do usuário atual, a ID do Objeto do Azure AD para o usuário atual, a ID do grupo Microsoft 365 no qual ele reside (se for uma equipe), a ID do locatário e a localidade atual do usuário. No entanto, para mapear essas IDs para as informações de um usuário, a guia teria que fazer o usuário entrar no Azure AD.

## <a name="connectors"></a>Conectores

Um conector posta mensagens em um canal quando ocorrem eventos em um sistema externo.

### <a name="required-permissions"></a>Permissões necessárias

POST_MESSAGE_CHANNEL

### <a name="optional-permissions"></a>Permissões opcionais

REPLYTO_CONNECTOR_MESSAGE. Determinados conectores suportam mensagens ativas, que permitem que os usuários postem respostas direcionadas à mensagem do conector, por exemplo, adicionando uma resposta a um problema GitHub ou adicionando uma data a um cartão Trello.

### <a name="considerations"></a>Considerações

- O sistema que posta mensagens do conector não sabe para quem está postando ou quem recebe as mensagens: nenhuma informação sobre o destinatário é divulgada. (A Microsoft é o destinatário real, não o locatário; A Microsoft faz a postagem real no canal.)

- Nenhum dado deixa a rede corporativa quando as mensagens do conector são postadas em um canal.

- Conectores que suportam mensagens ativas (REPLYTO_CONNECTOR_MESSAGE permissão) também não veem endereço IP e informações de referência; essas informações são enviadas para a Microsoft e roteadas para pontos de extremidade HTTP que foram registrados anteriormente com a Microsoft no portal conectores.

- Sempre que um conector é configurado para um canal, uma URL exclusiva para essa instância do conector é criada. Se essa instância do conector for excluída, a URL não poderá mais ser usada.

- As mensagens do conector não podem conter anexos de arquivo.

- A URL da instância do conector deve ser tratada como secreta/confidencial: qualquer pessoa que tenha essa URL pode postá-la, como um endereço de email. Portanto, há algum risco de spam ou links para phishing ou sites de malware. Se isso acontecer, os proprietários da equipe poderão excluir a instância do conector.

- Se o serviço que envia mensagens do conector se tornar comprometido e começar a enviar links de spam/phishing/malware, um administrador de locatários poderá impedir a criação de novas instâncias do conector e a Microsoft poderá bloqueá-las centralmente.

> [!NOTE]
> No momento, não é possível saber quais conectores suportam mensagens ativas (REPLYTO_CONNECTOR_MESSAGE permissão).

## <a name="outgoing-webhooks"></a>Webhooks de saída

*Webhooks de saída* são criados em tempo real por proprietários de equipe ou membros da equipe. Eles não são recursos de aplicativos Teams; essas informações são incluídas para a conclusão.

### <a name="required-permissions"></a>Permissões necessárias

RECEIVE_MESSAGE, REPLYTO_MESSAGE. Pode receber mensagens dos usuários e responder a eles.

### <a name="optional-permissions"></a>Permissões opcionais

Nenhum

### <a name="considerations"></a>Considerações

- Os webhooks de saída são semelhantes aos bots, mas têm menos privilégios. Eles devem ser explicitamente mencionados, assim como os bots.

- Quando um webhook de saída é registrado, um segredo é gerado, o que permite que o webhook de saída verifique se o remetente está Microsoft Teams em vez de um invasor mal-intencionado. Esse segredo deve permanecer em segredo; qualquer pessoa que tenha acesso a ela pode representar Microsoft Teams. Se o segredo for comprometido, o webhook de saída poderá ser excluído e re-criado, e um novo segredo será gerado.

- Embora seja possível criar um webhook de saída que não valide o segredo, recomendamos isso.

- Além de receber e responder mensagens, os webhooks de saída não podem fazer muito: eles não podem enviar mensagens de forma proativa, não podem enviar ou receber arquivos, não podem fazer mais nada que os bots possam fazer, exceto receber e responder a mensagens.