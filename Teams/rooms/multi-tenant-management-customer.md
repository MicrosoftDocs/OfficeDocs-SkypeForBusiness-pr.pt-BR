---
title: Gerenciamento de parceiros para clientes
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.date: 06/09/2022
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
description: gerenciamento de parceiros para clientes.
f1keywords: ''
ms.openlocfilehash: 56aaf61092dd1bbd61c2734be6da1732f4882e49
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046860"
---
# <a name="partner-management-for-customers"></a>Gerenciamento de parceiros para clientes

O gerenciamento de parceiros no serviço de Gerenciamento de Salas Teams Pro permite que os clientes delegam perfeitamente o acesso e as responsabilidades a uma ou muitas organizações parceiras. Os parceiros só podem gerenciar salas que são atribuídas para gerenciar.

## <a name="on-boarding-partners"></a>Parceiros de embarque
   Convide parceiros por meio do portal do Pro Management para estabelecer a relação entre sua organização e o locatário da organização parceira.
   
> [!NOTE]
> O parceiro precisa atender aos pré-requisitos no [Gerenciamento Multilocatário para Parceiros](multi-tenant-management-partner.md).

### <a name="invitation-to-partner"></a>Convite para parceiro

   Neste método, você deve saber o nome de domínio do parceiro (como Contoso.com).

**Para iniciar o convite** 

1. Faça logon no portal de Gerenciamento de Salas Teams Pro como administrador de serviço gerenciado.
1. Vá para **Configurações >** **Parceiros** e selecione **Adicionar parceiro.**
1. Insira o nome de domínio na primeira linha.
1. Configure o número de dias até que o convite expire inserindo um inteiro de 1 a 30.
1. Configure os eventos que exigirão uma aprovação de controle de alteração. Por padrão, todos os controles são definidos como **aprovação automática.**

   > [!NOTE]
   > *Somente a aprovação automática está disponível por enquanto.*
   > 
   >  1.  *Aprovação manual:* Quando o parceiro executa a ação, uma solicitação de aprovação é gerada para que o cliente examine e aprove. A ação não será implementada até que a solicitação tenha sido aprovada.
   >  
   >  1. *Aprovação automática:* Quando o parceiro executa a ação, nenhuma solicitação de aprovação é gerada e a ação é implementada imediatamente.
     
1. Selecione **Avançar.**
1. Atribua salas que o parceiro gerenciará e selecione **Avançar.**
1. Para continuar, examine os termos e selecione **Concordo.**
1. Examine os detalhes do convite.
1. Selecione **Adicionar parceiro** para enviar o convite.

O convite é enviado aos gerentes de locatários na instância do parceiro para revisão. O primeiro usuário parceiro que aceitar o convite estabelecerá o link entre o Parceiro e seu locatário e atribuirá administradores primários. Não há nenhuma associação especial com o usuário que estabelece o link, o que permite flexibilidade caso o usuário seja reatribuído. Sempre deve haver pelo menos um usuário na função de administrador primário.

Para gerenciar usuários na função de administrador primário, consulte [Gerenciamento multilocatário para parceiros](multi-tenant-management-partner.md).

## <a name="off-boarding-partners"></a>Parceiros de off-boarding

**Para remover um parceiro**

1. Faça logon no portal do MTM (Gerenciamento de Vários Locatários) do Pro Management como administrador do Serviço Gerenciado.
1. Navegue até **Configurações > Parceiros.**
1. Selecione o parceiro que você deseja remover.
1. No painel de detalhes do cliente, selecione **Remover parceiro.**
1. Selecione **Excluir**. 
1. No prompt de confirmação para encerrar a associação entre você e o locatário do cliente, **selecione Excluir**.

## <a name="managing-partner-roles"></a>Gerenciando funções de parceiro

As funções de parceiro permitem que seu parceiro delegar responsabilidades mais granularmente para pessoal adicional. O conceito dessas funções é o mesmo descrito no [controle de acesso baseado em função](rooms-pro-rbac.md). É importante observar que as funções de parceiro são distintas de suas funções personalizadas. 

A **função de administrador primário** é a única função interna para cada parceiro que você adiciona. Essa função tem quase todas as permissões para as salas atribuídas a esse parceiro para o serviço TRM (consulte [Tabela 1](#table-1)). Por exemplo, se você tiver salas em todo o mundo e atribuir um parceiro para gerenciar todas as salas dos EUA, o administrador primário só poderá gerenciar e delegar permissões para essas salas. Nesse caso, os administradores primários deste Parceiro não têm visibilidade para nenhuma sala fora dos EUA. 

### <a name="adding-primary-admins-to-partner"></a>Adicionar administradores primários ao parceiro

Se você já enviou um convite a um parceiro e deseja delegar mais salas, poderá adicionar salas à função de administrador do parceiro.

**Para adicionar novas salas a um parceiro existente**

1. Faça logon no portal do Pro Management-MTM como administrador do Serviço Gerenciado.
1. Acesse **Configurações > Funções.**
1. Selecione  **funções de parceiro.** 
1. Selecione a **função de administrador primário** para o nome do parceiro correspondente.
1. No painel de função, selecione **Atribuições**.
1. Selecione a atribuição **de administradores atribuídos** .
1. No painel Atribuição de administradores atribuídos, selecione **Escopo**.
1. Selecione **Editar**.
1. Pesquise as salas que você deseja adicionar e selecione a sala desejada.
1. Para confirmar as alterações, selecione **Salvar**.

### <a name="table-1"></a>Tabela 1

|Recurso|Permissão|**Serviço Gerenciado Administração**|**Site Lead**|**Site Tech**|**Administrador de parceiros**|
| :- | :- | :- | :- | :- | :- |
|Quartos|Exibir| &#10004;|&#10004;|&#10004;|&#10004;|
||Modificar|&#10004;|&#10004;|&#10004;|&#10004;|
||Redefinir chave|&#10004;||||
||Baixar chave|&#10004;|&#10004;|&#10004;||
||Unenroll|&#10004;|&#10004;|&#10004;||
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
|Configurações de gerenciamento pro|Exibir|&#10004;||||
||Modificar|&#10004;||||
|Gerenciamento de funções|Exibir |&#10004;|||&#10004;|
||Modificar|&#10004;|||&#10004;|

## <a name="security"></a>Segurança

Como cliente final, você mantém o controle sobre o acesso aos seus dados e pode remover completamente um parceiro a qualquer momento. 

Com o recurso de acesso delegado, um parceiro não obtém outros privilégios fora do portal do Pro Management. No entanto, todos os dados presentes no serviço pro management derivados de outros produtos da Microsoft são considerados dados no serviço. Como exemplo, enquanto os relatórios de qualidade de chamada são derivados de dados de qualidade de chamada do Teams, todos os dados no portal de Gerenciamento Profissional estão no escopo de permissão. 

Nenhuma permissão é concedida ao AAD ou ao Teams Administração Center ou a qualquer outro produto da Microsoft. Além disso, os parceiros não têm acesso para exibir ou modificar salas não definidas no escopo do convite. 

Os dados residem no locatário do cliente e não são copiados para o locatário do parceiro. 

O portal MTM usa Azure AD autenticação para validar as credenciais de logon do parceiro. Observe que, neste momento, as políticas de autenticação do cliente não se aplicam ao parceiro. Por exemplo, se o cliente tiver uma política de autenticação multifator, ele não se traduzirá para o parceiro. 

Para fazer pull de logs na atividade do parceiro, consulte [Auditoria](multi-tenant-auditing.md). 

> [!NOTE]
> A auditoria do AAD e a auditoria O365 não capturam logs do portal de Gerenciamento Profissional. 
