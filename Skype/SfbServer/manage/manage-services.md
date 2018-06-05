---
title: Gerenciar os serviços para Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Este artigo descreve como gerenciar os serviços em execução em um Skype para a topologia de negócios Server 2015.
ms.openlocfilehash: 87bf9fd90c68155504e6be5b28b56d571eaad924
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569572"
---
# <a name="manage-services-for-skype-for-business-server-2015"></a>Gerenciar os serviços para Skype para Business Server 2015

Este artigo descreve como gerenciar os serviços em execução em um Skype para a topologia de negócios Server 2015.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server-2015"></a>Exibir uma lista de computadores que executam o Skype para Business Server 2015
<a name="view_list"> </a>

Você pode usar o Skype para painel de controle do Business Server para exibir uma lista de todos os computadores que estejam executando o Skype para negócios 2015 de servidor em sua topologia e ver o status do serviço de cada um. Você pode classificar a lista por computador, pool ou site. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Para exibir uma lista de computadores que executam o Skype para Business Server

1. Usando uma conta de usuário atribuída a qualquer uma das funções administrativas predefinidas para Skype para Business Server 2015, faça logon em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype para Business Server 2015, consulte **Planning for Role-Based Access Control**.   
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.   
3. Na barra de navegação à esquerda, clique em **topologia** e clique em **Status**.   
4. Na página **Status** , faça qualquer um dos seguintes procedimentos conforme necessário:
   - Classifique a lista clicando em **computador**, **Pool**ou cabeçalho de coluna de **Site** e em seguida, clicando na seta para cima ou seta para baixo. 
   - Clique em **Atualizar** para exibir a lista mais atualizada.  
   - Procure um computador específico, digitando o nome do computador no campo de pesquisa.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-2015-server"></a>Exibir o status dos serviços executados em um Skype para o servidor de negócios 2015
<a name="view-status"> </a>

Você pode usar o Skype para painel de controle do Business Server para exibir todos os serviços que estão sendo executados em um determinado computador em sua Skype para a topologia de servidor de negócios e ver o status de cada serviço.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para exibir o status dos serviços executados em um computador

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
3. Na barra de navegação à esquerda, clique em **topologia**. 
4. Na página **Status** , classifique ou pesquise a lista conforme necessário para localizar o computador que você está interessado e clique no nome do computador.
5. Execute qualquer uma das seguintes ações:
   - Para ver o status mais recente dos serviços executados no computador, clique em **obter o status do serviço**.
   - Para ver uma lista de serviços específicos executados no computador e o status de cada serviço, clique em **Propriedades**e, em seguida, clique em **Fechar** para retornar à lista.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Exibindo o status do serviço com os cmdlets do Windows Powershell

Você também pode exibir o status do serviço usando o Windows PowerShell e o cmdlet **Get-CsWindowsService** . Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-view-service-status"></a>Para exibir o status do serviço

Para exibir o status do serviço em um computador, digite um comando semelhante ao seguinte no Skype do Shell de gerenciamento do servidor de negócios e pressione Enter:
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Este comando retorna informações semelhantes para o seguinte:
  
|**RoleName**|**Status**|
|:-----|:-----|
|{W3SVC}  <br/> |Em execução  <br/> |
|{CentralManagement}  <br/> | Em execução <br/> |
|{Com o ClsAgent}  <br/> |Em execução  <br/> |
|{Registrador, UserServer, EdgeServer}  <br/> |Em execução  <br/> |
|{ApplicationServer}  <br/> |Em execução  <br/> |
|{ConferencingServer}  <br/> |Em execução  <br/> |
|{MediationServer}  <br/> |Em execução  <br/> |
   
Para obter detalhes, consulte [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Exibir detalhes sobre um serviço
<a name="view_details"> </a>

Você pode usar o Skype para painel de controle do Business Server para exibir detalhes sobre cada serviço que está sendo executado em um computador específico em sua topologia. Você pode exibir o status de cada serviço e os detalhes de como os bancos de dados associados, portas e serviços dependentes.
  
### <a name="to-view-details-for-a-service"></a>Para visualizar detalhes de um serviço

1. Usando uma conta de usuário atribuída a qualquer uma das funções administrativas predefinidas para Skype para Business Server 2015, faça logon em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype para Business Server 2015, consulte **Planning for Role-Based Access Control**.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
3. Na barra de navegação à esquerda, clique em **topologia** e clique em **Status**.
4. Na página **Status** , classifique ou pesquisa na lista e, em seguida, clique no computador que você deseja exibir.
5. Clique em **Propriedades**.
6. Na janela **Exibir detalhes do computador** , classifique a lista de serviços, se necessário e clique no serviço que você deseja exibir.
7. Faça qualquer um dos seguintes procedimentos conforme necessário:
   - Para ver o status mais recente desse serviço específico, clique em **obter o status do serviço**.
   - Para ver os detalhes desse serviço específico, clique em **Propriedades** e, em seguida, clique em **Fechar**.
   - Para retornar à lista de todos os computadores em sua topologia, clique em **Fechar**.
    
## <a name="start-or-stop-skype-for-business-server-2015-services"></a>Iniciar ou parar Skype para serviços de Business Server 2015
<a name="StartStop"> </a>

Você pode usar o Skype para painel de controle do Business Server para iniciar ou parar todos o Skype para serviços de Business Server 2015 executados em um computador específico ou para iniciar ou parar um serviço específico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Para iniciar ou parar todos os Skype para serviços corporativos em um computador

1. A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015. Você pode determinar se você tiver atribuído a CsServerAdministrator ou a função CsAdministrator RBAC executando um comando semelhante ao seguinte:
    
  ```
  Get-CsAdminRoleAssignment -Identity "kenmyer"
  ```

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
3. Na barra de navegação à esquerda, clique em **topologia** e clique em **Status**.
4. Na página **Status** , classificação ou pesquisa até a lista conforme necessário para localizar o computador que está executando os serviços que você deseja iniciar ou parar e, em seguida, clique nele.
5. Clique em **ação**.
6. Clique em **Iniciar todos os serviços** ou **Parar todos os serviços**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Para iniciar ou parar um serviço específico

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
3. Na barra de navegação à esquerda, clique em **topologia** e clique em **Status**.
4. Na página **Status** , classificação ou pesquisa até a lista conforme necessário para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário e clique no serviço que você deseja iniciar ou parar.
7. Clique em **ação**.
8. Clique em **Iniciar serviço** ou **Parar o serviço**.
9. Clique em **Fechar**.
    
## <a name="prevent-sessions-for-services"></a>Evitar sessões de serviços
<a name="prevent_session"> </a>

Você pode usar o Skype para painel de controle do Business Server para impedir novas sessões para todos o Skype para serviços de Business Server 2015 executados em um computador específico ou para impedir novas sessões para um Skype específico para o serviço de Business Server 2015.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Para impedir novas sessões para todos os Skype para serviços corporativos de um computador

1. A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
3. Na barra de navegação à esquerda, clique em **topologia** e clique em **Status**.
4. Na página **Status** , classificação ou pesquisa através da lista como necessário para localizar o computador que está executando os serviços para o qual você deseja impedir novas sessões e, em seguida, clique nele.
5. Clique em **ação**.
6. Clique em **impedir novas sessões para todos os serviços**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para impedir novas sessões para um serviço específico

1. A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2015.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
3. Na barra de navegação à esquerda, clique em **topologia** e clique em **Status**.
4. Na página **Status** , classificação ou pesquisa até a lista conforme necessário para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele. 
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.
7. Clique em **ação**.
8. Clique em **impedir novas sessões para o serviço**.
9. Clique em **Fechar**.
    

