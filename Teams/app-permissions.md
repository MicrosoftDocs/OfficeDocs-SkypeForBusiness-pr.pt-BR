---
title: Permissões e considerações dos aplicativos Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 10/18/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_PracticalGuidance
search.appverid: MET150
ms.reviewer: lehewe
description: Saiba que aplicativos de dados e permissões estão solicitando da sua organização.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: da1c22852f12bad79413d8b1f57d129be4e0ffcd
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678398"
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
    <td valign="top" colspan="2"><ul><li>   RECEIVE_MESSAGE, REPLYTO_MESSAGE. O bot pode receber mensagens de usuários e responder a elas.<sup>1</sup></li><li>POST_MESSAGE_USER. Depois que um usuário envia uma mensagem para um bot, ele pode enviar mensagens diretas ao usuário (também chamadas de <em>mensagens proativas</em>) a qualquer momento.</li><li>GET_CHANNEL_LIST. Os bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais de uma equipe.</li></ul></td>
    <td valign="top"><ul><li>IDENTITY. Quando ele & #39; s usada em um canal, o aplicativo & #39; bots s pode acessar informações de identidade básica de membros da equipe (nome, sobrenome, nome principal do usuário [UPN], endereço de email); Quando ele & #39; s usado em um pessoal ou chat de grupo, o bot podem acessar as mesmas informações para os usuários.</li><li> POST_MESSAGE_TEAM. Permite que um aplicativo & #39; bots s para enviar mensagens (proativas) diretas para qualquer membro da equipe a qualquer momento, mesmo se o usuário nunca tiver falaram para o bot antes.</li><li>O que segue não são permissões explícitas, mas estão implícitas em RECEIVE_MESSAGE e REPLYTO_MESSAGE e nos escopos nos quais os bots podem ser usados, declarados no manifesto: <ul><li>RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</li><li>RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT<sup>2</sup> </li><li>RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</li></ul><li>SEND_FILES, RECEIVE_FILES.<sup>3</sup> Controla se um bot pode enviar e receber arquivos no bate-papo pessoal (ainda sem suporte para bate-papo ou canais em grupo).</li></ul></td>
    <td valign="top"><ul><li>Bots só têm acesso às equipes aos quais eles & #39; ve foram adicionadas ou para usuários que instalaram-los.</li><li>Bots apenas recebem mensagens em que eles & #39; re explicitamente mencionado pelos usuários. Esses dados saem da rede corporativa.</li><li>    Bots só pode responder ao conversas nas quais eles & #39; re mencionado.</li><li>Depois que um usuário tem conversed com um bot, se o bot armazena esse usuário & #39; s ID, ele pode enviar esse usuário diretas mensagens a qualquer momento. </li><li>Teoricamente, é possível que as mensagens do bot contenham links para sites de phishing ou malware, mas os bots podem ser bloqueados pelo usuário, pelo administrador do locatário ou globalmente pela Microsoft. </li><li>O bot pode recuperar (e pode armazenar) informações de identidade básicas dos membros da equipe aos quais o aplicativo foi adicionado ou de usuários individuais em bate-papos pessoais ou em grupo. Para obter mais informações sobre esses usuários, o bot deve solicitar que façam login no Azure Active Directory (Azure AD). </li><li>Os bots podem recuperar (e podem armazenar) a lista de canais de uma equipe; esses dados saem da rede corporativa. </li><li>Quando um arquivo é enviado para um bot, o arquivo sai da rede corporativa. O envio e o recebimento de arquivos requer a aprovação do usuário para cada arquivo. </li><li>Por padrão, don bots & #39; t têm a capacidade de atuar em nome do usuário, mas bots pode solicitar aos usuários que entrar; Assim que o usuário entra no, o bot terá um token de acesso com os quais ele pode fazer as coisas adicionais. O que essas outras coisas são exatamente depende do bot e de onde o usuário faz login: um bot é um aplicativo do Azure AD registrado em <a href="https://apps.dev.microsoft.com/">https://apps.dev.microsoft.com/</a> e pode ter o seu próprio conjunto de permissões.</li><li>Os bots são informados sempre que usuários são adicionados ou excluídos de uma equipe.</li><li>Don bots & #39; Consulte usuários de t & #39; Endereços IP ou outras informações de referência. Todas as informações vêm da Microsoft. (Há uma exceção: se um bot implementa sua própria experiência de entrada, a interface do usuário entrar verá usuários & #39; Endereços IP e informações de referência.)</li><li>Por outro lado, extensões de mensagens, consulte usuários & #39; Endereços IP e informações de referência.</li><li>As diretrizes do aplicativo (e nosso processo de avaliação do AppSource) requerem discrição do usuário ao publicar mensagens de bate-papo pessoal (por meio da permissão POST_MESSAGE_TEAM) para fins válidos. No caso de abuso, os usuários podem bloquear o bot, os administradores do locatário podem bloquear o aplicativo e a Microsoft pode bloquear os bots centralmente, se necessário.</li></ul></td>
</tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3">Alguns bots só enviam mensagens (POST_MESSAGE_USER). Eles & #39; re chamado &quot;somente notificação&quot; bots, mas o não termos & #39; t se referir a um bot que é permitido ou não é permitido fazer, isso significa que o não bot & #39; t deseja expor uma experiência de conversa. As equipes usa esse campo para desabilitar a funcionalidade na interface de usuário que normalmente seria habilitado; o não é de bot & #39; t restringidas no qual ele & #39; s permitido fazer em comparação com bots que expõem uma experiência de conversa.</td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3">Atualmente na previsualização do desenvolvedor.</td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3">Governado pelo <code>supportsFiles</code> propriedade booleana no objeto bot no arquivo manifest.json para o aplicativo.</td>
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
    <td valign="top"><ul><li>O perfil de risco para uma guia é quase idêntico ao mesmo site executando em uma guia de navegador. </li><li>Uma guia também obtém o contexto no qual ele & #39; s executando, incluindo o nome de entrada e o UPN do usuário atual, a ID de objeto do Windows Azure AD para o usuário atual, a ID do Office 365 grupo (equipe) no qual ele reside, a ID do inquilino e o local atual do usuário. No entanto mapear essas IDs para um usuário & #39; informações s, na guia teria que tornar o usuário entrar no Azure AD.</li></ul></td>
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
    <td valign="top">REPLYTO_CONNECTOR_MESSAGE. Determinadas conectores suportam a <em>mensagens acionáveis</em>, que permitem aos usuários postar respostas direcionadas à mensagem conector, por exemplo, adicionando uma resposta para um problema de GitHub ou uma data em um cartão de Trello.</td>
    <td valign="top"><ul><li>O sistema que postagens conector mensagens & #39; Saiba quem ele & #39; s postar ou quem recebe as mensagens: nenhuma informação sobre o destinatário está divulgada. (Microsoft é o destinatário real, não o locatário; A Microsoft faz a postagem real ao canal.)</li><li>Nenhum dado deixa a rede corporativa quando mensagens do conector são lançadas em um canal.</li><li>Conectores que suportam a mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE) também don & #39; t consulte IP endereço e referenciadora informações; Essas informações são enviadas à Microsoft e encaminhadas aos pontos de extremidade HTTP que foram registrados anteriormente com a Microsoft no portal de conectores.</li><li>Toda vez que um conector está configurado para um canal, uma URL exclusiva para essa instância do conector é criada. Se essa instância do conector é excluída, a URL não possa mais ser usada.</li><li>Conector mensagens can & #39; t que contêm anexos de arquivo.</li><li>A instância do conector URL deve ser tratado como segredo/confidencial: qualquer pessoa que tenha que URL pode postar a ele, como um endereço de email. Portanto, há & #39; s algum risco de spam ou links para sites de phishing ou malware. Se que acontecer, os proprietários de equipe podem excluir a instância do conector.</li><li>Se o serviço que envia mensagens de conector foram ficar comprometida e iniciar o envio de spam/phishing/malware links, um administrador de inquilino pode impedir que novas instâncias do conector seja criado e a Microsoft poderá bloqueá-la centralmente.</li></ul></td>
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
    <td valign="top"><ul><li>Webhooks de saída são semelhantes às bots, mas têm menos privilégios. Eles devem ser explicitamente mencionados, assim como bots.</li><li>Quando uma saída webhook é registrado, um <em>segredo</em> é gerado, que permite a saída webhook verificar se o remetente está Teams da Microsoft em vez de um invasor mal-intencionado. Esse segredo deve permanecer em segredo; qualquer pessoa que tenha acesso a ele pode representar Teams da Microsoft. Se o segredo for comprometido, a saída webhook pode ser excluído e recriado e será gerado um novo segredo.</li><li>Embora ele & #39; s possível criar um webhook de saída que não & #39; t validar o segredo, não é recomendável.</li><li>Que não sejam receber e responder às mensagens, saída webhooks can & #39; t fazer muito: eles can & #39; t proativamente enviar mensagens, eles can & #39; t enviar ou receber arquivos, eles podem & #39; t fazer qualquer outra coisa que bots pode exceto receber e responder para mensagens.</li></ul></td>
  </tr>
</table>
