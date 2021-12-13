---
title: Gerenciamento de parceiros para clientes
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: gerenciamento de parceiros para clientes.
f1keywords: ''
ms.openlocfilehash: 1379fff905275e9bed94f019dcb556e171683178
ms.sourcegitcommit: 4095a1d5e507ac5cb23ed17611c1fbd4b744b23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2021
ms.locfileid: "61420221"
---
# <a name="partner-management-for-customers"></a>Gerenciamento de parceiros para clientes


O gerenciamento de parceiros no serviço Salas do Teams Gerenciado (TRM) permite aos clientes delegar acesso e responsabilidades perfeitamente a uma ou várias organizações parceiras. Os parceiros só podem gerenciar salas atribuídas a eles para gerenciar. 

## <a name="on-boarding-partners"></a>Parceiros de entrada
   Convide parceiros por meio do portal TRM para estabelecer a relação entre sua organização e o locatário da organização parceira. 

### <a name="invitation-to-partner"></a>Convite para parceiro

   Neste método, o parceiro deve fornecer *os UPNs* dos usuários que serão os administradores principais atribuídos a você. 

**Para iniciar o convite** 

1. Faça logoff no portal Salas do Teams gerenciado como administrador mmr.
1. Vá para **Configurações >** **Parceiros** e selecione **Adicionar parceiro.**
1. Insira o nome e o UPN dos administradores principais na primeira linha.
1. Selecione **Adicionar contato** para confirmar.
1. Siga um destes procedimentos:
   - Para adicionar outro usuário, repita a etapa 4.
   - Para excluir um usuário, selecione o ícone de lixeira à direita do usuário.

    > [!NOTE]
    > Não é possível usar grupos ou listas de distribuição, pois o convite está vinculado ao UPN.

1. Selecione **Próximo.**
1. Configure os eventos que exigirão uma aprovação de controle de alteração. Por padrão, todos os controles são definidos como **Aprovação Automática.**

   > [!NOTE]
   > *Somente a aprovação automática está disponível no momento.*
   > 
   >  1.  *Aprovação manual:* Quando o parceiro executa a ação, uma solicitação de aprovação é gerada para que o cliente revise e aprove. A ação não será implementada até que a solicitação seja aprovada.
   >  
   >  1. *Aprovação automática:* Quando o parceiro executa a ação, nenhuma solicitação de aprovação é gerada e a ação é implementada imediatamente.
     
1. Selecione **Próximo.**
1. Atribua salas que o parceiro gerenciará e selecione **Next.**
1. Para continuar, revise os termos e selecione **Eu concordo.**
1. Revise os detalhes do convite.
1. Selecione **Adicionar parceiro** para enviar o convite.

O convite é exclusivo para cada usuário e é independente. O primeiro usuário parceiro que aceitar o convite estabelecerá o link entre o Parceiro e seu locatário. Não há nenhuma associação especial com o usuário que estabelece o link, o que permite a flexibilidade caso o usuário seja reatribuido. Os usuários subsequentes a aceitar serão atribuídos automaticamente à função de administradores primários. Sempre deve haver pelo menos um usuário na função de administrador principal.

Para gerenciar usuários na função de administrador principal, consulte [Multi-tenant Management for Partners](multi-tenant-management-partner.md).


## <a name="off-boarding-partners"></a>Parceiros de off-boarding

**Para remover um parceiro**

1. Faça logon no portal TRM-MTM como administrador mmr.
1. Navegue até **Configurações > Parceiros.**
1. Selecione o parceiro que deseja remover.
1. No painel de detalhes do cliente, selecione **Remover parceiro.**
1. Selecione **Excluir**. 
1. No prompt de confirmação para encerrar a associação entre seu locatário e o cliente, selecione **Excluir**.

## <a name="managing-partner-roles"></a>Gerenciando funções de parceiro

As funções de parceiro permitem que seu parceiro delegar responsabilidades de forma mais granular a funcionários adicionais. O conceito dessas funções é o mesmo descrito no controle de acesso [baseado em função.](microsoft-teams-rooms-premium-rbac.md) É importante observar que as funções de parceiro são distintas de suas funções personalizadas. 

A **função de administrador** principal é a única função criada para cada parceiro que você adicionar. Essa função tem quase todas as permissões para as salas atribuídas a esse parceiro para o serviço TRM (consulte [Tabela 1](#table-1)). Por exemplo, se você tiver salas em todo o mundo e atribuir um parceiro para gerenciar todas as salas dos EUA, o administrador principal só poderá gerenciar e delegar permissões para essas salas. Nesse caso, os administradores principais desse Parceiro não têm visibilidade para salas fora dos EUA. 

### <a name="adding-primary-admins-to-partner"></a>Adicionando administradores primários ao parceiro

Se você já enviou um convite a um parceiro e deseja adicionar mais usuários a esse administrador, você pode adicioná-los à função de administrador do parceiro. Isso envia efetivamente um convite aos usuários adicionados.

**Para adicionar novos usuários a um parceiro existente**

1. Faça logoff no portal TRM-MTM como administrador mmr.
1. Vá para **Configurações > Funções.**
1. Selecione  **Funções de parceiro.** 
1. Selecione a **função de administrador** principal para o nome do parceiro correspondente.
1. No painel de funções, selecione **Atribuições**.
1. Selecione a **atribuição Administradores convidados.** 
1. No painel de atribuição administradores convidados, selecione **Membros**.
1. Selecione **Editar**.
1. Insira o UPN do novo usuário e selecione **Adicionar contato.**
1. Para confirmar as alterações, selecione **Salvar**.

<!--To remove users for an existing partner~~

1. ~~Login to the TRM-MTM portal as a MMR administrator~~
1. ~~Navigate to **Settings > Roles**~~
1. ~~Select the **Partner roles** tab~~
1. ~~Select the **Primary admin** role for the corresponding Partner name~~
1. ~~In the role pane, select the **Assignments** tab~~
1. ~~Select the **Invited admins** assignment~~ 
1. ~~In the Invited admins assignment pane, select the **Members** tab~~
1. ~~Select the **Edit** icon~~
1. ~~Enter the UPN of the new user and select **Add contact**~~
1. ~~Click **Save** to confirm the changes-->




### <a name="table-1"></a>Tabela 1

|Recurso|Permissão|**Administrador mmr**|**Site Lead**|**Site Tech**|**Administrador de parceiros**|
| :- | :- | :- | :- | :- | :- |
|Salas|Exibir| &#10004;|&#10004;|&#10004;|&#10004;|
||Modificar|&#10004;|&#10004;|&#10004;|&#10004;|
||Tecla Redefinir|&#10004;||||
||Chave de download|&#10004;|&#10004;|&#10004;||
||Desemroll|&#10004;|&#10004;|&#10004;||
||Criar |&#10004;|&#10004;|||
|Gerenciamento de grupo|Exibir|&#10004;|&#10004;||&#10004;|
||Modificar|&#10004;|&#10004;|||
||Criar |&#10004;|&#10004;|||
|Atualizar o gerenciamento de anel|Exibir|&#10004;|&#10004;||&#10004;|
||Modificar|&#10004;|&#10004;||&#10004;|
|Relatórios|Exibir|&#10004;|&#10004;||&#10004;|
||Criar incidente do cliente|&#10004;|&#10004;|&#10004;|&#10004;|
|Gerenciamento de Tíquetes|Exibir|&#10004;|&#10004;|&#10004;|&#10004;|
||Atualizar|&#10004;|&#10004;|&#10004;|&#10004;|
|MMR Configurações|Exibir|&#10004;||||
||Modificar|&#10004;||||
|Gerenciamento de função|Exibir |&#10004;|||&#10004;|
||Modificar|&#10004;|||&#10004;|





## <a name="security"></a>Segurança

Como cliente final, você mantém o controle sobre o acesso aos seus dados e pode remover completamente um parceiro a qualquer momento. 

Com o recurso de acesso delegado, um parceiro não ganha outros privilégios fora do portal de serviço TRM. No entanto, quaisquer dados presentes no serviço TRM derivados de outros produtos Microsoft são considerados dados no serviço TRM. Como exemplo, enquanto os relatórios de qualidade de chamada são derivados Teams dados de qualidade de chamada, todos os dados no portal TRM estão no escopo de permissão. 

Nenhuma permissão é concedida ao AAD ou ao Centro de administração Teams ou qualquer outro produto da Microsoft. Além disso, os parceiros não têm acesso para exibir ou modificar salas não definidas no escopo do convite. 

Os dados residem no locatário do cliente e não são copiados para o locatário do parceiro. 

O portal MTM usa a autenticação do Azure AD para validar as credenciais de logon do parceiro. Observe que, neste momento, as políticas de autenticação do cliente não se aplicam ao parceiro. Por exemplo, se o cliente tiver uma política de autenticação multifaionária, ela não será traduzida para o parceiro. 

Para puxar logs na atividade do parceiro, consulte [Auditing](multi-tenant-auditing.md). 

> [!NOTE]
> AAD auditoria e auditoria do O365 não capturam logs do portal TRM. 
