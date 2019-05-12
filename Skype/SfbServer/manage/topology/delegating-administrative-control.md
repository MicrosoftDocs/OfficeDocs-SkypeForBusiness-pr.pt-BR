---
title: Delegar o controle administrativo do Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b8da2577140ca901c31b94c4b9987f2addef7bba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924833"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Delegar o controle administrativo do Skype para Business Server 

No Skype para Business Server, as tarefas administrativas são delegadas aos usuários usando o recurso de acesso baseado em função (RBAC) do controle. Quando você instala o Skype para Business Server, um número de funções de RBAC é criado para você. Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory. Por exemplo, a função RBAC CsHelpDesk corresponde ao grupo CsHelpDesk encontrado no contêiner usuários nos serviços de domínio Active Directory. Além disso, cada função RBAC é associada um conjunto de Skype para Business Server Windows PowerShell cmdlets. Esses cmdlets representam as tarefas que podem ser executadas pelos usuários que tiverem sido atribuídos a função RBAC determinada. Por exemplo, a função CsHelpDesk recebeu o Lock-CsClientPin e UnlockCsClientPin cmdlets. Isso significa que os usuários que tiverem sido atribuídos a função CsHelpDesk podem bloquear e desbloquear PINs de usuário. No entanto, a função CsHelpDesk não recebeu o cmdlet New-CsVoicePolicy. Isso significa que os usuários que tiverem sido atribuídos a função CsHelpDesk não é possível criar novas políticas de voz.

## <a name="viewing-information-about-rbac-roles"></a>Exibindo informações sobre funções de RBAC

É possível recuperar informações básicas sobre suas funções de RBAC executando o seguinte comando dentro do Skype do Shell de gerenciamento do servidor de negócios:

`Get-CsAdminRole`

Tenha em mente que a identidade da função de RBAC (por exemplo, CsVoiceAdministrator) tem um mapeamento direto para um grupo de segurança encontrado no contêiner usuários nos serviços de domínio Active Directory.

Para exibir uma lista dos cmdlets que tiverem sido atribuídos a uma função, use um comando semelhante a esta:

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Atribuindo uma função de RBAC a um usuário

Para atribuir uma função de RBAC a um usuário, você deve adicionar esse usuário ao grupo de segurança do Active Directory apropriado. Por exemplo, para atribuir a função cslocationadministrator tem a um usuário, você deve adicionar esse usuário ao grupo CsLocationAdministrator. Que pode ser feita por realizar o procedimento a seguir:

1. Usando uma conta que tenha permissão para modificar a associação de um grupo do Active Directory, faça logon em um computador no qual os computadores e usuários do Active Directory tenha sido instalado.
2. Clique em **Iniciar**, clique em **Todos os programas**, clique em **Ferramentas administrativas**e, em seguida, clique em **e computadores do Active Directory Users**.
3. Em e computadores do Active Directory Users, expanda o nome do seu domínio e clique no recipiente de **usuários** .
4. Com o botão direito do grupo de segurança **CsLocationAdministrator**e clique em **Propriedades**.
5. Na caixa de diálogo **Propriedades** , na guia **membros** , clique em **Adicionar**.
6. Na caixa de diálogo **Selecionar usuários, computadores, contatos ou grupos** , digite o nome de usuário ou exibir o nome do usuário a ser adicionado ao grupo (por exemplo, Ken Myer) na caixa **Digite os nomes de objeto a serem selecionados** e clique em **Okey**.
7. Na caixa de diálogo **Propriedades** , clique em **Okey**.

Para verificar se a função RBAC foi atribuída, use o cmdlet Get-CsAdminRoleAssignment, passando o cmdlet (nome de logon do Active Directory) SamAccountName do usuário. Por exemplo, execute este comando a partir do Skype do Shell de gerenciamento do servidor de negócios:

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
