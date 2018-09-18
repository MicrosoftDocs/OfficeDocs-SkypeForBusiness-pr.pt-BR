---
title: Permissões e considerações dos aplicativos Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lehewe
description: Saiba que aplicativos de dados e permissões estão solicitando da sua organização.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb8a6b6785e3cc4bcbf65bceeb51bf650b63a830
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883062"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Permissões e considerações dos aplicativos Microsoft Teams

Os aplicativos Microsoft Teams são uma forma de agregar um ou mais recursos em um _pacote de aplicativo_ que pode ser instalado, atualizado e desinstalado. Os recursos incluem:

-   Bots
-   Extensões de mensagens
-   Guias
-   Conectores

Os aplicativos são aceitos pelos usuários e gerenciados pela TI a partir de uma perspectiva política. No entanto, na maioria das vezes, as permissões e o perfil de risco de um aplicativo são definidos pelas permissões e perfis de risco dos recursos que ele contém. Assim, este artigo foca em permissões e considerações no nível de recurso.

As permissões listadas abaixo em maiúsculas, por exemplo, RECEIVE_MESSAGE e REPLYTO_MESSAGE, não aparece em nenhum lugar da [documentação do desenvolvedor do Microsoft Teams](https://aka.ms/teamsdevdocs) nem no [Gráfico de permissões da Microsoft](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). São somente uma abreviação descritiva para o propósito deste artigo.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Use as tabelas abaixo como um guia para entender as permissões que os aplicativos que você está investigando estão solicitando.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Próximo passo|<ul><li>Pesquise o aplicativo ou serviço para decidir se você deseja permitir o acesso a ele na sua organização. Por exemplo, os bots enviam e recebem mensagens dos usuários e, com exceção dos bots corporativos de linha de negócios, estão localizados fora do limite de conformidade. Portanto, qualquer aplicativo que inclua um bot exige essas permissões e tem esse perfil de risco, no mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Permissões e considerações globais para aplicativos

<table>
  <tr>
    <th width="25%">Permissões obrigatórias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">Nenhum</td>
    <td valign="top">Nenhum</td>
    <td valign="top">Os aplicativos devem divulgar que dados usam e que dados são usados nos links dos termos de uso e política de privacidade.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bots e extensões de mensagem

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">Permissões obrigatórias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. O bot pode receber mensagens de usuários e responder a elas.<sup>1</sup></li><li>POST_MESSAGE_USER. Depois que um usuário envia uma mensagem para um bot, ele pode enviar mensagens diretas ao usuário (também chamadas de _mensagens proativas_) a qualquer momento.</li><li>GET_CHANNEL_LIST. Os bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais de uma equipe.</li></ul></td>
    <td valign="top"><ul><li>IDENTITY. Quando usados em um canal, os bots do aplicativo podem acessar informações básicas de identidade dos membros da equipe (nome, sobrenome, nome principal de usuário [UPN], endereço de e-mail); quando é usado em um bate-papo pessoal ou em grupo, o bot pode acessar as mesmas informações desses usuários.</li><li> POST_MESSAGE_TEAM. Permite que os bots do aplicativo enviem mensagens diretas (proativas) a qualquer membro da equipe, a qualquer momento, mesmo que o usuário nunca tenha falado com o bot antes.</li><li>O que segue não são permissões explícitas, mas estão implícitas em RECEIVE_MESSAGE e REPLYTO_MESSAGE e nos escopos nos quais os bots podem ser usados, declarados no manifesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>3</sup> Controla se um bot pode enviar e receber arquivos no bate-papo pessoal (ainda sem suporte para bate-papo ou canais em grupo).</li></ul></td>
    <td valign="top"><ul><li>Os bots só têm acesso às equipes às quais foram adicionados ou aos usuários que os instalaram.</li><li>Os bots só recebem mensagens nas quais são mencionados explicitamente pelos usuários. Esses dados saem da rede corporativa.</li><li>    Os bots só podem responder a conversas em que são mencionados.</li><li>Depois que um usuário tiver conversado com um bot, se o bot armazenar o ID do usuário, ele poderá enviar mensagens diretas ao usuário a qualquer momento. </li><li>Teoricamente, é possível que as mensagens do bot contenham links para sites de phishing ou malware, mas os bots podem ser bloqueados pelo usuário, pelo administrador do locatário ou globalmente pela Microsoft. </li><li>O bot pode recuperar (e pode armazenar) informações de identidade básicas dos membros da equipe aos quais o aplicativo foi adicionado ou de usuários individuais em bate-papos pessoais ou em grupo. Para obter mais informações sobre esses usuários, o bot deve solicitar que façam login no Azure Active Directory (Azure AD). </li><li>Os bots podem recuperar (e podem armazenar) a lista de canais de uma equipe; esses dados saem da rede corporativa. </li><li>Quando um arquivo é enviado para um bot, o arquivo sai da rede corporativa. O envio e o recebimento de arquivos requer a aprovação do usuário para cada arquivo. </li><li>Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas podem solicitar que os usuários façam login; quando o usuário faz login, o bot obtém um token de acesso com o qual pode fazer outras coisas. O que essas outras coisas são exatamente depende do bot e de onde o usuário faz login: um bot é um aplicativo do Azure AD registrado em <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> e pode ter o seu próprio conjunto de permissões.</li><li>Os bots são informados sempre que usuários são adicionados ou excluídos de uma equipe.</li><li>Os bots não veem o endereço IP nem nenhuma informação referenciadora dos usuários. Todas as informações vêm da Microsoft. (Há uma exceção: se um bot implementa sua própria experiência de login, a IU de login verá o endereço IP e informações referenciadoras dos usuários.)</li><li>Por outro lado, as extensões de mensagem veem o endereço IP e informações referenciadoras dos usuários.</li><li>As diretrizes do aplicativo (e nosso processo de avaliação do AppSource) requerem discrição do usuário ao publicar mensagens de bate-papo pessoal (por meio da permissão POST_MESSAGE_TEAM) para fins válidos. No caso de abuso, os usuários podem bloquear o bot, os administradores do locatário podem bloquear o aplicativo e a Microsoft pode bloquear os bots centralmente, se necessário.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Alguns bots só enviam mensagens (POST_MESSAGE_USER). Eles são chamados de bots “somente notificação”, mas o termo não se refere ao que um bot tem permissão ou não para fazer; isso significa que o bot não quer expor uma experiência de conversação. O Teams usa esse campo para desativar a funcionalidade na IU que normalmente estaria ativada; o bot não tem restrição ao que é permitido fazer em comparação com bots que expõem uma experiência de conversação.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Atualmente na previsualização do desenvolvedor.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Atualmente na previsualização do desenvolvedor. Regido pela propriedade booleana <code>supportsFiles</code> no objeto do bot, no arquivo manifest.json do aplicativo.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Se o bot tiver seu próprio login, haverá uma segunda experiência de consentimento diferente na primeira vez em que o usuário fizer login.</li><li>No momento, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo Teams (bot, guia, conector ou extensão de mensagem) são completamente separadas das permissões do Teams listadas aqui.</li></ul>


## <a name="tabs"></a>Guias

Uma guia é um site sendo executado dentro do Teams.

<table>
  <tr>
    <th width="25%">Permissões obrigatórias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Nenhuma (no momento).</td>
    <td valign="top"><ul><li>O perfil de risco de uma guia é quase idêntico ao mesmo site sendo executado em uma guia do navegador. </li><li>Uma guia também obtém o contexto no qual está sendo executada, incluindo o nome login e o UPN do usuário atual, o ID do Objeto do Azure AD do usuário atual, o ID do Grupo do Office 365 (equipe) em que reside, o ID do locatário e a localidade atual do usuário. Entretanto, para mapear esses IDs para as informações de um usuário, a guia precisa que o usuário faça login no Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Conectores

Um conector envia mensagens para um canal quando ocorrem eventos em um sistema externo.

  <table>
  <tr>
    <th width="25%">Permissões obrigatórias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Alguns conectores têm suporte para _mensagens acionáveis_, que permitem que os usuários postem respostas direcionadas à mensagem do conector, por exemplo, adicionando uma resposta a um problema do GitHub ou adicionando uma data a um cartão Trello.</td>
    <td valign="top"><ul><li>O sistema que posta as mensagens do conector não sabe quem está postando nem quem recebe as mensagens: nenhuma informação sobre o destinatário é revelada. (A Microsoft é o destinatário real, não o locatário; a Microsoft faz a postagem real para o canal.)</li><li>Nenhum dado sai da rede corporativa quando as mensagens do conector são postadas em um canal.</li><li>Conectores que têm suporte para mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE) também não veem informações sobre o endereço IP e informações referenciadoras; essas informações são enviadas para a Microsoft e, em seguida, roteadas para pontos de extremidade HTTP previamente registrados com a Microsoft no portal de Conectores.</li><li>Cada vez que um conector é configurado para um canal, é criada uma URL exclusiva para essa instância do conector. Se essa instância do conector for excluída, a URL não poderá mais ser usada.</li><li>As mensagens do conector não podem conter arquivos anexados.</li><li>A URL da instância do conector deve ser tratada como secreta/confidencial: qualquer pessoa que tenha essa URL pode enviar a ele, como um endereço de e-mail. Portanto, existe um certo risco de spam ou links para sites de phishing ou malware. Se isso acontecer, os proprietários da equipe podem excluir a instância do conector.</li><li>Se o serviço que envia as mensagens do conector ficar comprometido e começar a enviar links de spam/phishing/malware, o administrador do locatário poderá impedir que novas instâncias sejam criadas e a Microsoft poderá bloqueá-las centralmente.</li></ul></td>
  </tr>
</table>

> [!Note]
> No momento, não é possível saber quais conectores têm suporte para mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Webhooks de saída

_Webhooks de saída_ são criados na hora pelos proprietários ou membros da equipe se o sideloading está habilitado para um locatário. Não são recursos dos aplicativos Teams; essa informação está incluída para fins de completude.

<table>
  <tr>
    <th width="25%">Permissões obrigatórias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Pode receber mensagens de usuários e responder a eles.</td>
    <td valign="top">Nenhum</td>
    <td valign="top"><ul><li>Os webhooks de saída são semelhantes aos bots, mas possuem menos privilégios. Eles devem ser mencionados explicitamente, assim como bots.</li><li>Quando um webhook de saída é registrado, é gerado um _segredo_ que permite que ele verifique se o remetente é o Microsoft Teams, e não um invasor mal-intencionado. O segredo deve permanecer um segredo; qualquer pessoa que tenha acesso a ele, pode se passar pelo Microsoft Teams. Se o segredo for comprometido, o webhook de saída poderá ser excluído e criado novamente, e um novo segredo será gerado.</li><li>Embora seja possível criar um webhook de saída que não valide o segredo, não o recomendamos.</li><li>Além de receber e responder mensagens, os webhooks de saída não podem fazer muito: eles não podem enviar mensagens proativamente, não podem enviar nem receber arquivos, não podem fazer mais nada que os bots podem fazer, exceto receber e responder mensagens.</li></ul></td>
  </tr>
</table>