---
title: Gerenciar serviços no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba como exibir o status do serviço, iniciar e parar serviços e impedir sessões para serviços.
ms.openlocfilehash: 90acd45675277dad0f63db342217cf914c97109a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991516"
---
# <a name="manage-services-in-skype-for-business-server"></a>Gerenciar serviços no Skype for Business Server

Você pode usar o painel de controle do Skype for Business Server para exibir uma lista de todos os computadores que estão executando o Skype for Business Server na sua topologia, exibir o status dos serviços, iniciar ou parar serviços e evitar sessões para serviços.

- [Exibir uma lista de computadores que executam o Skype for Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Exibir o status dos serviços em execução em um computador no Skype for Business](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Iniciar ou parar os serviços do Skype for Business](#start-or-stop-skype-for-business-services)
- [Evitar sessões de serviços](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Exibir uma lista de computadores que executam o Skype for Business Server

Use o painel de controle do Skype for Business Server para ver uma lista de todos os computadores que executam o Skype for Business na sua topologia e ver o status do serviço de cada um. Você pode classificar a lista por computador, pool ou site. 

1. Em uma conta de usuário que é atribuída a qualquer uma das funções administrativas predefinidas para o Skype for Business Server, faça logon em qualquer computador na sua implantação interna. Para obter mais informações, consulte [controle de acesso baseado em função (RBAC) para o Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 
4. Na página status, siga um destes procedimentos conforme necessário:
    - Classifique a lista clicando no título do **computador**, do **pool**ou da coluna do **site** e, em seguida, clicando na seta para cima ou na seta para baixo.
    - Clique em **Atualizar** para exibir a lista mais recente.
    - Procure um computador específico digitando o nome do computador no campo de pesquisa.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Exibir o status dos serviços em execução em um computador no Skype for Business

Use o painel de controle do Skype for Business Server para exibir todos os serviços que estão sendo executados em um computador específico na topologia do Skype for Business Server e ver o status de cada serviço.

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação à esquerda, clique em **topologia**.
4. Na página status, classifique ou pesquise a lista, conforme necessário, para localizar o computador no qual você está interessado e, em seguida, clique no nome do computador.
5. Siga um destes procedimentos:
    - Para ver o status mais recente dos serviços em execução no computador, clique em **obter status do serviço**.
    - Para ver uma lista de serviços específicos em execução no computador e o status de cada serviço, clique em **Propriedades**e, em seguida, clique em **fechar** para retornar à lista.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Visualizando o status do serviço usando cmdlets do Windows PowerShell

Você também pode exibir o status do serviço usando o Windows PowerShell e o cmdlet Get-CsWindowsService. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter mais informações, consulte [Shell de gerenciamento do Skype for Business Server](../management-shell.md).

**Para exibir o status do serviço**

Para exibir o status do serviço em um computador, digite um comando semelhante ao seguinte no Shell de gerenciamento do Skype for Business Server e pressione ENTER:

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

Este comando retorna informações semelhantes para o seguinte:

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

Para obter detalhes, consulte [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Iniciar ou parar os serviços do Skype for Business

Use o painel de controle do Skype for Business Server para iniciar ou parar todos os serviços do Skype for Business Server em execução em um computador específico ou para iniciar ou parar um serviço específico.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Iniciar ou parar todos os serviços do Skype for Business Server em um computador

1. Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server . Você pode determinar se você atribuiu o CsServerAdministrator ou a função RBAC CsAdministrator executando um comando semelhante ao seguinte:

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 
4. Na página status, classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando os serviços que você deseja iniciar ou parar e, em seguida, clique nele.
5. Clique em **ação**.
6. Clique em **Iniciar todos os serviços** ou **parar todos os serviços**.

### <a name="start-or-stop-a-specific-service"></a>Iniciar ou parar um serviço específico

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 
4. Na página status, classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.
5. Clique em **Propriedades**.
6. Classifique a lista de serviços, se necessário, e clique no serviço que você deseja iniciar ou parar.
7. Clique em **ação**.
8. Clique em **Iniciar serviço** ou **parar serviço**.
9. Clique em **Fechar**.


## <a name="prevent-sessions-for-services"></a>Evitar sessões de serviços

Use o painel de controle do Skype for Business para impedir novas sessões para todos os serviços do Skype for Business Server em execução em um computador específico ou para impedir novas sessões para um serviço específico.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Impedir novas sessões para todos os serviços do Skype for Business Server em um computador

1. Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.
4. Na página status, classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando os serviços para os quais você deseja impedir novas sessões e, em seguida, clique nela.
5. Clique em **ação**.
6. Clique em **impedir novas sessões para todos os serviços**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Impedir novas sessões para um serviço específico

1. Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server .
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Skype for Business Server, confira [instalar e abrir ferramentas administrativas](../../management-tools/install-and-open-administrative-tools.md).
3. Na barra de navegação esquerda, clique em **Topologia** e em **Status**. 
4. Clique em **Propriedades**.
5. Classifique a lista de serviços, se necessário, e clique no serviço para o qual você deseja impedir novas sessões.
6. Clique em **ação**.
7. Clique em **impedir novas sessões para o serviço**.
8. Clique em **Fechar**.
