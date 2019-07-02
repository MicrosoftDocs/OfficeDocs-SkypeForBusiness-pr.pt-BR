---
title: Barreiras de informações na visualização do Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/01/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: Saiba mais sobre barreiras de informação e como elas afetam o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a9c896e7131dfcd1a510a39712759fd8143fe3f
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418284"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a>Barreiras de informações na visualização do Microsoft Teams

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

Barreiras de informação são políticas que um administrador pode configurar para impedir que pessoas ou grupos se comuniquem uns com os outros. Isso é útil se, por exemplo, um departamento estiver manipulando informações que não devem ser compartilhadas com outros departamentos, ou se um grupo precisar ser impedido, ou isolado, de comunicar-se com qualquer pessoa fora do grupo.

> [!NOTE]
> - Grupos de barreira de informações não podem ser criados entre locatários.
> - Não há suporte para o uso de bots para adicionar usuários na versão 1.
> - Barreiras de informação a versão 1 não inclui suporte para o SharePoint e o OneDrive for Business. Estamos trabalhando para habilitar o recurso no SharePoint e ele se comunicará assim que estiver disponível.

As políticas de barreira de informações também impedem pesquisas e descobrimento. Isso significa que, se você tentar se comunicar com alguém com quem não deveria se comunicar, não encontrará esse usuário no seletor de pessoas.

## <a name="background"></a>Plano de fundo

O principal driver para barreiras de informação vem do setor de serviços financeiros. A autoridade de regulamentação do setor financeiro ([FINRA]( http://www.finra.org)) analisa as barreiras e os conflitos de interesse em instituições de membros e fornece orientação sobre como gerenciar tais conflitos (FINRA 2241, [aviso de regulamentação de pesquisa de dívidas 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>Quando devo usar as barreiras de informação?

Você pode querer usar barreiras de informação em situações como estas:

- Uma equipe deve ser impedida de comunicação ou compartilhamento de dados com outra equipe específica.
- Uma equipe não deve se comunicar nem compartilhar dados com pessoas de fora da equipe.

O serviço de avaliação da política de barreira de informações determina se uma comunicação está em conformidade com as políticas de barreira de informações. 

## <a name="managing-information-barrier-policies"></a>Gerenciar políticas de barreira de informações

As políticas de barreira de informações são gerenciadas com cmdlets do PowerShell do centro de conformidade do & Security (SCC). Para obter mais informações sobre como usar esses cmdlets, consulte [definir políticas para barreiras de informação (visualização)](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Antes de configurar ou definir políticas, **você deve habilitar a pesquisa de diretório em escopo no Microsoft Teams**. Aguarde pelo menos 24 horas depois de habilitar a pesquisa de diretório de escopo antes de configurar ou definir políticas para barreiras de informação.

## <a name="information-barriers-administrator-role"></a>Função de administrador de barreiras de informações

A função de administrador de barreiras de informação (gerenciamento de conformidade da IB) é responsável por gerenciar políticas de barreira de informações. Para obter mais informações sobre essa função, consulte [permissões no centro de conformidade do & de segurança do Office 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="when-are-information-barrier-policies-checked"></a>Quando as políticas de barreira de informações são verificadas?

As políticas de barreira de informações são verificadas quando ocorrem os seguintes eventos de equipe:

- **Os membros são adicionados a uma equipe** , sempre que você adiciona um usuário a uma equipe, a política do usuário deve ser avaliada em relação às políticas de barreira de informações de outros membros da equipe. Depois que o usuário for adicionado com êxito, o usuário poderá executar todas as funções na equipe sem verificações adicionais. Se a política do usuário impedir que elas sejam adicionadas à equipe, o usuário não aparecerá na pesquisa.
- **Um novo Chat é solicitado** -sempre que um novo Chat é solicitado entre dois ou mais usuários, o chat é avaliado para garantir que ele não viole nenhuma política de barreira de informações. Se a conversa violar uma política de barreira de informações, a conversa não será iniciada.
- **Um usuário é convidado a ingressar em uma reunião** -quando um usuário é convidado a ingressar em uma reunião, a política do usuário é avaliada em relação às políticas de outros membros da equipe e, se houver uma violação, o usuário não terá permissão para ingressar na reunião.
- **Uma tela é compartilhada entre dois ou mais usuários** -a qualquer momento em que uma tela é compartilhada entre dois ou mais usuários, o compartilhamento de tela deve ser avaliado para garantir que ele não viole as políticas de barreira de informações de outros usuários. Se uma política de barreira de informações for violada, o compartilhamento de tela não será permitido.
- **Um usuário insere uma chamada telefônica (VoIP) no Teams** -sempre que uma chamada de voz é iniciada por um usuário para outro usuário ou grupo de usuários, a chamada é avaliada para garantir que ela não viole as políticas de barreira de informações de outros membros da equipe. Se houver alguma violação, a chamada de voz será bloqueada.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>O que acontece com os threads de chat existentes quando uma política é alterada?

Quando o administrador da política de barreira de informações faz alterações em uma política ou uma alteração de política entra em vigor devido a uma alteração no perfil de um usuário (por exemplo, para uma alteração de trabalho ou um motivo semelhante), o serviço de avaliação da política de barreira de informações pesquisa automaticamente os membros para garantir que os membros da equipe não violem nenhuma política.

Se houver um chat existente ou outras comunicações entre usuários e uma nova política for definida ou uma política existente for alterada, o serviço avaliará as comunicações existentes para garantir que as comunicações ainda sejam permitidas. 

- **1:1 chat** -se a comunicação entre os dois usuários não for mais permitida (se uma comunicação de bloqueio de política for aplicada a um ou aos dois usuários), a comunicação adicional será bloqueada e a conversa de chat se tornará somente leitura.
- **Chat em grupo** -se a comunicação de um usuário para o grupo não for mais permitida (por exemplo, se um usuário alterar trabalhos), o usuário juntamente com os outros usuários que violam a política poderá ser removido do chat em grupo e outras comunicações com o grupo não serão autorizados. O usuário ainda pode ver conversas antigas (que serão somente leitura), mas não poderá ver ou participar de nenhuma nova conversa com o grupo. Se a política nova ou alterada que impede a comunicação for aplicada a mais de um usuário, os usuários afetados pela política poderão ser removidos do chat em grupo. Eles ainda podem ver conversas antigas. 
- **Equipe** -todos os usuários que foram removidos do grupo são removidos da equipe e não poderão ver nem participar de conversas existentes ou novas.

## <a name="what-will-users-experience-if-another-user-is-blocked"></a>O que os usuários terão se outro usuário estiver bloqueado?

No momento, os usuários perceberão o seguinte se uma política de barreira de informações bloquear outro usuário:

- **Guia pessoas** -um usuário pode ver alguns usuários bloqueados na guia **pessoas** . O usuário pode selecionar os usuários bloqueados.
- **Guia atividade** -se um usuário visitar a guia **atividade** de um usuário bloqueado, nenhuma postagem será exibida. (A guia **atividade** exibe somente Postagens de canal e não haveria canais comuns entre os dois usuários.)
- **Organogramas** -se um usuário acessar um organograma no qual um usuário bloqueado é exibido, o usuário verá o usuário bloqueado no gráfico e poderá clicar em ações no gráfico, mas as ações (como chamadas) não serão exibidas.
- **Cartão de visita** -se um usuário participar de uma conversa e estiver bloqueado posteriormente, outros usuários ainda poderão ver o cartão de pessoas para o usuário bloqueado. Todas as ações listadas no cartão (como chamada e chat) estarão disponíveis, mas as ações não passarão.
- **Contatos sugeridos** -na lista contatos sugeridos (a lista de contatos inicial exibida para novos usuários), os usuários podem ver todos os contatos sugeridos (incluindo usuários bloqueados). No entanto, se um usuário clicar no nome de um usuário bloqueado para abrir o painel chats, a mensagem será bloqueada.
- **Contatos do chat** -um usuário pode ver usuários bloqueados na lista de contatos do chat.
- **Chamadas para contatos** -um usuário pode ver os usuários bloqueados na lista de contatos chamadas, e as ações, como chamadas e mensagens, serão exibidas, mas quando o usuário tentar ligar ou enviar uma mensagem para o usuário bloqueado, a chamada ou mensagem não será perenviada.
- **Migração do Skype para** o Teams-durante uma migração do Skype for Business para o Teams, todos os usuários, mesmo aqueles bloqueados por políticas de barreira de informações, serão migrados para o Teams e, em seguida, serão manipulados conforme descrito acima.

Em breve: os usuários perceberão o seguinte se uma política de barreira de informações bloquear outro usuário:

- **Guia pessoas** -um usuário não pode ver usuários bloqueados na guia **pessoas** .
- **Guia atividade** -se um usuário visitar a guia **atividade** de um usuário bloqueado, nenhuma postagem será exibida. (A guia **atividade** exibe somente Postagens de canal e não haveria canais comuns entre os dois usuários.)
- **Organogramas** -se um usuário acessar um organograma no qual um usuário bloqueado é exibido, o usuário bloqueado não será exibido no organograma e uma mensagem de erro será exibida.
- **Cartão de visita** -se um usuário participar de uma conversa e o usuário for bloqueado posteriormente, outros usuários verão uma mensagem de erro em vez do cartão de pessoas quando passarem o mouse sobre o nome do usuário bloqueado. As ações listadas no cartão (como chamada e chat) não estarão disponíveis.
- **Contatos sugeridos** -os usuários bloqueados não aparecem na lista de contatos sugeridos (a lista de contatos inicial exibida para novos usuários).
- **Contatos do chat** -um usuário não pode ver usuários bloqueados na lista de contatos do chat.
- **Chamadas contatos** -um usuário pode ver os usuários bloqueados na lista de contatos chamadas, mas os usuários bloqueados serão identificados e a única ação que o usuário poderá executar será excluí-los.
- **Migração do Skype para** o Teams-durante uma migração do Skype for Business para o Teams, todos os usuários, mesmo aqueles bloqueados por políticas de barreira de informações, serão migrados para o Teams e, em seguida, serão manipulados conforme descrito acima.

## <a name="required-licenses-and-permissions"></a>Permissões e licenças necessárias

Atualmente, os recursos de barreira de informações estão em visualização pública. Quando esses recursos estiverem disponíveis em geral, eles serão incluídos em assinaturas, como:

- Microsoft 365 e5
- Office 365 E5
- Conformidade avançada do Office 365
- Conformidade com o Microsoft 365 e5

Para obter mais detalhes, incluindo planos e preços, consulte [soluções de conformidade](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).

## <a name="more-information"></a>Mais informações

- Para saber mais sobre as barreiras de informação, consulte [barreiras de informação (prévia)](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Para configurar políticas de barreira de informações, consulte [definir políticas para barreiras de informação (prévia)](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)
