---
title: Barreiras de informações no Microsoft Teams
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: Este artigo explica o que são barreiras de informações no Microsoft Teams e como elas podem afetar o Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94e0117e1f0956d8e3e9ae8e6bafc7feabcdf237
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196455"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barreiras de informações no Microsoft Teams

As barreiras de informações (IBs) são políticas que um administrador pode configurar para impedir que indivíduos ou grupos se comuniquem uns com os outros. IBs são úteis se, por exemplo, um departamento estiver manipulando informações que não devem ser compartilhadas com outros departamentos. As IBs também são úteis quando um grupo precisa ser isolado ou impedido de se comunicar com qualquer pessoa de fora desse grupo.

> [!NOTE]
> - Grupos de barreira de informações (IB) não podem ser criados entre locatários.
> - O uso de bots, aplicativos do Azure Active Directory (Azure AD) e algumas APIs para adicionar usuários não tem suporte na versão 1.
> - Os canais privados são compatíveis com as políticas de IB que você configura.
> - Novo: Para obter informações sobre suporte a barreiras para sites do SharePoint conectados ao Teams, consulte [Segmentos associados aos sites do Microsoft Teams.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

As políticas de IB também impedem a pesquisa e a descoberta. Se você tentar se comunicar com alguém com quem não deve se comunicar, não encontrará esse usuário no selador de pessoas.

## <a name="background"></a>Plano de fundo

O principal fator para IBs vem do setor de serviços financeiros. A Autoridade Regulatória do Setor Financeiro[(FINRA)]( https://www.finra.org)analisa IBs e conflitos de interesse dentro de empresas membros e fornece orientações sobre o gerenciamento desses conflitos (FINRA 2241, Aviso Regulamentar de Pesquisa de [Débitos 15-31).](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)


No entanto, desde a introdução de IBs, muitas outras áreas as descobriram úteis. Outros cenários comuns incluem:

- Educação: os alunos de uma escola não conseguem procurar detalhes de contato para alunos de outras escolas.

- Legal: manter a confidencialidade dos dados obtidos pelo cliente potencial e impedi-los de serem acessados por um responsável pela mesma empresa que representa um cliente diferente.

- Governo: o acesso e o controle de informações são limitados entre departamentos e grupos.

- Serviços profissionais: um grupo de pessoas em uma empresa só pode conversar com um cliente ou um cliente específico por meio do acesso de convidado durante um compromisso com o cliente.

Por exemplo, E ltda pertence ao segmento Bancário e Pradeep pertence ao segmento consultor financeiro. E ltda e Pradeep não podem se comunicar entre si porque a política de IB da organização bloqueia a comunicação e a colaboração entre esses dois segmentos. No entanto, E ltda e Pradeep podem se comunicar com Lee no RH.

![Exemplo mostrando barreiras de informações que impedem a comunicação entre segmentos](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quando usar barreiras de informações

Talvez você queira usar IBs em situações como estas:

- Uma equipe deve ser impedida de se comunicar ou compartilhar dados com uma outra equipe específica.
- Uma equipe não deve se comunicar ou compartilhar dados com ninguém de fora da equipe.

O Serviço de Avaliação da Política de Barreira de Informações determina se uma comunicação está em conformidade com as políticas de IB.

## <a name="managing-information-barrier-policies"></a>Gerenciar políticas de barreira de informações

As políticas de IB são gerenciadas no Centro de Conformidade (SCC) do Microsoft 365 usando cmdlets do PowerShell. Para obter mais informações, consulte [Definir políticas para barreiras de informações.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

> [!IMPORTANT]
> Antes de configurar ou definir políticas, você deve habilitar a pesquisa de diretório com escopo no Microsoft Teams. Aguarde pelo menos algumas horas após ativar a pesquisa de diretório com escopo antes de configurar ou definir políticas para barreiras de informações. Para obter mais informações, consulte [Definir políticas de barreira de informações.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>Função de administrador de barreiras de informações

A função Gerenciamento de Conformidade IB é responsável pelo gerenciamento de políticas de IB. Para obter mais informações sobre essa função, consulte Permissões no Centro de Conformidade do [Microsoft 365.](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Gatilhos de barreira de informações

As políticas IB são ativadas quando os seguintes eventos do Teams ocorrem:

- **Membros são adicionados a uma** equipe - Sempre que você adicionar um usuário a uma equipe, a política do usuário deve ser avaliada em relação às políticas de IB de outros membros da equipe. Depois que o usuário for adicionado com êxito, o usuário poderá executar todas as funções da equipe sem mais verificações. Se a política do usuário o impede de ser adicionado à equipe, o usuário não aparece na pesquisa.

    ![Captura de tela da pesquisa de um novo membro para adicionar a uma equipe e não encontrar nenhuma partida](media/information-barriers-add-members.png)

- **Um novo chat** é solicitado : sempre que um usuário solicita um novo chat com um ou mais outros usuários, o chat é avaliado para garantir que ele não viole as políticas de IB. Se a conversa violar uma política de IB, a conversa não será iniciada.

    Aqui está um exemplo de chat 1:1.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando a comunicação bloqueada no chat 1:1](media/information-barriers-one-one-chat.png)

    Veja um exemplo de chat em grupo.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando o chat em grupo](media/information-barriers-group-chat.png)

- Um usuário é convidado **a** ingressar em uma reunião - Quando um usuário é convidado a ingressar em uma reunião, a política de IB que se aplica ao usuário é avaliada em relação às políticas de IB que se aplicam aos outros membros da equipe. Se houver uma violação, o usuário não terá permissão para ingressar na reunião.

    ![Captura de tela mostrando o usuário bloqueado da reunião](media/information-barriers-meeting.png)

- **Uma tela** é compartilhada entre dois ou mais usuários - Quando um usuário compartilha uma tela com outros usuários, o compartilhamento deve ser avaliado para garantir que ele não viole as políticas de IB de outros usuários. Se uma política de IB for violada, o compartilhamento de tela não será permitido. 
 
    Veja um exemplo de compartilhamento de tela antes da política ser aplicada. 

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando um chat do usuário](media/ib-before-screen-share-policy.png)

    Veja um exemplo de compartilhamento de tela após a aplicação da política. Os ícones de compartilhamento de tela e chamada não estão visíveis.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando o nome do usuário com configurações bloqueadas](media/ib-after-screen-share-policy.png)

- Um usuário faz uma chamada telefônica no **Teams** - Sempre que um usuário inicia uma chamada de voz (via VOIP) para outro usuário ou grupo de usuários, a chamada é avaliada para garantir que ela não viole as políticas de IB de outros membros da equipe. Se houver alguma violação, a chamada de voz será bloqueada.

- **Convidados no Teams** - As políticas de IB também se aplicam aos convidados no Teams. Se os convidados precisam ser descobertos na lista de endereços global da sua organização, consulte Gerenciar o acesso de convidados em Grupos [do Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups) Depois que os convidados são descobertos, você [pode definir políticas de IB.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Como as alterações na política impactam os chats existentes

Quando o administrador da política IB faz alterações em uma política ou quando uma alteração de política é ativada devido a uma alteração no perfil de um usuário (como para uma alteração de emprego), o Serviço de Avaliação da Política de Barreira de Informações pesquisa automaticamente os membros para garantir que sua associação à equipe não viole nenhuma política.

Se houver um chat existente ou outra comunicação entre os usuários e uma nova política for definida ou uma política existente for alterada, o serviço avaliará as comunicações existentes para garantir que as comunicações ainda sejam permitidas. 

- **Chat 1:1** - Se a comunicação entre dois usuários não for mais permitida (devido ao aplicativo a um ou a ambos os usuários de uma política que bloqueia a comunicação), a comunicação posterior será bloqueada. Suas conversas de chat existentes se tornam somente leitura. 

    Veja um exemplo que mostra que o chat está visível.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando que o chat do usuário está disponível](media/ib-before-1-1chat-policy.png)

    Veja um exemplo que mostra que o chat está desabilitado.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando que o chat do usuário está desabilitado](media/ib-after-1-1chat-policy.png)

- Chat em grupo **–** se a comunicação de um usuário para um grupo não for mais permitida (por exemplo, porque um usuário alterou os trabalhos), o usuário, juntamente com os outros usuários cuja participação viola a política, poderá ser removido do chat em grupo, e a comunicação posterior com o grupo não será permitida. O usuário ainda pode ver conversas antigas, mas não poderá ver ou participar de novas conversas com o grupo. Se a política nova ou alterada que impede a comunicação for aplicada a mais de um usuário, os usuários afetados pela política poderão ser removidos do chat em grupo. Eles ainda podem ver conversas antigas.

  Neste exemplo, E ltda foi movido para um departamento diferente dentro da organização e é removido do chat em grupo.

  ![Captura de tela de um chat em grupo do qual um usuário foi removido](media/information-barriers-user-changes-job.png)

  E ltda não pode mais enviar mensagens para o chat em grupo.

  ![Captura de tela de como não conseguir enviar mensagens para o chat em grupo porque o usuário foi removido do grupo](media/information-barriers-user-changes-job-2.png)

- **Equipe** – Todos os usuários que foram removidos do grupo são removidos da equipe e não poderão ver ou participar de conversas novas ou existentes.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Cenário: um usuário em um chat existente é bloqueado

Atualmente, os usuários experimentam os seguintes cenários se uma política de IB bloquear outro usuário:

- **Guia Pessoas** – Um usuário não pode ver usuários bloqueados na **guia** Pessoas.

- **Selador de** Pessoas – Os usuários bloqueados não estarão visíveis no selador de pessoas.

    ![Captura de tela do Teams alertando o usuário de que a política impede a exibição das informações de outro usuário](media/information-barriers-people-picker.png)
    
- **Guia Atividade** - Se um usuário visitar a **guia Atividade** de um usuário bloqueado, nenhuma postagem será exibida. (A **guia Atividade** exibe apenas postagens de canal e não haverá canais comuns entre os dois usuários.)

    Aqui está um exemplo da exibição da guia atividade que está bloqueada.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando a guia atividade que está bloqueada](media/ib-after-activity-tab-policy.png)


- **Organogramas** - Se um usuário acessar um organograma no qual um usuário bloqueado aparece, o usuário bloqueado não aparecerá no organograma. Em vez disso, uma mensagem de erro será exibida.

- **Cartão de** visita – se um usuário participar de uma conversa e o usuário for bloqueado posteriormente, outros usuários verão uma mensagem de erro em vez do cartão de pessoas quando passar o mouse sobre o nome do usuário bloqueado. As ações listadas no cartão (como chamada e chat) não estarão disponíveis.

- **Contatos sugeridos** - Os usuários bloqueados não aparecem na lista de contatos sugeridos (a lista de contatos inicial exibida para novos usuários).

- **Contatos de chat** - Um usuário pode ver usuários bloqueados na lista de contatos de chats, mas os usuários bloqueados serão identificados. A única ação que o usuário pode executar nos usuários bloqueados é excluí-los. O usuário também pode clicar nele para exibir sua conversa passada.

- **Contatos de chamadas** - Um usuário pode ver usuários bloqueados na lista de contatos de chamadas, mas os usuários bloqueados serão identificados. A única ação que o usuário pode executar no bloco de usuários é excluí-los.

    Veja um exemplo de um usuário bloqueado na lista de contatos de chamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando o chat do usuário](media/ib-before-chat-contacts-policy.png)

    Veja um exemplo de como o chat está desabilitado para um usuário na lista de conteúdo de chamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando o usuário bloqueado do chat](media/ib-after-chat-contacts-policy.png)

- **Migração** do Skype para o Teams – Durante uma migração do Skype for Business para o Teams, todos os usuários , mesmo os usuários bloqueados por políticas de IB, serão migrados para o Teams. Esses usuários são tratados conforme descrito acima.

## <a name="teams-policies-and-sharepoint-sites"></a>Políticas do Teams e sites do SharePoint

Quando uma equipe é criada, um site do SharePoint é provisionado e associado ao Microsoft Teams para a experiência de arquivos. As políticas de IB não são apribadas neste site e arquivos do SharePoint por padrão. Para habilitar políticas de IB, o administrador já preencheu um formulário solicitando que as políticas de IB sejam habilitadas no SharePoint e no OneDrive (consulte a seção *Pré-requisitos* em Barreiras de [informações).](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites) Se a política IB estiver compartilhamento no SharePoint e no OneDrive, as políticas de IB funcionarão em sites do SharePoint que são provisionados quando uma equipe é criada com o Microsoft Teams.

Exemplo de políticas **de IB** no site do SharePoint de uma equipe: No Contoso Bank corporation, o usuário 'Sesha@contosobank.onmicrosoft.com' pertence ao segmento de Banco de Investimento e o usuário "Nikita@contosobank.onmicrosoft.com" pertence ao segmento de Consultoria. A política de IB da organização bloqueia a comunicação e a colaboração entre esses dois segmentos.
Quando o usuário Sesha cria uma equipe para o segmento de Banco de Investimentos, a equipe e o site do SharePoint que faz backs it serão acessíveis somente aos usuários do Investment Banking. User Ltda não poderá acessar esse site mesmo que ela tenha o link do site.

Para obter mais informações, [consulte Usar barreiras de informações com o SharePoint.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

## <a name="required-licenses-and-permissions"></a>Licenças e permissões necessárias

Para obter mais informações sobre licenças e permissões, incluindo planos e preços, consulte as diretrizes de licenciamento do [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)para conformidade & segurança.

## <a name="known-issues"></a>Problemas conhecidos
- Os usuários não podem ingressar em reuniões **ad hoc:** se as políticas de IB estão habilitadas, os usuários não têm permissão para ingressar em reuniões se o tamanho da lista de participação da reunião for maior do que os limites de participação na [reunião.](limits-specifications-teams.md) A causa raiz é que as verificações de IB dependem se os usuários podem ser adicionados a uma lista de chats de reunião e somente quando eles podem ser adicionados à lista têm permissão para ingressar na reunião. Um usuário in join a meeting once adds that user to the roster; portanto, para reuniões recorrentes, a lista pode ser preenchida rapidamente. Depois que a lista de participação na reunião atingir [os](limits-specifications-teams.md)limites de participação da reunião, nenhum usuário adicional poderá ser adicionado à reunião. Se a IB estiver habilitada para o locatário e a lista de chats estiver completa para uma reunião, novos usuários (os usuários que ainda não estão na lista) não poderão ingressar na reunião. Mas se a IB não estiver habilitada para o locatário e a lista de chats da reunião estiver completa, novos usuários (os usuários que ainda não estão na lista) poderão ingressar na reunião, embora não vejam a opção de chat na reunião. Uma solução a curto prazo é remover membros inativos da lista de chat da reunião para dar espaço a novos usuários. No entanto, aumentaremos o tamanho das escalações de chat de reunião em uma data posterior.

- **Os usuários não podem** ingressar em reuniões de canal: se as políticas de IB estão habilitadas, os usuários não têm permissão para ingressar em reuniões de canal se não são membros da equipe. A causa raiz é que as verificações de IB dependem se os usuários podem ser adicionados a uma lista de chats de reunião e somente quando eles podem ser adicionados à lista têm permissão para ingressar na reunião. O thread de chat em uma reunião de canal está disponível apenas para membros da Equipe/Canal, e não membros não podem ver ou acessar o thread de chat. Se a IB estiver habilitada para o locatário e um membro que não for da equipe tentar ingressar em uma reunião de canal, esse usuário não poderá ingressar na reunião. No entanto, se  a IB não estiver habilitada para o locatário e um membro que não for da equipe tentar ingressar em uma reunião de canal, o usuário terá permissão para ingressar na reunião, mas não verá a opção de chat na reunião.

## <a name="more-information"></a>Mais informações

- Para saber mais sobre IBs, consulte [Barreiras de informações.](https://docs.microsoft.com/office365/securitycompliance/information-barriers)

- Para configurar políticas de IB, consulte [Definir políticas para barreiras de informações.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Para editar ou remover políticas de IB, consulte [Editar (ou remover) políticas](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)de barreira de informações.

## <a name="availability"></a>Disponibilidade
- O recurso está disponível em nossa nuvem pública; em janeiro de 2021, mos lançado Barreiras de Informações na nuvem GCC.
- O recurso ainda não está disponível nas nuvens GCCH e DOD.
