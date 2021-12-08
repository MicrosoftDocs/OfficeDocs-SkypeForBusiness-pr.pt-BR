---
title: Gerenciamento de clientes de vários locatários para parceiros
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
description: Gerenciamento de clientes de locatário mult para parceiros.
f1keywords: ''
ms.openlocfilehash: edafdf182e0d27ec5c5524e9411b80de866d7f02
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331205"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Gerenciamento de clientes de vários locatários para parceiros

O gerenciamento de vários locatários (MTM) no serviço Salas do Teams Managed (TRM) ajuda as organizações parceiras a gerenciar vários clientes em um só lugar, com suas próprias credenciais de domínio. Os usuários parceiros verão apenas as salas de clientes atribuídas a eles para gerenciar. É possível aplicar funções personalizadas para cada cliente no locatário MTM, dando às organizações parceiras controle granular de permissões aos recursos do cliente. 

O portal MTM pode ser acessado por meio deste [link](https://partner.rooms.microsoft.com/).

> [!Note] 
> As organizações parceiras não podem gerenciar suas próprias salas por meio do portal MTM. Essas salas podem ser gerenciadas no [portal TRM](https://portal.rooms.microsoft.com/). 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Pré-requisitos para gerenciar seus clientes por meio da experiência MTM

Para obter acesso ao portal MTM, sua organização deve estar integrada como Um Parceiro de Elite para o serviço TRM. Para se tornar um parceiro elite de contato askelite@microsoft.com.


## <a name="on-boarding-customers"></a>Clientes ao entrar

Para gerenciar clientes por meio do portal TRM-MTM, uma relação deve ser estabelecida entre o locatário da organização do parceiro e o cliente por meio de um convite enviado pelo cliente. 

### <a name="invitation-from-the-customer"></a>Convite do cliente

O parceiro fornece os nomes de princípios do usuário (UPNs) dos usuários que serão administradores principais atribuídos ao cliente. Somente os usuários identificados no convite podem ver e aceitar o convite quando fizerem logoff no portal TRM-MTM. 

> [!Note]
> Mesmo que você tenha privilégios elevados, como Administrador Global, não verá o convite, a menos que seja explicitamente adicionado. 

Os detalhes sobre o convite do cliente são descritos no [gerenciamento de vários locatários para clientes.](multi-tenant-management-customer.md)

**Para aceitar um convite pendente**

1. Faça logoff no portal TRM-MTM como um dos usuários no convite.
1. Vá para **Clientes**.
1. Selecione o convite mostrando com um status de "Pendente".
1. Revise os detalhes do convite.
1. Selecione **Aceitar** para estabelecer o relacionamento parceiro-cliente.

   Selecionar **Negar** exclui o convite para o usuário negar. O convite ainda está disponível para outros usuários que ainda não atuaram.

   > [!Note]
   > O convite é exclusivo e independente para cada usuário. O primeiro usuário a aceitar estabelece o link entre o parceiro e o locatário do cliente. Não há associação permanente com o usuário que estabelece o link. Os usuários subsequentes que aceitam o convite são adicionados como administradores primários.

   > [!Note]
   > *Se um usuário parceiro negar acidentalmente o convite, é melhor ter outro usuário simplesmente adicioná-lo à função Partner (ou qualquer outra função RBAC) para esse cliente.* 

Depois de aceitar o convite, o usuário é adicionado automaticamente como administrador principal para o locatário desse cliente. 

Para revisar a configuração desse locatário, selecione o cliente na **lista Clientes.**


## <a name="off-boarding-customers"></a>Clientes de off-boarding

Para fazer a retirada de um cliente, você deve removê-los da lista Clientes.

**Para remover um cliente** 

1. Faça logon no portal TRM-MTM como administrador principal do cliente que você deseja remover.
1. Vá para **Clientes**.
1. Selecione o cliente que deseja remover.
1. No painel de detalhes do cliente, selecione **Remover cliente**.
1. Selecione **Excluir** no prompt de confirmação para encerrar a associação entre seu locatário e o cliente.


## <a name="managing-partner-roles"></a>Gerenciando funções de parceiro

As funções de parceiro permitem a delegação de responsabilidades para funcionários adicionais. O conceito dessas funções é o mesmo descrito no controle de acesso baseado em [função,](microsoft-teams-rooms-premium-rbac.md)mas no contexto de cada cliente. Além disso, é importante observar que as funções de parceiro são distintas das funções do cliente. As funções de parceiro podem ser excluídas pelo cliente. 

A função de administradores **primários** é a única função criada para cada cliente local e tem quase todas as permissões — no contexto do cliente — para o serviço TRM (consulte a tabela 1). As permissões de função partner** só se estendem até as salas designadas pelo cliente. Por exemplo, se o cCustomer for uma organização global e atribuir o Parceiro para gerenciar todas as salas dos EUA, o administrador principal só poderá gerenciar e delegar permissões para essas salas. O Parceiro não tem visibilidade para outras salas que o Cliente pode ter em outros países. 

> [!Important]
> Sempre deve haver pelo menos um usuário na **função Administradores primários.**

**Para gerenciar usuários na **função Parceiro** para um cliente**

1. Vá para **Configurações > Funções**. 
1. Selecione o cliente na listada para a qual você deseja editar a função de parceiro.
1. Selecione a **função de administradores primários** na lista.
1. Selecione **Atribuições.**
1. Na lista, selecione **Administradores Convidados.**
1. Selecione **Membros.**
1. Clique em Selecionar **Editar.** 
1. Pesquise o usuário ou grupo de segurança que deseja adicionar na barra de pesquisa.
1. Selecione o usuário ou grupo .
1. Clique em Selecionar **Salvar** para confirmar as alterações.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Gerenciando funções de parceiro personalizadas para um cliente

Como parceiro, você pode criar funções personalizadas para atender aos seus requisitos operacionais. Por exemplo, você pode criar uma função de help desk que só deve ter permissões de gerenciamento de incidentes. 

**Para gerenciar funções**

1. Vá para **Configurações > Funções**. 
1. Selecione o cliente no drop-down para o qual você deseja editar a função de parceiro.
1. Criar uma [função personalizada](microsoft-teams-rooms-premium-rbac.md#built-in-roles).




|Recurso|Permissão|**Administrador mmr**|**Site Lead**|**Site Tech**|**Administradores primários**|
| :- | :- | :- | :- | :- | :- |
|Salas|Exibir|||||
||Modificar|||||
||Tecla Redefinir|||||
||Chave de download|||||
||Desemroll|||||
|Gerenciamento de grupo|Criar |||||
||Exibir|||||
||Modificar|||||
|Atualizar o gerenciamento de anel|Criar |||||
||Exibir|||||
||Modificar|||||
|Relatórios|Exibir|||||
|Gerenciamento de tíquetes|Criar incidente do cliente|||||
||Exibir|||||
||Atualizar|||||
|MMR Configurações|Exibir|||||
||Modificar|||||
|Gerenciamento de função|Exibir |||||
||Modificar|||||

> [!Note]
> Um usuário atribuído como administrador primário do Cliente A tem permissões completas no serviço TRM apenas para esse cliente. As permissões do usuário no Cliente A não têm influência em outros clientes.

## <a name="security"></a>Segurança

Os clientes finais retêm o controle sobre o acesso a seus dados e podem remover completamente um parceiro ou funções específicas a qualquer momento.

Com o recurso de acesso delegado, um parceiro não ganha outros privilégios fora do portal de serviço TRM. Por exemplo, usando esse recurso para convidar um parceiro para gerenciar salas no serviço TRM, nenhuma permissão é concedida ao AAD, ao Centro de Administração Teams ou a qualquer outro produto microsoft. Além disso, os parceiros não têm acesso para exibir ou modificar salas não definidas no escopo do convite.

Depois que a relação parceiro-cliente for estabelecida , conforme descrito no "Integrando clientes" deste documento, o parceiro poderá exibir dados de sala no serviço TRM. Isso inclui todos os dados presentes no serviço TRM, mas derivados de outros produtos da Microsoft. Por exemplo, os relatórios de qualidade de chamada no portal TRM são derivados Teams dados de qualidade de chamada.

Os dados residem no locatário do cliente e não são copiados para o locatário do parceiro. 

O portal MTM usa AAD autenticação para validar as credenciais de logon do parceiro. É importante observar que, neste momento, as políticas de autenticação do cliente não se aplicarão ao parceiro. Por exemplo, se o cliente tiver uma política de autenticação multifaionária, ela não será traduzida para o parceiro.

O cliente pode puxar logs de auditoria para o serviço TRM, que inclui a atividade do parceiro. Consulte [Log de auditoria no serviço Salas do Teams Gerenciado.](multi-tenant-auditing.md)

> [!Note]
> AAD auditoria e a auditoria do O365 não captura logs do portal TRM.

## <a name="navigating-the-mtm-portal"></a>Navegando no portal MTM

O portal MTM tem dois modelos interativos para navegar entre dados do cliente:

- Os visualizações agregadas foram dados de todos os clientes consolidados em uma única lista e podem ser filtrados.

  > [!Note]
  > Esse modo de exibição só é suportado na página **Incidentes** quando **a exibição Habilitar todos os tíquetes** é ativada.

  ![Figura 1](../media/multi-tenant-management-partner-001.png)

 - Alternamento de locatários onde apenas os dados do **Cliente** selecionado na listada são exibidos.
