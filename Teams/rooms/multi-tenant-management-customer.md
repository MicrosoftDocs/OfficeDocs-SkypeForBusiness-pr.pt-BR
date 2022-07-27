---
title: Gerenciamento de parceiros para clientes
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.date: 06/09/2022
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
ms.openlocfilehash: b186adbf0df84e0739abd4675cfcf1437885d365
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023882"
---
# <a name="partner-management-for-customers"></a>Gerenciamento de parceiros para clientes

O gerenciamento de parceiros no serviço Salas do Teams gerenciado (TRM) permite que os clientes deleguem diretamente o acesso e as responsabilidades a uma ou várias organizações parceiras. Os parceiros só podem gerenciar salas atribuídas a eles para gerenciar.

## <a name="on-boarding-partners"></a>Parceiros de integração
   Convide parceiros por meio do portal TRM para estabelecer a relação entre sua organização e o locatário da organização parceira.

### <a name="invitation-to-partner"></a>Convite para parceiro

   Nesse método, você deve saber o nome de domínio do parceiro (como Contoso.com).

**Para iniciar o convite** 

1. Faça logon no Salas do Teams gerenciado como administrador de serviços gerenciados.
1. Vá para **Configurações >** **Parceiros** e, em seguida, **selecione Adicionar parceiro.**
1. Insira o nome de domínio na primeira linha.
1. Configure o número de dias até que o convite expire inserindo um inteiro de 1 a 30.
1. Configure os eventos que exigirão uma aprovação de controle de alteração. Por padrão, todos os controles são definidos como **Aprovação automática.**

   > [!NOTE]
   > *Somente a aprovação automática está disponível no momento.*
   > 
   >  1.  *Aprovação manual:* Quando o parceiro executa a ação, uma solicitação de aprovação é gerada para que o cliente examine e aprove. A ação não é implementada até que a solicitação seja aprovada.
   >  
   >  1. *Aprovação automática:* Quando o parceiro executa a ação, nenhuma solicitação de aprovação é gerada e a ação é implementada imediatamente.
     
1. Selecione **Avançar.**
1. Atribua salas que o parceiro gerenciará e selecione **Avançar.**
1. Para continuar, examine os termos e selecione Eu **concordo.**
1. Examine os detalhes do convite.
1. Selecione **Adicionar parceiro** para enviar o convite.

O convite é enviado aos gerentes de locatário na instância do parceiro para revisão. O primeiro usuário parceiro que aceitar o convite estabelecerá o vínculo entre o Parceiro e seu locatário e atribuirá administradores primários. Não há nenhuma associação especial com o usuário que estabeleça o link, o que permite flexibilidade caso o usuário seja reatribuido. Sempre deve haver pelo menos um usuário na função de administrador primário.

Para gerenciar usuários na função de administrador principal, consulte [Gerenciamento multilocatário para parceiros](multi-tenant-management-partner.md).

## <a name="off-boarding-partners"></a>Parceiros de desa integração

**Para remover um parceiro**

1. Faça logon no portal TRM-MTM como administrador mmr.
1. Navegue até **Configurações > Parceiros.**
1. Selecione o parceiro que você deseja remover.
1. No painel de detalhes do cliente, selecione **Remover parceiro.**
1. Selecione **Excluir**. 
1. No prompt de confirmação para encerrar a associação entre você e o locatário do cliente, selecione **Excluir**.

## <a name="managing-partner-roles"></a>Gerenciando funções de parceiro

As funções de parceiro permitem que seu parceiro delegue de forma mais granular as responsabilidades para funcionários adicionais. O conceito dessas funções é o mesmo descrito no [controle de acesso baseado em função](microsoft-teams-rooms-premium-rbac.md). É importante observar que as funções de parceiro são diferentes das suas funções personalizadas. 

A **função de** administrador principal é a única função interna para cada parceiro que você adicionar. Essa função tem quase todas as permissões para as salas que você atribuiu a esse parceiro para o serviço TRM (consulte [a Tabela 1](#table-1)). Por exemplo, se você tiver salas em todo o mundo e atribuir um parceiro para gerenciar todas as salas dos EUA, o administrador principal só poderá gerenciar e delegar permissões para essas salas. Nesse caso, os administradores primários desse Parceiro não têm visibilidade de nenhuma sala fora dos EUA. 

### <a name="adding-primary-admins-to-partner"></a>Adicionando administradores primários ao parceiro

Se você já enviou um convite para um parceiro e deseja delegar mais salas, pode adicionar salas à função de administrador do parceiro.

**Para adicionar novas salas a um parceiro existente**

1. Faça logon no portal TRM-MTM como administrador mmr.
1. Vá para **Configurações > Funções.**
1. Selecione  **Funções de parceiro.** 
1. Selecione a **função de administrador** principal para o nome do parceiro correspondente.
1. No painel de função, selecione **Atribuições**.
1. Selecione **a atribuição administradores atribuídos** .
1. No painel de atribuição administradores atribuídos, selecione **Escopo**.
1. Selecione **Editar**.
1. Pesquise as salas que você deseja adicionar e selecione a sala desejada.
1. Para confirmar as alterações, selecione **Salvar**.

### <a name="table-1"></a>Tabela 1

|Recurso|Permissão|**MmR Administração**|**Cliente potencial do site**|**Site Tech**|**Administrador de parceiros**|
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

## <a name="security"></a>Segurança

Como cliente final, você mantém o controle sobre o acesso aos seus dados e pode remover completamente um parceiro a qualquer momento. 

Com o recurso de acesso delegado, um parceiro não obtém nenhum outro privilégio fora do portal do serviço TRM. No entanto, todos os dados presentes no serviço TRM derivados de outros produtos da Microsoft são considerados dados no serviço TRM. Por exemplo, embora os relatórios de qualidade de chamada sejam derivados de dados de qualidade de chamada do Teams, todos os dados no portal TRM estão no escopo de permissão. 

Nenhuma permissão é concedida ao AAD ou ao Teams Administração Center ou qualquer outro produto da Microsoft. Além disso, os parceiros não têm acesso para exibir ou modificar salas não definidas no escopo do convite. 

Os dados residem no locatário do cliente e não são copiados para o locatário do parceiro. 

O portal MTM usa Azure AD autenticação para validar as credenciais de logon do parceiro. Observe que, no momento, as políticas de autenticação do cliente não se aplicam ao parceiro. Por exemplo, se o cliente tiver uma política de autenticação multifator, ela não será convertida para o parceiro. 

Para efetuar pull de logs na atividade do parceiro, consulte [Auditoria](multi-tenant-auditing.md). 

> [!NOTE]
> A auditoria do AAD e a auditoria do O365 não capturam logs do portal TRM. 
