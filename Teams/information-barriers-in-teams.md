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
description: Este artigo explica o que são barreiras de informações no Microsoft Teams e como eles podem afetar o Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 87e282673d1fabec5b751b0a3722515585e5e404
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50837008"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barreiras de informações no Microsoft Teams

As barreiras de informações (IBs) são políticas que um administrador pode configurar para impedir que indivíduos ou grupos se comuniquem uns com os outros. Os EIs serão úteis se, por exemplo, um departamento estiver manipulando informações que não devem ser compartilhadas com outros departamentos. Os EIs também são úteis quando um grupo precisa ser isolado ou impedido de se comunicar com qualquer pessoa fora desse grupo.

> [!NOTE]
> - Grupos de barreira de informações (IB) não podem ser criados entre locatários.
> - O uso de bots, aplicativos do Azure Active Directory (Azure AD) e algumas APIs para adicionar usuários não é suportado na versão 1.
> - Os canais privados são compatíveis com as políticas de IB que você configura.
> - Novo: para obter informações sobre o suporte a barreiras para sites do SharePoint conectados ao Teams, consulte [Segments associated with Microsoft Teams sites](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

As políticas de IB também impedem pesquisa e descoberta. Se você tentar se comunicar com alguém com quem não deve se comunicar, não encontrará esse usuário no selador de pessoas.

## <a name="background"></a>Plano de fundo

O principal fator de IBs vem do setor de serviços financeiros. A Autoridade Regulatória do Setor Financeiro[(FINRA)]( https://www.finra.org)revisa IBs e conflitos de interesse em empresas membro e fornece orientações sobre como gerenciar esses conflitos (FINRA 2241, Aviso Regulatório de Pesquisa de [Dívidas 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).


No entanto, desde a introdução de EIs, muitas outras áreas os descobriram úteis. Outros cenários comuns incluem:

- Educação: os alunos de uma escola não podem procurar detalhes de contato para alunos de outras escolas.

- Legal: manter a confidencialidade dos dados obtidos pelo advogado de um cliente e impedi-los de serem acessados por um advogado para a mesma empresa que representa um cliente diferente.

- Governo: o acesso e o controle de informações são limitados entre departamentos e grupos.

- Serviços profissionais: um grupo de pessoas em uma empresa só é capaz de conversar com um cliente ou um cliente específico por meio do acesso de convidados durante um envolvimento do cliente.

Por exemplo, Enrico pertence ao segmento Bancário e Pradeep pertence ao segmento consultor financeiro. Enrico e Pradeep não podem se comunicar uns com os outros porque a política de IB da organização bloqueia a comunicação e a colaboração entre esses dois segmentos. No entanto, Enrico e Pradeep podem se comunicar com Lee no RH.

![Exemplo mostrando barreiras de informações que impedem a comunicação entre segmentos](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quando usar barreiras de informações

Talvez você queira usar EIs em situações como estas:

- Uma equipe deve ser impedida de se comunicar ou compartilhar dados com uma outra equipe específica.
- Uma equipe não deve se comunicar ou compartilhar dados com qualquer pessoa fora da equipe.

O Serviço de Avaliação da Política de Barreira de Informações determina se uma comunicação está em conformidade com as políticas de IB.

## <a name="managing-information-barrier-policies"></a>Gerenciar políticas de barreira de informações

As políticas de IB são gerenciadas no Centro de Conformidade do Microsoft 365 (SCC) usando cmdlets do PowerShell. Para obter mais informações, consulte [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Antes de configurar ou definir políticas, você deve habilitar a pesquisa de diretório com escopo no Microsoft Teams. Aguarde pelo menos algumas horas após a habilitação da pesquisa de diretório com escopo antes de configurar ou definir políticas para barreiras de informações. Para obter mais informações, consulte [Definir políticas de barreira de informações](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Função de administrador de barreiras de informações

A função de Gerenciamento de Conformidade do IB é responsável pelo gerenciamento de políticas de IB. Para obter mais informações sobre essa função, consulte Permissões no Centro de Conformidade do [Microsoft 365.](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Gatilhos de barreira de informações

As políticas de IB são ativadas quando os seguintes eventos do Teams ocorrem:

- **Membros são adicionados a uma** equipe - Sempre que você adiciona um usuário a uma equipe, a política do usuário deve ser avaliada em relação às políticas de IB de outros membros da equipe. Depois que o usuário for adicionado com êxito, o usuário poderá executar todas as funções na equipe sem mais verificações. Se a política do usuário os impede de serem adicionados à equipe, o usuário não aparece na pesquisa.

    ![Captura de tela da pesquisa de um novo membro para adicionar a uma equipe e não encontrar nenhuma corresponde](media/information-barriers-add-members.png)

- **Um novo chat** é solicitado - Sempre que um usuário solicita um novo chat com um ou mais usuários, o chat é avaliado para garantir que ele não está violando nenhuma política de IB. Se a conversa violar uma política de IB, a conversa não será iniciada.

    Veja um exemplo de um chat 1:1.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando a comunicação bloqueada no chat 1:1](media/information-barriers-one-one-chat.png)

    Veja um exemplo de chat em grupo.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando chat em grupo](media/information-barriers-group-chat.png)

- Um usuário é convidado **a** participar de uma reunião - Quando um usuário é convidado a participar de uma reunião, a política de IB que se aplica ao usuário é avaliada em relação às políticas de IB que se aplicam aos outros membros da equipe. Se houver uma violação, o usuário não poderá participar da reunião.

    ![Captura de tela mostrando o usuário bloqueado da reunião](media/information-barriers-meeting.png)

- **Uma tela é** compartilhada entre dois ou mais usuários - Quando um usuário compartilha uma tela com outros usuários, o compartilhamento deve ser avaliado para garantir que ele não viole as políticas de IB de outros usuários. Se uma política de IB for violada, o compartilhamento de tela não será permitido. 
 
    Veja um exemplo de compartilhamento de tela antes da aplicação da política. 

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando um chat do usuário](media/ib-before-screen-share-policy.png)

    Veja um exemplo de compartilhamento de tela após a aplicação da política. Os ícones de compartilhamento de tela e chamada não estão visíveis.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando a char do usuário com configurações bloqueadas](media/ib-after-screen-share-policy.png)

- Um usuário faz uma chamada telefônica no **Teams** - Sempre que um usuário inicia uma chamada de voz (via VOIP) para outro usuário ou grupo de usuários, a chamada é avaliada para garantir que ela não viole as políticas de IB de outros membros da equipe. Se houver alguma violação, a chamada de voz será bloqueada.

- **Convidados no Teams** - As políticas de IB também se aplicam aos convidados no Teams. Se os convidados precisam ser descobertos na lista de endereços global da sua organização, consulte Gerenciar o acesso de convidados [nos Grupos do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups). Depois que os convidados são descobertos, você pode [definir políticas de IB.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Como as alterações de política impactam chats existentes

Quando o administrador de política de IB faz alterações em uma política ou quando uma alteração de política é ativada devido a uma alteração no perfil de um usuário (como para uma alteração de trabalho), o Serviço de Avaliação da Política de Barreira de Informações pesquisa automaticamente os membros para garantir que sua associação à equipe não viole nenhuma política.

Se houver um chat ou outra comunicação existente entre os usuários e uma nova política for definida ou uma política existente for alterada, o serviço avaliará as comunicações existentes para garantir que as comunicações ainda sejam permitidas. 

- **Chat 1:1** - Se a comunicação entre dois usuários não for mais permitida (por causa do aplicativo para um ou ambos os usuários de uma política que bloqueia a comunicação), a comunicação posterior será bloqueada. Suas conversas de chat existentes se tornam somente leitura. 

    Veja um exemplo que mostra que o chat está visível.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando o chat do usuário está disponível](media/ib-before-1-1chat-policy.png)

    Veja um exemplo que mostra que o chat está desabilitado.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando que o chat do usuário está desabilitado](media/ib-after-1-1chat-policy.png)

- Chat em grupo **-** Se a comunicação de um usuário para um grupo não for mais permitida (por exemplo, porque um usuário mudou de trabalho), o usuário, juntamente com os outros usuários cuja participação viola a política, poderá ser removido do chat em grupo, e a comunicação posterior com o grupo não será permitida. O usuário ainda pode ver conversas antigas, mas não poderá ver ou participar de novas conversas com o grupo. Se a política nova ou alterada que impede a comunicação for aplicada a mais de um usuário, os usuários afetados pela política poderão ser removidos do chat de grupo. Eles ainda podem ver conversas antigas.

  Neste exemplo, Enrico foi movido para um departamento diferente dentro da organização e é removido do chat de grupo.

  ![Captura de tela de um chat de grupo do qual um usuário foi removido](media/information-barriers-user-changes-job.png)

  Enrico não pode mais enviar mensagens para o chat de grupo.

  ![Captura de tela de não poder enviar mensagens para chat em grupo porque o usuário foi removido do grupo](media/information-barriers-user-changes-job-2.png)

- **Equipe** - Todos os usuários que foram removidos do grupo são removidos da equipe e não poderão ver ou participar de conversas existentes ou novas.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Cenário: um usuário em um chat existente é bloqueado

Atualmente, os usuários experimentam os seguintes cenários se uma política de IB bloqueia outro usuário:

- **Guia Pessoas** - Um usuário não pode ver usuários bloqueados na **guia** Pessoas.

- **Selador de** Pessoas - Os usuários bloqueados não estarão visíveis no selador de pessoas.

    ![Captura de tela do Teams alertando o usuário de que a política impede a exibição das informações de outro usuário](media/information-barriers-people-picker.png)
    
- **Guia Atividade** - Se um usuário visitar a guia **Atividade** de um usuário bloqueado, nenhuma postagem será exibida. (A **guia Atividade** exibe apenas postagens de canal e não haveria canais comuns entre os dois usuários.)

    Aqui está um exemplo do exibição de guia atividade bloqueado.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando a guia atividade bloqueada](media/ib-after-activity-tab-policy.png)


- **Gráficos de** organização - Se um usuário acessar um gráfico de organização no qual um usuário bloqueado aparece, o usuário bloqueado não aparecerá no gráfico da organização. Em vez disso, uma mensagem de erro aparecerá.

- **Cartão de** pessoas - Se um usuário participar de uma conversa e o usuário for bloqueado posteriormente, outros usuários verão uma mensagem de erro em vez do cartão de pessoas quando passar o mouse sobre o nome do usuário bloqueado. As ações listadas no cartão (como chamada e chat) não estarão disponíveis.

- **Contatos sugeridos** - Os usuários bloqueados não aparecem na lista de contatos sugeridos (a lista de contatos inicial que aparece para novos usuários).

- **Contatos de chat** - Um usuário pode ver usuários bloqueados na lista de contatos de chats, mas os usuários bloqueados serão identificados. A única ação que o usuário pode executar nos usuários bloqueados é excluí-los. O usuário também pode clicar neles para exibir sua conversa passada.

- **Contatos de chamadas** - Um usuário pode ver usuários bloqueados na lista de contatos de chamadas, mas os usuários bloqueados serão identificados. A única ação que o usuário pode executar no bloco de usuários é excluí-los.

    Veja um exemplo de um usuário bloqueado na lista de contatos de chamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando o chat do usuário](media/ib-before-chat-contacts-policy.png)

    Veja um exemplo do chat que está sendo desabilitado para um usuário na lista de conteúdos de chamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de tela mostrando o usuário bloqueado do chat](media/ib-after-chat-contacts-policy.png)

- **Migração** do Skype para o Teams - Durante uma migração do Skype for Business para o Teams, todos os usuários, mesmo os usuários bloqueados por políticas de IB, serão migrados para o Teams. Esses usuários são tratados conforme descrito acima.

## <a name="teams-policies-and-sharepoint-sites"></a>Políticas do Teams e sites do SharePoint

Quando uma equipe é criada, um site do SharePoint é provisionado e associado ao Microsoft Teams para a experiência de arquivos. As políticas de IB não são aduzidas neste site e arquivos do SharePoint por padrão. Para habilitar políticas de IB, o administrador já preencheu um formulário, solicitando que as políticas de IB sejam habilitadas no SharePoint e no OneDrive (consulte a seção *Pré-requisitos* em [Barreiras](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)de informações ). Se a política de IB estiver ativas no SharePoint e no OneDrive, as políticas de IB funcionarão em sites do SharePoint provisionados quando uma equipe for criada com o Microsoft Teams.

Exemplo de políticas **de IB** no site do SharePoint de uma equipe : na empresa do Banco Contoso, o usuário 'Sesha@contosobank.onmicrosoft.com' pertence ao segmento de Banco de Investimentos e o usuário 'Nikita@contosobank.onmicrosoft.com' pertence ao segmento de Consultoria. A política de IB da organização bloqueia a comunicação e a colaboração entre esses dois segmentos.
Quando o usuário Sesha cria uma equipe para o segmento de Banco de Investimentos, a equipe e o site do SharePoint que o ressarmam estarão acessíveis somente aos usuários do Banco de Investimento. A usuária Nikita não poderá acessar esse site mesmo que ela tenha o link do site.

Para obter mais informações, [consulte Use information barriers with SharePoint](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

## <a name="required-licenses-and-permissions"></a>Licenças e permissões necessárias

Para obter mais informações sobre licenças e permissões, incluindo planos e preços, consulte Diretrizes de licenciamento do [Microsoft 365 para](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)conformidade & segurança.

## <a name="known-issues"></a>Problemas conhecidos
- Os usuários não podem ingressar em reuniões **ad hoc**: se as políticas de IB estão habilitadas, os usuários não podem participar de reuniões se o tamanho da lista de reuniões for maior do que os limites de participação da [reunião.](limits-specifications-teams.md) A causa raiz é que as verificações de IB dependem se os usuários podem ser adicionados a uma lista de chat de reunião e somente quando eles podem ser adicionados à lista têm permissão para ingressar na reunião. Um usuário que entra em uma reunião uma vez adiciona esse usuário à lista; portanto, para reuniões recorrentes, a lista pode ser preenchida rapidamente. Depois que a lista de chat atingir [os](limits-specifications-teams.md)limites de participação da reunião, nenhum usuário adicional poderá ser adicionado à reunião. Se a IB estiver habilitada para o locatário e a lista de chat estiver cheia para uma reunião, novos usuários (os usuários que ainda não estão na lista) não poderão participar da reunião. Porém, se a IB não estiver habilitada para o locatário e a lista de chat de reunião estiver cheia, novos usuários (os usuários que ainda não estão na lista) poderão ingressar na reunião, embora não vejam a opção de chat na reunião. Uma solução de curto prazo é remover membros inativos da lista de chat de reunião para dar espaço a novos usuários. No entanto, aumentaremos o tamanho das escalações de chat de reunião em uma data posterior.

- **Os usuários não podem participar** de reuniões de canal: se as políticas de IB estão habilitadas, os usuários não podem participar de reuniões de canal se não são membros da equipe. A causa raiz é que as verificações de IB dependem se os usuários podem ser adicionados a uma lista de chat de reunião e somente quando eles podem ser adicionados à lista têm permissão para ingressar na reunião. O thread de chat em uma reunião de canal está disponível apenas para membros da equipe/canal, e os não membros não podem ver ou acessar o thread de chat. Se a IB estiver habilitada para o locatário e um membro não da equipe tentar ingressar em uma reunião de canal, esse usuário não poderá ingressar na reunião. No entanto, se  o IB não estiver habilitado para o locatário e um membro não da equipe tentar ingressar em uma reunião de canal, o usuário poderá ingressar na reunião, mas não verá a opção de chat na reunião.

- Proprietários de equipe não são removidos **:** se uma nova política de IB for aplicada que resulta em dois ou mais segmentos conflitantes presentes em um canal do Teams, os segmentos com proprietários de equipe receberão preferência maior e outros usuários de segmento serão removidos. Além disso, no momento, os proprietários da equipe não estão sendo removidos, mesmo que eles estão em conflito com outros proprietários/usuários. Os administradores de locatários e outros proprietários de canal terão que remover os proprietários conflitantes manualmente. Estamos trabalhando em uma correção.

## <a name="more-information"></a>Mais informações

- Para saber mais sobre IBs, consulte [Barreiras de informações.](https://docs.microsoft.com/office365/securitycompliance/information-barriers)

- Para configurar políticas de IB, consulte [Define policies for information barriers](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

- Para editar ou remover políticas de IB, consulte [Editar (ou remover)](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)políticas de barreira de informações.

## <a name="availability"></a>Disponibilidade
- O recurso está disponível em nossa nuvem pública; em janeiro de 2021, nós rolamos Barreiras de Informações na nuvem GCC.
- O recurso ainda não está disponível nas nuvens GCCH e DOD.
