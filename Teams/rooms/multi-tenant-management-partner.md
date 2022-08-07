---
title: Gerenciamento de clientes multilocatário para parceiros
author: donnah007
ms.author: v-donnahill
ms.date: 07/25/2022
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Gerenciamento de clientes multilocatário para parceiros.
f1keywords: ''
ms.openlocfilehash: 37ba5cfc12229685bbe4ac8cf188301e9fa7b1f7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269097"
---
# <a name="multi-tenant-customer-management-for-partners"></a>Gerenciamento de clientes multilocatário para parceiros

O MTM (gerenciamento multilocatário) no serviço Salas do Teams gerenciado (TRM) ajuda as organizações parceiras a gerenciar vários clientes em um só lugar, com suas próprias credenciais de domínio. Os usuários parceiros só verão as salas do cliente que são atribuídas para gerenciar. É possível aplicar funções personalizadas para cada cliente no locatário MTM, dando às organizações parceiras controle granular de permissões aos recursos do cliente. 

O portal do MTM pode ser acessado por meio deste [link](https://partner.rooms.microsoft.com/).

> [!Note] 
> As organizações parceiras não podem gerenciar suas próprias salas por meio do portal MTM. Essas salas podem ser gerenciadas no [portal do TRM](https://portal.rooms.microsoft.com/). 

## <a name="pre-requisites-for-managing-your-customers-through-the-mtm-experience"></a>Pré-requisitos para gerenciar seus clientes por meio da experiência MTM

Para obter acesso ao portal MTM, sua organização deve ser integrada como um Parceiro elite para o serviço TRM. Para se tornar um parceiro elite contato askelite@microsoft.com.

## <a name="on-boarding-customers"></a>Clientes de integração

Para gerenciar clientes por meio do portal TRM-MTM, é necessário estabelecer uma relação entre o locatário da organização parceira e o cliente por meio de um convite enviado pelo cliente. 

## <a name="tenant-managers"></a>Gerenciadores de locatários

Essa função interna só é configurável no portal TRM-MTM. Essa função permite atribuir um grupo de usuários que aceitam convites, mas não estão envolvidos com o gerenciamento de salas de clientes. É recomendável configurar a função. Caso contrário, somente os usuários com a função Administrador de Serviços Gerenciados em seu locatário poderão aceitar convites.

**Para configurar gerenciadores de locatários**
 
1.  Faça logon no portal TRM-MTM como administrador global ou administrador de Serviço Gerenciado.
2.  Vá para gerenciadores de locatários.
3.  Selecione **Adicionar gerenciadores de locatários**.
4.  No painel de detalhes, pesquise os usuários ou grupos de segurança.
5.  Selecione o usuário ou grupo.
6.  Selecione **Adicionar**.

### <a name="invitation-from-the-customer"></a>Convite do cliente

O parceiro deve fornecer o nome de domínio aos clientes. Somente as funções administrador global, administrador de serviços gerenciados e gerenciadores de locatários podem ver e aceitar o convite quando fizerem logon no portal TRM-MTM. 

> [!Note]
> Embora essas funções possam ver convites e metadados de locatário de alto nível, você não verá os dados do cliente até receber uma função com esse cliente.

Os detalhes sobre o convite do cliente são descritos no [gerenciamento multilocatário para clientes](multi-tenant-management-customer.md).

**Para aceitar um convite pendente**

1. Faça logon no portal TRM-MTM como administrador global, administrador de Serviço Gerenciado ou Gerenciador de Locatários.
1. Vá para **Locatários**.
1. Selecione o convite exibido com o status "Pendente".
1. Examine os detalhes do convite.
1. Atribua usuários que serão os principais administradores desse cliente.
1. Selecione **Aceitar** para estabelecer a relação parceiro-cliente.

   Selecionar **Negar** exclui o convite.

   > [!Note]
   > Não há nenhuma associação permanente com o usuário que aceita o convite.

   > [!Note]
   > *Se o convite for negado acidentalmente, o cliente deverá criar um novo convite.* 

**Para examinar a configuração ou adicionar mais administradores primários para um locatário**

1. Selecione o cliente na lista **Locatários** .
1. No painel de detalhes, selecione **Administradores primários**.
1. Pesquise o usuário ou grupo.
1. Selecione **Adicionar** para confirmar a seleção.

## <a name="off-boarding-customers"></a>Clientes fora de integração

Para remover um cliente, você deve removê-lo da lista **locatários** .

**Para remover um cliente** 

1. Faça logon no portal TRM-MTM como administrador primário do cliente que você deseja remover.
1. Vá para **Locatários**.
1. Selecione o cliente que você deseja remover.
1. No painel de detalhes do cliente, selecione **Remover cliente**.
1. Selecione **Excluir** no prompt de confirmação para encerrar a associação entre você e o locatário do cliente.

## <a name="managing-partner-roles"></a>Gerenciando funções de parceiro

As funções de parceiro permitem a delegação de responsabilidades para funcionários adicionais. O conceito dessas funções é o mesmo descrito no controle de acesso baseado em [função](microsoft-teams-rooms-premium-rbac.md), mas no contexto de cada cliente. Além disso, é importante observar que as funções de parceiro são distintas das funções do cliente. As funções de parceiro podem ser excluídas pelo cliente. 

A função administradores **primários** é a única função interna para cada cliente integrado e tem quase todas as permissões , no contexto do cliente, para o serviço TRM (consulte a tabela 1). As permissões de função de parceiro** só se estendem até as salas designadas pelo cliente. Por exemplo, se o cliente for uma organização global e atribuir o Parceiro para gerenciar todas as salas dos EUA, o administrador principal só poderá gerenciar e delegar permissões para essas salas. O Parceiro não tem visibilidade para outras salas que o Cliente pode ter em outros países. 

**Para gerenciar usuários na função **parceiro** de um cliente**

1. Vá para **Configurações > Funções**. 
1. Selecione o cliente na lista suspensa para a qual você deseja editar a função de parceiro.
1. Selecione **a função interna de** administradores primários na lista.
1. Selecione **Atribuições.**
1. Na lista, selecione **Administradores Atribuídos.**
1. Selecione **Membros.**
1. Selecione **Editar.** 
1. Pesquise o usuário ou grupo de segurança que você deseja adicionar na barra de pesquisa.
1. Selecione o usuário ou grupo.
1. Selecione **Salvar** para confirmar as alterações.

### <a name="managing-custom-partner-roles-for-a-customer"></a>Gerenciando funções de parceiro personalizadas para um cliente

Como parceiro, você pode criar funções personalizadas para atender aos seus requisitos operacionais. Por exemplo, você pode criar uma função de suporte ajuda que só deve ter permissões de gerenciamento de incidentes. 

**Para gerenciar funções**

1. Vá para **Configurações > Funções**. 
1. Selecione o cliente no menu suspenso para o qual você deseja editar a função de parceiro.
1. Crie uma [função personalizada](microsoft-teams-rooms-premium-rbac.md#built-in-roles).




|Recurso|Permissão|**MmR Administração**|**Cliente potencial do site**|**Site Tech**|**Administradores primários**|
| :- | :- | :- | :- | :- | :- |
|Quartos|Exibir| &#10004;|&#10004;|&#10004;|&#10004;|
||Modificar|&#10004;|&#10004;|&#10004;|&#10004;|
||Redefinir chave|&#10004;||||
||Chave de download|&#10004;|&#10004;|&#10004;||
||Cancelar registro|&#10004;|&#10004;|&#10004;||
||Criar |&#10004;|&#10004;|||
|Gerenciamento de grupo|Exibir|&#10004;|&#10004;||&#10004;|
||Modificar|&#10004;|&#10004;|||
||Criar |&#10004;|&#10004;|||
|Gerenciamento de anel de atualização|Exibir|&#10004;|&#10004;||&#10004;|
||Modificar|&#10004;|&#10004;||&#10004;|
|Relatórios|Exibir|&#10004;|&#10004;||&#10004;|
||Criar incidente de cliente|&#10004;|&#10004;|&#10004;|&#10004;|
|Gerenciamento de tíquetes|Exibir|&#10004;|&#10004;|&#10004;|&#10004;|
||Atualizar|&#10004;|&#10004;|&#10004;|&#10004;|
|Configurações de MMR|Exibir|&#10004;||||
||Modificar|&#10004;||||
|Gerenciamento de funções|Exibir |&#10004;|||&#10004;|
||Modificar|&#10004;|||&#10004;|

> [!Note]
> Um usuário atribuído como administrador primário do Cliente A tem permissões completas no serviço TRM somente para esse cliente. As permissões do usuário no Cliente A não têm influência sobre outros clientes.

## <a name="security"></a>Segurança

Os clientes finais mantêm o controle sobre o acesso aos dados e podem remover completamente um parceiro ou funções específicas a qualquer momento.

Com o recurso de acesso delegado, um parceiro não obtém nenhum outro privilégio fora do portal do serviço TRM. Por exemplo, usando esse recurso para convidar um parceiro para gerenciar salas no serviço TRM, nenhuma permissão é concedida ao AAD, ao Teams Administração Center ou a qualquer outro produto da Microsoft. Além disso, os parceiros não têm acesso para exibir ou modificar salas não definidas no escopo do convite.

Depois que o parceiro – relacionamento com o cliente for estabelecido – conforme descrito no documento "Integração de clientes" – o parceiro poderá exibir dados de sala no serviço TRM. Isso inclui todos os dados presentes no serviço TRM, mas derivados de outros produtos da Microsoft. Por exemplo, os relatórios de qualidade de chamada no portal do TRM são derivados dos dados de qualidade de chamada do Teams.

Os dados residem no locatário do cliente e não são copiados para o locatário do parceiro. 

O portal MTM usa a autenticação do AAD para validar as credenciais de logon do parceiro. É importante observar que, no momento, as políticas de autenticação do cliente não se aplicarão ao parceiro. Por exemplo, se o cliente tiver uma política de autenticação multifator, ela não será convertida para o parceiro.

O cliente pode efetuar pull de logs de auditoria para o serviço TRM, que inclui a atividade do parceiro. Consulte [o log de auditoria no Salas do Teams Gerenciado](multi-tenant-auditing.md).

> [!Note]
> A auditoria do AAD e a auditoria do O365 não capturam logs do portal TRM.

## <a name="navigating-the-mtm-portal"></a>Navegando no portal do MTM

O portal MTM tem dois modelos interativos para navegar entre os dados do cliente:

- Agrega exibições em que os dados de todos os seus clientes são consolidados em uma única lista e podem ser filtrados.

  > [!Note]
  > Essa exibição só tem suporte na página **Incidentes** quando a exibição Habilitar todos os **tíquetes** está ativada.
  >
  > ![Figura 1](../media/multi-tenant-management-partner-001.png)

 - Alternância de locatários em que somente os dados **do Cliente** selecionados na lista suspensa são exibidos.
