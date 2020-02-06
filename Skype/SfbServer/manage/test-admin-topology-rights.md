---
title: Testando direitos de topologia de administração no Skype for Business Server
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
description: Como testar os direitos de topologia no Skype for Business Server
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817307"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testando direitos de topologia de administração no Skype for Business Server

| | |
|--|--|
|Cronograma de verificação|Após a implantação inicial do Skype for Business Server. Conforme necessário se surgirem problemas relacionados à permissão.|
|Ferramenta de teste|Windows PowerShell|
|Permissões necessárias|Quando executado localmente usando o Shell de gerenciamento do Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.<br/><br/>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsSetupPermission. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-corresponde a "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descrição

Por padrão, somente os administradores de domínio podem habilitar uma topologia do Skype for Business Server e fazer grandes alterações na infraestrutura do Skype for Business Server. Isso não será um problema, contanto que seus administradores de domínio e seus administradores do Skype for Business Server sejam os mesmos. Em muitas organizações, os administradores do Skype for Business Server não mantêm direitos administrativos para todo o domínio. Por padrão, isso significa que esses administradores (definidos como membros do grupo RTCUniversalServerAdmins) não podem fazer alterações de topologia do Skype for Business Server. Para dar aos membros do grupo RTCUniversalServerAdmins o direito de fazer alterações de topologia, você deve atribuir as permissões necessárias do Active Directory usando o cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .
 
O cmdlet Test-CsSetupPermission verifica se as permissões necessárias necessárias para instalar o Skype for Business Server ou um de seus componentes estão configuradas no contêiner especificado do Active Directory. Se as permissões não forem atribuídas, você poderá executar o cmdlet Grant-CsSetupPermission para dar aos membros do grupo RTCUniversalServerAdmins o direito de instalar e habilitar o Skype for Business Server.

## <a name="running-the-test"></a>Executar o teste

Para determinar se as permissões de configuração são atribuídas para um contêiner do Active Directory, chame o cmdlet Test-CsSetupPermission. Especifique o nome diferenciado do contêiner a ser verificado. Por exemplo, esse comando verifica as permissões de configuração no container ou = CsServers, DC = litwareinc, DC = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se Test-CsSetupPermission determinar que as permissões necessárias já foram definidas em um contêiner do Active Directory, o cmdlet retornará o valor true:

Verdadeiro 

Se as permissões não estiverem definidas, Test-CsSetupPermission retornará o valor false. Observe que esse valor normalmente será incluído em muitas mensagens de aviso. Por exemplo:

Aviso: entrada de controle de acesso (ACE) atl-cs-001\RTCUniversalServerAdmins; Habilitar ExtendedRight; Nenhuma Nenhuma 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

Aviso: as entradas de controle de acesso (ACEs) no objeto "CN = Computers, DC = litwareinc, DC = com" não estão prontas. 

Falso 

Aviso: o processamento de "Test-CsSetupPermission" foi concluído com avisos. "2" avisos foram registrados durante a execução. 

Aviso: os resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Embora existam exceções raras, se Test-CsSetupPermission falhar, isso geralmente significa que as permissões de configuração não são atribuídas para o contêiner do Active Directory especificado. Essas permissões podem ser atribuídas usando o cmdlet Grant-CsSetupPermission. Por exemplo, esse comando concede permissões de configuração para o contêiner de computadores no domínio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
