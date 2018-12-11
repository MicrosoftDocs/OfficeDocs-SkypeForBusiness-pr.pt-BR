---
title: Testes de permissões de administrador no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Como testar as permissões de administrador no Skype para Business Server
ms.openlocfilehash: 528f12a01483750360a54a2e4d8fe516cf1b2d46
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222951"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testes de permissões de administrador no Skype para Business Server

| | |
|--|--|
|Agenda de verificação|Após Skype inicial para implantação de servidor de negócios. Conforme necessário se surgirem problemas relacionados a permissão.|
|Ferramenta de teste|Windows PowerShell|
|Permissões necessárias|Quando executar o Skype localmente por meio do Shell de gerenciamento do servidor de negócios, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.<br><br/>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem ter uma função de RBAC que tem permissão para executar o cmdlet Test-CsOUPermission. Para ver uma lista de todas as funções RBAC que pode usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Cmdlets-corresponder "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descrição

Quando você instala o Skype para Business Server, uma das tarefas que foi executada pelo programa de instalação oferece o grupo RTCUniversalUserAdmins as permissões do Active Directory que são necessárias para gerenciar usuários, computadores, contatos, contatos de aplicativo e InetOrg pessoas. Se você desabilitou a herança de permissões no Active Directory, a instalação não poderá atribuir essas permissões. Como resultado, os membros do grupo RTCUniversalUserAdmins não será possível gerenciar Skype para entidades Business Server. Esses privilégios de gerenciamento só estará disponíveis para os administradores de domínio. 

O cmdlet Test-CsOUPermission verifica se as permissões necessárias requeridas para gerenciar usuários, computadores e outros objetos estão definidas em um contêiner do Active Directory. Se essas permissões não estiverem definidas, você pode resolver esse problema, executando o [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Observe que o Grant-CsOUPermission só pode atribuir permissões a membros do grupo RTCUniversalUserAdmins. Você não pode usar esse cmdlet para conceder permissões a um usuário ou grupo arbitrário. Se desejar que um usuário ou grupo diferente para ter permissões de gerenciamento de usuário, você deve adicionar o usuário (ou grupo) ao grupo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Executando o teste

Para verificar se as permissões de gerenciamento estão definidas em um contêiner, execute o cmdlet Test-CsOUPermission seguido do nome diferenciado do contêiner e o tipo das permissões que você está verificando. Por exemplo, este comando verifica se as permissões de usuário são definidas na OU ou = Redmond, dc = litwareinc, dc = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Para verificar permissões de vários usando um único comando, coloque cada tipo de permissão entre aspas e separe os tipos por vírgulas. Por exemplo, esse único comando verifica o usuário, o computador e o contato permissões:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Para obter mais informações, consulte o [tópico de ajuda para o cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou falha

Se já tem sido definidas as permissões necessárias, Test-CsOUPermission retornará uma resposta de uma palavra:

True

Se as permissões necessárias não estiverem definidas, Test-CsOUPermission retornará o valor falso. Você pode precisar procurar um pouco encontrar esse valor. Ele será normalmente incorporado dentro de vários avisos acompanha. Por exemplo:

Aviso: ACE (entrada) atl-cs-001\RTCUniversalUserReadOnlyGroup; de controle de acesso permitir; ReadProperty; ContainerInherit; Descendentes; 0 bf967aba-0de6 - 11d-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

Aviso: As controle entradas de acesso (ACEs) no objeto "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" não estiver tudo pronto. 

False 

Aviso: Processamento de "Test-CsOUPermission" foi concluída com avisos. "2" avisos foram registrados durante dessa execução. 

Aviso: Resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por que o teste pode ter falhado

Se Test-CsOUPermission falhar, isso normalmente significa que a permissão especificada não tem sido atribuída ao grupo RTCUniversalUserAdmins. Você pode resolver esse problema e atribuir as permissões necessárias, usando o cmdlet Grant-CsOUPermission. Por exemplo, este comando concede permissões de UO para usuários, contatos e inetOrgPersons ao grupo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Para obter mais informações, consulte o [tópico de ajuda para o cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).