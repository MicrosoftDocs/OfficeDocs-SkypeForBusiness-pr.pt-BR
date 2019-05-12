---
title: Testes de direitos de administrador da topologia no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Como testar os direitos de topologia em Skype para Business Server
ms.openlocfilehash: 239c35eba451166f4e9fb5755535cf15999cdaea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910365"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Testes de direitos de administrador da topologia no Skype para Business Server

| | |
|--|--|
|Agenda de verificação|Após Skype inicial para implantação de servidor de negócios. Conforme necessário se surgirem problemas relacionados a permissão.|
|Ferramenta de teste|Windows PowerShell|
|Permissões necessárias|Quando executar o Skype localmente por meio do Shell de gerenciamento do servidor de negócios, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.<br/><br/>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem ter uma função de RBAC que tem permissão para executar o cmdlet Test-CsSetupPermission. Para ver uma lista de todas as funções RBAC que pode usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Cmdlets-corresponder "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descrição

Por padrão, somente os administradores de domínio podem habilitar um Skype para a topologia de servidor de negócios e fazer alterações grandes Skype a infra-estrutura de servidor de negócios. Isso não será um problema, desde que os administradores de domínio e sua Skype para administradores do servidor de negócios são o mesmo. Em muitas organizações, Skype para administradores do servidor de negócios não segure direitos administrativos para o domínio inteiro. Por padrão, o que significa que esses administradores (definidos como membros do grupo RTCUniversalServerAdmins) não é possível fazer Skype para alterações de topologia de servidor de negócios. Para dar a membros do grupo RTCUniversalServerAdmins o direito de fazer alterações de topologia, você deve atribuir as permissões necessárias do Active Directory usando o cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .
 
O cmdlet Test-CsSetupPermission verifica se as permissões necessárias que são necessárias para instalar o Skype para Business Server ou um de seus componentes estão configuradas no contêiner do Active Directory especificado. Se as permissões não são atribuídas, é possível executar o cmdlet Grant-CsSetupPermission para conceder o direito para instalar e habilitar Skype para Business Server de membros do grupo RTCUniversalServerAdmins.

## <a name="running-the-test"></a>Executando o teste

Para determinar se as permissões de configuração são atribuídas para um contêiner do Active Directory, chame o cmdlet Test-CsSetupPermission. Especifique o nome diferenciado do contêiner a ser verificado. Por exemplo, este comando verifica as permissões de instalação na unidade organizacional de contêiner = CsServers, dc = litwareinc, dc = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou falha

Se Test-CsSetupPermission determina se as permissões necessárias já foram definidas em um contêiner do Active Directory, o cmdlet retornará o valor verdadeiro:

True 

Se as permissões não estiverem definidas, Test-CsSetupPermission retornará o valor falso. Observe que esse valor geralmente será incluído em várias mensagens de aviso. Por exemplo:

Aviso: ACE (entrada) atl-cs-001\RTCUniversalServerAdmins; de controle de acesso Permitir; ExtendedRight; None; None; 1131f6aa-9c07-11D1-f79f-00c04fc2dcd2 

Aviso: As controle entradas de acesso (ACEs) no objeto "CN = computadores, DC = litwareinc, DC = com" não estiver tudo pronto. 

False 

Aviso: Processamento de "Test-CsSetupPermission" foi concluída com avisos. "2" avisos foram registrados durante dessa execução. 

Aviso: Resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por que o teste pode ter falhado

Embora existam raras exceções, se Test-CsSetupPermission falhar que geralmente significa que as permissões de instalação não está atribuídas para o contêiner do Active Directory especificado. Essas permissões podem ser atribuídas usando o cmdlet Grant-CsSetupPermission. Por exemplo, este comando concede permissões de instalação para o contêiner de computadores no domínio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
