---
title: Barreiras de informação no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: Saiba mais sobre barreiras de informação e como elas afetam o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cdb736db3234d0c7e24729a7d8e2b06c2d068d0
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780810"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barreiras de informação no Microsoft Teams

As barreiras de informação (IB) são políticas que um administrador pode configurar para impedir que pessoas ou grupos se comuniquem uns com os outros. Isso é útil se, por exemplo, um departamento estiver manipulando informações que não devem ser compartilhadas com outros departamentos, ou se um grupo precisar ser impedido, ou isolado, de comunicar-se com qualquer pessoa fora do grupo.

> [!NOTE]
> - Grupos de barreira de informações não podem ser criados entre locatários.
> - Não há suporte para o uso de bots para adicionar usuários na versão 1.
> - Os canais privados são compatíveis com as políticas de barreira de informações que você configurar.
> - Novo: o suporte à barreira de informações do site do SharePoint conectado ao Teams agora está em visualização particular. Clique [aqui](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) para participar da visualização particular.

As políticas de barreira de informações também impedem pesquisas e descobrimento. Isso significa que, se você tentar se comunicar com alguém com quem não deveria se comunicar, não encontrará esse usuário no seletor de pessoas.

## <a name="background"></a>Plano de fundo

O principal driver para barreiras de informação vem do setor de serviços financeiros. A autoridade de regulamentação do setor financeiro ([FINRA]( http://www.finra.org)) analisa as barreiras e os conflitos de interesse em instituições de membros e fornece orientação sobre como gerenciar tais conflitos (FINRA 2241, [aviso de regulamentação de pesquisa de dívidas 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

No entanto, como apresentar barreiras de informação, muitas outras áreas o encontraram para serem úteis. Outros cenários comuns incluem:

- Educação: os alunos em uma escola não conseguem Pesquisar detalhes de contato para alunos de outras escolas.
- Legal: manter a confidencialidade dos dados obtidos pela advogado de um cliente de ser acessado por um advogado para a mesma firma que representa um cliente diferente.
- Governo: o acesso às informações e o controle são limitados entre departamentos e grupos.
- Serviços profissionais: um grupo de pessoas em uma empresa só pode conversar com um cliente ou cliente específico via Federação ou acesso de convidado durante um envolvimento do cliente.

Por exemplo, Enrico pertence ao segmento bancário e Pradeep pertence ao segmento de supervisor financeiro. O Enrico e o Pradeep não conseguem se comunicar uns com os outros porque a política IB da organização bloqueia a comunicação e a colaboração entre esses dois segmentos. No entanto, Enrico e Pradeep podem se comunicar com Lee em RH.

![Exemplo que mostra barreiras de informação impedindo a comunicação entre segmentos](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quando usar barreiras de informações

Você pode querer usar barreiras de informação em situações como estas:

- Uma equipe deve ser impedida de comunicação ou compartilhamento de dados com outra equipe específica.
- Uma equipe não deve se comunicar nem compartilhar dados com pessoas de fora da equipe.

O serviço de avaliação da política de barreira de informações determina se uma comunicação está em conformidade com as políticas de barreira de informações.

## <a name="managing-information-barrier-policies"></a>Gerenciar políticas de barreira de informações

As políticas de barreira de informações são gerenciadas no centro de conformidade do Microsoft 365 (SCC) usando cmdlets do PowerShell. Para obter mais informações, consulte [definir políticas para barreiras de informação](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Antes de configurar ou definir políticas, **você deve habilitar a pesquisa de diretório em escopo no Microsoft Teams**. Aguarde pelo menos 24 horas depois de habilitar a pesquisa de diretório de escopo antes de configurar ou definir políticas para barreiras de informação. [Saiba mais sobre pré-requisitos para barreiras de informação](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Função de administrador de barreiras de informações

A função de gerenciamento de conformidade IB é responsável por gerenciar políticas de barreira de informações. Para obter mais informações sobre essa função, consulte [permissões no centro de conformidade do Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="information-barrier-triggers"></a>Gatilhos de barreira de informações

As políticas de barreira de informações são ativadas quando ocorrem os seguintes eventos de equipe:

- **Os membros são adicionados a uma equipe** , sempre que você adiciona um usuário a uma equipe, a política do usuário deve ser avaliada em relação às políticas de barreira de informações de outros membros da equipe. Depois que o usuário for adicionado com êxito, o usuário poderá executar todas as funções na equipe sem verificações adicionais. Se a política do usuário impedir que elas sejam adicionadas à equipe, o usuário não aparecerá na pesquisa.

    ![Captura de tela mostrando o chat em grupo](media/information-barriers-add-members.png)

- **Um novo Chat é solicitado** -sempre que um novo Chat é solicitado entre dois ou mais usuários, o chat é avaliado para garantir que ele não viole nenhuma política de barreira de informações. Se a conversa violar uma política de barreira de informações, a conversa não será iniciada.

    Veja um exemplo de um chat do 1:1.

     ![Captura de tela mostrando comunicações bloqueadas no chat do 1:1](media/information-barriers-one-one-chat.png)

    Aqui está um exemplo de um chat em grupo.

    ![Captura de tela mostrando o chat em grupo](media/information-barriers-group-chat.png)

- **Um usuário é convidado a ingressar em uma reunião** -quando um usuário é convidado a ingressar em uma reunião, a política do usuário é avaliada em relação às políticas de outros membros da equipe e, se houver uma violação, o usuário não terá permissão para ingressar na reunião.

    ![Captura de tela mostrando usuário bloqueado da reunião](media/information-barriers-meeting.png)

- **Uma tela é compartilhada entre dois ou mais usuários** -a qualquer momento em que uma tela é compartilhada entre dois ou mais usuários, o compartilhamento de tela deve ser avaliado para garantir que ele não viole as políticas de barreira de informações de outros usuários. Se uma política de barreira de informações for violada, o compartilhamento de tela não será permitido.
- **Um usuário insere uma chamada telefônica (VoIP) no Teams** -sempre que uma chamada de voz é iniciada por um usuário para outro usuário ou grupo de usuários, a chamada é avaliada para garantir que ela não viole as políticas de barreira de informações de outros membros da equipe. Se houver alguma violação, a chamada de voz será bloqueada.
- **Usuários convidados em equipes** – as políticas de barreira de informações se aplicam também a usuários convidados no Microsoft Teams. Se os usuários convidados precisarem ser detectáveis na lista de endereços global da sua organização, consulte [gerenciar o acesso de convidados nos grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#can-i-make-guest-objects-visible-in-the-global-address-list). Depois que os usuários convidados são detectáveis, você pode [definir políticas de barreira de informações](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Como as alterações de política afetam os chats existentes

Quando o administrador de política de barreira de informações faz alterações em uma política ou uma alteração de política entra em vigor devido a uma alteração no perfil de um usuário (por exemplo, para uma alteração de trabalho ou um motivo semelhante), o serviço de avaliação da política de barreira de informações pesquisa automaticamente os membros para garantir que os membros da equipe não estejam violando nenhuma política.

Se houver um chat existente ou outras comunicações entre usuários e uma nova política for definida ou uma política existente for alterada, o serviço avaliará as comunicações existentes para garantir que as comunicações ainda sejam permitidas.

- **1:1 chat** -se a comunicação entre os dois usuários não for mais permitida (se uma comunicação de bloqueio de política for aplicada a um ou aos dois usuários), a comunicação adicional será bloqueada e a conversa de chat se tornará somente leitura.

- **Chat em grupo** -se a comunicação de um usuário para o grupo não for mais permitida (por exemplo, se um usuário alterar trabalhos), o usuário juntamente com os outros usuários que violam a política poderá ser removido do chat em grupo e outras comunicações com o grupo não serão permitidas. O usuário ainda pode ver conversas antigas (que serão somente leitura), mas não poderá ver ou participar de nenhuma nova conversa com o grupo. Se a política nova ou alterada que impede a comunicação for aplicada a mais de um usuário, os usuários afetados pela política poderão ser removidos do chat em grupo. Eles ainda podem ver conversas antigas.

Neste exemplo, o Enrico é movido para um departamento diferente dentro da organização e é removido do chat em grupo.

  ![Captura de tela mostrando o chat em grupo](media/information-barriers-user-changes-job.png)

O Enrico não pode mais enviar mensagens para o chat em grupo.

  ![Captura de tela mostrando o chat em grupo](media/information-barriers-user-changes-job-2.png)

- **Equipe** -todos os usuários que foram removidos do grupo são removidos da equipe e não poderão ver nem participar de conversas existentes ou novas.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Cenário: um usuário em um chat existente torna-se bloqueado

No momento, os usuários perceberão o seguinte se uma política de barreira de informações bloquear outro usuário:

- **Guia pessoas** -um usuário não pode ver usuários bloqueados na guia **pessoas** .
- **Seletor de pessoas** -os usuários bloqueados não ficarão visíveis no seletor de pessoas.

    ![Captura de tela mostrando o chat em grupo](media/information-barriers-people-picker.png)
    
- **Guia atividade** -se um usuário visitar a guia **atividade** de um usuário bloqueado, nenhuma postagem será exibida. (A guia **atividade** exibe somente Postagens de canal e não haveria canais comuns entre os dois usuários.)
- **Organogramas** -se um usuário acessar um organograma no qual um usuário bloqueado é exibido, o usuário bloqueado não será exibido no organograma e uma mensagem de erro será exibida.
- **Cartão de visita** -se um usuário participar de uma conversa e o usuário for bloqueado posteriormente, outros usuários verão uma mensagem de erro em vez do cartão de pessoas quando passarem o mouse sobre o nome do usuário bloqueado. As ações listadas no cartão (como chamada e chat) não estarão disponíveis.
- **Contatos sugeridos** -os usuários bloqueados não aparecem na lista de contatos sugeridos (a lista de contatos inicial exibida para novos usuários).
- **Contatos de chat** -um usuário pode ver usuários bloqueados na lista de contatos chats, mas os usuários bloqueados serão identificados e a única ação que o usuário poderá executar será excluí-los. O usuário também pode clicar neles para ver a conversa anterior.
- **Chamadas contatos** -um usuário pode ver os usuários bloqueados na lista de contatos chamadas, mas os usuários bloqueados serão identificados e a única ação que o usuário poderá executar será excluí-los.
- **Migração do Skype para o Teams** -durante uma migração do Skype for Business para o Teams, todos os usuários, mesmo aqueles bloqueados por políticas de barreira de informações, serão migrados para o Teams e, em seguida, serão manipulados conforme descrito acima.

## <a name="teams-policies-and-sharepoint-sites"></a>Políticas de equipe e sites do SharePoint

Quando uma equipe é criada, um site do SharePoint é provisionado e associado à equipe para a experiência dos arquivos. O acesso a este site e arquivos do SharePoint honra a IB da organização, ou seja, somente os usuários cuja segmento de IB corresponde a política de IB têm permissão de acesso. Mesmo no momento do compartilhamento de arquivos, a política IB é respeitada.

Por exemplo: na contoso Bank Corporation, o usuário ' Sesha@contosobank.onmicrosoft.com ' pertence ao segmento bancário de investimentos e o usuário ' Nikita@contosobank.onmicrosoft.com ' pertence ao consultor do segmento. A política IB da organização bloqueia a comunicação e a colaboração entre esses dois segmentos.
Quando o usuário Sesha cria um segmento de banco de investimentos, a equipe e o site do SharePoint que os reproduzir serão acessíveis somente para os usuários do segmento do banco de investimentos. O Nikita do usuário não pode acessar esse site, mesmo que ele tenha o link do site.

## <a name="required-licenses-and-permissions"></a>Permissões e licenças necessárias

Para obter mais detalhes, incluindo planos e preços, consulte [orientação de licenciamento](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="more-information"></a>Mais informações

- Para saber mais sobre as barreiras de informação, consulte [barreiras de informações](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Para configurar políticas de barreira de informações, consulte [definir políticas para barreiras de informação](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

- Para editar ou remover as políticas de barreira de informações, consulte [Editar (ou remover) políticas de barreira de informações](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).
