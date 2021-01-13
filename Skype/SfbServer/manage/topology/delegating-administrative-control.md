---
title: Delegar o controle administrativo do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832791"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegar o controle administrativo do Skype for Business Server 

No Skype for Business Server, as tarefas administrativas são delegadas aos usuários usando o recurso de controle de acesso baseado em função (RBAC). Quando você instala o Skype for Business Server, várias funções do RBAC são criadas para você. Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio active Directory. Por exemplo, a função CsHelpDesk do RBAC corresponde ao grupo CsHelpDesk encontrado no contêiner Usuários nos Serviços de Domínio do Active Directory. Além disso, cada função do RBAC está associada a um conjunto de cmdlets do Windows PowerShell do Skype for Business Server. Esses cmdlets representam as tarefas que podem ser realizadas por usuários que receberam a função RBAC determinada. Por exemplo, a função CsHelpDesk foi atribuída aos cmdlets Lock-CsClientPin e UnlockCsClientPin. Isso significa que os usuários que foram atribuídos com a função CsHelpDesk podem bloquear e desbloquear números PIN do usuário. No entanto, a função CsHelpDesk não recebeu a atribuição do cmdlet New-CsVoicePolicy. Isso significa que os usuários que receberam a função CsHelpDesk não podem criar novas políticas de voz.

## <a name="viewing-information-about-rbac-roles"></a>Exibindo informações sobre funções RBAC

Você pode recuperar informações básicas sobre suas funções do RBAC executando o seguinte comando no Shell de Gerenciamento do Skype for Business Server:

`Get-CsAdminRole`

Tenha em mente que a Identidade da função RBAC (por exemplo, CsVoiceAdministrator) tem um mapeamento direto para um grupo de segurança encontrado no contêiner Usuários nos Serviços de Domínio do Active Directory.

Para visualizar uma lista de cmdlets que foram designados a uma função, use um comando semelhante a este:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Atribuindo uma função RBAC a um usuário

Para atribuir uma função RBAC a um usuário, você deve adicionar esse usuário ao grupo de segurança apropriado do Active Directory. Por exemplo, para atribuir a função CsLocationAdministrator a um usuário, você deve adicionar esse usuário ao grupo CsLocationAdministrator. Isso pode ser feito realizando o seguinte procedimento:

1. Usando uma conta que tenha permissão para modificar a associação a um grupo do Active Directory, faça logon em um computador em que os usuários e computadores do Active Directory tenham sido instalados.
2. Clique em **Iniciar**, clique em **Todos os Programas**, clique em **Ferramentas Administrativas** e, em seguida, clique em **Usuários e Computadores do Active Directory**.
3. Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de **Usuários**.
4. Clique com o botão direito no grupo de segurança **CsLocationAdministrator** e clique em **Propriedades**.
5. Na caixa de diálogo **Propriedades**, na guia **Membros**, clique em **Adicionar**.
6. Na caixa de diálogo Selecionar **Usuários, Computadores,** Contatos ou Grupos, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo (por exemplo, Ken Myer) na caixa Digite os nomes de objeto a serem selecionados e clique em **OK.** 
7. Na caixa de diálogo **Propriedades**, clique em **OK**.

Para verificar se a função RBAC foi atribuída, use o cmdlet Get-CsAdminRoleAssignment, passando ao cmdlet o SamAccountName (nome de logon do Active Directory) do usuário. Por exemplo, execute este comando no Shell de Gerenciamento do Skype for Business Server:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
