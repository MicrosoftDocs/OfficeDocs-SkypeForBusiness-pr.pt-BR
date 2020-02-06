---
title: Testar permissões de administrador no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como testar permissões de administrador no Skype for Business Server
ms.openlocfilehash: 97db574803b575d484240e7339d56603ae5432da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817182"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Testar permissões de administrador no Skype for Business Server

| | |
|--|--|
|Cronograma de verificação|Após a implantação inicial do Skype for Business Server. Conforme necessário se surgirem problemas relacionados à permissão.|
|Ferramenta de teste|Windows PowerShell|
|Permissões necessárias|Quando executado localmente usando o Shell de gerenciamento do Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.<br><br/>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsOUPermission. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-corresponde a "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descrição

Ao instalar o Skype for Business Server, uma das tarefas realizadas pelo programa de instalação fornece ao grupo RTCUniversalUserAdmins as permissões do Active Directory necessárias para gerenciar usuários, computadores, contatos, contatos de aplicativos e InetOrg pessoas. Se você desabilitou a herança de permissão no Active Directory, a configuração não poderá atribuir essas permissões. Como resultado, os membros do grupo RTCUniversalUserAdmins não poderão gerenciar entidades do Skype for Business Server. Esses privilégios de gerenciamento só estarão disponíveis para administradores de domínio. 

O cmdlet Test-CsOUPermission verifica se as permissões necessárias necessárias para gerenciar usuários, computadores e outros objetos estão definidas em um contêiner do Active Directory. Se essas permissões não estiverem definidas, você poderá resolver esse problema executando o [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Observe que Grant-CsOUPermission só pode atribuir permissões a membros do grupo RTCUniversalUserAdmins. Você não pode usar esse cmdlet para conceder permissões a um usuário ou grupo arbitrário. Se quiser que um usuário ou grupo diferente tenha permissões de gerenciamento de usuário, você deve adicionar esse usuário (ou grupo) ao grupo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Executar o teste

Para verificar se as permissões de gerenciamento estão definidas em um contêiner, execute o cmdlet Test-CsOUPermission seguido pelo nome distinto do contêiner e pelo tipo de permissões que você está verificando. Por exemplo, esse comando verifica se as permissões de usuário estão definidas na UO ou em Redmond, DC = litwareinc, DC = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Para verificar várias permissões usando um único comando, coloque cada tipo de permissão entre aspas e, em seguida, separe esses tipos usando vírgulas. Por exemplo, este comando verifica as permissões de usuário, computador e contato:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Para obter mais informações, consulte o [tópico da ajuda para o cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se as permissões necessárias já foram definidas, Test-CsOUPermission retornará uma resposta de uma palavra:

Verdadeiro

Se as permissões necessárias não estiverem definidas, Test-CsOUPermission retornará o valor false. Talvez seja necessário procurar por um momento para encontrar esse valor. Geralmente, ele será inserido dentro de vários avisos que acompanham. Por exemplo:

Aviso: entrada de controle de acesso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; habilitar ReadProperty; ContainerInherit; Descendentes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

Aviso: as entradas de controle de acesso (ACEs) no objeto "UO = América do Access = atl-cs-001\DC = litwareinc, DC = com" não estão prontas. 

Falso 

Aviso: o processamento de "Test-CsOUPermission" foi concluído com avisos. "2" avisos foram registrados durante a execução. 

Aviso: os resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se Test-CsOUPermission falhar, geralmente significa que a permissão especificada não foi atribuída ao grupo RTCUniversalUserAdmins. Você pode resolver esse problema e atribuir as permissões necessárias, usando o cmdlet Grant-CsOUPermission. Por exemplo, esse comando fornece permissões de OU para usuários, contatos e inetOrgPersons ao grupo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Para obter mais informações, consulte o [tópico da ajuda para o cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).
