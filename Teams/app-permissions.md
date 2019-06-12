---
title: Permissões e considerações dos aplicativos Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 10/18/2018
ms.topic: conceptual
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: Saiba que aplicativos de dados e permissões estão solicitando da sua organização.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 167e8d8e628927e470422bf9d0a21adb06e48b53
ms.sourcegitcommit: c13bd343c3f3d14c7b8ff710ac5a4fec17ab88b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2019
ms.locfileid: "34859732"
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
| ![Um ícone que representa um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Use as tabelas a seguir como um guia para entender quais permissões os aplicativos que você está investigando estão solicitando.</li></ul> |
| ![Um ícone que representa a próxima etapa](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Pesquise o aplicativo ou o próprio serviço para decidir se deseja permitir o acesso a ele dentro da sua organização. Por exemplo, os bots enviam e recebem mensagens de usuários e, exceto para os bots de linha de negócios corporativo, estão localizados fora do limite de conformidade. Portanto, qualquer aplicativo que inclua um bot requer essas permissões e tem esse perfil de risco, no mínimo. </li></ul>|

## <a name="global-app-permissions-and-considerations"></a>Permissões e considerações globais do aplicativo

<table>
  <tr>
    <th width="25%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">Nenhum</td>
    <td valign="top">Nenhum</td>
    <td valign="top">Um aplicativo deve divulgar quais dados ele usa e o que os dados são usados nos termos de uso e nos links da política de privacidade.</td>
  </tr>
</table>

## <a name="bots-and-messaging-extensions"></a>Bots e extensões de mensagens

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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. O bot pode receber mensagens de usuários e respondê-las. <sup>1</sup></li><li>POST_MESSAGE_USER. Depois que um usuário envia uma mensagem para um bot, o bot pode enviar mensagens diretas ao usuário (também chamadas de <em>mensagens</em>proativas) a qualquer momento.</li><li>GET_CHANNEL_LIST. Os bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais de uma equipe.</li></ul></td>
    <td valign="top"><ul><li>Entidade. Quando&#39;s usado em um canal, os bots do aplicativo&#39;s podem acessar informações de identidade básicas dos membros da equipe (nome, sobrenome, nome UPN, endereço de email); Quando&#39;s usado em um chat pessoal ou em grupo, o bot pode acessar as mesmas informações para esses usuários.</li><li> POST_MESSAGE_TEAM. Permite que um aplicativo&#39;s bots envie mensagens diretas (pró-ativas) para qualquer membro da equipe a qualquer momento, mesmo que o usuário nunca tenha se falado com o bot antes.</li><li>As seguintes permissões não são explícitas, mas são implícitas por RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots podem ser usados, declarados no manifesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES. <sup>2</sup> controla se um bot pode enviar e receber arquivos em um chat pessoal (ainda não compatível com o chat em grupo ou canais).</li></ul></td>
    <td valign="top"><ul><li>Os bots só têm acesso às equipes às quais eles&#39;foram adicionados ou aos usuários que os instalaram.</li><li>Os bots só recebem mensagens em que&#39;são explicitamente mencionados pelos usuários. Esses dados saem da rede corporativa.</li><li>    Os bots só podem responder a conversas em que eles&#39;reformulados.</li><li>Depois que um usuário tiver disparado com um bot, se o bot armazenar esse usuário&#39;s ID, ele poderá enviar mensagens diretas ao usuário a qualquer momento. </li><li>Teoricamente, é possível que as mensagens de bot contenham links para sites de phishing ou de malware, mas os bots podem ser bloqueados pelo usuário, pelo administrador de locatários ou globalmente pela Microsoft. </li><li>Um bot pode recuperar (e pode armazenar) informações de identidade muito básicas para os membros da equipe para os quais o aplicativo foi adicionado ou para usuários individuais em chats pessoais ou em grupo. Para obter mais informações sobre esses usuários, o bot deve exigir que eles entrem no Azure Active Directory (Azure AD). </li><li>Os bots podem recuperar (e podem armazenar) a lista de canais em uma equipe; esses dados saem da rede corporativa. </li><li>Quando um arquivo é enviado a um bot, o arquivo sai da rede corporativa. O envio e recebimento de arquivos requer a aprovação do usuário para cada arquivo. </li><li>Por padrão, os bots Don&#39;t têm a capacidade de agir em nome do usuário, mas os bots podem solicitar que os usuários entrem; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer outras coisas. Exatamente o que essas coisas adicionais dependem do bot e do local em que o usuário entra: um bot é um aplicativo do Azure AD <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> registrado em e pode ter seu próprio conjunto de permissões.</li><li>Os bots são informados sempre que os usuários são adicionados ou excluídos de uma equipe.</li><li>Bots Don&#39;t Veja os usuários&#39; endereços IP ou outras informações referenciais. Todas as informações vêm da Microsoft. (Há uma exceção: se um bot implementar sua própria experiência de entrada, a interface do usuário de entrada irá ver os usuários&#39; endereços IP e informações de referenciais.)</li><li>As extensões de mensagens, por outro lado, podem ver os usuários&#39; endereços IP e informações de referenciais.</li><li>As diretrizes do aplicativo (e o processo de revisão do AppSource) exigem critério para o lançamento de mensagens de chat pessoais para usuários (por meio da permissão POST_MESSAGE_TEAM) para fins válidos. Em caso de abuso, os usuários podem bloquear o bot, os administradores de locatários podem bloquear o aplicativo e a Microsoft pode bloquear os bots de forma centralizada, se necessário.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Alguns bots apenas enviam mensagens (POST_MESSAGE_USER). Elas&#39;re chamadas &quot;para bots somente&quot; de notificação, mas o termo que não&#39;t se referem ao que um bot é permitido ou que não pode fazer, isso significa que o bot não&#39;quer expor uma experiência de conversa. O Microsoft Teams usa esse campo para desativar a funcionalidade na interface do usuário que normalmente seria habilitada; o bot não&#39;t restrito em o que&#39;s permitiu fazer em comparação com os bots que expõem uma experiência de conversa.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Controlado pela propriedade <code>supportsFiles</code> booliana no objeto bot no arquivo manifest. JSON do aplicativo.</td>
</tr>
</tfoot>
</table>

> [!Note]
> <ul><li>Se um bot tem sua própria entrada, há um segundo: experiência de consentimento diferente na primeira vez que o usuário entra.</li><li>Atualmente, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo do Teams (bot, guia, conector ou extensão de mensagens) são completamente separadas das permissões do teams listadas aqui.</li></ul>


## <a name="tabs"></a>Guias

Uma guia é um site em execução dentro do teams.

<table>
  <tr>
    <th width="25%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">SEND_AND_RECEIVE_WEB_DATA</td>
    <td valign="top">Nenhum (no momento).</td>
    <td valign="top"><ul><li>O perfil de risco para uma guia é quase idêntico ao mesmo site em execução em uma guia do navegador. </li><li>Uma guia também obtém o contexto em que ele&#39;s em execução, incluindo o nome de entrada e o UPN do usuário atual, a ID de objeto do Azure AD para o usuário atual, a ID do grupo do Office 365 em que ele reside (se for uma equipe) , a ID do locatário e a localidade atual do usuário. No entanto, para mapear essas IDs para um usuário&#39;s informações, a guia teria que fazer com que o usuário entre no Azure AD.</li></ul></td>
  </tr>
  </table>

## <a name="connectors"></a>Alinha

Um conector publica mensagens em um canal quando ocorrem eventos em um sistema externo.

  <table>
  <tr>
    <th width="25%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
  <tr>
    <td valign="top">POST_MESSAGE_CHANNEL</td>
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Certos conectores oferecem suporte a <em>mensagens acionáveis</em>, que permitem que os usuários publiquem respostas direcionadas para a mensagem do conector, por exemplo, adicionando uma resposta a um problema do GitHub ou adicionando uma data a um cartão Trello.</td>
    <td valign="top"><ul><li>O sistema que envia mensagens de conector não&#39;não sabe com quem ela&#39;está postando ou quem recebe as mensagens: nenhuma informação sobre o destinatário é divulgada. (A Microsoft é o destinatário real, e não o locatário; A Microsoft faz a postagem real para o canal.)</li><li>Nenhum dado sai da rede corporativa quando as mensagens do conector são postadas em um canal.</li><li>Os conectores que dão suporte a mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE) também não são&#39;a ver o endereço IP e informações de referenciais; essas informações são enviadas à Microsoft e roteadas para pontos de extremidade HTTP que foram registrados anteriormente na Microsoft no portal de conectores.</li><li>Cada vez que um conector é configurado para um canal, uma URL exclusiva para essa instância do conector é criada. Se essa instância do conector for excluída, a URL não poderá mais ser usada.</li><li>As mensagens do conector podem&#39;t contêm anexos de arquivo.</li><li>A URL da instância do conector deve ser tratada como segredo/confidencial: qualquer pessoa que tenha essa URL pode postá-la, como um endereço de email. Portanto, há&#39;pouco de risco de spam ou links para sites de phishing ou malware. Se isso fosse acontecer, os proprietários da equipe podem excluir a instância do conector.</li><li>Se o serviço que envia mensagens de conector fosse comprometido e começar a enviar spam/phishing/malware links, um administrador de locatário pode impedir que novas instâncias de conector sejam criadas e a Microsoft possa bloqueá-las de forma centralizada.</li></ul></td>
  </tr>
</table>

> [!Note]
> No momento, não é possível saber quais conectores suportam mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE).


## <a name="outgoing-webhooks"></a>WebHooks de saída

Os WebHooks de _saída_ são criados instantaneamente por proprietários da equipe ou pelos membros da equipe se o Sideload estiver habilitado para um locatário. Eles não são recursos de aplicativos Teams; essas informações estão incluídas para fins de integridade.

<table>
  <tr>
    <th width="25%">Permissões necessárias</th>
    <th width="25%">Permissões opcionais</th>
    <th width="50%">Considerações</th>
  </tr>
    <tr>
    <td valign="top">RECEIVE_MESSAGE, REPLYTO_MESSAGE. Pode receber mensagens de usuários e respondê-las.</td>
    <td valign="top">Nenhum</td>
    <td valign="top"><ul><li>Os WebHooks de saída são semelhantes aos bots, mas têm menos privilégios. Eles devem ser explicitamente mencionados, exatamente como os bots.</li><li>Quando um webhook de saída é registrado, um <em>segredo</em> é gerado, o que permite que o webhook de saída Verifique se o remetente é o Microsoft Teams em oposição a um invasor mal-intencionado. Esse segredo deve permanecer como um segredo; qualquer pessoa que tenha acesso a ela pode representar o Microsoft Teams. Se o segredo estiver comprometido, o webhook de saída pode ser excluído e recriado, e um novo segredo será gerado.</li><li>Embora&#39;possível criar um webhook de saída que não&#39;o segredo validar o segredo, recomendamos-o.</li><li>Além de receber e responder a mensagens, os WebHooks de saída podem&#39;eu realmente fazer: eles podem&#39;eu enviar mensagens proativamente, eles podem&#39;t enviar ou receber arquivos, eles podem&#39;eu fazer qualquer outra coisa que os bots possam fazer, exceto receber e responder às mensagens.</li></ul></td>
  </tr>
</table>
