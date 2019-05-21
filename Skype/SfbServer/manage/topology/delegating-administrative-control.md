---
title: Delegar o controle administrativo do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 1775fc4f02b7efa9ec26b962154f0aa90b59b296
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279204"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegar o controle administrativo do Skype for Business Server 

No Skype for Business Server, as tarefas administrativas são delegadas aos usuários usando o recurso controle de acesso baseado em função (RBAC). Quando você instala o Skype for Business Server, várias funções RBAC são criadas para você. Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory. Por exemplo, a função RBAC CsHelpDesk corresponde ao grupo CsHelpDesk localizado no contêiner usuários nos serviços de domínio Active Directory. Além disso, cada função RBAC está associada a um conjunto de cmdlets do Windows PowerShell do Skype for Business Server. Esses cmdlets representam as tarefas que podem ser realizadas pelos usuários que receberam a função RBAC fornecida. Por exemplo, a função CsHelpDesk foi atribuída aos cmdlets Lock-CsClientPin e UnlockCsClientPin. Isso significa que os usuários que receberam a função CsHelpDesk podem bloquear e desbloquear números de PIN do usuário. No entanto, a função CsHelpDesk não foi atribuída ao cmdlet New-CsVoicePolicy. Isso significa que os usuários que receberam a função CsHelpDesk não poderão criar novas políticas de voz.

## <a name="viewing-information-about-rbac-roles"></a>Exibir informações sobre as funções RBAC

Você pode recuperar informações básicas sobre as funções RBAC executando o seguinte comando no Shell de gerenciamento do Skype for Business Server:

`Get-CsAdminRole`

Lembre-se de que a identidade da função RBAC (por exemplo, CsVoiceAdministrator) tem um mapeamento direto para um grupo de segurança localizado no contêiner usuários nos serviços de domínio Active Directory.

Para exibir uma lista dos cmdlets que foram atribuídos a uma função, use um comando semelhante a este:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Atribuindo uma função RBAC a um usuário

Para atribuir uma função RBAC a um usuário, você deve adicionar esse usuário ao grupo de segurança apropriado do Active Directory. Por exemplo, para atribuir a função CsLocationAdministrator a um usuário, você deve adicionar esse usuário ao grupo CsLocationAdministrator. Isso pode ser feito executando o seguinte procedimento:

1. Usando uma conta que tenha permissão para modificar a associação de um grupo do Active Directory, faça logon em um computador onde usuários e computadores do Active Directory tenham sido instalados.
2. Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e em **usuários e computadores do Active Directory**.
3. Em usuários e computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner **usuários** .
4. Clique com o botão direito do mouse no grupo de segurança **CsLocationAdministrator**e, em seguida, clique em **Propriedades**.
5. Na caixa de diálogo **Propriedades** , na guia **Membros** , clique em **Adicionar**.
6. Na caixa de diálogo **Selecionar usuários, computadores, contatos ou grupos** , digite o nome de usuário ou o nome para exibição do usuário a ser adicionado ao grupo (por exemplo, Ken Myer) na caixa **digite os nomes de objeto a serem selecionados** e clique em **OK**.
7. Na caixa de diálogo **Propriedades** , clique em **OK**.

Para verificar se a função RBAC foi atribuída, use o cmdlet Get-CsAdminRoleAssignment, passando o cmdlet do SamAccountName (nome de logon do Active Directory) do usuário. Por exemplo, execute este comando dentro do Shell de gerenciamento do Skype for Business Server:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
