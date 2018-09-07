---
title: Considerações e permissões de aplicativos do Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 08/20/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: lehewe
description: Saiba o que estão solicitando permissões e dados de aplicativos da sua organização.
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.openlocfilehash: f35620c1778bbe12f7d98f1a326e47a58804680b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870169"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a>Considerações e permissões de aplicativos do Microsoft Teams

Aplicativos do Microsoft Teams são uma maneira agregar um ou mais recursos em um _pacote de aplicativos_ que podem ser instalados, atualizados e desinstalado. Os recursos incluem:

-   Bots
-   Extensões de mensagens
-   Guias
-   Conectores

Aplicativos são consentiu pelos usuários e gerenciados por IT de uma perspectiva de política. No entanto, na maioria das vezes, permissões e perfil de risco de um aplicativo são definidos pelas permissões e os perfis de risco dos recursos que ele contém. Portanto, este artigo concentra-se sobre permissões e considerações no nível do recurso.

As permissões listadas a seguir em letras maiusculas, por exemplo, RECEIVE_MESSAGE e REPLYTO_MESSAGE, não aparecem em qualquer lugar na [documentação do desenvolvedor de equipes da Microsoft](https://aka.ms/teamsdevdocs) ou as [permissões para o Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference). Eles são simplesmente uma descritiva abreviada para fins deste artigo.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Use as tabelas abaixo como guia para compreender quais permissões os aplicativos que você está investigando estão solicitando.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>O aplicativo de pesquisa ou serviço propriamente dito para decidir se deseja permitir acesso a ele dentro da sua organização. Por exemplo, bots enviar e receber mensagens de usuários, e — exceto bots de linha de negócios da empresa — eles estão localizados fora do limite de conformidade. Portanto, qualquer aplicativo que inclui um bot requer essas permissões e tem esse perfil de risco, no mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Considerações e as permissões globais do aplicativo

<table>
  <tr>
    <th width="25%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">Nenhum</td>
    <td valign="top">Nenhum</td>
    <td valign="top">Um aplicativo deve divulgar quais dados ele usa e quais os dados são usados para em seus termos de uso e a privacidade links de política.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Extensões de mensagens e bots

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="24.5%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. O bot pode receber mensagens de usuários e responder a eles. <sup>1</sup></li><li>POST_MESSAGE_USER. Depois que um usuário tiver enviado uma mensagem a um bot, o bot pode ser enviar em usuário diretas mensagens (também chamadas de _mensagens proativas_) a qualquer momento.</li><li>GET_CHANNEL_LIST. Bots adicionados às equipes pode obter uma lista de nomes e identificações dos canais em uma equipe.</li></ul></td>
    <td valign="top"><ul><li>IDENTIDADE. Quando ela é usada em um canal, bots do aplicativo pode acessar informações de identidade básica de membros da equipe (nome, sobrenome, nome principal do usuário [UPN], endereço de email); Quando ela é usada em um bate-papo pessoal ou de grupo, o bot pode acessar as mesmas informações para os usuários.</li><li> POST_MESSAGE_TEAM. Permite bots de um aplicativo enviar mensagens de (proativas) diretas para qualquer membro da equipe a qualquer momento, mesmo que o usuário nunca tiver falaram para o bot antes.</li><li>O exemplo a seguir não é permissões explícitas, mas implicado RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots pode ser usados, declarado no manifesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. Controles de <sup>3</sup> se um bot pode enviar e receber arquivos em bate-papo pessoal (ainda não é suportado para o chat de grupo ou canais).</li></ul></td>
    <td valign="top"><ul><li>Bots só têm acesso às equipes para que eles tenha sido adicionados ou para usuários que instalaram-los.</li><li>Bots só receberão mensagens em que eles estiver explicitamente mencionados pelos usuários. Esses dados deixam a rede corporativa.</li><li>    Bots só pode responder a conversas nas quais eles estiver mencionados.</li><li>Depois que um usuário tem conversed com um bot, se o bot armazena a ID do usuário, ele pode enviar esse usuário diretas mensagens a qualquer momento. </li><li>Ele é teoricamente possível para que as mensagens bot contêm links para sites de phishing ou malware, mas bots poderão ser bloqueados pelo usuário, o administrador de locatário, ou globalmente pela Microsoft. </li><li>Um bot pode recuperar (e pode armazenar) informações básicas de identidade para os membros da equipe que o aplicativo foi adicionado ao ou para usuários individuais em bate-papos pessoais ou de grupo. Para obter mais informações sobre esses usuários, o bot deve requer que eles para entrar no Azure Active Directory (AD Azure). </li><li>Bots pode recuperar (e podem armazenar) na lista de canais em uma equipe; Esses dados deixam a rede corporativa. </li><li>Quando um arquivo é enviado para um bot, o arquivo deixa a rede corporativa. Enviando e recebendo arquivos requerem aprovação do usuário para cada arquivo. </li><li>Por padrão, bots não têm a capacidade de atuar em nome do usuário, mas bots pode solicitar aos usuários que entrar; Assim que o usuário entra no, o bot terá um token de acesso com os quais ele pode fazer as coisas adicionais. Exatamente o que esses fatores adicionais são depende do bot e onde o usuário entra no: um bot é um aplicativo do Windows Azure AD registrado na <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> e pode ter seu próprio conjunto de permissões.</li><li>Bots for informados sempre que os usuários são adicionados ou excluídos da equipe.</li><li>Bots não verá endereços IP de usuários ou outras informações de referência. Todas as informações proveniente da Microsoft. (Há uma exceção: se um bot implementa sua própria experiência de entrada, a interface do usuário entrar verá informações de referência e endereços IP de usuários.)</li><li>Por outro lado, extensões de mensagens, consulte informações de referência e endereços IP de usuários.</li><li>Diretrizes de aplicativo (e o processo de revisão de nosso AppSource) exigem o critério em mensagens de chat pessoal de lançamento para os usuários (via a permissão POST_MESSAGE_TEAM) para fins de válido. No caso de mau uso, os usuários podem bloquear o bot, administradores de Inquilino podem bloquear o aplicativo e Microsoft pode bloquear bots centralmente se necessário.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Alguns bots só enviam mensagens (POST_MESSAGE_USER). São chamados "somente notificação" bots, mas o termo não se referir a um bot que é permitido ou não é permitido fazer, isso significa que o bot não deseja expor uma experiência de conversa. As equipes usa esse campo para desabilitar a funcionalidade na interface de usuário que normalmente seria habilitado; o bot não é restrito no qual ele permitiu fazer em comparação com bots que expõem uma experiência de conversa.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">No momento na visualização do desenvolvedor.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">No momento na visualização do desenvolvedor. Governado pelo <code>supportsFiles</code> propriedade booleana no objeto bot no arquivo manifest.json para o aplicativo.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Se um bot tem seu próprio entrar, há um segundo — diferentes — experiência de consentimento na primeira vez em que o usuário entra no.</li><li>Atualmente, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo de equipes (bot, guia, conector ou extensão de mensagens) são totalmente separadas as permissões de equipes listadas aqui.</li></ul>


## <a name="tabs"></a>Guias

Uma guia é um site executando dentro de equipes.

<table>
  <tr>
    <th width="25%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Nenhum (atualmente).</td>
    <td valign="top"><ul><li>O perfil de risco para uma guia é quase idêntico ao mesmo site executando em uma guia de navegador. </li><li>Uma guia também obtém o contexto no qual ele estiver em execução, incluindo o nome de entrada e ID de UPN do usuário atual, o objeto do Windows Azure AD para o usuário atual, a ID do Office 365 grupo (equipe) no qual ele reside, a ID do inquilino e o local atual do usuário. No entanto, para mapear essas IDs para informações de um usuário, na guia teria que tornar o usuário entrar no Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Conectores

Um conector posta mensagens a um canal de ocorrências de eventos em um sistema externo.

  <table>
  <tr>
    <th width="25%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Determinadas conectores suportam a _mensagens acionáveis_, que permitem aos usuários postar respostas direcionadas à mensagem conector, por exemplo, adicionando uma resposta para um problema de GitHub ou uma data em um cartão de Trello.</td>
    <td valign="top"><ul><li>O sistema que posta mensagens conector não sabe que ele é postar ou quem recebe as mensagens: nenhuma informação sobre o destinatário está divulgada. (Microsoft é o destinatário real, não o locatário; A Microsoft faz a postagem real ao canal.)</li><li>Nenhum dado deixa a rede corporativa quando mensagens do conector são lançadas em um canal.</li><li>Conectores que oferecem suporte a mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE) não veja informações de referência e o endereço IP; Essas informações são enviadas à Microsoft e encaminhadas aos pontos de extremidade HTTP que foram registrados anteriormente com a Microsoft no portal de conectores.</li><li>Toda vez que um conector está configurado para um canal, uma URL exclusiva para essa instância do conector é criada. Se essa instância do conector é excluída, a URL não possa mais ser usada.</li><li>Mensagens do conector não podem conter anexos de arquivo.</li><li>A instância do conector URL deve ser tratado como segredo/confidencial: qualquer pessoa que tenha que URL pode postar a ele, como um endereço de email. Portanto, não há algum risco de spam ou links para sites de phishing ou malware. Se que acontecer, os proprietários de equipe podem excluir a instância do conector.</li><li>Se o serviço que envia mensagens de conector foram ficar comprometida e iniciar o envio de spam/phishing/malware links, um administrador de inquilino pode impedir que novas instâncias do conector seja criado e a Microsoft poderá bloqueá-la centralmente.</li></ul></td>
  </tr>
</table>

> [!Note]
> Não é possível atualmente saber quais conectores suportam a mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>Saída webhooks

_Webhooks de saída_ são criados dinamicamente por proprietários de equipe ou membros da equipe se sideloading estiver habilitado para um inquilino. Eles não são recursos de aplicativos de equipes; Essa informação é incluída para preservar a integridade.

<table>
  <tr>
    <th width="25%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Pode receber mensagens de usuários e responder a eles.</td>
    <td valign="top">Nenhum</td>
    <td valign="top"><ul><li>Webhooks de saída são semelhantes às bots, mas têm menos privilégios. Eles devem ser explicitamente mencionados, assim como bots.</li><li>Quando uma saída webhook é registrado, um _segredo_ é gerado, que permite a saída webhook verificar se o remetente está Teams da Microsoft em vez de um invasor mal-intencionado. Esse segredo deve permanecer em segredo; qualquer pessoa que tenha acesso a ele pode representar Teams da Microsoft. Se o segredo for comprometido, a saída webhook pode ser excluído e recriado e será gerado um novo segredo.</li><li>Embora seja possível criar um webhook de saída que não valida o segredo, é recomendável em relação a ele.</li><li>Diferente de receber e responder às mensagens, webhooks de saída não podem fazer muito: proativamente, eles não podem enviar mensagens, eles não podem enviar ou receber arquivos, eles não podem fazer qualquer outra coisa que bots pode exceto receber e responder a mensagens.</li></ul></td>
  </tr>
</table>