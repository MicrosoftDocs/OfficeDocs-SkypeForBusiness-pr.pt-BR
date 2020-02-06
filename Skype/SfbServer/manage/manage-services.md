---
title: Gerenciar serviços para o Skype for Business Server
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Este artigo descreve como gerenciar serviços executados em uma topologia do Skype for Business Server.
ms.openlocfilehash: f730f095bdbf88af68afa0cd93568b1bf35ebdd9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817570"
---
# <a name="manage-services-for-skype-for-business-server"></a>Gerenciar serviços para o Skype for Business Server

Este artigo descreve como gerenciar serviços executados em uma topologia do Skype for Business Server.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Exibir uma lista de computadores que executam o Skype for Business Server
<a name="view_list"> </a>

Você pode usar o painel de controle do Skype for Business Server para ver uma lista de todos os computadores que estão executando o Skype for Business Server na sua topologia e ver o status do serviço de cada um. Você pode classificar a lista por computador, pool ou site. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Para exibir uma lista de computadores que executam o Skype for Business Server

1. Em uma conta de usuário que é atribuída a qualquer uma das funções administrativas predefinidas para o Skype for Business Server, faça logon em qualquer computador na sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype for Business Server, consulte **planejando o controle de acesso baseado em função**.   
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.   
3. Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.   
4. Na página **status** , siga qualquer um destes procedimentos conforme necessário:
   - Classifique a lista clicando no título do **computador**, do **pool**ou da coluna do **site** e, em seguida, clicando na seta para cima ou na seta para baixo. 
   - Clique em **Atualizar** para exibir a lista mais recente.  
   - Procure um computador específico digitando o nome do computador no campo de pesquisa.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Exibir o status dos serviços em execução em um servidor do Skype for Business
<a name="view-status"> </a>

Você pode usar o painel de controle do Skype for Business Server para exibir todos os serviços que estão sendo executados em um computador específico na topologia do Skype for Business Server e ver o status de cada serviço.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Para exibir o status dos serviços em execução em um computador

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
3. Na barra de navegação à esquerda, clique em **topologia**. 
4. Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador no qual você está interessado e, em seguida, clique no nome do computador.
5. Execute qualquer uma das seguintes ações:
   - Para ver o status mais recente dos serviços em execução no computador, clique em **obter status do serviço**.
   - Para ver uma lista de serviços específicos em execução no computador e o status de cada serviço, clique em **Propriedades**e, em seguida, clique em **fechar** para retornar à lista.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Exibir o status do serviço com cmdlets do Windows PowerShell

Você também pode exibir o status do serviço usando o Windows PowerShell e o cmdlet **Get-CsWindowsService** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-view-service-status"></a>Para exibir o status do serviço

Para exibir o status do serviço em um computador, digite um comando semelhante ao seguinte no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Este comando retorna informações semelhantes para o seguinte:
  
|**RoleName**|**Situação**|
|:-----|:-----|
|W3SVC  <br/> |Executando  <br/> |
|{CentralManagement}  <br/> | Executando <br/> |
|{ClsAgent}  <br/> |Executando  <br/> |
|{Registrador, userserver, EdgeServer}  <br/> |Executando  <br/> |
|{ApplicationServer}  <br/> |Executando  <br/> |
|{ConferencingServer}  <br/> |Executando  <br/> |
|{MediationServer}  <br/> |Executando  <br/> |
   
Para obter detalhes, consulte [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Exibir detalhes sobre um serviço
<a name="view_details"> </a>

Você pode usar o painel de controle do Skype for Business Server para ver detalhes sobre cada serviço que está em execução em um computador específico na sua topologia. Você pode exibir o status de cada serviço e detalhes, como os bancos de dados, portas e serviços dependentes associados.
  
### <a name="to-view-details-for-a-service"></a>Para ver os detalhes de um serviço

1. Em uma conta de usuário que é atribuída a qualquer uma das funções administrativas predefinidas para o Skype for Business Server, faça logon em qualquer computador na sua implantação interna. Para obter detalhes sobre as funções administrativas predefinidas disponíveis no Skype for Business Server, consulte **planejando o controle de acesso baseado em função**.
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
3. Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.
4. Na página **status** , classifique ou pesquise na lista e, em seguida, clique no computador que você deseja exibir.
5. Clique em **Propriedades**.
6. Na janela **Exibir detalhes do computador** , classifique a lista de serviços, se necessário, e clique no serviço que você deseja exibir.
7. Siga um destes procedimentos conforme necessário:
   - Para ver o status mais recente desse serviço específico, clique em **obter status do serviço**.
   - Para ver os detalhes desse serviço específico, clique em **Propriedades** e, em seguida, clique em **fechar**.
   - Para retornar à lista de todos os computadores na sua topologia, clique em **fechar**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Iniciar ou parar os serviços do Skype for Business Server
<a name="StartStop"> </a>

Você pode usar o painel de controle do Skype for Business Server para iniciar ou parar todos os serviços do Skype for Business Server em execução em um computador específico ou para iniciar ou parar um serviço específico.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Para iniciar ou parar todos os serviços do Skype for Business em um computador

1. Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server . Você pode determinar se você atribuiu o CsServerAdministrator ou a função RBAC CsAdministrator executando um comando semelhante ao seguinte:
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
3. Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.
4. Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando os serviços que você deseja iniciar ou parar e, em seguida, clique nele.
5. Clique em **ação**.
6. Clique em **Iniciar todos os serviços** ou **parar todos os serviços**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Para iniciar ou parar um serviço específico

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
3. Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.
4. Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário, e clique no serviço que você deseja iniciar ou parar.
7. Clique em **ação**.
8. Clique em **Iniciar serviço** ou **parar serviço**.
9. Clique em **Fechar**.
    
## <a name="prevent-sessions-for-services"></a>Evitar sessões de serviços
<a name="prevent_session"> </a>

Você pode usar o painel de controle do Skype for Business Server para impedir novas sessões para todos os serviços do Skype for Business Server executados em um computador específico ou para impedir novas sessões para um serviço específico do Skype for Business Server.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Para impedir novas sessões para todos os serviços do Skype for Business em um computador

1. Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
3. Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.
4. Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando os serviços para os quais você deseja impedir novas sessões e, em seguida, clique nela.
5. Clique em **ação**.
6. Clique em **impedir novas sessões para todos os serviços**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para impedir novas sessões para um serviço específico

1. Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 
3. Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.
4. Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele. 
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário, e clique no serviço para o qual você deseja impedir novas sessões.
7. Clique em **ação**.
8. Clique em **impedir novas sessões para o serviço**.
9. Clique em **Fechar**.
    

