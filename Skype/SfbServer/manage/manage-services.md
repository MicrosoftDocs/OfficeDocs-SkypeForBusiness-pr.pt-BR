---
title: Gerenciar serviços para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Este artigo descreve como gerenciar serviços executados em uma topologia de Skype for Business Server.
ms.openlocfilehash: 9a26accf8e8c9a4c20b9fea99eac6d9dc2cbadea
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410784"
---
# <a name="manage-services-for-skype-for-business-server"></a>Gerenciar serviços para Skype for Business Server

Este artigo descreve como gerenciar serviços executados em uma topologia de Skype for Business Server.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Exibir uma lista de computadores que executam Skype for Business Server
<a name="view_list"> </a>

Você pode usar Skype for Business Server Painel de Controle para exibir uma lista de todos os computadores que estão executando Skype for Business Server em sua topologia e ver o status de serviço de cada um. Você pode classificar a lista por computador, pool ou site. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Para exibir uma lista de computadores que executam Skype for Business Server

1. Em uma conta de usuário atribuída a qualquer uma das funções administrativas predefinida para Skype for Business Server, faça logoff em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinida disponíveis no Skype for Business Server, consulte **Planning for Role-Based Access Control**.   
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.   
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**.   
4. Na página **Status**, execute um dos seguintes procedimentos conforme necessário:
   - Classifique a lista clicando no título de coluna **Computador**, **Pool** ou **Site** e, em seguida, clicando na seta para cima ou seta para baixo. 
   - Clique em **Atualizar** para exibir a lista mais atualizada.  
   - Procure um computador específico, digitando o nome do computador no campo de pesquisa.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Exibir o status dos serviços em execução em um Skype for Business servidor
<a name="view-status"> </a>

Você pode usar Skype for Business Server Painel de Controle para exibir todos os serviços que estão sendo executados em um computador específico em sua topologia Skype for Business Server e ver o status de cada serviço.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para exibir o status dos serviços executados em um computador

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
3. Na barra de navegação esquerda, clique em **Topologia**. 
4. Na página **Status** , sort or search the list, as required, to find the computer you're interested in, and then click the computer name.
5. Faça qualquer um dos seguintes:
   - Para ver os status de serviços mais atuais executados no computador, clique em **Obter status de serviço**.
   - Para ver uma lista de serviços específicos executados no computador e o status de cada serviço, clique em **Propriedades** e em **Fechar** para retornar à lista.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Exibindo o status do serviço Windows cmdlets do Powershell

Você também pode exibir o status do serviço usando o Windows PowerShell e o cmdlet **Get-CsWindowsService**. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Administração do Microsoft Lync Remote PowerShell](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-service-status"></a>Para exibir o status do serviço

Para exibir o status do serviço em um computador, digite um comando semelhante ao seguinte no Shell de Gerenciamento Skype for Business Server e pressione Enter:
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Esse comando retornará informações parecidas com:
  
|**RoleName**|**Status**|
|:-----|:-----|
|{W3SVC}  <br/> |Em execução  <br/> |
|{CentralManagement}  <br/> | Em execução <br/> |
|{ClsAgent}  <br/> |Em execução  <br/> |
|{Registrador, UserServer, EdgeServer}  <br/> |Em execução  <br/> |
|{ApplicationServer}  <br/> |Em execução  <br/> |
|{ConferencingServer}  <br/> |Em execução  <br/> |
|{MediationServer}  <br/> |Em execução  <br/> |
   
Para obter detalhes, [consulte Get-CsWindowsService](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Exibir detalhes sobre um serviço
<a name="view_details"> </a>

Você pode usar Skype for Business Server Painel de Controle para exibir detalhes sobre cada serviço que está sendo executado em um computador específico em sua topologia. É possível exibir o status e os detalhes de cada serviço, como bancos de dados, portas e serviços dependentes associados.
  
### <a name="to-view-details-for-a-service"></a>Para exibir detalhes de um serviço

1. Em uma conta de usuário atribuída a qualquer uma das funções administrativas predefinida para Skype for Business Server, faça logoff em qualquer computador em sua implantação interna. Para obter detalhes sobre as funções administrativas predefinida disponíveis no Skype for Business Server, consulte **Planning for Role-Based Access Control**.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**.
4. Na página **Status**, classifique ou pesquisa na lista e clique no computador que deseja exibir.
5. Clique em **Propriedades**.
6. Na janela **Exibir Detalhes do Computador**, classifique a lista de serviços, se for necessário, e clique no serviço que você deseja exibir.
7. Siga um destes procedimentos, conforme o necessário:
   - Para ver o status mais recente desse serviço específico, clique em **Obter o status do serviço**.
   - Para ver detalhes desse serviço específico, clique em **Propriedades** e em **Fechar**.
   - Para retornar à lista com todos os computadores em sua topologia, clique **Fechar**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Iniciar ou interromper Skype for Business Server serviços
<a name="StartStop"> </a>

Você pode usar Skype for Business Server Painel de Controle para iniciar ou interromper todos os serviços Skype for Business Server em execução em um computador específico ou para iniciar ou interromper um serviço específico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Para iniciar ou interromper todos os Skype for Business em um computador

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server. Você pode determinar se foi atribuída a função CsServerAdministrator ou CsAdministrator RBAC executando um comando semelhante ao seguinte:
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**.
4. Na página **Status**, classifique ou procure pela lista para encontrar o computador executando os serviços que você deseja iniciar ou parar e clique neles.
5. Clique em **Ação**.
6. Clique em **Iniciar todos os serviços** ou **Parar todos os serviços**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Para iniciar ou parar um serviço específico

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**.
4. Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele.
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário e clique no serviço que você deseja iniciar ou parar.
7. Clique em **Ação**.
8. Clique em **Iniciar serviço** ou **Parar serviço**.
9. Clique em **Fechar**.
    
## <a name="prevent-sessions-for-services"></a>Evitar sessões de serviços
<a name="prevent_session"> </a>

Você pode usar Skype for Business Server Painel de Controle para impedir novas sessões para todos os serviços Skype for Business Server em execução em um computador específico ou para impedir novas sessões para um serviço Skype for Business Server específico.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Para evitar novas sessões para todos os serviços Skype for Business em um computador

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
3. Na barra de navegação à esquerda, clique em **Topologia** e, em seguida, clique em **Status**.
4. Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando os serviços para os quais você deseja impedir novas sessões e clique nele.
5. Clique em **Ação**.
6. Clique em **Impedir novas sessões para todos os serviços**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para Impedir novas sessões para um serviço específico

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**.
4. Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele. 
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.
7. Clique em **Ações**.
8. Clique em **Impedir novas sessões para o serviço**.
9. Clique em **Fechar**.
